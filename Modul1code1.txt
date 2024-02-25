import java.time.LocalDate;
import java.time.Period;
import java.util.Scanner;

public class materimodul1 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Nama: ");
        String name = scanner.nextLine();

        System.out.print("Masukkan jenis kelamin (L/P): ");
        char jenisKelamin = scanner.next().charAt(0);

        System.out.print("Tanggal Lahir (yyyy-mm-dd): ");
        String dobInput = scanner.nextLine();
        LocalDate dob = LocalDate.parse(dobInput);

        switch (jenisKelamin) {
            case 'L':
            case 'l':
                System.out.println("Gender : Laki-Laki");
                break;
            case 'P':
            case 'p':
                System.out.println("Gender : perempuan");
                break;
            default:
                System.out.println("Jenis kelamin tidak valid");
        }

        LocalDate now = LocalDate.now();
        Period period = Period.between(dob, now);

        System.out.println("nama Anda: " +name);
        System.out.println("Umur Anda :" + period.getYears() + " tahun " + period.getMonths() + " bulan");

        scanner.close();
    }
}