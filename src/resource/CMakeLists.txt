add_library(CemuResource)

set_property(TARGET CemuResource PROPERTY MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")

# icon resources
if(UNIX)
	target_sources(CemuResource PRIVATE
	embedded/resources.cpp
	embedded/resources.h
	)
endif()

target_sources(CemuResource PRIVATE CafeDefaultFont.cpp)

target_include_directories(CemuResource PUBLIC "../")

target_link_libraries(CemuResource PRIVATE CemuCommon CemuComponents)
