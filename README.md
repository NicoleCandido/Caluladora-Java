# Caluladora-Java
Este código em Java implementa uma calculadora simples usando Programação Orientada a Objetos (POO).
----Class OperacaoMatematica------
public class OperaçãoMatematica {
    public double calcular (double valor1, double valor2){
        return 0.0;
    }
}
-------Class Soma---------
public class Soma extends OperaçãoMatematica{
    public double calcular (double valor1, double valor2){
        return valor1+valor2;
    }
}
-------Class Subtracao------
public class Subtracao extends OperaçãoMatematica{
    public double calcular (double valor1, double valor2) {
        return valor1-valor2;
    }
}
--------Class Divisao-------
public class Divisao extends OperaçãoMatematica{
     public double calcular (double valor1, double valor2) {
        return valor1/valor2;
     }
}

---------Class visao--------------
public class JFcalculadora extends javax.swing.JFrame {
public static double calcule
        (OperaçãoMatematica op, double valor1, double valor2){
            return op.calcular(valor1, valor2);
        }
---botão----
  Double valor1 = Double.valueOf(jTvalor1.getText());
        Double valor2 = Double.valueOf(jTvalor2.getText());
        
        if (jRsoma.isSelected()){
            jLresposta.setText
       (" Soma "+calcule(new Soma(),valor1,valor2));
        }
        if(jRsubtracao.isSelected()){
            jLresposta.setText(" Subtracao "+calcule(new Subtracao(), valor1,valor2));
        }
        if (jRdivisao.isSelected()){
            jLresposta.setText(" Divisao "+calcule(new Divisao(),valor1, valor2));
        }
    }      
