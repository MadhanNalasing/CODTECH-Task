# CODTECH-Task
/*The provided code consists of several Java classes aimed at implementing an inventory management system and a basic graphical user interface (GUI) for user authentication.*/




package com.Inventory;

import java.util.HashMap;
import java.util.Map;

public class UserAuthentication {
	private Map<String, String> users = new HashMap<>();

    public UserAuthentication() {
        // Add some default users
        users.put("admin", "password123");
        users.put("user", "password");
    }

    public boolean authenticate(String username, String password) {
        return users.containsKey(username) && users.get(username).equals(password);
    }
}
package com.Inventory;

public class Product {
	private String id;
    private String name;
    private int quantity;
    private double price;

    public Product(String id, String name, int quantity, double price) {
        this.id = id;
        this.name = name;
        this.quantity = quantity;
        this.price = price;
    }

    // Getters and Setters
    public String getId() { return id; }
    public void setId(String id) { this.id = id; }

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public int getQuantity() { return quantity; }
    public void setQuantity(int quantity) { this.quantity = quantity; }

    public double getPrice() { return price; }
    public void setPrice(double price) { this.price = price; }

    @Override
    public String toString() {
        return "Product{id='" + id + "', name='" + name + "', quantity=" + quantity + ", price=" + price + "}";
    }
}
package com.Inventory;

import java.util.ArrayList;
import java.util.List;

public class InventoryManager {
	private List<Product> products = new ArrayList<>();

    public void addProduct(Product product) {
        products.add(product);
    }

    public void editProduct(String id, String name, int quantity, double price) {
        for (Product product : products) {
            if (product.getId().equals(id)) {
                product.setName(name);
                product.setQuantity(quantity);
                product.setPrice(price);
                break;
            }
        }
    }

    public void deleteProduct(String id) {
        products.removeIf(product -> product.getId().equals(id));
    }

    public Product findProductById(String id) {
        for (Product product : products) {
            if (product.getId().equals(id)) {
                return product;
            }
        }
        return null;
    }

    public List<Product> getLowStockProducts(int threshold) {
        List<Product> lowStockProducts = new ArrayList<>();
        for (Product product : products) {
            if (product.getQuantity() < threshold) {
                lowStockProducts.add(product);
            }
        }
        return lowStockProducts;
    }

    public void generateSalesSummary() {
        // Example: Print all products
        for (Product product : products) {
            System.out.println(product);
        }
    }
}
package com.Inventory;

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPasswordField;
import javax.swing.JTextField;

public class InventoryManagementGUI {
	private JFrame frame;
    public InventoryManagementGUI() {
        new InventoryManager();
        new UserAuthentication();
        initialize();
    }

    private void initialize() {
        frame = new JFrame();
        frame.setBounds(100, 100, 450, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.getContentPane().setLayout(null);

        JLabel lblUsername = new JLabel("Username:");
        lblUsername.setBounds(10, 11, 80, 14);
        frame.getContentPane().add(lblUsername);

        JTextField txtUsername = new JTextField();
        txtUsername.setBounds(100, 8, 86, 20);
        frame.getContentPane().add(txtUsername);
        txtUsername.setColumns(10);

        JLabel lblPassword = new JLabel("Password:");
        lblPassword.setBounds(10, 42, 80, 14);
        frame.getContentPane().add(lblPassword);

        JPasswordField txtPassword = new JPasswordField();
        txtPassword.setBounds(100, 39, 86, 20);
        frame.getContentPane().add(txtPassword);

        JButton btnLogin = new JButton("Login");
        btnLogin.setBounds(100, 70, 89, 23);
        frame.getContentPane().add(btnLogin);

        JLabel lblMessage = new JLabel("");
        lblMessage.setBounds(10, 100, 414, 14);
        frame.getContentPane().add(lblMessage);

        btnLogin.addActionListener(new ActionListener() {
            @Override
			public void actionPerformed(ActionEvent e) {
				
			}
        });
    }

    public static void main(String[] args) {
        InventoryManagementGUI window = new InventoryManagementGUI();
        window.frame.setVisible(true);
    }
}
