# Postfix-to-Prefix-Conversion

import java.util.*; 
  
class GFG 
{ 
static boolean isOperand(char x)
{
    return (x >= 'a' && x <= 'z') || 
            (x >= 'A' && x <= 'Z'); 
}
 
static String getInfix(String exp) 
{ 
    Stack<String> s = new Stack<String>(); 
  
    for (int i = exp.length() - 1; i >= 0; i--) 
    {
      if(isOperand(exp.charAt(i)))
      {
          s.push(exp.charAt(i)+ ""); 
      }
      else
      {
          String op1 = s.peek();
          s.pop();
          String op2 = s.peek();
          s.pop();
           String temp =   exp.charAt(i) + op1 + op2 ;
           s.push(temp); 
           
      }
    }
    
     return s.peek(); 
    
}
        
public static void main(String args[]) 
{ 
    String exp = "*+AB-CD"; 
    System.out.println( getInfix(exp)); 
} 
} 
