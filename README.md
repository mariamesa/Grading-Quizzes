# Grading-Quizzes
This program incorporates both method call and arrays to assist in grading quizzes. Javadoc comments are also included.


import java.util.Scanner;

public class GradingQuizzes {
    public static void main(String[] arg) {
        final int data = 10;
        String[] studentResponse = new String[data];
        //Declare and initialize an array with the correct answers
        String[] answerKey = {"a", "b", "c", "d", "b", "d", "c", "c", "b", "a"};
        //Read in student's responses
        System.out.println("Please enter your answers to the quiz.");
        //Call all the methods to be used in this program
        readResponse(studentResponse);
        int grade = gradeResponse(studentResponse, answerKey);
        System.out.println("\n" + grade);
        boolean correctResponses= didPass(studentResponse, answerKey);
        System.out.println("\n"+ correctResponses);
        //Print whether the student passes; if yes, print the grade as well
        if(correctResponses==true) {
            System.out.println(" You passed! Your grade is " + grade);
        }
        else {
            System.out.println(" You failed...good luck on the next one!");
        }
    }
    /**
     * This method will read in a student's response and store them in an array
     * @param studentResponse is the array that will store the student responses
     */
    public static void readResponse(String studentResponse[]) {
        Scanner sc = new Scanner(System.in);
        for (int i = 0; i < studentResponse.length; i++) {
            studentResponse[i] = sc.next();
        }
    }
    /**
     * This method will compare the two arrays and return a grade
     * @param studentResponse is the array that carries the student's responses on the quiz
     * @param answerKey is the array that carries the correct answers
     * @return the student's grade on the quiz
     */
    public static int gradeResponse(String studentResponse[], String answerKey[]) {
        int grade = 0;
        for (int i = 0; i < answerKey.length; i++) {
            if (answerKey[i].equals(studentResponse[i])) {
                grade += 10;
            }
        }
        return grade;
    }
    /**
     * This method will determine whether the student passes using a boolean; the passing grade is determined by 6+
     * correct answers
     * @param studentResponse is the array that carries the student's responses
     * @param answerKey is the array that carries the correct answers
     * @return true if the student has six or more correct responses, and false if the correct responses is under six
     */
    public static boolean didPass(String studentResponse[], String answerKey[]) {
        int correctResponses = 0;
        for (int i = 0; i < answerKey.length; i++) {
            if (answerKey[i].equals(studentResponse[i])) {
                correctResponses++;
            }
        }
        return correctResponses>=6;
    }
}





