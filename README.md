# Purpose

I want to use this repository as starting point to develop crossplatform compatible GD Extensions.

My personal toolchain + Godot set up in this project:

* C++ as language
* glm for having geometric vector classes
* nlohmann::json for a general purpose tree data
* vcpkg for dependencies
* cmake
* visual studio
* catch2 for testing
* clang-format
* GDExtension

You should be able to not use vcpkg by removing glm, nlohmann::json and catch2 from all Cmakelists.txt and use it as normal cmake project.
Also remove all test stuff (which isn't much).

# Project Structure

* Library contains the logic (The Hello World string)
* Executable contains a console Hello World programm calling Library
* LibraryGD contains a HelloWorld godot object calling Library
* godotProject displays text with help of the hello world string in LibraryGD
* LibraryGD has a copy script to place the dll after each build in the correct place

# Example iteration

* set everything up
* Start godotProject in godot
* press play, see the string in ingame window
* close ingame window (keep godotProject open)
* manipulate the string in Library/HelloWorld.cpp
* hit compile everything in Visual Studio
* press play, see the modified string in ingame window

# VCPKG

* Clone VCPKG with git (https://github.com/microsoft/vcpkg)
* Double click or use bootstrap-vcpkg.bat in Windows or bootstrap-vcpkg.sh in Linux
* pass "[your path]\vcpkg\scripts\buildsystems\vcpkg.cmake" in "Specify toolchain file for crosscompiling" in cmake for windows
* in linux use linux command line magic instead. Search for toolchain.

# Prepare (windows)

* install git (e.g. github desktop)
* install https://cmake.org/
* checkout this repo
* choose this repo as "where is the sourcecode"
* choose [repopath]/out as "where to build binaries"
* press configure
  * specify toolchainfile and editor
* press generate
* press open project
* compile all
* start godot 4.3 stable
  * if other version is desired specify branch in root/CmakeList.txt
* import [repopath]/godotProject
* enjoy
