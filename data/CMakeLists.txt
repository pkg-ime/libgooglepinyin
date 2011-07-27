add_custom_command(OUTPUT dict_pinyin.dat
                   DEPENDS dictbuilder
                   COMMAND dictbuilder ${CMAKE_CURRENT_SOURCE_DIR}/rawdict_utf16_65105_freq.txt ${CMAKE_CURRENT_SOURCE_DIR}/valid_utf16.txt)

add_custom_target(datafile ALL DEPENDS dict_pinyin.dat)

configure_file(googlepinyin.pc.in ${CMAKE_CURRENT_BINARY_DIR}/googlepinyin.pc)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/dict_pinyin.dat DESTINATION ${datadir}/googlepinyin)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/googlepinyin.pc DESTINATION ${libdir}/pkgconfig)
