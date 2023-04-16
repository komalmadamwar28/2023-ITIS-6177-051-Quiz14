# 2023-ITIS-6177-051-Quiz14

I have used xmysql, which connects to a database and generates APIs on the same. I have referred the documenation given on this site,
https://github.com/o1lab/xmysql/

1. I first created a database named "sample" in mysql workbench
    create database sample;
    
2. Created two tables "users" and "orders" in the same database and added some sample values
        --------------------------------------------------------------------------------------------
        
            CREATE TABLE `users` (
          `id` INT(11) NOT NULL AUTO_INCREMENT,
          `name` VARCHAR(255) NOT NULL,
          `email` VARCHAR(255) NOT NULL,
          PRIMARY KEY (`id`)
        );
        --------------------------------------------------------------------------------------------
        
        INSERT INTO `users` (`name`, `email`)
        VALUES
          ('John Doe', 'johndoe@example.com'),
          ('Jane Doe', 'janedoe@example.com'),
          ('Bob Smith', 'bobsmith@example.com'),
          ('Alice Johnson', 'alicejohnson@example.com'),
          ('Mike Williams', 'mikewilliams@example.com');
        --------------------------------------------------------------------------------------------


        CREATE TABLE `orders` (
          `id` INT NOT NULL AUTO_INCREMENT,
          `user_id` INT NOT NULL,
          `product_name` VARCHAR(255) NOT NULL,
          `price` DECIMAL(10,2) NOT NULL,
          PRIMARY KEY (`id`),
          FOREIGN KEY (`user_id`) REFERENCES `users` (`id`)
        );
        --------------------------------------------------------------------------------------------


        INSERT INTO `orders` (`user_id`, `product_name`, `price`)
        VALUES
          (1, 'Product A', 9.99),
          (2, 'Product B', 19.99),
          (1, 'Product C', 14.99),
          (3, 'Product D', 24.99),
          (2, 'Product E', 29.99);
        --------------------------------------------------------------------------------------------


3. Installed xmysql package using the command , "npm install -g xmysql"
4. Ran command to create apis on the given database using below , "xmysql -h localhost -u root -p <password> -d sample"
