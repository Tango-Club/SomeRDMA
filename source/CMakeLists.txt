include_directories(${PROJECT_SOURCE_DIR}/include)

set(BASE_INCLUDE
    kv_engine.h msg.h rdma_conn.h rdma_conn_manager.h rdma_mem_pool.h)

install(FILES   ${BASE_INCLUDE}
    DESTINATION include)

set(BASE_SOURCE
    local_engine.cpp remote_engine.cpp rdma_conn_manager.cpp rdma_conn.cpp rdma_mem_pool.cpp)

add_library(polarkv STATIC ${BASE_SOURCE})

install(TARGETS polarkv
        ARCHIVE DESTINATION lib
        LIBRARY DESTINATION lib
        RUNTIME DESTINATION bin
        PUBLIC_HEADER DESTINATION include)
