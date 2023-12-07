# UAS-Pemrograman-komputer-Alrin-Melanie-Putri-09011282328085
Nama : Alrin Melanie Putri
NIM : 09011282328085
Kelas : SK1A
Ujian Akhir Semester Pemerograman Komputer 

Soal 1
Seorang pelanggan sedang berbelanja di sebuah toko online. Terdapat sebuah barang dengan harga tertentu dan diskon berdasarkan jumlah pembelian. 
Implementasikan program Java untuk menghitung total harga yang harus dibayar oleh pelanggan.
Jika pelanggan membeli barang dengan jumlah kurang dari 5, tidak ada diskon.
Jika pelanggan membeli barang antara 5 hingga 10, berikan diskon 5%.Jika pelanggan membeli barang antara 11 hingga 20, berikan diskon 10%.Jika pelanggan membeli barang lebih dari 20, berikan diskon 20%.
Tampilkan total harga setelah diskon.

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int jumlahBeli, hargaBarang, totalHarga;
        double diskon = 0;

        System.out.print("Masukkan jumlah barang yang dibeli: ");
        jumlahBeli = input.nextInt();

        System.out.print("Masukkan harga barang: ");
        hargaBarang = input.nextInt();

        if (jumlahBeli >= 5 && jumlahBeli <= 10) {
            diskon = 0.05;
        } else if (jumlahBeli >= 11 && jumlahBeli <= 20) {
            diskon = 0.1;
        } else if (jumlahBeli > 20) {
            diskon = 0.2;
        }

        totalHarga = (int) Math.round(jumlahBeli * hargaBarang * (1 - diskon));

        System.out.println("Total harga setelah diskon: Rp " + totalHarga);
    }
}

Soal 2   
Buatlah program Java untuk melakukan autentikasi pengguna berdasarkan username dan password. 
Jika username dan password yang dimasukkan sesuai dengan nilai yang telah ditentukan, tampilkan pesan "Autentikasi Berhasil". 
Jika tidak, tampilkan pesan "Autentikasi Gagal".
import java.util.Scanner;

public class UAS_progkom2 {
    public static void main(String[] args) {

        // menentukan username dan password yang benar
        String usernameTrue = "Alrin";
        String passwordTrue = "akucantik123";

        // memasukkan username dan password
        Scanner scanner = new Scanner(System.in);
        System.out.print("Masukkan username: ");
        String usernameInput = scanner.nextLine();
        System.out.print("Masukkan password: ");
        String passwordInput = scanner.nextLine();

        // Memeriksa apakah username dan password sesuai dengan nilai yang benar
        if (usernameInput.equals(usernameTrue) && passwordInput.equals(passwordTrue)) {
            System.out.println("Autentikasi Berhasil");
        } else {
            System.out.println("Autentikasi Gagal");
        }

        scanner.close();
    }
}

Soal 3 
Buat program Java untuk menampilkan deret Fibonacci hingga suku ke-n. 
Deret Fibonacci adalah deret bilangan yang setiap suku setelah dua suku pertama adalah penjumlahan dari kedua suku sebelumnya.

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int n, first = 0, second = 1, next;

        System.out.print("Masukkan jumlah suku: ");
        n = input.nextInt();

        System.out.println("Deret Fibonacci hingga suku ke-" + n + " adalah: ");

        for (int i = 0; i < n; i++) {
            if (i <= 1) {
                next = i;
            } else {
                next = first + second;
                first = second;
                second = next;
            }
            System.out.print(next + " ");
        }
    }
}

Soal 4
Buat program Java untuk memfaktorisasi suatu bilangan bulat positif menjadi faktor-faktornya. 
Misalnya, jika input adalah 12, hasilnya harus menampilkan "Faktorisasi 12: 2 * 2 * 3".

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int bilangan, i, jumlahFaktor = 0;

        System.out.print("Masukkan bilangan bulat positif: ");
        bilangan = input.nextInt();

        for (i = 1; i <= bilangan; i++) {
            if (bilangan % i == 0) {
                jumlahFaktor++;
                System.out.print(i + " * ");
                bilangan /= i;
            }
        }

        System.out.println("Faktorisasi " + bilangan + " adalah: " + jumlahFaktor + " faktor");
    }
}

