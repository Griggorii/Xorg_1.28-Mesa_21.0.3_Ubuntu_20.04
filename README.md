# Xorg_1.28-Mesa_21.2.6_Ubuntu_20.04
Mesa+Xorg full my build , ubuntu 20.04 , libc-2.31 , mesa-20.1.0 , (dri new libgallium_drv_video , libmesa_dri_drivers add alternative link ) (vdpau libvdpau_gallium add alternative link ) , ( gallium add alternative link ) wayland speed fast +50% , mesa perfomance

             Ubuntu 20.04 special edition video driver architect Griggorii update old xorg generate 1.20.4 fix fast ui chrome/um resize page F11 11.08.2021

Download deb package ubuntu 20.04 LTS mesa+xorg new video driver: https://github.com/Griggorii/Xorg_1.28-Mesa_21.2.6_Ubuntu_20.04/releases/tag/libmesa_dri

Development xorg: sudo cp libwayland-server.la /usr/lib/x86_64-linux-gnu

Development drm: sudo cp amdgpu.ids /usr/share/libdrm

Wayland ubuntu 20.04 session mesa libLLVM-10

$ sudo apt reinstall libllvm10 -y

Deb kernel recomendation support all nvidia , touchpad , zfs , bbswitch: https://github.com/Griggorii/linux-image-unsigned-5.6.0-1020-oem-kernel-mod-rpm-deb/releases/tag/linux-image-unsigned-5.6.0-1020-fedora

Test run video driver chromium/chrome/opera/brave/and analog engine browser replace (chromium-browser) flag: https://github.com/Griggorii/Chromium_OS_77

____________________________________________________________________________________________________

                                     Test run wayland session mesa 20.1.0

RUS: Отказ от ответственности все данные запуски тестирования могут вести себя по разному и могут привести к черному экрану тогда понадобиться лайв диск что бы зайти в вашу home дирикторию юзера и включить показ скрытох фаилов и удалить полностью внесенную строчку по типу указанную в командах и начинающиюся после echo "export  (  = bla bla bla  )  из фаила с именем .profile сделайте бекап что бы понять какие изменения были внесены в случае торможения системы или черного экрана с первой данной команды вы получите достоверный фаил backup_profile и будет изменяться только фаил .profile который надо будет в случае не удачи исправить обычным копированием и видеть который можно включив если есть даже быстрой командой CTRL+H

Данные способы не обязательно могут сработать из за множества разных операционных систем не приведенных к единому и желательно одному стандарту glx wayland gbm и возможно более рабочие но опасный способ может есть в каком нибудь перенаправлении на более системный конфиг вида  >> /etc/profile и не менее интересный новый ~/.pam_environment включая директории d 

cp ~/.profile ~/backup_profile

ENG: Disclaimer All Test start data may behave in different ways and can lead to a black screen then need a live drive to enter your Home Diriktoria of the user and turn on the display of Failov hidden and delete the fully made line by type specified in the commands and starting after ECHO EXPORT (= BLA BLA BLA) from Faale named .profile Make backup to understand which changes were made in the event of a system braking or black screen from the first command you will receive a reliable file backup_profile and will change only the file .profile to be changed in case Do not good luck to correct usual copying and see which you can turn on if there is even a fast Ctrl + H command

These methods do not have to work because of the multiple of different operating systems not specified to one and preferably one GLX WAYLAND GBM standard and possibly more workers, but a dangerous method may have in any redirect to a more system config of the form >> /etc/profile and at least Interesting new ~/.pam_environment  including directory D

cp ~/.profile ~/backup_profile
_________________________________________________________________________________________________________

echo "export SDL_VIDEODRIVER=glx" >> ~/.profile

echo "export SDL_VIDEODRIVER=wayland" >> ~/.profile

echo "export SDL_VIDEODRIVER=x11" >> ~/.profile

echo "export SDL_VIDEODRIVER=dummy" >> ~/.profile

