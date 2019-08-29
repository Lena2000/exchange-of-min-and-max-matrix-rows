# exchange-of-min-and-max-matrix-rows
Ввод/вывод элементов матрицы. Подсчет суммы каждой строки матрицы. Обмен строк минимального и максимального значений. 
package двумер5;

import java.util.Scanner;

/**
 *
 * @author LENOVO
 */
public class Двумер5 {

    /**
     * @param args the command line arguments
     */
       public static void main(String[] args) {
          Scanner sc=new Scanner(System.in);
          System.out.println("Введите размер высоты матрицы:");
          int n=sc.nextInt();
          System.out.println("Введите размер ширины матрицы:");
          int m=sc.nextInt();
          int k=n*m;
          System.out.println("Введите "+k+" элементов матрицы:");
          int mas[][]=new int[n][m];
          int i;
          int j;
          int r=0;
          
          
          for(i=0; i<n; i++){
              for(j=0;j<m ;j++){
               mas[i][j]=sc.nextInt();
               if (i==0) r=r+mas[i][j];
              }
          }
          
          int summin=r;
          int summax=r;
          int indexmax=0;
          int indexmin=0;
          int temp;
          int sum;
         // 
          for(i=0; i<mas.length; i++){
              sum=0;
          for(j=0; j<mas[i].length; j++){
              System.out.print(mas[i][j]+ "\t");
               sum=sum+mas[i][j];
          }
              System.out.println("===" + sum);
          if(sum>summax){
                       summax=sum;
                       indexmax=i;
                   }
          if(sum<summin){
                       summin=sum;
                       indexmin=i;
                   }                  
               }
            
          for(j=0; j<m; j++){
              temp=mas[indexmax][j];
              mas[indexmax][j]=mas[indexmin][j];
              mas[indexmin][j]=temp;
              
              }
          System.out.println("Ваши элементы матрицы:");
          for(i=0; i<mas.length; i++){
          for(j=0; j<mas[i].length; j++){
              System.out.print(mas[i][j]+ "\t");
             
          }
              System.out.println();
       }
          
         
          }
          
}
          
          
    