Soal 5
Buatlah program Java untuk kalkulator sederhana yang dapat melakukan operasi penjumlahan, pengurangan, perkalian, dan pembagian. 
Gunakan metode untuk setiap operasi.

import java.util.Scanner;

public class CalculatorAlrin {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double num1, num2;

        System.out.print("Masukkan angka pertama: ");
        num1 = input.nextDouble();
        System.out.print("Masukkan angka kedua: ");
        num2 = input.nextDouble();

        System.out.println("Penjumlahan: " + add(num1, num2));
        System.out.println("Pengurangan: " + subtract(num1, num2));
        System.out.println("Perkalian: " + multiply(num1, num2));
        System.out.println("Pembagian: " + divide(num1, num2));
    }

    public static double add(double num1, double num2) {
        return num1 + num2;
    }

    public static double subtract(double num1, double num2) {
        return num1 - num2;
    }

    public static double multiply(double num1, double num2) {
        return num1 * num2;
    }

    public static double divide(double num1, double num2) {
        if (num2 != 0) {
            return num1 / num2;
        } else {
            System.out.println("Error: Pembagian dengan nol");
            return Double.NaN;
        }
    }
}

Soal 6
Buat program Java untuk mengecek apakah suatu kata atau frase adalah palindrom atau tidak. 
Gunakan metode untuk melakukan pengecekan.

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String kata;

        System.out.print("Masukkan kata atau frase: ");
        kata = input.nextLine();

        if (isPalindrome(kata)) {
            System.out.println(kata + " adalah palindrom");
        } else {
            System.out.println(kata + " bukan palindrom");
        }
    }

    public static boolean isPalindrome(String kata) {
        kata = kata.toLowerCase().replaceAll("[^a-zA-Z0-9]", "");
        int panjang = kata.length();

        for (int i = 0; i < panjang / 2; i++) {
            if (kata.charAt(i) != kata.charAt(panjang - i - 1)) {
                return false;
            }
        }
        return true;
    }
}

Soal 7
Buatlah kelas Java untuk mengelola buku-buku dalam suatu perpustakaan. 
Setiap buku memiliki atribut judul, penulis, dan tahun terbit. 
Implementasikan metode untuk menampilkan informasi buku dan metode untuk meminjam buku.

public class Buku {
    private final String judul;
    private final String penulis;
    private final int tahunTerbit;
    private boolean tersedia;

    public Buku(String judul, String penulis, int tahunTerbit) {
        this.judul = judul;
        this.penulis = penulis;
        this.tahunTerbit = tahunTerbit;
        this.tersedia = true;
    }

    public void tampilkanInformasi() {
        System.out.println("Judul: " + judul);
        System.out.println("Penulis: " + penulis);
        System.out.println("Tahun Terbit: " + tahunTerbit);
        System.out.println("Status: " + (tersedia ? "Tersedia" : "Dipinjam"));
        System.out.println();
    }

    public void pinjamBuku() {
        if (tersedia) {
            tersedia = false;
            System.out.println("Buku berhasil dipinjam.");
        } else {
            System.out.println("Maaf, buku sedang tidak tersedia untuk dipinjam.");
        }
    }

    public void kembalikanBuku() {
        tersedia = true;
        System.out.println("Buku berhasil dikembalikan.");
    }

    public boolean isTersedia() {
        return tersedia;
    }

