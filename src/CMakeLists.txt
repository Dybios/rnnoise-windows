set(RN_NOISE_SRC
        denoise.c
        celt_lpc.c
        pitch.c
        rnn.c
        kiss_fft.c
        nnet.c
        nnet_default.c
        parse_lpcnet_weights.c
        rnnoise_data.c)


set(LIBRARY_OUTPUT_PATH "${PROJECT_BINARY_DIR}/lib")
include_directories("../include")
add_library(rnnoise SHARED ${RN_NOISE_SRC})
add_library(rnnoise_static STATIC ${RN_NOISE_SRC})
set_target_properties(rnnoise_static PROPERTIES OUTPUT_NAME "rnnoise")

