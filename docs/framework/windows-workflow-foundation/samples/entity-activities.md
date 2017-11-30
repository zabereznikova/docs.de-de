---
title: "Entitätsaktivitäten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a3f50999e80cea0cf2d3e8280abe4204076e653
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="entity-activities"></a><span data-ttu-id="51bff-102">Entitätsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="51bff-102">Entity Activities</span></span>
<span data-ttu-id="51bff-103">In diesem Beispiel wird gezeigt, wie das ADO.NET Entity Framework mit [!INCLUDE[wf2](../../../../includes/wf2-md.md)] verwendet wird, um den Datenzugriff zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="51bff-103">This sample shows how to use the ADO.NET Entity Framework with [!INCLUDE[wf2](../../../../includes/wf2-md.md)] to simplify data access.</span></span>  
  
 <span data-ttu-id="51bff-104">Das ADO.NET Entity Framework ermöglicht es Entwicklern, in Form von domänenspezifischen Objekten, Eigenschaften und Beziehungen, z. B. Kunden, Bestellungen, Bestelldetails und den Beziehungen zwischen diesen Entitäten, mit Daten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="51bff-104">The ADO.NET Entity Framework enables developers to work with data in the form of domain-specific objects, properties and relationships such as Customers, Orders, Order Details and the relationships between these entities.</span></span> <span data-ttu-id="51bff-105">Das ADO.NET Entity Framework ermöglicht dies, indem eine Abstraktionsebene bereitgestellt wird, die das Programmieren mit einem konzeptionellen Anwendungsmodell anstelle des direkten Programmierens mit einem Speicherschema ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="51bff-105">The ADO.NET Entity Framework does this by providing a level of abstraction that enables programming against a conceptual application model instead of programming directly against a relational storage schema.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="51bff-106">Das ADO.NET Entity Framework finden Sie unter [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span><span class="sxs-lookup"><span data-stu-id="51bff-106"> the ADO.NET Entity Framework see [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="51bff-107">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="51bff-107">Sample details</span></span>  
 <span data-ttu-id="51bff-108">In diesem Beispiel wird die Datenbank `Northwind` verwendet; es umfasst Skripts zum Erstellen und Entfernen der Datenbank `Northwind` (Setup.cmd und Cleanup.cmd).</span><span class="sxs-lookup"><span data-stu-id="51bff-108">This sample uses the `Northwind` database and includes scripts for creating and removing the `Northwind` database (Setup.cmd and Cleanup.cmd).</span></span> <span data-ttu-id="51bff-109">Die Projekte in diesem Beispiel umfassen ein Entity Data Model auf Grundlage der Datenbank `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="51bff-109">The projects in this sample include an Entity Data Model based on the `Northwind` database.</span></span> <span data-ttu-id="51bff-110">Sie finden das Modell, indem Sie die Datei `Northwind.edmx` öffnen, die im Projekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="51bff-110">You can find the model by opening the `Northwind.edmx` file that is included in the project.</span></span> <span data-ttu-id="51bff-111">Dies ist das Modell, das die Form der Objekte definiert, auf die mit dem ADO.NET Entity Framework zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="51bff-111">This is the model that defines the shape of the objects that can be accessed using the ADO.NET Entity Framework.</span></span>  
  
 <span data-ttu-id="51bff-112">Die folgenden Aktivitäten sind in diesem Beispiel enthalten:</span><span class="sxs-lookup"><span data-stu-id="51bff-112">The following activities are included in this sample:</span></span>  
  
-   <span data-ttu-id="51bff-113">`EntitySQLQuery`: Mit der `EntitySQLQuery`-Aktivität können Sie Objekte aus der Datenbank auf Grundlage einer Entity SQL-Abfragezeichenfolge abrufen.</span><span class="sxs-lookup"><span data-stu-id="51bff-113">`EntitySQLQuery`: The `EntitySQLQuery` activity allows you to retrieve objects from the database based on an Entity SQL query string.</span></span> <span data-ttu-id="51bff-114">Entity SQL ist eine speicherunabhängige Sprache, die SQL ähnlich ist und es Ihnen, Abfragen auf Grundlage des konzeptionellen Modells und der Entitäten anzugeben, die ein Teil des Modells oder der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="51bff-114">Entity SQL is a store independent language that is similar to SQL and it allows you to specify queries based on the conceptual model and the entities that are a part of the model or domain.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="51bff-115">Entity SQL-Sprache finden Sie unter [Entity SQL-Sprache](http://go.microsoft.com/fwlink/?LinkId=165646).</span><span class="sxs-lookup"><span data-stu-id="51bff-115"> Entity SQL Language, see [Entity SQL Language](http://go.microsoft.com/fwlink/?LinkId=165646).</span></span>  
  
-   <span data-ttu-id="51bff-116">`EntityLinqQuery`: Mit dieser Aktivität können Sie Objekte aus der Datenbank auf Grundlage einer LINQ-Abfrage oder eines Prädikats abrufen.</span><span class="sxs-lookup"><span data-stu-id="51bff-116">`EntityLinqQuery`: This activity allows you to retrieve objects from the database based on a LINQ query or predicate.</span></span>  
  
-   <span data-ttu-id="51bff-117">`EntityAdd`: Mit der `EntityAdd`-Aktivität können Sie der Datenbank eine Entität oder eine Auflistung von Entitäten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="51bff-117">`EntityAdd`: The `EntityAdd` activity allows you to add an entity or a collection of entities to the database.</span></span>  
  
-   <span data-ttu-id="51bff-118">`EntityDelete`: Mit der `EntityDelete`-Aktivität können Sie eine Entität oder eine Auflistung von Entitäten aus der Datenbank löschen.</span><span class="sxs-lookup"><span data-stu-id="51bff-118">`EntityDelete`: The `EntityDelete` activity allows you to delete an entity or a collection of entities from the database.</span></span>  
  
-   <span data-ttu-id="51bff-119">`ObjectContextScope`: Die zuvor erwähnten Aktivitäten können nur Instanz innerhalb einer enthaltenden `ObjectContextScope`-Aktivitätsinstanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51bff-119">`ObjectContextScope`: The previously mentioned activities can only be used within a containing `ObjectContextScope` activity instance.</span></span> <span data-ttu-id="51bff-120">Die `ObjectContextScope`-Aktivität stellt die Verbindung zur Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="51bff-120">The `ObjectContextScope` activity sets up the connection to the database.</span></span> <span data-ttu-id="51bff-121">Sie erfordert eine Verbindungszeichenfolge (die entweder übergeben oder mit einer Konfigurationsdateieinstellung abgerufen wird).</span><span class="sxs-lookup"><span data-stu-id="51bff-121">It requires a connection string (that is either passed in or retrieved using a configuration file setting).</span></span> <span data-ttu-id="51bff-122">Die `ObjectContextScope`-Aktivität erleichtert das Ausführen einer Gruppe von zusammengehörigen Vorgängen in Entitäten.</span><span class="sxs-lookup"><span data-stu-id="51bff-122">The `ObjectContextScope` activity makes it easy to perform a group of related operations on entities.</span></span> <span data-ttu-id="51bff-123">Da dieser Bereich eine aktive Verbindung aufrechterhält, handelt es sich um einen nicht persistenten Bereich.</span><span class="sxs-lookup"><span data-stu-id="51bff-123">Because this scope maintains an active connection, it is a No Persist scope.</span></span> <span data-ttu-id="51bff-124">Wenn die `ObjectContextScope`-Aktivität beendet wird, werden außerdem alle Änderungen, die an Objekten vorgenommen wurden, die mit Entitätsaktivitäten innerhalb dieses Bereichs abgerufen wurden, automatisch in die Datenbank übernommen, und es ist keine explizite oder nachfolgende Aktion erforderlich, um Objekte zurück in die Datenbank zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51bff-124">In addition, when the `ObjectContextScope` activity exits, any changes that are made to objects retrieved using Entity Activities within that scope automatically get persisted back to the database, and no explicit or subsequent action is required to save objects back to the database.</span></span>  
  
## <a name="using-the-entity-activities"></a><span data-ttu-id="51bff-125">Verwenden der Entitätsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="51bff-125">Using the entity activities</span></span>  
 <span data-ttu-id="51bff-126">Die folgenden Codeausschnitte veranschaulichen, wie die in diesem Beispiel dargestellten Entitätsaktivitäten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51bff-126">The following code snippets demonstrate how to use the entity activities presented in this sample.</span></span>  
  
### <a name="entitysql"></a><span data-ttu-id="51bff-127">EntitySQL</span><span class="sxs-lookup"><span data-stu-id="51bff-127">EntitySql</span></span>  
 <span data-ttu-id="51bff-128">Der Codeausschnitt unten stellt dar, wie alle nach Namen sortierten Kunden in London abgefragt werden und wie die Liste der Kunden durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="51bff-128">The code snippet below shows how to query all customers in London sorted by name and how to iterate through the list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>();  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>();  
  
// create and return the workflow  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
        {  
            Activities =   
                {               
                    new WriteLine { Text = "Executing query" },                            
                    // query for all customers that are in london   
                    new EntitySqlQuery<Customer>  
                    {  
                        EntitySql =  @"SELECT VALUE Customer   
                                        FROM NorthwindEntities.Customers AS Customer   
                                        WHERE Customer.City = 'London'   
                                        ORDER BY Customer.ContactName",  
                        Result = londonCustomers  
                    },  
  
                    // iterate through the list of customers and display them   
                    new ForEach<Customer>  
                    {                                      
                        Values = londonCustomers,  
                        Body = new ActivityAction<Customer>  
                        {  
                            Argument = iterationVariable,  
                            Handler = new WriteLine   
                            {   
                                  Text = new InArgument<String>(e =>    
                                              iterationVariable.Get(e).ContactName)   
                            }  
                        }  
                    }  
                }  
        }                 
};     
```  
  
### <a name="entitylinqquery"></a><span data-ttu-id="51bff-129">EntityLinqQuery</span><span class="sxs-lookup"><span data-stu-id="51bff-129">EntityLinqQuery</span></span>  
 <span data-ttu-id="51bff-130">Der Codeausschnitt unten stellt dar, wie alle Kunden in London abgefragt werden und wie die resultierende Liste der Kunden durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="51bff-130">The code snippet below shows how to query all customers in London and how to iterate through the resulting list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>() { Name = "LondonCustomers" };  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>() { Name = "iterationVariable" };  
  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // return all the customers that match with the provided Linq predicate  
            new EntityLinqQuery<Customer>  
            {   
                Predicate = new LambdaValue<Func<Customer, bool>>(  
                          ctx => new Func<Customer, bool>(c => c.City.Equals("London"))),                              
                Result = londonCustomers  
            },  
  
            // iterate through the list of customers and display in the console  
            new ForEach<Customer>  
            {                                      
                Values = londonCustomers,  
                Body = new ActivityAction<Customer>  
                {  
                    Argument = iterationVariable,  
                    Handler = new WriteLine   
                    {   
                        Text = new InArgument<String>(e =>   
                                      iterationVariable.Get(e).ContactName)   
                    }  
                }  
            }  
        }  
    }  
};  
```  
  
### <a name="entityadd"></a><span data-ttu-id="51bff-131">EntityAdd</span><span class="sxs-lookup"><span data-stu-id="51bff-131">EntityAdd</span></span>  
 <span data-ttu-id="51bff-132">Der Codeausschnitt unten stellt dar, wie einem vorhandenen Auftrag ein OrderDetail-Datensatz hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="51bff-132">The code snippet below shows how to add an OrderDetail record to an existing Order.</span></span>  
  
```  
Variable<IEnumerable<Order>> orders = new Variable<IEnumerable<Order>>();  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();  
Variable<Order> order = new Variable<Order>();  
Variable<OrderDetail> orderDetail = new Variable<OrderDetail>();              
  
