#task 2
import java.util.Scanner;
public class Task2 {
    public static void main(String[] args) {
        System.out.println("Welcome to 'Student Grade Calculator' by utkarsh");
        try (Scanner sc = new Scanner(System.in)) {
            System.out.println("Enter the number of subjects: ");
            int n = sc.nextInt();

            int[] array = new int[n];

            int total_sum = 0;
            // For Input
            for(int i=0; i<n; i++){
                System.out.println("Enter the marks(out of 100) of subject "+(i+1)+": ");
                array[i] = sc.nextInt();

                // For Valid Input
                if(array[i]<0 || array[i]>100){
                    System.out.println("Invalid Input. Please enter no. between 0 and 100.");
                    i--;
                }
                else{
                    total_sum = total_sum + array[i];
                }
            }
            double average_percentage = total_sum / n;

            char grade;
            // For Grades 
            if(average_percentage >= 90){
                grade = 'A';
            }
            else if(average_percentage >= 80){
                grade = 'B';
            }
            else if(average_percentage >= 70){
                grade = 'C';
            }
            else if(average_percentage >= 60){
                grade = 'D';
            }
            else if(average_percentage >= 50){
                grade = 'E';
            }
            else{
                grade = 'F';
            }
            
            System.out.println("---------Your Result----------");
            System.out.println("Total Marks: "+total_sum);
            System.out.println("Average Perccentage: "+average_percentage+"%");
            System.out.println("Grade: "+grade);
        }
    }
}
