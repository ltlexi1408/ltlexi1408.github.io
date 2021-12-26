---
layout: post
title:  "C# tick tak toe"
date:   2021-12-12 21:24:41 +1100
categories: [code ,C#]
---
Python tic tak toe game

{% highlight java %}
using System;

namespace tic_tak_toe{
    class tic_tak_toe{
        static void Main (string[]args){
            char[,] poss = new char [3,3];
            char player = 'x';
            bool cont = true; 

            Console.Write(player);
            Console.Write('\n');
            board(poss);
            show(poss);
             
            while(cont){
                play(ref poss, ref player);
                Console.Write(player);
                Console.Write('\n');
                show(poss);
                cont = end(poss);
            }
        }

        static char[,] board(char[,] poss){
            for(int i = 0; i < poss.GetLength(0); i++){
                for(int j = 0; j < poss.GetLength(1); j++){
                    poss[i,j] = '-';
                }
            }
            return poss;
        }

        static void show(char[,] poss){
            for(int i = 0; i < poss.GetLength(0); i++){
                for(int j = 0; j < poss.GetLength(1); j++){
                    Console.Write(poss[i,j]);
                }

                Console.Write('\n');
            }
        }

        static void play(ref char[,] poss, ref char player){
            bool invalid = false;

            while(!invalid){
                int place = Convert.ToInt32(Console.ReadLine());

                if(place <= 0 || place >= 10){
                    Console.Write("Invalid placement");
                    Console.Write('\n');
                    break;
                }
                else{
                    if(place < 4){
                        if(poss[0, (place - 1)] == '-'){ poss[0, (place - 1)] = player; } else { Console.Write("Invalid placement"); Console.Write('\n'); break; }
                    }
                    else if(place < 7){
                        if(poss[1, (place - 4)] == '-'){ poss[1, (place - 4)] = player; } else { Console.Write("Invalid placement"); Console.Write('\n'); break; }
                    }
                    else{
                        if(poss[2, (place - 7)] == '-'){ poss[2, (place - 7)] = player; } else { Console.Write("Invalid placement"); Console.Write('\n'); break; }
                    }

                    if(player == 'x'){
                        player = 'o';
                    }
                    else{
                        player = 'x';
                    }

                    invalid = true;
                }
            }
        }

        static bool end(char[,] poss){
            int full = 0;

            for(int i = 0; i < poss.GetLength(0); i++){
                for(int j = 0; j < poss.GetLength(1); j++){
                    if(poss[i,j] != '-'){ full += 1; }
                }
            }

            if(full == 9){ Console.Write("Draw"); return false; }

            for(int i = 0; i < poss.GetLength(0); i++){
                if(poss[i,0] == poss[i,1] && poss[i,1] == poss[i,2]){ 
                    Console.Write("player" + poss[i,0] + "wins");
                    return false;
                }
            }

            for(int i = 0; i < poss.GetLength(1); i++){
                if(poss[0,i] == poss[1,i] && poss[1,i] == poss[2,i]){ 
                    Console.Write("player" + poss[1,i] + "wins");
                    return false;
                }
            }

            if((poss[0,0] == poss[1,1] && poss[1,1] == poss[2,2]) && (poss[1,1] == 'x' || poss[1,1] == 'o')){
                Console.Write("player" + poss[1,1] + "wins");
                return false;
            }

            if((poss[0,2] == poss[1,1] && poss[1,1] == poss[2,0]) && (poss[1,1] == 'x' || poss[1,1] == 'o')){
                Console.Write("player" + poss[1,1] + "wins");
                return false;
            }
            
            return true;
        }
    }
}
{% endhighlight %}