# Food-Allergens
Q. Create a table named Allergens under a database named FIA

   create table Allergens
   ( 
     Food_Product varchar(100),
     Main_Ingredient varchar(100),
     Sweetener varchar(100),
     Fat_Oil varchar(100),
     Seasoning varchar(100),
     Allergens varchar(100),
     Prediction varchar(100)
   )
  
  Note: I uploaded data to the Allergens table by using Import data wizard on MySQL 
  
  Q. Show all columns contained in the dataset
  
      select * from allergens
  
  Q. Show the Food Products where there are no sweetener and fat/oil
  
     select Food_Product 
     from allergens
     where Sweetener="None" and Fat_Oil="None"
     
  Q. Extract all Food Products where there are Allergens present
     
     Select Food_Product 
     from Allergens
     where Allergens!= "None"
     Group by Food_Product
   
   Q. Show the contents of the table where the Prediction is that there is no Allergen present in the Food Product
      
      select *, count(Allergens) as Number_as 
      from allergens
      where Prediction = "Does not contain"
      Group by Food_Product
      Order  by Number_as desc
   
   Q. Print the Food Product where there are no sweeteners, fat/oil and allergens but the prediction is that food product consits of allergens
      
      select Food_Product
      from allergens
      where Sweetener="None" and 
      Fat_Oil="None" and 
      Allergens="None" and 
      Prediction="Contains"
  
  
