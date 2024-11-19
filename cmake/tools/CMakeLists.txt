set(files)

list(APPEND files
  Tools/scripts/run_tests.py
)

foreach(file IN LISTS files)
  get_filename_component(path ${file} PATH)
  file(COPY ${SRC_DIR}/${file} DESTINATION ${PROJECT_BINARY_DIR}/${LIBDIR}/${path})
  install(FILES ${SRC_DIR}/${file} DESTINATION ${LIBDIR}/${path})
endforeach()
