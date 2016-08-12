#Create MySQL DB for Django app

    mysql -u root -p

    CREATE DATABASE app CHARACTER SET utf8;
    CREATE USER app@localhost IDENTIFIED BY 'pass';
    GRANT ALL PRIVILEGES ON app.* TO app@localhost;
    FLUSH PRIVILEGES;
