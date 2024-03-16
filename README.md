# System-Integration-granular-access
Documentation for accessing the a granular access database and testing granular access as user 

### Indtroduktion
  I dette scenarie er det muligt at tilslutte en database for en keramik butik.
  Denne butik laver forskellige typer keramik hvor det er muligt at bestemme hvilket farver du som kunde ønsker.
  Herudover er det også muligt at se status på dine nuværende bestillinger 



### Connection to the database
  Conection string: granularaccess.database.windows.net
  Har du ikke et login kan du eftersprøge dette hos DevPortal@WeMakeCeramic.com

### Select
- Items <em> (Her kan du se de forskellige produkter der tilbydes) <em>
- Orders <em> (Her kan du se <em> **dine** ordre<em>) <em>
- OrderItems <em>(En ordre kan have flere varer, derfor kan du her se varerne der hører til <em>**dine**<em> ordre)<em>
- OrderItemsProduced <em>(<em>**Dine** <em>ordre der er færdigt produceret kan findes her, samt deres status på levering)<em>
 
### Insert
  - Orders <em>(Der er ingen værdier der alle er auto sat)<em>
    ~~~~sql
      INSERT INTO ORDERS
    ~~~~
  - OrderItems <em>(Brug OrderId fra **din** ordre brug select til at finde dette)<em>
    ~~~~sql
      INSERT INTO OrderItems (OrderID, ItemID, Quantity, Colors)
      VALUES (OrderID, ItemID, Quantity, Colors)
    ~~~~

### Update
  - OrderItems
    ~~~~sql
      UPDATE OrderItems (Colors)
      VALUES (Colors)
      WHERE ORDERITEMSID = (Your OrderItemId)
    ~~~~


### Color Scheme
