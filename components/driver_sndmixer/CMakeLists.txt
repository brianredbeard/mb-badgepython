if(CONFIG_DRIVER_SNDMIXER_ENABLE)
    set(srcs
        "driver_i2s.c"
        "snd_source_mod.c"
        "snd_source_mp3.c"
        "snd_source_opus.c"
        "snd_source_synth.c"
        "snd_source_wav.c"
        "sndmixer.c"
        "ibxm/ibxm.c"
        "ibxm/xm2wav.c"
        "libhelix-mp3/bitstream.c"
        "libhelix-mp3/buffers.c"
        "libhelix-mp3/dct32.c"
        "libhelix-mp3/dequant.c"
        "libhelix-mp3/dqchan.c"
        "libhelix-mp3/huffman.c"
        "libhelix-mp3/hufftabs.c"
        "libhelix-mp3/imdct.c"
        "libhelix-mp3/mp3dec.c"
        "libhelix-mp3/mp3tabs.c"
        "libhelix-mp3/polyphase.c"
        "libhelix-mp3/scalfact.c"
        "libhelix-mp3/stproc.c"
        "libhelix-mp3/subband.c"
        "libhelix-mp3/trigtabs.c"
        "modsndmixer.c"
    )
else()
    set(srcs "")
endif()


set(includes
    "."
    "ibxm"
    )

set(IDF_COMPONENTS
    nvs_flash
    libopus
    micropython)

idf_component_register(SRCS "${srcs}"
                       INCLUDE_DIRS ${includes}
                       REQUIRES ${IDF_COMPONENTS})