    public static void main(String[] args) {
        Buku buku1 = new Buku("Java Programming", "John Doe", 2020);
        Buku buku2 = new Buku("Data Structures", "Jane Smith", 2018);

        System.out.println("Informasi Buku 1:");
        buku1.tampilkanInformasi();

        System.out.println("Informasi Buku 2:");
        buku2.tampilkanInformasi();

        buku1.pinjamBuku();
        buku2.pinjamBuku();

        System.out.println("Setelah Peminjaman:");
        buku1.tampilkanInformasi();
        buku2.tampilkanInformasi();

        buku1.kembalikanBuku();
        buku2.kembalikanBuku();

        System.out.println("Setelah Pengembalian:");
        buku1.tampilkanInformasi();
        buku2.tampilkanInformasi();
    }
}

Soal 8
Buat kelas Java untuk mengelola akun pengguna. Setiap akun memiliki atribut username, password, dan status aktif/nonaktif. 
Implementasikan metode untuk mengaktifkan atau menonaktifkan akun.

public class AkunPengguna {
    private final String username;
    private String password;
    private boolean aktif;

    public AkunPengguna(String username, String password) {
        this.username = username;
        this.password = password;
        this.aktif = true; // Saat akun baru dibuat, dianggap aktif
    }

    public void tampilkanInformasi() {
        System.out.println("Username: " + username);
        System.out.println("Status: " + (aktif ? "Aktif" : "Nonaktif"));
        System.out.println();
    }

    public void aktifkanAkun() {
        aktif = true;
        System.out.println("Akun berhasil diaktifkan.");
    }

    public void nonaktifkanAkun() {
        aktif = false;
        System.out.println("Akun berhasil dinonaktifkan.");
    }

    public static void main(String[] args) {
        AkunPengguna akun1 = new AkunPengguna("user1", "password123");
        AkunPengguna akun2 = new AkunPengguna("user2", "securePass");

        System.out.println("Informasi Akun 1:");
        akun1.tampilkanInformasi();

        System.out.println("Informasi Akun 2:");
        akun2.tampilkanInformasi();

        akun1.nonaktifkanAkun();
        akun2.aktifkanAkun();

        System.out.println("Setelah Pembaruan Status Akun:");
        akun1.tampilkanInformasi();
        akun2.tampilkanInformasi();
    }
}

Soal 9
Buat program Java yang menggunakan struktur data stack untuk memeriksa apakah urutan kurung buka dan kurung tutup pada suatu ekspresi matematika sudah benar.

import java.util.Stack;

public class PemeriksaKurung {
    public static boolean periksaUrutanKurung(String ekspresi) {
        Stack<Character> stack = new Stack<>();

        for (char karakter : ekspresi.toCharArray()) {
            if (karakter == '(' || karakter == '{' || karakter == '[') {
                // Tambahkan kurung buka ke stack
                stack.push(karakter);
            } else if (karakter == ')' || karakter == '}' || karakter == ']') {
                // Periksa apakah stack tidak kosong dan kurung sesuai
                if (stack.isEmpty() || !cekPasangan(stack.pop(), karakter)) {
                    return false;
                }
            }
        }

        // Periksa apakah stack kosong setelah memproses seluruh ekspresi
        return stack.isEmpty();
    }

    private static boolean cekPasangan(char buka, char tutup) {
        return (buka == '(' && tutup == ')') ||
                (buka == '{' && tutup == '}') ||
                (buka == '[' && tutup == ']');
    }

    public static void main(String[] args) {
        String ekspresi1 = "((a+b)*(c-d))";
        String ekspresi2 = "({[a+b]*c}-d)";
        String ekspresi3 = "([a+b)*c-d]";

        System.out.println("Ekspresi 1: " + (periksaUrutanKurung(ekspresi1) ? "Benar" : "Salah"));
        System.out.println("Ekspresi 2: " + (periksaUrutanKurung(ekspresi2) ? "Benar" : "Salah"));
        System.out.println("Ekspresi 3: " + (periksaUrutanKurung(ekspresi3) ? "Benar" : "Salah"));
    }
}
