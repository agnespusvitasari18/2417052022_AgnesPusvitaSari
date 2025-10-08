# 2417052022_AgnesPusvitaSari
/**
 * Class Kopi adalah blueprint untuk merepresentasikan pesanan kopi.
 */
class Kopi {

    // Atribut atau properti yang dimiliki oleh setiap objek Kopi.
    String jenisBiji; // Contoh: Arabika, Robusta
    String levelGula; // Contoh: Normal, Less Sugar, Tanpa Gula

    // -- CONSTRUCTORS --

    /**
     * 1. No-Argument Constructor (Constructor Tanpa Parameter).
     * Membuat objek kopi dengan nilai default jika tidak ada info spesifik.
     */
    public Kopi() {
        this.jenisBiji = "House Blend";
        this.levelGula = "Normal";
    }

    /**
     * 2. Parameterized Constructor (Constructor dengan Parameter).
     * Membuat objek kopi sesuai dengan pesanan pelanggan.
     * @param jenisBiji Jenis biji kopi yang dipilih.
     * @param levelGula Level gula yang diinginkan.
     */
    public Kopi(String jenisBiji, String levelGula) {
        this.jenisBiji = jenisBiji;
        this.levelGula = levelGula;
    }
    
    // -- METHOD OVERLOADING --

    /**
     * 3. Method Overloading pertama.
     * Menyajikan kopi dengan cara standar.
     */
    public void sajikan() {
        System.out.println("Secangkir kopi " + this.jenisBiji + 
                           " (" + this.levelGula + ") siap dinikmati.");
    }

    /**
     * 3. Method Overloading kedua.
     * Nama method sama ("sajikan"), tetapi dengan parameter berbeda.
     * Menyajikan kopi untuk pelanggan dengan nama tertentu.
     * @param namaPelanggan Nama pelanggan yang memesan.
     */
    public void sajikan(String namaPelanggan) {
        System.out.println("Kopi " + this.jenisBiji + 
                           " pesanan Sdr. " + namaPelanggan + " siap!");
    }

    /**
     * Method tambahan untuk menampilkan detail pesanan.
     */
    public void tampilkanPesanan() {
        System.out.println("Jenis Biji  : " + this.jenisBiji);
        System.out.println("Level Gula  : " + this.levelGula);
        System.out.println("============================");
    }
}


/**
 * Class Kedai adalah public class utama yang berisi method main.
 * Nama file harus sama dengan nama class ini, yaitu Kedai.java.
 */
public class Kedai {
    public static void main(String[] args) {

        // Membuat objek 'kopiStandar' menggunakan constructor default.
        System.out.println("PESANAN 1");
        Kopi kopiStandar = new Kopi();
        kopiStandar.tampilkanPesanan();

        // Membuat objek 'pesananAgnes' menggunakan parameterized constructor.
        System.out.println("PESANAN 2");
        Kopi pesananAgnes = new Kopi("Arabica", "Less Sugar");
        pesananAgnes.tampilkanPesanan();

        // -- Demonstrasi pemanggilan Method Overloading --
        System.out.println("--- PENYAJIAN KOPI ---");
        
        // Memanggil method sajikan() yang tanpa parameter.
        System.out.println("-> Panggilan method pertama:");
        kopiStandar.sajikan();
        
        System.out.println(); // Baris kosong untuk pemisah
        
        // Memanggil method sajikan() yang memiliki satu parameter String.
        System.out.println("-> Panggilan method kedua:");
        pesananAgnes.sajikan("Agnes");
    }
}
