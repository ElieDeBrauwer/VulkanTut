VULKAN_SDK_PATH = /home/edb/scratch/vulkan/VulkanSDK/1.1.73.0/x86_64/
CFLAGS = -std=c++11 -I$(VULKAN_SDK_PATH)/include
LDFLAGS = -L$(VULKAN_SDK_PATH)/lib -lvulkan `pkg-config --static --libs glfw3`

VulkanTest: main.cpp
	g++ $(CFLAGS) -o VulkanTest main.cpp $(LDFLAGS)

.PHONY: test clean

test: VulkanTest
	./VulkanTest

clean:
	rm -f VulkanTest