return new ObjectContextScope  
{  
    Variables = { order, orders, orderDetail, orderDetails },  
    ContainerName = "NorthwindEntities",  
    ConnectionString = new InArgument<string>(connStr),                  
    Body = new Sequence  
    {                      
        Activities =   
        {                            
           // get the order where we want to add the detail  
           new EntitySqlQuery<Order>  
           {  
               EntitySql =    
                    @"SELECT VALUE [Order]  
                      FROM NorthwindEntities.Orders as [Order]  
                      WHERE Order.OrderID == 10249",  
               Result = orders  
           },  
  
           // store the order in a variable  
           new Assign<Order>   
           {  
               To = new OutArgument<Order>(order),  
               Value = new InArgument<Order>(c => orders.Get(c).First<Order>())  
           },  
  
           // add the detail to the order  
           new EntityAdd<OrderDetail>  
           {  
               Entity = new InArgument<OrderDetail>(c =>   
                                         new OrderDetail {   
                                                  OrderID=10249, ProductID=11,   
                                                  Quantity=1, UnitPrice = 15,   
                                                  Discount = 0, Order = order.Get(c) })  
           }  
        }  
    }  
};  
```  
  
### <a name="entitydelete"></a><span data-ttu-id="51bff-133">EntityDelete</span><span class="sxs-lookup"><span data-stu-id="51bff-133">EntityDelete</span></span>  
 <span data-ttu-id="51bff-134">Der Codeausschnitt unten stellt dar, wie ein vorhandener OrderDetail-Datensatz aus einem Auftrag gelöscht wird (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="51bff-134">The code snippet below shows how to delete an existing OrderDetail record in an Order (if it exists).</span></span>  
  
```  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();              
  
