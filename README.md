package zakat1;

import java.util.Scanner;

public class Zakat1 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String ulangi;  // Deklarasi variabel ulangi di luar perulangan
        
        do {
            System.out.println("- - - - - - - - - - - - - - - - - - - -");
            System.out.println("Program Sederhana");
            System.out.println("Selamat Datang di Kalkulator Zakat Mal (Uang)");
            System.out.println("- - - - - - - - - - - - - - - - - - - -");
            System.out.println();
            
            // Input nama pengguna
            System.out.print("Masukkan Nama Anda : ");
            String nama = input.nextLine();
            
            // Input jumlah penghasilan pengguna
            System.out.print("Masukkan Jumlah Penghasilan " + nama + " per Bulan dalam Rupiah: ");
            double jumlahHarta = input.nextDouble();

            // Cek apakah penghasilan memenuhi syarat nisab
            if (jumlahHarta >= 6859394) {
                double zakatMal = jumlahHarta * 2.5 / 100;
                System.out.println("Jadi, jumlah harta yang harus " + nama + " zakatkan adalah sebesar " + zakatMal + " Rupiah");
            } else {
                System.out.println("Penghasilan Anda tidak mencukupi syarat dari nisab zakat yaitu penghasilan Rp6.859.394/ bulan");
            }

            // Membersihkan input buffer setelah nextDouble()
            input.nextLine();

            // Menanyakan apakah ingin menghitung lagi
            System.out.println("\nApakah Anda ingin menghitung zakat lagi? (y/n) ");
            ulangi = input.nextLine();
         
            // Menggunakan switch-case untuk melanjutkan atau keluar
            switch (ulangi.toLowerCase()) {
                case "y":
                    System.out.println("\nBaik, mari kita hitung kembali.");
                    break;
                case "n":
                    System.out.println("\nTerima kasih telah menggunakan Kalkulator Zakat Penghasilan. Sampai jumpa, " + nama + "!");
                    break;
                default:
                    System.out.println("Pilihan tidak valid, program akan berhenti.");
                    ulangi = "n"; // Secara default keluar jika input tidak valid
                    break;
            }
            
        } while (ulangi.equalsIgnoreCase("y"));

        input.close();
    }
}
