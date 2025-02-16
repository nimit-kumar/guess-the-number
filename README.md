package com.company;
import java.util.Scanner;
import java.util.Random;
class Game{
    int num;
    int attempts;
    public Game(){
        Random rand = new Random();
        num=rand.nextInt(100);
        attempts=0;

    }
    public int input(){
        Scanner sc= new Scanner(System.in);
        System.out.println("enter your guess:");
        int n= sc.nextInt();
        attempts++;
        return n;

    }
    public boolean Iscorrect(int guess){
        if(guess==num){
            System.out.println("you guessed the number correctly in "+attempts+" attempts CONGRATULATIONS!!!..");
            return true;
        }

        else if (guess<num) {
            System.out.println("your guess is less than num");

        }
        else{

            System.out.println("Your number is higher than the guess");

        }
        return false;
    }
}
public class main{

    public static void main(String[] args){
        System.out.println("welcome to the number guessing game!!!...");
        Game obj=new Game();

        boolean guessed=false;



        while(!guessed){
            int guess = obj.input();
            guessed = obj.Iscorrect(guess);

        }


    }
}
