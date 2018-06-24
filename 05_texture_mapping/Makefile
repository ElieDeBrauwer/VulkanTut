VULKAN_SDK_PATH = /home/edb/scratch/vulkan/VulkanSDK/1.1.73.0/x86_64/
GLSLANG = $(VULKAN_SDK_PATH)/bin/glslangValidator
CFLAGS = -std=c++11 -I$(VULKAN_SDK_PATH)/include -I.
LDFLAGS = -L$(VULKAN_SDK_PATH)/lib -lvulkan `pkg-config --static --libs glfw3`

VulkanTest: main.cpp vert.spv frag.spv
	g++ $(CFLAGS) -o VulkanTest main.cpp $(LDFLAGS)

vert.spv: shaders/shader.vert
	$(GLSLANG) -V $^

frag.spv: shaders/shader.frag
	$(GLSLANG) -V $^


.PHONY: test clean

test: VulkanTest
	./VulkanTest

clean:
	rm -f VulkanTest *.spv
