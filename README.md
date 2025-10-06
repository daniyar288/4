import java.util.Scanner;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class OnlinePayment {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);

        System.out.println("=== Онлайн-оплата услуги: СВЕТ ===");
        System.out.println("Добро пожаловать в систему онлайн-оплаты коммунальных услуг!");
        System.out.println();

        System.out.print("Введите ФИО: ");
        String name = in.nextLine();

        System.out.print("\nВведите номер лицевого счета: ");
        String account = in.nextLine();

        System.out.print("\nВведите сумму оплаты (в тенге): ");
        double sum = in.nextDouble();

        if (sum <= 0) {
            System.out.println("Ошибка: сумма оплаты должна быть больше 0!");
            return;
        }

        System.out.println("Обработка платежа...");
        System.out.println("Пожалуйста, подождите...");
        try {
            Thread.sleep(1500); 
        } catch (InterruptedException e) {
            System.out.println("Ошибка при обработке платежа.");
        }

        LocalDateTime now = LocalDateTime.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd.MM.yyyy HH:mm:ss");

        System.out.println("\n=== ЧЕК ОБ ОПЛАТЕ ===");
        System.out.println("Услуга: Свет");
        System.out.println("ФИО плательщика: " + name);
        System.out.println("Лицевой счет: " + account);
        System.out.println("Сумма оплаты: " + sum + " тг");
        System.out.println("Дата и время: " + now.format(formatter));
        System.out.println("Статус: оплата прошла успешно");
        System.out.println("=============================");
        System.out.println("Спасибо за использование онлайн-оплаты!");

        in.close();
    }
}
