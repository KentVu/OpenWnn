
add_library( # Specifies the name of the library.
             libwnndict

             # Sets the library as a shared library.
             SHARED

             # Provides a relative path to your source file(s).
            OpenWnnDictionaryImplJni.c
            engine/ndapi.c
            engine/neapi.c
            engine/ndbdic.c
            engine/ndfdic.c
            engine/ndldic.c
            engine/ndrdic.c
            engine/necode.c
            engine/ndcommon.c
            engine/nj_str.c)

find_library( # Defines the name of the path variable that stores the
              # location of the NDK library.
              libdl

              # Specifies the name of the NDK library that
              # CMake needs to locate.
              dl )

# Links your native library against one or more other native libraries.
target_link_libraries( # Specifies the target library.
                       libwnndict

                       # Links the log library to the target library.
                       ${libdl} )


# Specifies a path to native header files.
#[[ include_directories (src/main/cpp/include/)]]
include_directories (
            .
            include)