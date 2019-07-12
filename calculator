import java.util.Scanner;

public class Main {
    public static class Calculator {
        private double result;
        private Scanner in = new Scanner(System.in);

        private Calculator() {
            this.result = 0;
        }

        public double getDouble() {
            System.out.print("Argument: ");
            double res = 0;
            try {
                res = in.nextDouble();
            } catch (java.util.InputMismatchException e) {
                System.out.println("Error, bad argument");
                in.nextLine();
                res = this.getDouble();
            }
            return res;
        }

        public char getOperation() {
            System.out.print("Operation: ");
            char operation;
            operation = in.next().charAt(0);
            if (operation == '-' || operation == '+' || operation == '*' || operation == '/') {
                return operation;
            } else {
                System.out.println("Error operation");
                System.out.println("Operation: -, +, *, /, C - clear");
                operation = this.getOperation();
            }
            return operation;
        }

        public double calc(double a, char operation, double b){
            this.result = a;
            switch (operation){
                case '+':
                    this.result += b;
                    break;
                case '-':
                    this.result -= b;
                    break;
                case '*':
                    this.result *= b;
                    break;
                case '/':
                    if (b == 0)
                        System.out.println("Error, divide by zero");
                    else
                        this.result /= b;
                    break;
                default:
                    System.out.println("Error, bad operation");
            }
            return this.result;
        }

        public double getResult() {
            return this.result;
        }

        public void clearResult() {
            this.result = 0;
        }
    }

    public static void main(String[] args) {
        Calculator calc = new Calculator();
        boolean newCalc = true;
        while (true) {
            if (newCalc) {
                calc.calc(calc.getDouble(), calc.getOperation(), calc.getDouble());
                System.out.println("Result: " + calc.getResult());
                newCalc =  false;
            } else {
                System.out.println("n - clear result, c - continue, other - exit");
                Scanner in = new Scanner(System.in);
                char oper;
                oper = in.next().charAt(0);
                switch (oper){
                    case 'n':
                        calc.clearResult();
                        newCalc =  true;
                        break;
                    case 'c':
                        calc.calc(calc.getResult(), calc.getOperation(), calc.getDouble());
                        System.out.println("Result: " + calc.getResult());
                        break;
                    default:
                        System.out.println("Exit");
                        return;
                }
            }
        }
    }
}
