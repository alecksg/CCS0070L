package com.mycompany.mp3;

import java.util.ArrayDeque;
import java.util.Queue;
import java.util.Scanner;

class Ticket {
    int number;
    String name;
    String request;

    Ticket(int number, String name, String request) {
        this.number = number;
        this.name = name;
        this.request = request;
    }
}

public class MP3 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Queue<Ticket> tickets = new ArrayDeque<>();
        int choice = -1;
        int ticketNumber = 1;

        do {
            System.out.println("\n=== Customer Service Queue ===");
            System.out.println("1. New Ticket");
            System.out.println("2. Serve Next");
            System.out.println("3. Preview Next");
            System.out.println("4. Show Queue");
            System.out.println("0. Exit");
            System.out.print("Choice: ");

            if (!input.hasNextInt()) {
                System.out.println("Invalid input");
                input.nextLine();
                continue;
            }

            choice = input.nextInt();
            input.nextLine();

            switch (choice) {
                case 1 -> {
                    System.out.print("Customer name: ");
                    String name = input.nextLine().trim();

                    System.out.print("Request: ");
                    String request = input.nextLine().trim();

                    if (name.isEmpty() || request.isEmpty()) {
                        System.out.println("Invalid input");
                    } else {
                        tickets.offer(new Ticket(ticketNumber, name, request));
                        System.out.println("Ticket " + ticketNumber + " created");
                        ticketNumber++;
                    }
                }

                case 2 -> {
                    Ticket t = tickets.poll();

                    if (t == null) {
                        System.out.println("No pending tickets");
                    } else {
                        System.out.println("Ticket " + t.number + " served");
                    }
                }

                case 3 -> {
                    Ticket t = tickets.peek();

                    if (t == null) {
                        System.out.println("No pending tickets");
                    } else {
                        System.out.println("Next: Ticket " + t.number + " " + t.name);
                    }
                }

                case 4 -> {
                    if (tickets.isEmpty()) {
                        System.out.println("No pending tickets");
                    } else {
                        for (Ticket t : tickets) {
                            System.out.println("Ticket " + t.number + " - " + t.name + " - " + t.request);
                        }
                    }
                }

                case 0 -> System.out.println("Exit");
                default -> System.out.println("Invalid choice");
            }

        } while (choice != 0);

        input.close();
    }
}
