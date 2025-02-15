# This is tutorial how to install OpenGL library on ubuntu

## About modules

- #### GL - rendering
- #### GLFW - window
- #### GLAD - lowlevel commands
- #### GLEW - 


## Install OpenGL
#### Install packages

```
sudo apt install libopengl-dev libglfw3 libglfw3-dev
```

#### Get version of openGl

Copy to file:

```
#include <GLFW/glfw3.h>
#include <iostream>

int main(){
        glfwInit();
        glfwWindowHint(GLFW_VISIBLE, GL_FALSE); //dont show the window

    // Open a window and create its OpenGL context
    GLFWwindow* window;
    window = glfwCreateWindow(100, 100, "Dummy window", NULL, NULL);
    if (window == NULL) {
        return 0;
    }
    glfwMakeContextCurrent(window);

    std::string versionString = std::string((const char*)glGetString(GL_VERSION));
    std::cout << versionString << '\n';
        return 0;
}
```

and compile with options 

```
-lGL -lglfw 
```

#### Get GLAD

go to [link](https://glad.dav1d.de)

choose gl version to your version 

click 'generate' button

download .zip arch

#### Use glad in projects

go to directory with .zip archive of glad

make command 
```
unzip glad.zip
sudo cp include/* /usr/include -r
```

now you can include glad with '<>'

cp src to directory with your project
```
cp src/* {path_to_your_project}
```

## Using

After installation to use openGL you need to add 
```
-lGL -lglfw
```
To compilers options
And add c source file 
```
glad.c
```
