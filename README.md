# SDL2-CPP
Me learning SDL

I am trying to learn SDL using C++, I have found the two tutorials online that seem to be all of them. I am going to put together my own tutorial ype thing. Hopefully I finish it. 
## 01, Open A Window
Part one I am going to make a window, a surface to fill it and set a delay to close it after 5 seconds.

    #include <SDL2/SDL.h>
    #include <iostream>
    using namespace std;
    
    int main(){
      if(SDL_Init(SDL_INIT_VIDEO) < 0){
        cout << "Could not initialize SDL, Error: " << SDL_GetError() << endl;
      }
      else{
        SDL_Window* win = SDL_CreateWindow("My Win", SDL_WINDOWPOS_CENTERED, SDL_WINDOWPOS_CENTERED, 620, 480, SDL_WINDOW_SHOWN);
        if(win == 0){
          cout << "Could not create window, Error: " << SDL_GetError() << endl;
        }
        else{
          SDL_Surface* sur = SDL_GetWindowSurface(win);
          SDL_FillRect(sur, NULL, SDL_MapRGB(sur->format, 255, 0, 255));
          SDL_UpdateWindowSurface(win);
          
          SDL_Delay(5000);
          SDL_Quit();
        }
      }
    return 0;
    }
To build: 
  > g++ main.cpp -lSDL2
  
To run: 
  >./a.out
  
You can capy paste this and save as main.cpp then goto that directory via console or terminal and run the code above. If you are using a differant compiler then g++ then replace that part ie:clang main.cpp -lSDL2;

###Next
We I will break this same code into functions and put that inside of a loop that will close when we click the X button.
