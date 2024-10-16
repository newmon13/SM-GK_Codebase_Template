# Clion and SDL2 Setup
To avoid using goofy-ass IDE->Codeblock at classes, I forked repo, that provides fast & easy set up for SDL lib for CLion.
After setting up project in CLion go to the section *Code adjustments*.
Have fun using normal IDE.



## Fast setup

All the files needed to make it work are already uploaded. You just need to open with it Clion and start coding.

* Download or clone the repository

### I recommend this one. Really. 
```
git clone https://github.com/llanillo/clion-cmake-sdl2-template
```

* Open it with Clion and click **Ok** to the Project Wizard.
* **(Optional)** Rename the project. To do it you must change _PROJECT_NAME_ **ONLY in line 2** of CMaLists.txt.
* Compile and run it. Everything went well if you see a purple window with exit code '0'.

## Manual setup

* Download the latest [SDL Development Libraries (MinGW version)](https://www.libsdl.org/download-2.0.php)

* Download the [SDL2 Cmake Scripts](https://github.com/tcbrindle/sdl2-cmake-scripts)

* Create a cmake/modules directory in your project root and unzip all cmake scripts there.

* Unzip the SDL Development libraries in your project root, rename the folder to 'SDL2'

* Mark the SDL2 folder as excluded in Clion (Optional)

* Download the CMakeLists.txt from this repository and copy it to your project.

* **(Optional) Rename the project editing line 2 (PROJECT_NAME)** in line 2.

* Copy the SDL2.dll from the SDL2 folder into your cmake-build-debug folder:
    - For 64 bits version it's located at x86_64-w65-mingw32/bin/SDL2.dll
    - For 32 bits version it's located at i686-w64-mingw32/bin/SDL2.dll

* Modify the main.cpp signature to look like:

```
int main (int argc, char* args[])
```

If your exit code is 0 and Clion detects your SDL2 headers then you are good to go.

## Important READ

* The paths should be exactly as told otherwise change the folder's paths inside the CMakeLists.txt.
* MingGw should be the default toolchains for Clion.
* Add SDL2 and cmake folders to the gitignore.
* Disable Avast or other antivirus software if needed (or exclude project directory from it's range of scanning).

## Project tree example

<p align="center">
  <img src="resources/Example2.png"  alt="example"/>
</p>

## Setup SDL2 Image

1. Download the [SDL Image Development Release](https://github.com/libsdl-org/SDL_image/releases)

2. Inside your SDL2 Image folder (downloaded from step 1), select the version you are using for SDL2 and copy it to your
   SDL2 folder in your project (It won't override anything)

3. Put the SDL2_image.dll from the SDL2 Image folder into your cmake-build-debug folder.

4. Add to the CMakeList:

``` 
set(SDL2_IMAGE_PATH "SDL2/x86_64-w64-mingw32")
find_package(SDL2_image REQUIRED) 
```

**Modify the SDL2_IMAGE_PATH if you are using the 32 bit version**


# Code adjustments

1. Make sure, that path to the resources you use in your program is correct. Entry point of CMake to look for files is main project directory.
<p align="center">
  <img src="resources/Example3.png"  alt="example"/>
</p>

