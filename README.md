# materiales

            +------------------+
            |     Material     |
            +------------------+
            | - id: int        |
            | - nombre: String |
            +------------------+
            | + obtenerId()    |
            | + obtenerNombre()|
            +------------------+
                   ^
                   |
            +------------------------+
            |     Producto          |
            +-----------------------+
            | - idProducto: int     |
            | - nombre: String |
            | - material: Material  |
            +------------------------+
            | + obtenerIdProducto() |
            | + obtenerNombre()     |
            | + obtenerMaterial()   |
            +------------------------+

            import java.util.Scanner;

class Material {
    private int id;
    private String nombre;

    public Material(int id, String nombre) {
        this.id = id;
        this.nombre = nombre;
    }

    public int obtenerId() {
        return id;
    }

    public String obtenerNombre() {
        return nombre;
    }
}

class Producto {
    private int idProducto;
    private String nombre;
    private Material material;

    public Producto(int idProducto, String nombre, Material material) {
        this.idProducto = idProducto;
        this.nombre = nombre;
        this.material = material;
    }

    public int obtenerIdProducto() {
        return idProducto;
    }

    public String obtenerNombre() {
        return nombre;
    }

    public Material obtenerMaterial() {
        return material;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Ingrese los datos del material:");
        System.out.print("ID del material: ");
        int materialId = scanner.nextInt();
        scanner.nextLine();  // Consume the newline character
        System.out.print("Nombre del material: ");
        String materialNombre = scanner.nextLine();
        Material material = new Material(materialId, materialNombre);

        System.out.println("\nIngrese los datos del producto:");
        System.out.print("ID del producto: ");
        int productoId = scanner.nextInt();
        scanner.nextLine();  // Consume the newline character
        System.out.print("Nombre del producto: ");
        String productoNombre = scanner.nextLine();
        Producto producto = new Producto(productoId, productoNombre, material);

        System.out.println("\nDatos del producto:");
        System.out.println("ID: " + producto.obtenerIdProducto());
        System.out.println("Nombre: " + producto.obtenerNombre());
        System.out.println("Material: " + producto.obtenerMaterial().obtenerNombre());
    }
}