echo "export SDL_VIDEODRIVER=qxl" >> ~/.profile

echo "export SDL_VIDEODRIVER=wayland-egl" >> ~/.profile

echo "export SDL_VIDEODRIVER=kms" >> ~/.profile

echo "export GDK_BACKEND=x11" >> ~/.profile

echo "export GDK_BACKEND=wayland" >> ~/.profile

echo "export GDK_BACKEND=glx" >> ~/.profile && not recommended

echo "export GDK_BACKEND=qxl" >> ~/.profile && not recommended

echo "export GDK_BACKEND=dummy" >> ~/.profile && not recommended

echo "export GDK_BACKEND=kms" >> ~/.profile && not recommended

Elementary engine ECORE EVAS not elementary os ? danger not recommended ECORE_EVAS_ENGINE

echo "export ECORE_EVAS_ENGINE=wayland-egl" >> ~/.profile

______________________________________________________________________________________________

                                             Test run wayland session mesa 20.1.0 run green-recorder

SDL_VIDEODRIVER=glx green-recorder <- run support

SDL_VIDEODRIVER=qxl green-recorder <- run support

GDK_BACKEND=wayland green-recorder <- run support

GDK_BACKEND=dummy green-recorder <- not run support

GDK_BACKEND=glx green-recorder <- not run support

GDK_BACKEND=qxl green-recorder <- not run support

GDK_BACKEND=wayland-egl green-recorder <- not run support

GDK_BACKEND=kms green-recorder <- not run support
____________________________________________________________________________________________________

Elementary engine ECORE EVAS not elementary os ? danger not recommended ECORE_EVAS_ENGINE

echo "ECORE_EVAS_ENGINE=wayland-egl" >> ~/.profile

ECORE_EVAS_ENGINE=wayland-egl green-recorder <- not run support


лучший по моему мнению флаг было получено при самом первом запуске позднее становилось меньше и видимо надо как то включать ускорение которое срабатывает почему то во время запуска и потом затухает

the best flag in my opinion was received at the very first start, later it became smaller and apparently it is necessary to somehow turn on the acceleration, which works for some reason during startup and then fades

1 ) SDL_VIDEODRIVER=glx glxgears | 11281 frames in 5.0 seconds = 2256.105 FPS

2 ) SDL_VIDEODRIVER=wayland-egl glxgears | 9909 frames in 5.0 seconds = 1981.597 FPS

3 ) SDL_VIDEODRIVER=qxl glxgears | 9486 frames in 5.0 seconds = 1896.988 FPS

4 ) ECORE_EVAS_ENGINE=wayland-egl glxgears | 9759 frames in 5.0 seconds = 1951.755 FPS

4 ) GDK_BACKEND=kms glxgears | 8526 frames in 5.0 seconds = 1704.321 FPS

5 ) SDL_VIDEODRIVER=kms glxgears | 7411 frames in 5.0 seconds = 1481.780 FPS



Informations all developers /usr/include/X11/Xlib.h a lot of duplicate functions and repeated slightly altered lines that roughly provide the same duplicate functions and the library needs to be redirected



                         ________________________________________________
                        |                                                |
                        | Test fbdev new video driver architect Griggorii|
                        |_______________________________________________ |


The text of the settings on the Internet page FBDEV is not correctly displayed. Downloads readme.md to see the correct settings and correct setting copy alternative raw page https://raw.githubusercontent.com/Griggorii/Xorg_1.28-Mesa_23.0.1_libmesa_dri_Ubuntu_20.04/main/README.md 

Monitor support 60-75 hz replace string  (VertRefresh 60-75) example support  monitor 110-120 hz ? , danger experiment monitor not support blackscreen (VertRefresh 110-120)

$ cat << EOF > xorg.conf
Section "Device"
	Identifier "Configured Video Device"
	Driver "fbdev"
EndSection

Section "Module"
    Load "dbe"
    Load "ddc"
    Load "extmod"
    Load "glx"
    Load "int10"
    Load "record"
    Load "vbe"
    Load "glamoregl"
    Load "xorgxrdp"
    Load "fb"
