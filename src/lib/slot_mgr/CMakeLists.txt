project(softhsm_slotmgr)

set(INCLUDE_DIRS ${PROJECT_SOURCE_DIR}
                 ${PROJECT_SOURCE_DIR}/../common
                 ${PROJECT_SOURCE_DIR}/../crypto
                 ${PROJECT_SOURCE_DIR}/../data_mgr
                 ${PROJECT_SOURCE_DIR}/../object_store
                 ${PROJECT_SOURCE_DIR}/../pkcs11
                 ${PROJECT_SOURCE_DIR}/../session_mgr
                 )

set(SOURCES SlotManager.cpp
            Slot.cpp
            Token.cpp
            )

include_directories(${INCLUDE_DIRS})

add_library(${PROJECT_NAME} OBJECT ${SOURCES})

if(BUILD_TESTS)
    add_subdirectory(test)
endif(BUILD_TESTS)
