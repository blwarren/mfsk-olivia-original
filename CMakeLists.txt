cmake_minimum_required(VERSION 3.16)

project(mfsk_olivia LANGUAGES C CXX)

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(${PROJECT_SOURCE_DIR}/include/mfsk)

find_package(Curses REQUIRED)

set(COMMON_COMPILE_OPTIONS -Wall -O2 -fpermissive)

add_executable(mfsk_tx apps/mfsk_tx.cc)
target_compile_options(mfsk_tx PRIVATE ${COMMON_COMPILE_OPTIONS})
target_link_libraries(mfsk_tx PRIVATE m ${CURSES_LIBRARIES})

add_executable(mfsk_rx apps/mfsk_rx.cc)
target_compile_options(mfsk_rx PRIVATE ${COMMON_COMPILE_OPTIONS})
target_link_libraries(mfsk_rx PRIVATE m ${CURSES_LIBRARIES})

add_executable(mfsk_trx apps/mfsk_trx.cc)
target_compile_options(mfsk_trx PRIVATE ${COMMON_COMPILE_OPTIONS})
target_link_libraries(mfsk_trx PRIVATE m ${CURSES_LIBRARIES})

add_executable(mfsk_encode tools/mfsk_encode.cc)
target_compile_options(mfsk_encode PRIVATE ${COMMON_COMPILE_OPTIONS})
target_link_libraries(mfsk_encode PRIVATE m ${CURSES_LIBRARIES})

add_executable(mfsk_symb tools/mfsk_symb.cc)
target_compile_options(mfsk_symb PRIVATE ${COMMON_COMPILE_OPTIONS})
target_link_libraries(mfsk_symb PRIVATE m ${CURSES_LIBRARIES})

add_executable(mfsk_test tests/mfsk_test.cc)
target_compile_options(mfsk_test PRIVATE ${COMMON_COMPILE_OPTIONS})
target_link_libraries(mfsk_test PRIVATE m)

add_executable(rate_check tools/rate_check.cc)
target_compile_options(rate_check PRIVATE ${COMMON_COMPILE_OPTIONS})
target_link_libraries(rate_check PRIVATE m)

add_executable(peakrms tools/peakrms.c)
target_compile_options(peakrms PRIVATE -Wall -O2)
target_link_libraries(peakrms PRIVATE m ${CURSES_LIBRARIES})

add_executable(addnoise tools/addnoise.c)
target_compile_options(addnoise PRIVATE -Wall -O2)
target_link_libraries(addnoise PRIVATE m ${CURSES_LIBRARIES})

add_executable(addcarr tools/addcarr.c)
target_compile_options(addcarr PRIVATE -Wall -O2)
target_link_libraries(addcarr PRIVATE m ${CURSES_LIBRARIES})
