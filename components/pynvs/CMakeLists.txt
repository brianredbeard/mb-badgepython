set(srcs "modnvs.c")
set(includes ".")

idf_component_register(SRCS "${srcs}"
                       INCLUDE_DIRS ${includes}
                       REQUIRES lwip micropython)
