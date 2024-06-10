import java.util.Scanner;

public class GradeCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Step 1: Take marks obtained in each subject
        System.out.println("Enter marks obtained in each subject (out of 100):");
        int totalSubjects;
        do {
            System.out.print("Enter the total number of subjects: ");
            totalSubjects = scanner.nextInt();
        } while (totalSubjects <= 0);

        int totalMarks = 0;
        for (int i = 1; i <= totalSubjects; i++) {
            System.out.print("Enter marks obtained in subject " + i + ": ");
            int marks = scanner.nextInt();
            if (marks < 0 || marks > 100) {
                System.out.println("Marks should be between 0 and 100. Please enter valid marks.");
                i--; // Repeat for the same subject
            } else {
                totalMarks += marks;
            }
        }

        // Step 2: Calculate total marks
        double averagePercentage = (double) totalMarks / totalSubjects;

        // Step 3: Calculate average percentage
        char grade;
        if (averagePercentage >= 90) {
            grade = 'A';
        } else if (averagePercentage >= 80) {
            grade = 'B';
        } else if (averagePercentage >= 70) {
            grade = 'C';
        } else if (averagePercentage >= 60) {
            grade = 'D';
        } else if (averagePercentage >= 50) {
            grade = 'E';
        } else {
            grade = 'F';
        }

        // Step 4: Display results
        System.out.println("Total Marks: " + totalMarks);
        System.out.println("Average Percentage: " + averagePercentage);
        System.out.println("Grade: " + grade);

        scanner.close();
    }
}
