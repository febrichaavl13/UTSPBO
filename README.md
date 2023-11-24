// UTSPBO
//Class Siswa

public class Siswa {
    private String nama;
    private int umur;

    public Siswa(String nama, int umur) {
        this.nama = nama;
        this.umur = umur;
    }

    public String getNama() {
        return nama;
    }

    public int getUmur() {
        return umur;
    }

    public void add(Siswa siswa) {
    }
}

// Model

import java.util.ArrayList;
import java.util.List;

public class ModelSiswa {
    private List<Siswa> siswa = new ArrayList<>();

    public void addStudent(Siswa siswa) {
        siswa.add(siswa);
    }

    public List<Siswa> getSiswa() {
        return getSiswa();
    }

}

// View

import java.util.List;

public class SiswaView {
    public void displaySiswa(List<Siswa> siswa) {
        System.out.println("Daftar Siswa:");
        Siswa[] Siswa;
        for (Siswa siswa1 : siswa) {
            System.out.println("Nama: " + siswa1.getNama() + ", Umur: " + siswa1.getUmur());
        }
    }
}

// Controller

import java.util.List;
public class Controller {
        private ModelSiswa model;
        private SiswaView view;

        public Controller(ModelSiswa model, SiswaView view) {
            this.model = model;
            this.view = view;
        }

        public void tambahSiswa(String nama, int umur) {
            Siswa siswa1 = new Siswa(nama, umur);
            model.addStudent(siswa1);
        }

        public void displayStudents() {
            List<Siswa> students = model.getSiswa();
            view.displaySiswa(students);
        }
    }

// Main

import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        ModelSiswa model = new ModelSiswa();
        SiswaView view = new SiswaView();
        Controller controller = new Controller(model,view);

        Scanner scanner = new Scanner(System.in);
        System.out.print("Masukan Jumlah Siswa: ");
        int numberOfStudents = scanner.nextInt();

        for (int i = 0; i < numberOfStudents; i++) {
            System.out.print("Masukan Nama: ");
            String name = scanner.next();
            System.out.print("Masukan Umur: ");
            int age = scanner.nextInt();

            controller.tambahSiswa(name,age);
        }

        controller.displayStudents();

        scanner.close();
    }
}
