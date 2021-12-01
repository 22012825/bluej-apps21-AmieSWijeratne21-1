------------------------------------------------------------------------
* @author Amie Shanaya Wijeratne 22012825
 * @version 2016.02.29
 */
public class StockDemo
{
    private StockList stock;

    /**
     * Create a StockManager and populate it with at least
     * 10 sample products.
     */
    public StockDemo(StockList stock)
    {
        this.stock = stock;
        
        stock.add(new Product(101, "Nomads of the North"));
        stock.add(new Product(102, "Necromancer"));
        stock.add(new Product(103, "Butterfly Lion"));
        stock.add(new Product(104, "Spirited Away"));
        stock.add(new Product(105, "Danaganronpa Trigger Happy Havoc"));
        stock.add(new Product(106, "Howls Moving Castle"));
        stock.add(new Product(107, "Bird Box"));
        stock.add(new Product(108, "The Strange Case of Dr Jekyll and Mr Hyde"));
        stock.add(new Product(109, "Silence of the Lambs"));
        stock.add(new Product(110, "The Shining"));
    }

    /**
     * Provide a demonstration of how the ProductList meets all
     * the user requirements by making a delivery of each product 
     * buying it in various amounts and then selling each
     * product by various amounts. Make sure all the requirements
     * have been demonstrated.
     */
    
    public void runDemo()
    {
                
        stock.print();

        buyProducts();
        stock.print();        

        sellProducts();
        stock.print();        
    }
    
    private void buyProducts()
    {
        stock.buyProduct (101,921);
        stock.buyProduct (102, 46);
        stock.buyProduct (103, 50);
        stock.buyProduct (104, 13);
        stock.buyProduct (105, 500);
        stock.buyProduct (106, 23);
        stock.buyProduct (107, 40);
        stock.buyProduct (108, 4000);
        stock.buyProduct (108, 400);
        stock.buyProduct (109, 80);
        stock.buyProduct (110, 5000);
    }

    private void sellProducts()
    {
        stock.sellProduct(101,921);
        stock.sellProduct(102,20);
        stock.sellProduct(103, 11);
        stock.sellProduct(104, 76);
        stock.sellProduct(105, 4000);
        stock.sellProduct(106, 70);
        stock.sellProduct(107, 56);
        stock.sellProduct(108, 990);
        stock.sellProduct(109, 30);
        stock.sellProduct(110, 75);
    }    
    
    
}
import java.util.ArrayList;

/**
 * Manage the stock in a business.
 * The stock is described by zero or more Products.
 * 
 * @author Amie Shanaya Wijeratne 22012825   
 * @version V1 24/11/2021
 */
public class StockList
{
    // A list of the products.
    private ArrayList<Product> stock;

    /**
     * Initialise the stock manager.
     */
    public StockList()
    {
        stock = new ArrayList<Product>();
    }

    /**
     * Add a product to the list.
     * @param item The product item to be added.
     */
    public void add(Product item)
    {
        stock.add(item);
    }
    
    /**
     * A method to buy a single quantity of the product
     */
    public void buyProduct(int productID)
    {
        buyProduct(productID, 1);
    }
    
    
    /**
     * Buy a quantity of a particular product.
     * Increase the quantity of the product by the given amount.
     * @param id The ID of the product.
     * @param amount The amount to increase the quantity by.
     */
    public void buyProduct(int productID, int amount)
    {
        Product product = findProduct(productID);
        if(product != null) 
        {
            if(product.getQuantity() + amount < 1000)
            {
                product.increaseQuantity(amount);
                System.out.println("Bought " + amount + " of" + product.getName());
            }
            else
            {
                 System.out.println("There is not enough storage to buy " 
                 + amount + " of " + product.getName());
            }
        }
        else
        {
            System.out.println("The product is not availble");
        }
    }
    
    /**
     * Find a product to match the product id,
     * if not found return null
     */
    public Product findProduct(int productID)
    {
        for(Product product : stock)
        {
            if(product.getID() == productID)
            return product;
        }
        return null;
    }
    
    /**
     * Sell one of the given product.
     * Show the before and after status of the product.
     * @param id The ID of the product being sold.
     */
    public void sellProduct(int productID, int amount)
    {
      Product product = findProduct(productID);
        
      if(product != null) 
      {
            if(product.getQuantity() > 0 &&product.getQuantity() >= amount)
            {
                product.decreaseQuantity(amount);
                System.out.println("Sold " + amount + " of " + product.getName());
            }
            else if(product.getQuantity() < amount)
            {
                System.out.println("Cannot sell product");
            }
      }
      else
      {
            System.out.println("The product is not availble");
      }
    }    

    
    /**
     * Locate a product with the given ID, and return how
     * many of this item are in stock. If the ID does not
     * match any product, return zero.
     * @param id The ID of the product.
     * @return The quantity of the given product in stock.
     */
    public int numberInStock(int productID)
    {
        return 6;
    }

    /**
     * Print details of the given product. If found,
     * its name and stock quantity will be shown.
     * @param id The ID of the product to look for.
     */

    public void printProduct(int productID)
    {
        Product product = findProduct(productID);
        
        if(product != null) 
        {
            System.out.println(product.toString());
        }
    }
    
    /**
     * Print out each product in the stock
     * in the order they are in the stock list
     */
    public void print()
    {
        printHeading();
        
        for(Product product : stock)
        {
            System.out.println(product);
        }

        System.out.println();
    }
    
    public void printHeading()
    {
        System.out.println();
        System.out.println(" Amie's Stock List");
        System.out.println(" ====================");
        System.out.println();
    }
    
    
    
}
/**
 * Model some details of a product sold by a company.
 * 
 * @author Amie Shanaya Wijeratne
 * @V1 24/11/2021
 */
public class Product
{
    // An identifying number for this product.
    private int id;
    // The name of this product.
    private String name;
    // The quantity of this product in stock.
    private int quantity;

    /**
     * Constructor for objects of class Product.
     * The initial stock quantity is zero.
     * @param id The product's identifying number.
     * @param name The product's name.
     */
    public Product(int id, String name)
    {
        this.id = id;
        this.name = name;
        
        quantity = 0;
    }

    /**
     * @return The product's id.
     */
    public int getID()
    {
        return id;
    }

    /**
     * @return The product's name.
     */
    public String getName()
    {
        return name;
    }

    /**
     * @return The quantity in stock.
     */
    public int getQuantity()
    {
        return quantity;
    }

    public void setQuantity(int quantity)
    {
        this.quantity = quantity;
    }
    
    public void increaseQuantity(int amount)
    {
        quantity = quantity + amount;
    }
    
    public void decreaseQuantity(int amount)
    {
        if(quantity >= amount)
            quantity = quantity - amount;
    }
    
    /**
     * @return The id, name and quantity in stock.
     */
    public String toString()
    {
        return " ID " + id + ": " +  name + " stock level: " + quantity;
    }

    
    public void print()
    {
        System.out.println(toString());
    }
}
