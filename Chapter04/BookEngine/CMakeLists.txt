cmake_minimum_required(VERSION 3.0)

project(BookEngine)
set(SOURCES
AnimatedSprite.cpp
AnimatedSprite.h
Animation.cpp
Animation.h
AudioEngine.h
AudioManager.cpp
AudioManager.h
BookEngine.cpp
BookEngine.h
Camera2D.cpp
Camera2D.h
Camera3D.cpp
Camera3D.h
Exception.h
GameObject.cpp
GameObject.h
GLTexture.h
IGame.cpp
IGame.h
ImageLoader.cpp
ImageLoader.h
InputManager.cpp
InputManager.h
IOManager.cpp
IOManager.h
IScreen.h
IState.h
Logger.cpp
Logger.h
Mesh.cpp
Mesh.h
MeshLoader.cpp
MeshLoader.h
ParticleBatch2D.cpp
ParticleBatch2D.h
ParticleManager2D.cpp
ParticleManager2D.h
PNGdecoder.cpp
PNGdecoder.h
ResourceManager.cpp
ResourceManager.h
ScreenList.cpp
ScreenList.h
ShaderManager.cpp
ShaderManager.h
Sprite.cpp
Sprite.h
SpriteBatch.cpp
SpriteBatch.h
SpriteFont.cpp
SpriteFont.h
StateList.cpp
StateList.h
TextureCache.cpp
TextureCache.h
Timing.cpp
Timing.h
UnitConverter.h
Vertex2D.h
Window.cpp
Window.h
)


include_directories(${CHAP_SRC_DIR}/include)
link_directories(${CHAP_SRC_DIR}/lib/Windows/x86)

# To build shared libraries in Windows, we set CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS to TRUE
# See https://cmake.org/cmake/help/v3.4/variable/CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS.html
# See https://blog.kitware.com/create-dlls-on-windows-without-declspec-using-new-cmake-export-all-feature/
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

add_library(BookEngine SHARED ${SOURCES})

#target_link_libraries(BookEngine debug BookEngine)
target_link_libraries(BookEngine debug glew32 SDL2 SDL2main SDL2_ttf SDL2_mixer OpenGL32)
target_link_libraries(BookEngine optimized glew32 SDL2 SDL2main SDL2_ttf SDL2_mixer OpenGL32)