return new ObjectContextScope  
{  
    Variables = { orderDetails },  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // find the entitiy to be deleted (order detail for product 11 in order 10249)  
            new EntitySqlQuery<OrderDetail>  
            {  
                EntitySql = @"SELECT VALUE OrderDetail  
                                FROM NorthwindEntities.OrderDetails as OrderDetail  
                               WHERE OrderDetail.OrderID == 10249   
                                 AND OrderDetail.ProductID == 11",  
                Result = orderDetails  
            },  
  
            // if the order detail is found, delete it, otherwise, display a message  
            new If  
            {  
                Condition = new InArgument<bool>(c=>orderDetails.Get(c).Count() > 0),  
                Then = new Sequence  
                {   
                    Activities =   
                    {                                      
                        new EntityDelete<OrderDetail>  
                        {  
                            Entity = new InArgument<OrderDetail>(c =>   
                                              orderDetails.Get(c).First<OrderDetail>())  
                        },  
                    }  
                },                              
                Else = new WriteLine { Text = "Order Detail for Deleting not found" }                              
            }                                                  
        }  
    }  
};  
```  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="51bff-135">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="51bff-135">To use this sample</span></span>  
 <span data-ttu-id="51bff-136">Sie müssen die Datenbank `Northwind` in der lokalen SQL Server Express-Instanz vor dem Ausführen dieses Beispiels erstellen.</span><span class="sxs-lookup"><span data-stu-id="51bff-136">You must create the `Northwind` database in your local SQL server Express instance before running this sample.</span></span>  
  
#### <a name="to-set-up-the-northwind-database"></a><span data-ttu-id="51bff-137">So richten Sie die Datenbank Northwind ein</span><span class="sxs-lookup"><span data-stu-id="51bff-137">To set up the Northwind database</span></span>  
  
1.  <span data-ttu-id="51bff-138">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="51bff-138">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="51bff-139">Navigieren Sie in dem neuen Eingabeaufforderungsfenster zum Ordner "EntityActivities\CS".</span><span class="sxs-lookup"><span data-stu-id="51bff-139">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="51bff-140">Typ `setup.cmd` , und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="51bff-140">Type `setup.cmd` and press ENTER.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="51bff-141">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="51bff-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="51bff-142">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "EntityActivities.sln".</span><span class="sxs-lookup"><span data-stu-id="51bff-142">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EntityActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="51bff-143">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="51bff-143">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="51bff-144">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="51bff-144">To run the solution, press CTRL+F5.</span></span>  
  
 <span data-ttu-id="51bff-145">Nach Ausführen dieses Beispiels können Sie die Datenbank `Northwind` entfernen.</span><span class="sxs-lookup"><span data-stu-id="51bff-145">After running this sample, you may want to remove the `Northwind` database.</span></span>  
  
#### <a name="to-uninstall-the-northwind-database"></a><span data-ttu-id="51bff-146">So deinstallieren Sie die Datenbank Northwind</span><span class="sxs-lookup"><span data-stu-id="51bff-146">To uninstall the Northwind database</span></span>  
  
1.  <span data-ttu-id="51bff-147">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="51bff-147">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="51bff-148">Navigieren Sie in dem neuen Eingabeaufforderungsfenster zum Ordner "EntityActivities\CS".</span><span class="sxs-lookup"><span data-stu-id="51bff-148">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="51bff-149">Typ `cleanup.cmd` , und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="51bff-149">Type `cleanup.cmd` and press ENTER.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="51bff-150">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="51bff-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="51bff-151">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="51bff-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="51bff-152">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="51bff-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51bff-153">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="51bff-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`