package phuongtrinhbac2;
import java.util.Scanner;
import java.io.*;

public class Phuongtrinhbac2 {
    private double a;
    private double b;
    private double c;
    public Phuongtrinhbac2(){
         
    }
        // Phương thức tạo lập
    public Phuongtrinhbac2(double a, double b, double c){
        this.a=a;
        this.b=b;
        this.c=c;
    }
        // Phương thức nhập dữ liệu
    public double nhapDouble() {
        double so;
        Scanner scan = new Scanner(System.in);
        try {
        so = Double.parseDouble(scan.nextLine());
        }
        catch (Exception e) {           // Nếu nhập vào lỗi
            System.out.println("Nhap lai!");
            so=nhapDouble();  // Đệ quy hàm nhập
        }
        return so;     // Trả về giá trị nhập
    }
    void nhapPT() {
        System.out.println("Moi ban nhap phuong trinh can giai: ");
        System.out.println("a: ");a=nhapDouble();
        System.out.println("b: ");b=nhapDouble();
        System.out.println("c: ");c=nhapDouble();
    }
    void giaiPt() {
        if(a==0) {
            if(b!=0) {
                double x;
                System.out.println("Nghiem phuong trinh: "+x);
            }
            else if(b==0) {
                System.out.println("Phuong trinh khong hop le!");
                return;
            }
             
        }
        else {
            double delta= b*b -4*a*c;
            if(delta<0) {
//              System.out.println("Phuong trinh  " +a+ "x^2 +" + b+"x + "+c+"  vo nghiem");
                System.out.println("Phuong trinh vo nghiem!");
            }
            else if(delta ==0) {
                double x;
                x=(-b)/(2*a);
                System.out.println("Phuong trinh co nghiem kep: ");
            }
            else {
                double x1;
                double x2;
                x1=(-b +Math.sqrt(delta))/(2*a);
                x2=(-b +Math.sqrt(delta))/(2*a);
                System.out.println("Phuong trinh co nghiem phan biet: ");
                System.out.println("x1: "+ Math.ceil(x1*100.0)/100.0);
                System.out.println("x2: "+ Math.round(x2*100.0)/100.0);
            }
        }
    }
    public static void main(String[] args) {
        Phuongtrinhbac2 _ptb2 = new Phuongtrinhbac2();
        _ptb2.nhapPT();
        _ptb2.giaiPt();
    }
}
