/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package javaapplication2;

import java.util.Scanner;

/**
 *
 * @author User
 */
public class JavaApplication2 {

    /**
     * @param args the command line arguments
     */
    public static Scanner inp = new Scanner(System.in);
    public static void main(String[] args) {
        String text;
        text = inp.nextLine();
            if(checker(text)){
            System.out.println("This is a constant");
        }else{
            System.out.println("This is not a constant");
        }   
    }
    public static boolean checker(String line){
        char digit[] = {'0','1','2','3','4','5','6','7','8','9','.'};
        Boolean flag = false;
        int dot=0;
        for(int i=0;i<line.length();i++){
            char  c = line.charAt(i);
            boolean x=false;
            for(char a:digit){
                if(a==c){
                    flag=true;
                    x=true;
                    if(c=='.')
                        dot++;
                }
            }
            if(x==false) return false;
        }
        if(flag &&dot<=1){
            return true;
        }
        return false;
    }
    
}
