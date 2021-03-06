# Copyright(c) 2018, NVIDIA CORPORATION. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

cmake_minimum_required(VERSION 3.2)

project(01_InitInstance)

set(HEADERS
)

set(SOURCES
  01_InitInstance.cpp
)

source_group(headers FILES ${HEADERS})
source_group(sources FILES ${SOURCES})

add_executable(01_InitInstance
  ${HEADERS}
  ${SOURCES}
)

set_target_properties(01_InitInstance PROPERTIES FOLDER "Samples")

if (SAMPLES_BUILD_WITH_LOCAL_VULKAN_HPP)
  target_include_directories(01_InitInstance PUBLIC "${CMAKE_SOURCE_DIR}")
endif()
target_include_directories(01_InitInstance PUBLIC "$ENV{VK_SDK_PATH}/include")

target_link_libraries(01_InitInstance "$ENV{VK_SDK_PATH}/Lib/vulkan-1.lib")
