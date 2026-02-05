public class ClubMeetingApp {

    // 1. Random number from minimum to maximumExclusive
    public static int randomNumberExclusive(int minimum, int maximumExclusive) {
        return (int)(Math.random() * (maximumExclusive - minimum)) + minimum;
    }

    // 2. Cheater's dice that favors higher numbers
    public static int cheatersDiceMax(int minimum, int maximumExclusive) {
        int num1 = randomNumberExclusive(minimum, maximumExclusive);
        int num2 = randomNumberExclusive(minimum, maximumExclusive);
        return Math.max(num1, num2);
    }

    // 3. Cheater's dice that favors lower numbers
    public static int cheatersDiceMin(int minimum, int maximumExclusive) {
        int num1 = randomNumberExclusive(minimum, maximumExclusive);
        int num2 = randomNumberExclusive(minimum, maximumExclusive);
        return Math.min(num1, num2);
    }

    public static void main(String[] args) {

        System.out.println("1. Where will we meet?");
        int room = randomNumberExclusive(266, 268);
        System.out.println("Coding club will meet in room " + room + ".");

        System.out.println("2. What time will we meet?");
        int time = randomNumberExclusive(3, 6);
        System.out.println("We will meet at " + time + " pm.");

        System.out.println("3. What grade will provide snacks?");
        int grade = cheatersDiceMin(9, 13);
        System.out.println(grade + "th graders will be providing snacks.");

        System.out.println("4. What will the membership fee be?");
        int fee = cheatersDiceMax(5, 16);
        System.out.println("Membership fee is $" + fee + ".");

        System.out.println("5. Club motto:");
        int mottoChoice = randomNumberExclusive(1, 4);
        if (mottoChoice == 1) {
            System.out.println("Code. Create. Repeat.");
        } else if (mottoChoice == 2) {
            System.out.println("Think logically. Code boldly.");
        } else {
            System.out.println("Building the future with code.");
        }

        System.out.println("JOIN TODAY!");
    }
}
