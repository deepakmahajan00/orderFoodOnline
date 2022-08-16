# order Food Online
NodeJs backend application to give you APIs to search resturants, food and place order.

## Required technologies
1. NodeJs `Backend api written in NodeJs`
2. PHP `Creat tables and loanding master data into database written in PHP`
3. Mysql `Mysql used as database`
4. Docker
5. Postman `to hit apis`

## Clone repository
git clone `https://github.com/deepakmahajan00/orderFoodOnline.git`

## Setup local without docker-compose

1. Enable `mysqli` in your `php.ini`
2. Install web server either `apache` or `Nginx`
3. Create `order_food` database in your local mysql
3. Open `connect.php` located at onlineFoodOrder/infrastructure/sql-data
4. Change `mysqli host, user, password, database_name, port` as per your local mysql setup
5. Run below commands to create and load database
    1. Go to project directory `onlineFoodOrder/infrastructure/sql-data` 
    2. `php createTables.php`
    3. `php loadResturantsAndMenuData.php`
    4. `php loadResturantsData.php`
    5. `php loadMenusData.php`
    6. `php loadCustomerAndPurchaseHistoryData.php`
    7. `php loadCustomersData.php`
    8. `php loadCustomerPurchaseHistory.php`
    9. `php loadBusinessHours.php`
6. Create .env file and add below lines, also update there respective values for each variable
    1. NODE_ENV=development
    2. PORT=`<nodejs-app-port example 8010>`
    3. HOST=`localhost`
    4. DB_HOST=`localhost` OR in case of docker-service use `mydb`
    5. DB_USER=`db_user`
    6. DB_DATABASE=`order_food`
    7. DB_PASSWORD=`db_password`
    8. DB_PORT=`3306`
    9. MYSQLDB_LOCAL_PORT=`3306`
7. Run `npm install`
8. Run `npm test` to check code-coverage
9. Run `npm start`
10. Hit the server to test health `curl localhost:8010/health` or `http://localhost:8010/health` and expect a `200` response
11. Swagger api-documentation `http://localhost:8010/api-docs`


## Setup with docker-compose

1. Run `docker-compose up`
2. Hit the server to test health `http://localhost:18010/health` and expect a `200` response
3. Swagger api-documentation `http://localhost:18010/api-docs`
4. Open `connect.php` located at onlineFoodOrder/infrastructure/sql-data
5. Change `mysqli host, user, password, database_name, port` as per your local mysql setup
6. Run `docker-compose exec www /bin/bash`
7. Run below commands to create and load database
   1. `cd infrastructure/sql-data`
   2. `php createTables.php`
   3. `php loadResturantsAndMenuData.php`
   4. `php loadResturantsData.php`
   5. `php loadMenusData.php`
   6. `php loadCustomerAndPurchaseHistoryData.php`
   7. `php loadCustomersData.php`
   8. `php loadCustomerPurchaseHistory.php`
   9. `php loadBusinessHours.php`

## List of APIs
- Docker Setup `http://localhost:18010/api-docs`
- Local Setup `http://localhost:18010/api-docs`