EndSection

Section "Monitor"
    Identifier "Monitor"
    Option "DPMS"
    HorizSync 30-80
    VertRefresh 60-75
    ModeLine "1920x1080" 138.500 1920 1968 2000 2080 1080 1083 1088 1111 +hsync -vsync
    ModeLine "1280x720" 74.25 1280 1720 1760 1980 720 725 730 750 +HSync +VSync
    Modeline "1368x768" 72.25 1368 1416 1448 1528 768 771 781 790 +hsync -vsync
    Modeline "1600x900" 119.00 1600 1696 1864 2128 900 901 904 932 -hsync +vsync
EndSection

Section "Monitor"
    Identifier "Video Card (fbdev)"
    Driver "fbdev"
    Option "DRMDevice" "/dev/dri/renderD128"
    Option "DRI3" "1"
EndSection

Section "Screen"
    Identifier "Screen (fbdev)"
    Device "Video Card (fbdev)"
    Monitor "Monitor"
    DefaultDepth 24
    SubSection "Display"
        Depth 24
        Modes "640x480" "800x600" "1024x768" "1280x720" "1280x1024" "1600x900" "1920x1080"
    EndSubSection
EndSection
EOF

$ sudo mkdir /etc/X11/xorg.conf.d

$ sudo cp xorg.conf /etc/X11/xorg.conf.d/

________________________________________________________________________________________________________________________________________________________h                   Mesa https://ru.wikipedia.org/wiki/%D0%9F%D0%B0%D1%82%D0%B5%D0%BD%D1%82%D0%BD%D1%8B%D0%B9_%D0%BF%D1%83%D0%BB			   
_______________________________________________________________________________________________________________________________________________________________

        Vulkan my build mesa chrome://gpu browser information dump parametr auto compile generation json scheme
					
					Video Acceleration Information
					   
					   
