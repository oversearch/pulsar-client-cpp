#
# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.
#

if (NOT MSVC)
  set(CMAKE_C_FLAGS " -std=c99 ${CMAKE_C_FLAGS}")
  add_compile_options(-Wextra -Wno-unused-parameter)
endif()

set(SAMPLE_ASYNC_PRODUCER_SOURCES
  SampleAsyncProducer.cc
)

set(SAMPLE_CONSUMER_SOURCES
  SampleConsumer.cc
)

set(SAMPLE_CONSUMER_LISTENER_SOURCES
  SampleConsumerListener.cc
)

set(SAMPLE_PRODUCER_SOURCES
  SampleProducer.cc
)

set(SAMPLE_FILE_LOGGER_SOURCES
  SampleFileLogger.cc
)

set(SAMPLE_PRODUCER_C_SOURCES
    SampleProducerCApi.c
)

set(SAMPLE_CONSUMER_C_SOURCES
    SampleConsumerCApi.c
)

set(SAMPLE_ASYNC_CONSUMER_C_SOURCES
    SampleAsyncConsumerCApi.c
)

set(SAMPLE_CONSUMER_LISTENER_C_SOURCES
    SampleConsumerListenerCApi.c
)

set(SAMPLE_READER_C_SOURCES
        SampleReaderCApi.c
)
set(SAMPLE_KEY_VALUE_SCHEMA_CONSUMER
        SampleKeyValueSchemaConsumer.cc
)

set(SAMPLE_KEY_VALUE_SCHEMA_PRODUCER
        SampleKeyValueSchemaProducer.cc
)

set(SAMPLE_CUSTOM_LOGGER_CAPI
        SampleCustomLoggerCApi.c
        )

add_executable(SampleAsyncProducer                    ${SAMPLE_ASYNC_PRODUCER_SOURCES})
add_executable(SampleConsumer                         ${SAMPLE_CONSUMER_SOURCES})
add_executable(SampleConsumerListener                 ${SAMPLE_CONSUMER_LISTENER_SOURCES})
add_executable(SampleProducer                         ${SAMPLE_PRODUCER_SOURCES})
add_executable(SampleFileLogger                       ${SAMPLE_FILE_LOGGER_SOURCES})
add_executable(SampleProducerCApi                     ${SAMPLE_PRODUCER_C_SOURCES})
add_executable(SampleConsumerCApi                     ${SAMPLE_CONSUMER_C_SOURCES})
add_executable(SampleAsyncConsumerCApi                ${SAMPLE_CONSUMER_LISTENER_C_SOURCES})
add_executable(SampleConsumerListenerCApi             ${SAMPLE_CONSUMER_LISTENER_C_SOURCES})
add_executable(SampleReaderCApi                       ${SAMPLE_READER_C_SOURCES})
add_executable(SampleKeyValueSchemaConsumer           ${SAMPLE_KEY_VALUE_SCHEMA_CONSUMER})
add_executable(SampleKeyValueSchemaProducer           ${SAMPLE_KEY_VALUE_SCHEMA_PRODUCER})
add_executable(SampleCustomLoggerCApi                 ${SAMPLE_CUSTOM_LOGGER_CAPI})

if (INTEGRATE_VCPKG)
    # pulsarShared already carries INCLUDE_DIRECTORIES and LINK_DIRECTORIES properties
    set(CLIENT_LIBS "")
endif ()

target_link_libraries(SampleAsyncProducer              ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleConsumer                   ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleConsumerListener           ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleProducer                   ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleFileLogger                 ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleProducerCApi               ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleConsumerCApi               ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleAsyncConsumerCApi          ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleConsumerListenerCApi       ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleReaderCApi                 ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleKeyValueSchemaConsumer     ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleKeyValueSchemaProducer     ${CLIENT_LIBS} pulsarShared)
target_link_libraries(SampleCustomLoggerCApi           ${CLIENT_LIBS} pulsarShared)
