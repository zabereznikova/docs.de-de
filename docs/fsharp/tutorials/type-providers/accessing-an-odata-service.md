---
title: 'Exemplarische Vorgehensweise: Zugreifen auf einen OData-Dienst mithilfe von Typanbietern (F#)'
description: Erfahren Sie, wie die F#-ODataService-Typanbieter in f# 3.0 zu verwenden, um Clienttypen für einen OData-Dienst zu generieren und -Datenfeeds, die den Dienst abzufragen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0adae84c-b0fa-455f-994b-274ecdc6df30
ms.openlocfilehash: 750407c36a989cece30c0c0654ff905c8eee3b33
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-an-odata-service-by-using-type-providers"></a>Exemplarische Vorgehensweise: Zugreifen auf einen OData-Dienst mithilfe von Typanbietern

> [!NOTE]
Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.  Unter [FSharp.Data](https://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.

> [!NOTE]
Die API-Referenz Links gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

OData, oder Open Data Protocol, ist ein Protokoll zur Datenübertragung im Internet. Viele Datenanbieter bieten Zugriff auf ihre Daten, indem sie einen OData-Webdienst veröffentlichen. Mithilfe der Datentypen, die vom `ODataService`-Typanbieter automatisch generiert werden, können Sie in F# 3.0 auf Daten in jeder OData-Quelle zugreifen. Weitere Informationen zu OData finden Sie unter https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62.

In dieser exemplarischen Vorgehensweise wird erläutert, wie der ODataService-Typanbieter in F# verwendet wird, um Clienttypen für einen OData-Dienst zu generieren und die vom Dienst bereitgestellten Datenfeeds abzufragen.

Die exemplarische Vorgehensweise veranschaulicht die folgenden Aufgaben, die Sie in der angegebenen Reihenfolge ausführen müssen, um die exemplarische Vorgehensweise erfolgreich abzuschließen:


- Konfigurieren eines Clientprojekts für einen OData-Dienst
<br />

- Zugreifen auf OData-Typen
<br />

- Abfragen eines OData-Diensts
<br />

- Überprüfen der OData-Anforderungen
<br />


## <a name="configuring-a-client-project-for-an-odata-service"></a>Konfigurieren eines Clientprojekts für einen OData-Dienst
In diesem Schritt erstellen Sie ein Projekt, das einen OData-Typanbieter verwendet.


#### <a name="to-configure-a-client-project-for-an-odata-service"></a>So konfigurieren Sie ein Clientprojekt für einen OData-Dienst

- Öffnen Sie ein F#-Konsolenanwendungsprojekt, und fügen Sie anschließend einen Verweis auf die `System.Data.Services.Client` Frameworkassembly hinzu.
<br />

- Klicken Sie unter `Extensions`, fügen einen Verweis auf die `FSharp.Data.TypeProviders` Assembly.
<br />

## <a name="accessing-odata-types"></a>Zugreifen auf OData-Typen
In diesem Schritt erstellen Sie einen Typanbieter, der Zugriff auf die Typen und Daten eines OData-Diensts bietet.


#### <a name="to-access-odata-types"></a>So greifen Sie auf OData-Typen zu

- Öffnen Sie im Code-Editor eine F#-Quelldatei, und geben Sie den folgenden Code ein.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type Northwind = ODataService<"https://services.odata.org/Northwind/Northwind.svc/">

let db = Northwind.GetDataContext()
let fullContext = Northwind.ServiceTypes.NorthwindEntities()
```

In diesem Beispiel haben Sie den F#-Typanbieter aufgerufen und ihn angewiesen, basierend auf dem angegebenen OData-URI einen Satz von Typen zu erstellen. Es sind zwei Objekte verfügbar, die Informationen zu den Daten enthalten. Das erste ist ein vereinfachter Datenkontext (`db` im Beispiel). Dieses Objekt enthält nur die Datentypen, die mit der Datenbank in Beziehung stehen, einschließlich der Typen für Tabellen und Feeds. Das andere Objekt (`fullContext` in diesem Beispiel) ist eine Instanz von `System.Data.Linq.DataContext` und enthält viele zusätzliche Eigenschaften, Methoden und Ereignisse.
<br />


## <a name="querying-an-odata-service"></a>Abfragen eines OData-Diensts
In diesem Schritt verwenden Sie F#-Abfrageausdrücke, um den OData-Dienst abzufragen.


#### <a name="to-query-an-odata-service"></a>So fragen Sie einen OData-Dienst ab

1. Nachdem Sie den Typanbieter eingerichtet haben, können Sie einen OData-Dienst abfragen.
<br />  OData unterstützt nur eine Teilmenge der verfügbaren Abfrageoperationen. Im Folgenden werden die unterstützten Operationen und die zugehörigen Schlüsselwörter aufgeführt:
<br />
  - Projektion (`select`)
<br />

  - Filtern (`where`, unter Verwendung von Zeichenfolgen und Datumsoperationen)
<br />

  - Paging (`skip`, `take`)
<br />

  - Sortierung (`orderBy`, `thenBy`)
<br />

  - `AddQueryOption` und `Expand`, die OData-spezifische Vorgänge sind
<br />

  Weitere Informationen finden Sie unter [Überlegungen zu LINQ &#40;WCF Data Services&#41;](https://msdn.microsoft.com/library/ee622463.aspx).
<br />  Wenn Sie alle Einträge aus einem Feed oder einer Tabelle abrufen möchten, verwenden Sie die einfachste Form des Abfrageausdrucks, wie im folgenden Code gezeigt:
<br />

```fsharp
query {
  for customer in db.Customers do
  select customer
} |> Seq.iter (fun customer ->
                  printfn "ID: %s\nCompany: %s" customer.CustomerID customer.CompanyName
                  printfn "Contact: %s\nAddress: %s" customer.ContactName customer.Address
                  printfn "         %s, %s %s" customer.City customer.Region customer.PostalCode
                  printfn "%s\n" customer.Phone)
```

2. Geben Sie die gewünschten Felder oder Spalten in einem Tupel nach dem select-Schlüsselwort an.
<br />

```fsharp
  query { 
    for cat in db.Categories do
    select (cat.CategoryID, cat.CategoryName, cat.Description)
  } |> Seq.iter (fun (id, name, description) ->
                    printfn "ID: %d\nCategory: %s\nDescription: %s\n" id name description)
```

3. Formulieren Sie Bedingungen mit einer `where`-Klausel.
<br />

```fsharp
query {
  for employee in db.Employees do
  where (employee.EmployeeID = 9)
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

4. Formulieren Sie eine Teilzeichenfolgen-Bedingung mit der `System.String.Contains(System.String)`-Methode. Die folgende Abfrage gibt alle Produkte mit der Zeichenfolge „Chef“ im Namen zurück. Beachten Sie auch die Verwendung von `System.Nullable<'T>.GetValueOrDefault()`. Der Wert von `UnitPrice` kann NULL sein. Sie müssen den Wert also entweder über die `Value`-Eigenschaft abrufen oder den Aufruf `System.Nullable<'T>.GetValueOrDefault()` verwenden.
<br />

```fsharp
query { 
  for product in db.Products do
  where (product.ProductName.Contains("Chef"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

5. Verwenden Sie die `System.String.EndsWith(System.String)`-Methode, um anzugeben, dass eine Zeichenfolge mit einer bestimmten Teilzeichenfolge endet.
<br />

```fsharp
query {
  for product in db.Products do
  where (product.ProductName.EndsWith("u"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

6. Kombinieren Sie Bedingungen in einer where-Klausel mit dem `&&`-Operator.
<br />

```fsharp
// Open this module to use the nullable operators ?> and ?<.
open Microsoft.FSharp.Linq.NullableOperators

let salesIn1997 = query { 
  for sales in db.Category_Sales_for_1997 do
  where (sales.CategorySales ?> 50000.00M && sales.CategorySales ?< 60000.0M)
  select sales }

salesIn1997
|> Seq.iter (fun sales ->
                printfn "Category: %s Sales: %M" sales.CategoryName (sales.CategorySales.GetValueOrDefault()))
```

Die Operatoren `?>` und `?<` sind Operatoren, die NULL-Werte zulassen. Ihnen steht ein vollständiger Satz an Gleichheits- und Vergleichsoperatoren zur Verfügung, die NULL-Werte zulassen. Weitere Informationen finden Sie unter [Linq.NullableOperators-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).
<br />

7. Verwenden Sie den `sortBy`-Abfrageoperator, um eine Reihenfolge anzugeben, und `thenBy`, um eine weitere Ebene für die Reihenfolge hinzuzufügen. Beachten Sie auch die Verwendung des Tupels im select-Teil der Abfrage. Dies bedeutet, dass die Abfrage ein Tupel als Elementtyp verwendet.
<br />

```fsharp
printfn "Freight for some orders: "

query { 
  for order in db.Orders do
  sortBy (order.OrderDate.Value)
  thenBy (order.OrderID)
  select (order.OrderDate, order.OrderID, order.Customer.CompanyName)
} |> Seq.iter (fun (orderDate, orderID, company) ->
                  printfn "OrderDate: %s" (orderDate.GetValueOrDefault().ToString())
                  printfn "OrderID: %d Company: %s\n" orderID company)
```

8. Ignorieren Sie eine Anzahl von Datensätzen mit dem skip-Operator, und verwenden Sie den take-Operator, um anzugeben, wie viele Datensätze zurückgegeben werden sollen. Auf diese Weise können Sie eine seitenweise Darstellung für Datenfeeds implementieren.
<br />

```fsharp
printfn "Get the first page of 2 employees."

query { 
  for employee in db.Employees do
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID)) 

printfn "Get the next 2 employees."

query { 
  for employee in db.Employees do
  skip 2
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

## <a name="verifying-the-odata-request"></a>Überprüfen der OData-Anforderung
Jede OData-Abfrage wird in einen bestimmten OData-Anforderungs-URI übersetzt. Sie können den URI überprüfen, z. B. zu Debuggingzwecken, indem Sie dem `SendingRequest`-Ereignis des vollständigen Datenkontextobjekts einen Ereignishandler hinzufügen.


#### <a name="to-verify-the-odata-request"></a>So überprüfen Sie eine OData-Anforderung

- Um den OData-Anforderungs-URI zu überprüfen, verwenden Sie folgenden Code:
<br />

```fsharp
// The DataContext property returns the full data context.
db.DataContext.SendingRequest.Add (fun eventArgs -> printfn "Requesting %A" eventArgs.Request.RequestUri)
```

Die Ausgabe des vorherigen Codes lautet:
<br />`requesting https://services.odata.org/Northwind/Northwind.svc/Orders()?$orderby=ShippedDate&amp;$select=OrderID,ShippedDate`


## <a name="see-also"></a>Siehe auch
[Abfrageausdrücke](../../language-reference/query-expressions.md)

[Überlegungen zu LINQ (WCF Data Services)](https://msdn.microsoft.com/library/ee622463.aspx)

[ODataService-Typanbieter (f#)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/odataservice-type-provider-%5bfsharp%5d)
