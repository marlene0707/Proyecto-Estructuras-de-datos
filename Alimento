import java.time.LocalDate;
import java.time.temporal.ChronoUnit;

public class Alimento {

    private String nombre;
    private String categoria;
    private int cantidad;
    private double precio;
    private LocalDate fechaCaducidad;

    public Alimento(String nombre, String categoria,
                    int cantidad, double precio,
                    LocalDate fechaCaducidad) {

        this.nombre = nombre;
        this.categoria = categoria;
        this.cantidad = cantidad;
        this.precio = precio;
        this.fechaCaducidad = fechaCaducidad;
    }

    public String getNombre() {
        return nombre;
    }

    public String getCategoria() {
        return categoria;
    }

    public int getCantidad() {
        return cantidad;
    }

    public double getPrecio() {
        return precio;
    }

    public LocalDate getFechaCaducidad() {
        return fechaCaducidad;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setCategoria(String categoria) {
        this.categoria = categoria;
    }

    public void setCantidad(int cantidad) {
        this.cantidad = cantidad;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }

    public void setFechaCaducidad(LocalDate fechaCaducidad) {
        this.fechaCaducidad = fechaCaducidad;
    }

    public long diasParaCaducar() {
        return ChronoUnit.DAYS.between(
                LocalDate.now(), fechaCaducidad);
    }

    public boolean estaCaducado() {
        return diasParaCaducar() < 0;
    }

    public boolean estaPorCaducar() {
        long dias = diasParaCaducar();
        return dias >= 0 && dias <= 3;
    }

    public boolean tienePocasUnidades() {
        return cantidad <= 2;
    }

    // DESCUENTO AUTOMÁTICO
    public int calcularDescuento() {

        long dias = diasParaCaducar();

        if (dias < 0) {
            return 0;
        }

        if (dias == 0 || dias == 1) {
            return 60;
        }

        if (dias == 2) {
            return 40;
        }

        if (dias == 3) {
            return 30;
        }

        if (dias == 4) {
            return 20;
        }

        if (dias == 5) {
            return 10;
        }

        return 0;
    }

    // PRECIO CON DESCUENTO
    public double calcularPrecioFinal() {

        int descuento = calcularDescuento();

        return precio * (1 - descuento / 100.0);
    }

    @Override
    public String toString() {

        return nombre
                + " - " + categoria
                + " - Cantidad: " + cantidad
                + " - Precio: $" + precio
                + " - Caducidad: " + fechaCaducidad;
    }
}
