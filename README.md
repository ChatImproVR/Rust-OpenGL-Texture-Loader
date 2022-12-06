# Rust-OpenGL-Texture-Loader
Adds a designated texture to an object in Rust. Right now, we are focusing on developing `mesh_loader`.

## `texture_loader`
This crate takes in two images and renders the combination of those two images as a texture on a single triangle.

> The idea is that we can use this program as a base to assign more complex textures onto more complex objects. We will probably need to write more specific functions that do more than just combine two images (the Rat and the Rust icon), but we will save that for later.

## `mesh_loader`
Since the `texture_loader` is able to render a triangle inside of a window, `mesh_laoder` will take its window configurations and attempt to render an object as specified by an OBJ file. 

> As of right now, the crate does not do that... we are still working on the function for parsing an OBJ file in Rust. A sample of the code that we hope to start with is in `./LoadObj.cpp`.

While not currently in use, once we begin writing the mesh loader function, there is a valid OBJ file provided in the crate as `./mesh_loader/teapot.obj`. We can use this file to test if our objects are properly rendered in the window when we `cargo run`.

For `mesh_loader`, we plan on implementing GLOW to make this work. SO far it is the simplest and most reliable method of converting GL-isms from C++ to Rust. `texture_loader` is also a great example of what OpenGL will look like in our Rust code.

---
## TODO
* Read through `./LoadObj.cpp`. If you're feeling particularly masochistic and are interested in seeing its full implementation in C++, you can find it on [my GitHub here.](https://github.com/toddgr/CS450-Animate-A-Helicopter/blob/main/sample.cpp)
* Break down `LoadObj` into a barest-bone algorithm. This is probably a better practice than translating it into Rust directly.
* That being said, we then need to translate `LoadObj` algorithm into a Rust function.
* Integrate that `LoadObj` Rust function into `mesh_loader`