file(GLOB OVIS_AUDIO_HEADER_FILES "*.hpp")
file(GLOB OVIS_AUDIO_SOURCE_FILES "*.cpp")

add_library(
  OvisAudio
  ${OVIS_AUDIO_HEADER_FILES}
  ${OVIS_AUDIO_SOURCE_FILES}
)

find_package(PkgConfig REQUIRED) 
pkg_check_modules(SDL2_mixer REQUIRED IMPORTED_TARGET SDL2_mixer)

target_link_libraries(
  OvisAudio
  PUBLIC
    OvisCore
    PkgConfig::SDL2_mixer
)
