---
title: Entitätsaktivitäten
ms.date: 03/30/2017
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
ms.openlocfilehash: 96301c15b849749299e744a435068c3ec9be2e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519135"
---
# <a name="entity-activities"></a>Entitätsaktivitäten
In diesem Beispiel wird gezeigt, wie das ADO.NET Entity Framework mit Windows Workflow Foundation zu verwenden, um den Datenzugriff zu vereinfachen.  
  
 Das ADO.NET Entity Framework ermöglicht es Entwicklern, in Form von domänenspezifischen Objekten, Eigenschaften und Beziehungen, z. B. Kunden, Bestellungen, Bestelldetails und den Beziehungen zwischen diesen Entitäten, mit Daten zu arbeiten. Das ADO.NET Entity Framework ermöglicht dies, indem eine Abstraktionsebene bereitgestellt wird, die das Programmieren mit einem konzeptionellen Anwendungsmodell anstelle des direkten Programmierens mit einem Speicherschema ermöglicht. Weitere Informationen zu der ADO.NET Entity Framework finden Sie unter [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).  
  
## <a name="sample-details"></a>Beispieldetails  
 In diesem Beispiel wird die Datenbank `Northwind` verwendet; es umfasst Skripts zum Erstellen und Entfernen der Datenbank `Northwind` (Setup.cmd und Cleanup.cmd). Die Projekte in diesem Beispiel umfassen ein Entity Data Model auf Grundlage der Datenbank `Northwind`. Sie finden das Modell, indem Sie die Datei `Northwind.edmx` öffnen, die im Projekt enthalten ist. Dies ist das Modell, das die Form der Objekte definiert, auf die mit dem ADO.NET Entity Framework zugegriffen werden kann.  
  
 Die folgenden Aktivitäten sind in diesem Beispiel enthalten:  
  
-   `EntitySQLQuery`: Mit der `EntitySQLQuery`-Aktivität können Sie Objekte aus der Datenbank auf Grundlage einer Entity SQL-Abfragezeichenfolge abrufen. Entity SQL ist eine speicherunabhängige Sprache, die SQL ähnlich ist und es Ihnen, Abfragen auf Grundlage des konzeptionellen Modells und der Entitäten anzugeben, die ein Teil des Modells oder der Domäne sind. Weitere Informationen über Entity SQL-Sprache finden Sie unter [Entity SQL-Sprache](http://go.microsoft.com/fwlink/?LinkId=165646).  
  
-   `EntityLinqQuery`: Mit dieser Aktivität können Sie Objekte aus der Datenbank auf Grundlage einer LINQ-Abfrage oder eines Prädikats abrufen.  
  
-   `EntityAdd`: Mit der `EntityAdd`-Aktivität können Sie der Datenbank eine Entität oder eine Auflistung von Entitäten hinzufügen.  
  
-   `EntityDelete`: Mit der `EntityDelete`-Aktivität können Sie eine Entität oder eine Auflistung von Entitäten aus der Datenbank löschen.  
  
-   `ObjectContextScope`: Die zuvor erwähnten Aktivitäten können nur Instanz innerhalb einer enthaltenden `ObjectContextScope`-Aktivitätsinstanz verwendet werden. Die `ObjectContextScope`-Aktivität stellt die Verbindung zur Datenbank her. Sie erfordert eine Verbindungszeichenfolge (die entweder übergeben oder mit einer Konfigurationsdateieinstellung abgerufen wird). Die `ObjectContextScope`-Aktivität erleichtert das Ausführen einer Gruppe von zusammengehörigen Vorgängen in Entitäten. Da dieser Bereich eine aktive Verbindung aufrechterhält, handelt es sich um einen nicht persistenten Bereich. Wenn die `ObjectContextScope`-Aktivität beendet wird, werden außerdem alle Änderungen, die an Objekten vorgenommen wurden, die mit Entitätsaktivitäten innerhalb dieses Bereichs abgerufen wurden, automatisch in die Datenbank übernommen, und es ist keine explizite oder nachfolgende Aktion erforderlich, um Objekte zurück in die Datenbank zu speichern.  
  
## <a name="using-the-entity-activities"></a>Verwenden der Entitätsaktivitäten  
 Die folgenden Codeausschnitte veranschaulichen, wie die in diesem Beispiel dargestellten Entitätsaktivitäten verwendet werden.  
  
### <a name="entitysql"></a>EntitySQL  
 Der Codeausschnitt unten stellt dar, wie alle nach Namen sortierten Kunden in London abgefragt werden und wie die Liste der Kunden durchlaufen wird.  
  
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
  
### <a name="entitylinqquery"></a>EntityLinqQuery  
 Der Codeausschnitt unten stellt dar, wie alle Kunden in London abgefragt werden und wie die resultierende Liste der Kunden durchlaufen wird.  
  
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
  
### <a name="entityadd"></a>EntityAdd  
 Der Codeausschnitt unten stellt dar, wie einem vorhandenen Auftrag ein OrderDetail-Datensatz hinzugefügt wird.  
  
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
  
### <a name="entitydelete"></a>EntityDelete  
 Der Codeausschnitt unten stellt dar, wie ein vorhandener OrderDetail-Datensatz aus einem Auftrag gelöscht wird (falls vorhanden).  
  
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
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
 Sie müssen die Datenbank `Northwind` in der lokalen SQL Server Express-Instanz vor dem Ausführen dieses Beispiels erstellen.  
  
#### <a name="to-set-up-the-northwind-database"></a>So richten Sie die Datenbank Northwind ein  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Navigieren Sie in dem neuen Eingabeaufforderungsfenster zum Ordner "EntityActivities\CS".  
  
3.  Typ `setup.cmd` , und drücken Sie die EINGABETASTE.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "EntityActivities.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
 Nach Ausführen dieses Beispiels können Sie die Datenbank `Northwind` entfernen.  
  
#### <a name="to-uninstall-the-northwind-database"></a>So deinstallieren Sie die Datenbank Northwind  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Navigieren Sie in dem neuen Eingabeaufforderungsfenster zum Ordner "EntityActivities\CS".  
  
3.  Typ `cleanup.cmd` , und drücken Sie die EINGABETASTE.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`