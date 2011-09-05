if (ENABLE_PYTHON2)
    add_subdirectory(python)

    if (ENABLE_IBUS)
        add_subdirectory(ibus)
    endif (ENABLE_IBUS)
endif (ENABLE_PYTHON2)
