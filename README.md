# linc/SDL
Haxe/hxcpp @:native bindings for SDL.

This is a [linc](http://snowkit.github.io/linc/) library.

---

This library works with the Haxe cpp target only.

---

### Example usage

See test/Test.hx

Be sure to read the SDL documentation
https://wiki.libsdl.org/

```haxe
import sdl.SDL;

class Example {

    static var state : { window:Window, renderer:Renderer };

        //Haxe entry point
    static function main() {

        SDL.init(SDL_INIT_VIDEO | SDL_INIT_EVENTS);
        state = SDL.createWindowAndRenderer(320, 320, SDL_WINDOW_RESIZABLE);
        update();

    }

    static function update() {
        while(SDL.hasAnEvent()) {

            var e = SDL.pollEvent();
            if(e.type == SDL_QUIT) return false;

            SDL.setRenderDrawColor(state.renderer, 255,255,255,255);
            SDL.renderClear(state.renderer);
            SDL.renderPresent(state.renderer);
            SDL.delay(4);

        }
    }

}
```