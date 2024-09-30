# Minpro-1
 Nama: Joshua Timothy
 Nim:2309116070
 Kelas: B

SOURCEE

1.MAIN

package com.mycompany.Main;

import rentalManagement.ManajemenRental;

public class Main {
    public static void main(String[] args) {
        ManajemenRental manajemen = new ManajemenRental();
        manajemen.tampilkanMenu();
    }
}


2.Kendaraan.Java

package rental;

public class Kendaraan {
    private final String nomorPlat;
    private String merk;
    private String jenis;
    
    // Static property untuk menghitung jumlah kendaraan
    public static int jumlahKendaraan = 0;
    
    // Constructor
    public Kendaraan(String nomorPlat, String merk, String jenis) {
        this.nomorPlat = nomorPlat;
        this.merk = merk;
        this.jenis = jenis;
        jumlahKendaraan++;
    }
    
    // Getter untuk nomor plat
    public String getNomorPlat() {
        return nomorPlat;
    }

    // Getter dan Setter untuk merk
    public String getMerk() {
        return merk;
    }

    public void setMerk(String merk) {
        this.merk = merk;
    }

    // Getter dan Setter untuk jenis
    public String getJenis() {
        return jenis;
    }

    public void setJenis(String jenis) {
        this.jenis = jenis;
    }
    
    // Method untuk menampilkan detail kendaraan
    public void tampilkanDetail() {
        System.out.println("Nomor Plat: " + nomorPlat);
        System.out.println("Merk: " + merk);
        System.out.println("Jenis: " + jenis);
    }
}


3.ManajemenRental.JAVA

package rentalManagement;

import rental.Kendaraan;
import java.util.ArrayList;
import java.util.Scanner;

public class ManajemenRental {
    private final ArrayList<Kendaraan> daftarKendaraan = new ArrayList<>();
    private final Scanner scanner = new Scanner(System.in);

    // Constructor untuk inisialisasi kendaraan
    public ManajemenRental() {
        inisialisasiKendaraan(); // Memanggil method untuk menambahkan beberapa kendaraan
    }

    // Method untuk inisialisasi kendaraan default
    public void inisialisasiKendaraan() {
        daftarKendaraan.add(new Kendaraan("B 1234 CD", "Toyota", "SUV"));
        daftarKendaraan.add(new Kendaraan("D 5678 EF", "Honda", "Sedan"));
        daftarKendaraan.add(new Kendaraan("E 9101 GH", "Suzuki", "Minivan"));
        daftarKendaraan.add(new Kendaraan("F 2345 IJ", "BMW", "Coupe"));
    }

    // Method untuk menambah Kendaraan
    public void tambahKendaraan() {
        System.out.print("Masukkan Nomor Plat: ");
        String nomorPlat = scanner.nextLine();
        System.out.print("Masukkan Merk Kendaraan: ");
        String merk = scanner.nextLine();
        System.out.print("Masukkan Jenis Kendaraan: ");
        String jenis = scanner.nextLine();
        
        Kendaraan kendaraan = new Kendaraan(nomorPlat, merk, jenis);
        daftarKendaraan.add(kendaraan);
        System.out.println("Kendaraan berhasil ditambahkan!");
    }

    // Method lainnya tetap sama...
    
    public void editKendaraan() {
        System.out.print("Masukkan Nomor Plat kendaraan yang ingin diedit: ");
        String nomorPlat = scanner.nextLine();
        
        for (Kendaraan k : daftarKendaraan) {
            if (k.getNomorPlat().equalsIgnoreCase(nomorPlat)) {
                System.out.print("Masukkan Merk Baru: ");
                String merkBaru = scanner.nextLine();
                System.out.print("Masukkan Jenis Baru: ");
                String jenisBaru = scanner.nextLine();

                k.setMerk(merkBaru);
                k.setJenis(jenisBaru);
                System.out.println("Kendaraan berhasil diedit!");
                return;
            }
        }
        System.out.println("Kendaraan dengan nomor plat tersebut tidak ditemukan.");
    }

    public void hapusKendaraan() {
        System.out.print("Masukkan Nomor Plat kendaraan yang ingin dihapus: ");
        String nomorPlat = scanner.nextLine();

        for (Kendaraan k : daftarKendaraan) {
            if (k.getNomorPlat().equalsIgnoreCase(nomorPlat)) {
                daftarKendaraan.remove(k);
                System.out.println("Kendaraan berhasil dihapus!");
                Kendaraan.jumlahKendaraan--;
                return;
            }
        }
        System.out.println("Kendaraan dengan nomor plat tersebut tidak ditemukan.");
    }

    public void tampilkanSemuaKendaraan() {
        if (daftarKendaraan.isEmpty()) {
            System.out.println("Tidak ada kendaraan yang terdaftar.");
        } else {
            for (Kendaraan k : daftarKendaraan) {
                k.tampilkanDetail();
                System.out.println("-------------------------");
            }
        }
    }

    public void tampilkanMenu() {
        while (true) {
            System.out.println("1. Tambah Kendaraan");
            System.out.println("2. Edit Kendaraan");
            System.out.println("3. Hapus Kendaraan");
            System.out.println("4. Tampilkan Semua Kendaraan");
            System.out.println("5. Keluar");
            System.out.print("Pilih menu: ");
            int pilihan = scanner.nextInt();
            scanner.nextLine();  // Consume newline

            switch (pilihan) {
                case 1 -> tambahKendaraan();
                case 2 -> editKendaraan();
                case 3 -> hapusKendaraan();
                case 4 -> tampilkanSemuaKendaraan();
                case 5 -> {
                    System.out.println("Terima kasih telah menggunakan program ini.");
                    return;
                }
                default -> System.out.println("Pilihan tidak valid. Coba lagi.");
            }
        }
    }
}





















 1.TAMBAH KENDARAAN
 
 ![Screenshot 2024-09-30 213208](https://github.com/user-attachments/assets/24218db8-26ee-4616-ab0d-33c01ff6ee80)


2.EDIT KENDARAAN

![Screenshot 2024-09-30 213648](https://github.com/user-attachments/assets/b29e287a-6de2-43dc-8a52-7f8dbd8109d5)

3.HAPUS KENDARAAN

![Screenshot 2024-09-30 213818](https://github.com/user-attachments/assets/9e6656c0-8627-4ed7-97bb-b07cb1571c86)

![Screenshot 2024-09-30 213836](https://github.com/user-attachments/assets/c2bc53b9-b476-4ec0-8bb7-4be4f6995f15)

4. TAMPILKAN SEMUA KENDARAAN

![Screenshot 2024-09-30 214105](https://github.com/user-attachments/assets/743d6cbd-4d2b-4dd6-86dd-c92bd329c598)

5.KELUAR

![Screenshot 2024-09-30 214233](https://github.com/user-attachments/assets/6c5925c2-7801-410c-8e58-a7878a49c896)