info	{
  "apiVersion": 4202627,
  "usedApiVersion": 4198400,
  "instanceExtensions": [
    {
      "extensionName": "VK_KHR_device_group_creation",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_display",
      "specVersion": 23
    },
    {
      "extensionName": "VK_KHR_external_fence_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_external_memory_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_external_semaphore_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_get_display_properties2",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_get_physical_device_properties2",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_get_surface_capabilities2",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_surface",
      "specVersion": 25
    },
    {
      "extensionName": "VK_KHR_surface_protected_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_wayland_surface",
      "specVersion": 6
    },
    {
      "extensionName": "VK_KHR_xcb_surface",
      "specVersion": 6
    },
    {
      "extensionName": "VK_KHR_xlib_surface",
      "specVersion": 6
    },
    {
      "extensionName": "VK_EXT_acquire_xlib_display",
      "specVersion": 1
    },
    {
      "extensionName": "VK_EXT_debug_report",
      "specVersion": 9
    },
    {
      "extensionName": "VK_EXT_direct_mode_display",
      "specVersion": 1
    },
    {
      "extensionName": "VK_EXT_display_surface_counter",
      "specVersion": 1
    },
    {
      "extensionName": "VK_EXT_debug_utils",
      "specVersion": 1
    }
  ],
  "enabledInstanceExtensions": [
    "VK_KHR_external_memory_capabilities",
    "VK_KHR_external_semaphore_capabilities",
    "VK_EXT_debug_report"
  ],
  "instanceLayers": [
    {
      "layerName": "VK_LAYER_NV_optimus",
      "specVersion": 4198519,
      "implementationVersion": 1,
      "description": "NVIDIA Optimus layer"
    },
    {
      "layerName": "VK_LAYER_MESA_device_select",
      "specVersion": 4202569,
      "implementationVersion": 1,
      "description": "Linux device selection layer"
    },
    {
      "layerName": "VK_LAYER_GOOGLE_threading",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "Google Validation Layer"
    },
    {
      "layerName": "VK_LAYER_MESA_overlay",
      "specVersion": 4198473,
      "implementationVersion": 1,
      "description": "Mesa Overlay layer"
    },
    {
      "layerName": "VK_LAYER_KHRONOS_validation",
      "specVersion": 4202627,
      "implementationVersion": 1,
      "description": "Khronos Validation Layer"
    },
    {
      "layerName": "VK_LAYER_LUNARG_core_validation",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "LunarG Validation Layer"
    },
    {
      "layerName": "VK_LAYER_GOOGLE_unique_objects",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "Google Validation Layer"
    },
    {
      "layerName": "VK_LAYER_LUNARG_object_tracker",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "LunarG Validation Layer"
    },
    {
      "layerName": "VK_LAYER_LUNARG_standard_validation",
      "specVersion": 4202627,
      "implementationVersion": 1,
      "description": "LunarG Standard Validation"
    },
    {
      "layerName": "VK_LAYER_LUNARG_parameter_validation",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "LunarG Validation Layer"
    }
  ],
  "physicalDevices": [
    {
      "properties": {
        "apiVersion": 4194306,
        "driverVersion": 1,
        "vendorID": 65541,
        "deviceID": 0,
        "deviceType": 4,
        "deviceName": "llvmpipe (LLVM 12.0.0, 256 bits)",
        "pipelineCacheUUID": [
          118,
          97,
          108,
          45,
          105,
          109,
          101,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0
        ],
        "limits": {
          "maxImageDimension1D": 16384,
          "maxImageDimension2D": 16384,
          "maxImageDimension3D": 4096,
          "maxImageDimensionCube": 32768,
          "maxImageArrayLayers": 2048,
          "maxTexelBufferElements": 134217728,
          "maxUniformBufferRange": 65536,
          "maxStorageBufferRange": 134217728,
          "maxPushConstantsSize": 128,
          "maxMemoryAllocationCount": 4096,
          "maxSamplerAllocationCount": 32768,
          "bufferImageGranularity": 1,
          "sparseAddressSpaceSize": 0,
          "maxBoundDescriptorSets": 8,
          "maxPerStageDescriptorSamplers": 32,
          "maxPerStageDescriptorUniformBuffers": 16,
          "maxPerStageDescriptorStorageBuffers": 16,
          "maxPerStageDescriptorSampledImages": 128,
          "maxPerStageDescriptorStorageImages": 16,
          "maxPerStageDescriptorInputAttachments": 8,
          "maxPerStageResources": 128,
          "maxDescriptorSetSamplers": 32768,
          "maxDescriptorSetUniformBuffers": 256,
          "maxDescriptorSetUniformBuffersDynamic": 256,
          "maxDescriptorSetStorageBuffers": 256,
          "maxDescriptorSetStorageBuffersDynamic": 256,
          "maxDescriptorSetSampledImages": 256,
          "maxDescriptorSetStorageImages": 256,
          "maxDescriptorSetInputAttachments": 256,
          "maxVertexInputAttributes": 32,
          "maxVertexInputBindings": 32,
          "maxVertexInputAttributeOffset": 2047,
          "maxVertexInputBindingStride": 2048,
          "maxVertexOutputComponents": 128,
          "maxTessellationGenerationLevel": 64,
          "maxTessellationPatchSize": 32,
          "maxTessellationControlPerVertexInputComponents": 128,
          "maxTessellationControlPerVertexOutputComponents": 128,
          "maxTessellationControlPerPatchOutputComponents": 128,
          "maxTessellationControlTotalOutputComponents": 4096,
          "maxTessellationEvaluationInputComponents": 128,
          "maxTessellationEvaluationOutputComponents": 128,
          "maxGeometryShaderInvocations": 32,
          "maxGeometryInputComponents": 64,
          "maxGeometryOutputComponents": 128,
          "maxGeometryOutputVertices": 1024,
          "maxGeometryTotalOutputComponents": 1024,
          "maxFragmentInputComponents": 128,
          "maxFragmentOutputAttachments": 8,
          "maxFragmentDualSrcAttachments": 2,
          "maxFragmentCombinedOutputResources": 8,
          "maxComputeSharedMemorySize": 32768,
          "maxComputeWorkGroupCount": [
            65535,
            65535,
            65535
          ],
          "maxComputeWorkGroupInvocations": 1024,
          "maxComputeWorkGroupSize": [
            1024,
            1024,
            1024
          ],
          "subPixelPrecisionBits": 8,
          "subTexelPrecisionBits": 8,
          "mipmapPrecisionBits": 8,
          "maxDrawIndexedIndexValue": 4294967295,
          "maxDrawIndirectCount": 4294967295,
          "maxSamplerLodBias": 16,
          "maxSamplerAnisotropy": 16,
          "maxViewports": 16,
          "maxViewportDimensions": [
            16384,
            16384
          ],
          "viewportBoundsRange": [
            -32768,
            32768
          ],
          "viewportSubPixelBits": 0,
          "minMemoryMapAlignment": 4096,
          "minTexelBufferOffsetAlignment": 1,
          "minUniformBufferOffsetAlignment": 1,
          "minStorageBufferOffsetAlignment": 1,
          "minTexelOffset": -32,
          "maxTexelOffset": 31,
          "minTexelGatherOffset": -32,
          "maxTexelGatherOffset": 31,
          "minInterpolationOffset": -2,
          "maxInterpolationOffset": 2,
          "subPixelInterpolationOffsetBits": 8,
          "maxFramebufferWidth": 16384,
          "maxFramebufferHeight": 16384,
          "maxFramebufferLayers": 2048,
          "framebufferColorSampleCounts": 5,
          "framebufferDepthSampleCounts": 5,
          "framebufferStencilSampleCounts": 5,
          "framebufferNoAttachmentsSampleCounts": 5,
          "maxColorAttachments": 8,
          "sampledImageColorSampleCounts": 5,
          "sampledImageIntegerSampleCounts": 5,
          "sampledImageDepthSampleCounts": 5,
          "sampledImageStencilSampleCounts": 5,
          "storageImageSampleCounts": 5,
          "maxSampleMaskWords": 1,
          "timestampComputeAndGraphics": true,
          "timestampPeriod": 1,
          "maxClipDistances": 8,
          "maxCullDistances": 8,
          "maxCombinedClipAndCullDistances": 8,
          "discreteQueuePriorities": 2,
          "pointSizeRange": [
            0,
            255
          ],
          "lineWidthRange": [
            1,
            1
          ],
          "pointSizeGranularity": 0.125,
          "lineWidthGranularity": 0,
          "strictLines": false,
          "standardSampleLocations": true,
          "optimalBufferCopyOffsetAlignment": 1,
          "optimalBufferCopyRowPitchAlignment": 1,
          "nonCoherentAtomSize": 1
        },
        "sparseProperties": {
          "residencyStandard2DBlockShape": false,
          "residencyStandard2DMultisampleBlockShape": false,
          "residencyStandard3DBlockShape": false,
          "residencyAlignedMipSize": false,
          "residencyNonResidentStrict": false
        }
      },
      "extensions": [
        {
          "extensionName": "VK_KHR_bind_memory2",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_dedicated_allocation",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_descriptor_update_template",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_device_group",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_draw_indirect_count",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_driver_properties",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_get_memory_requirements2",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_incremental_present",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_maintenance1",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_push_descriptor",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_relaxed_block_layout",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_sampler_mirror_clamp_to_edge",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_storage_buffer_storage_class",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_swapchain",
          "specVersion": 68
        },
        {
          "extensionName": "VK_EXT_external_memory_dma_buf",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_index_type_uint8",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_post_depth_coverage",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_private_data",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_shader_stencil_export",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_transform_feedback",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_vertex_attribute_divisor",
          "specVersion": 3
        },
        {
          "extensionName": "VK_GOOGLE_decorate_string",
          "specVersion": 1
        },
        {
          "extensionName": "VK_GOOGLE_hlsl_functionality1",
          "specVersion": 1
        }
      ],
      "features": {
        "robustBufferAccess": false,
        "fullDrawIndexUint32": false,
        "imageCubeArray": false,
        "independentBlend": false,
        "geometryShader": false,
        "tessellationShader": false,
        "sampleRateShading": false,
        "dualSrcBlend": false,
        "logicOp": false,
        "multiDrawIndirect": false,
        "drawIndirectFirstInstance": false,
        "depthClamp": false,
        "depthBiasClamp": false,
        "fillModeNonSolid": false,
        "depthBounds": false,
        "wideLines": false,
        "largePoints": false,
        "alphaToOne": false,
        "multiViewport": false,
        "samplerAnisotropy": false,
        "textureCompressionETC2": false,
        "textureCompressionASTCLDR": false,
        "textureCompressionBC": false,
        "occlusionQueryPrecise": false,
        "pipelineStatisticsQuery": false,
        "vertexPipelineStoresAndAtomics": false,
        "fragmentStoresAndAtomics": false,
        "shaderTessellationAndGeometryPointSize": false,
        "shaderImageGatherExtended": false,
        "shaderStorageImageExtendedFormats": false,
        "shaderStorageImageMultisample": false,
        "shaderStorageImageReadWithoutFormat": false,
        "shaderStorageImageWriteWithoutFormat": false,
        "shaderUniformBufferArrayDynamicIndexing": false,
        "shaderSampledImageArrayDynamicIndexing": false,
        "shaderStorageBufferArrayDynamicIndexing": false,
        "shaderStorageImageArrayDynamicIndexing": false,
        "shaderClipDistance": false,
        "shaderCullDistance": false,
        "shaderFloat64": false,
        "shaderInt64": false,
        "shaderInt16": false,
        "shaderResourceResidency": false,
        "shaderResourceMinLod": false,
        "sparseBinding": false,
        "sparseResidencyBuffer": false,
        "sparseResidencyImage2D": false,
        "sparseResidencyImage3D": false,
        "sparseResidency2Samples": false,
        "sparseResidency4Samples": false,
        "sparseResidency8Samples": false,
        "sparseResidency16Samples": false,
        "sparseResidencyAliased": false,
        "variableMultisampleRate": false,
        "inheritedQueries": false
      },
      "featureSamplerYcbcrConversion": false,
      "featureProtectedMemory": false,
      "queueFamilies": [
        {
          "queueFlags": 7,
          "queueCount": 1,
          "timestampValidBits": 64,
          "minImageTransferGranularity": {
            "width": 1,
            "height": 1,
            "depth": 1
          }
        }
      ]
    }
  ]
	
_______________________________________________________________________________________
	
	One core
	
processor	: 0
vendor_id	: GenuineIntel
cpu family	: 6
model		: 42
model name	: Intel(R) Core(TM) i3-2328M CPU @ 2.20GHz
stepping	: 7
microcode	: 0x2f
cpu MHz		: 2193.481
cache size	: 3072 KB
physical id	: 0
siblings	: 4
core id		: 0
cpu cores	: 2
apicid		: 0
initial apicid	: 0
fpu		: yes
fpu_exception	: yes
cpuid level	: 13
wp		: yes
flags		: fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni pclmulqdq dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer xsave avx lahf_lm epb pti ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid xsaveopt dtherm arat pln pts md_clear flush_l1d
vmx flags	: vnmi preemption_timer invvpid ept_x_only flexpriority tsc_offset vtpr mtf vapic ept vpid unrestricted_guest
bugs		: cpu_meltdown spectre_v1 spectre_v2 spec_store_bypass l1tf mds swapgs itlb_multihit
bogomips	: 4389.90
clflush size	: 64
cache_alignment	: 64
address sizes	: 36 bits physical, 48 bits virtual
power management:
