import java.io.FileWriter;
import java.io.IOException;
 
public class Main {
    public static void main(String[] args) {
        int[] integers = {1, 25, 31, 49, 53, 62, 72, 86, 91, 100};
        String[] friends = {"Dhito", "Hosea", "James", "Rofi", "Irwan"};
 
        DataDiri myData = new DataDiri("Yehuda Adi S.", "22201070", "Bluluk Lamongan", 19, 178);
 
        try {
            FileWriter writer = new FileWriter("data.txt");
            // Tulis array integer
            for (int i = 0; i < integers.length; i++) {
                writer.write(integers[i] + " ");
            }
            writer.write("\n");
 
            // Tulis array nama teman
            for (int i = 0; i < friends.length; i++) {
                writer.write(friends[i] + " ");
            }
            writer.write("\n");
 
            // Tulis data diri
            writer.write("Nama: " + myData.nama + "\n");
            writer.write("NIM: " + myData.nim + "\n");
            writer.write("Alamat: " + myData.alamat + "\n");
            writer.write("Umur: " + myData.umur + "\n");
            writer.write("Tinggi Badan: " + myData.tinggiBadan + "\n");
 
            writer.close();
            System.out.println("Data berhasil disimpan dalam file.");
        } catch (IOException e) {
            System.out.println("Terjadi kesalahan dalam menyimpan data.");
            e.printStackTrace();
        }
    }
}
 
class DataDiri {
    String nama;
    String nim;
    String alamat;
    int umur;
    int tinggiBadan;
 
    public DataDiri(String nama, String nim, String alamat, int umur, int tinggiBadan) {
        this.nama = nama;
        this.nim = nim;
        this.alamat = alamat;
        this.umur = umur;
        this.tinggiBadan = tinggiBadan;
    }
}
