
En este trabajo explico de una forma simple cómo se pueden hacer interfaces gráficas usando Java Swing. Swing es una parte de Java que sirve para crear ventanas, botones, cuadros de texto y esas cosas que se ven en los programas. La idea es mostrar los componentes más básicos y cómo se usan, con ejemplos cortos que se entienden rápido.

1. JFrame

El JFrame es básicamente la ventana principal. Es lo primero que aparece cuando abrís un programa y es donde van todos los demás elementos.

Ejemplo:

import javax.swing.JFrame;

public class MiVentana {
    public static void main(String[] args) {
        JFrame ventana = new JFrame("Mi primera ventana");
        ventana.setSize(300, 200);
        ventana.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        ventana.setVisible(true);
    }
}


Este código crea una ventana simple con un tamaño fijo y un título arriba.

2. JPanel

El JPanel es como un “panel” donde podés poner cosas. Te sirve para ordenar mejor los elementos dentro del JFrame.

Ejemplo:

import javax.swing.*;

public class PanelEjemplo {
    public static void main(String[] args) {
        JFrame ventana = new JFrame("Ejemplo con JPanel");
        JPanel panel = new JPanel();

        ventana.add(panel);
        ventana.setSize(300, 200);
        ventana.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        ventana.setVisible(true);
    }
}


Acá simplemente se crea un panel y se lo mete dentro de la ventana.

3. JTextField

JTextField es el típico cuadro donde uno escribe texto. Como cuando llenás un formulario.

Ejemplo:

JTextField campo = new JTextField(15);
panel.add(campo);


Ese 15 significa el tamaño aproximado del cuadro.

4. JButton

JButton es un botón que el usuario puede apretar para hacer algo.

Ejemplo:

JButton boton = new JButton("Enviar");
panel.add(boton);

5. ActionListener

Para que un botón haga algo, hay que darle una acción. Si no, queda como un botón “de mentira”.

Ejemplo:

boton.addActionListener(e -> {
    System.out.println("El botón fue presionado");
});


Cuando lo apretás, aparece un mensaje en la consola.

6. Layouts

Los layouts son formas de acomodar los elementos dentro del panel. Uno de los más fáciles es FlowLayout, que ordena las cosas una al lado de la otra.

Ejemplo:

panel.setLayout(new java.awt.FlowLayout());

Ejemplo completo

Este código junta todo en un programa simple: una ventana con un cuadro de texto y un botón. Cuando el usuario escribe algo y toca el botón, lo que escribió se muestra en la consola.

import javax.swing.*;

public class AppEjemplo {
    public static void main(String[] args) {

        JFrame ventana = new JFrame("Formulario simple");

        JPanel panel = new JPanel();
        panel.setLayout(new java.awt.FlowLayout());

        JLabel labelNombre = new JLabel("Nombre:");
        JTextField campoNombre = new JTextField(15);

        JButton boton = new JButton("Guardar");

        boton.addActionListener(e -> {
            String nombre = campoNombre.getText();
            System.out.println("Guardado: " + nombre);
        });

        panel.add(labelNombre);
        panel.add(campoNombre);
        panel.add(boton);

        ventana.add(panel);
        ventana.setSize(300, 200);
        ventana.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        ventana.setVisible(true);
    }
}


Este ejemplo es útil para entender cómo funcionan los elementos básicos de Swing y cómo se combinan para armar una interfaz gráfica simple.
