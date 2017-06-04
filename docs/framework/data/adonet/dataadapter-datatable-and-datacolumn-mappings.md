---
title: "DataAdapter DataTable- und DataColumn-Zuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DataAdapter DataTable- und DataColumn-Zuordnungen
Ein **DataAdapter** enthält eine Auflistung von 0 \(null\) oder mehr <xref:System.Data.Common.DataTableMapping>\-Objekten in der zugehörigen **TableMappings**\-Eigenschaft.  Eine **DataTableMapping** stellt eine Masterzuordnung zwischen den nach einer Abfrage einer Datenquelle zurückgegebenen Daten und einer <xref:System.Data.DataTable> bereit.  Der **DataTableMapping**\-Name kann anstelle des **DataTable**\-Namens an die **Fill**\-Methode des **DataAdapter** übergeben werden.  Im folgenden Beispiel wird eine **DataTableMapping** mit dem Namen **AuthorsMapping** für die **Authors**\-Tabelle erstellt.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Mithilfe von **DataTableMapping** können Sie in einer **DataTable** andere Spaltennamen als in der Datenbank verwenden.  Der **DataAdapter** gleicht beim Update der Tabelle mithilfe der Zuordnung die Spalten miteinander ab.  
  
 Wenn Sie beim Aufruf der **Fill**\-Methode oder der **Update**\-Methode des **DataAdapter** keinen **TableName** oder **DataTableMapping**\-Namen angeben, sucht der **DataAdapter** nach einer **DataTableMapping** mit dem Namen "Table".  Wenn **DataTableMapping** nicht vorhanden ist, lautet der **TableName** von **DataTable** "Table".  Sie können eine Standard\-**DataTableMapping** angeben, indem Sie eine **DataTableMapping** mit dem Namen "Table" erstellen.  
  
 Im folgenden Beispiel wird eine **DataTableMapping** \(aus dem <xref:System.Data.Common>\-Namespace\) erstellt und zur Standardzuordnung für den angegebenen **DataAdapter** erklärt, indem sie als "Table" benannt wird.  Das Beispiel ordnet anschließend die Spalten in der ersten Tabelle des Abfrageergebnisses \(die **Customers**\-Tabelle der **Northwind**\-Datenbank\) einer Gruppe von benutzerfreundlicheren Namen in der **Northwind Customers**\-Tabelle im <xref:System.Data.DataSet> zu.  Für Spalten, die nicht zugeordnet werden, wird der Name der Spalte in der Datenquelle verwendet.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 In komplexeren Situationen können Sie mit demselben **DataAdapter** das Laden verschiedener Tabellen mit verschiedenen Zuordnungen unterstützen.  Hierfür fügen Sie einfach weitere **DataTableMapping**\-Objekte hinzu.  
  
 Wenn der **Fill**\-Methode eine Instanz des **DataSet** und ein **DataTableMapping**\-Name übergeben wird, wird dieser verwendet, sofern eine Zuordnung mit diesem Namen vorhanden ist. Andernfalls wird eine **DataTable** mit diesem Namen verwendet.  
  
 Im folgenden Beispiel werden eine **DataTableMapping** mit dem Namen **Customers** und die **DataTable** mit dem Namen **BizTalkSchema** erstellt.  Das Beispiel ordnet dann die von der SELECT\-Anweisung zurückgegebenen Zeilen der **BizTalkSchema**\-**DataTable** zu.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  Wenn für eine Spaltenzuordnung kein Quellspaltenname bzw. für eine Tabellenzuordnung kein Quelltabellenname angegeben wird, werden automatisch Standardnamen generiert.  Fehlt der Quellspaltenname einer Spaltenzuordnung, so erhält die Spaltenzuordnung den Standardnamen **SourceColumn** *N,* beginnend mit **SourceColumn1**, der jeweils um eins erhöht wird.  Fehlt der Quelltabellenname einer Tabellenzuordnung, so erhält die Tabellenzuordnung den Standardnamen **SourceTable** *N,* beginnend mit **SourceTable1**, der jeweils um eins erhöht wird.  
  
> [!NOTE]
>  Es wird davon abgeraten, die Benennungskonvention **SourceColumn** *N* für eine Spaltenzuordnung oder **SourceTable** *N* für eine Tabellenzuordnung zu verwenden, da dieser Name u. U. einen Konflikt mit einem bereits vorhandenen Standardspaltennamen in der **ColumnMappingCollection** oder mit einem bereits vorhandenen Standardtabellennamen in der **DataTableMappingCollection** verursacht.  Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
## Umgang mit mehreren Resultsets  
 Wenn mit **SelectCommand** mehrere Tabellen zurückgegeben werden, werden mit der **Fill**\-Methode automatisch Tabellennamen mit inkrementellen Werten für die Tabellen im **DataSet** generiert. Der angegebene Tabellenname kommt zuerst, und die folgenden Tabellen werden nach dem Schema **TableName** *N* benannt, wobei mit **TableName1** begonnen wird.  Mit Tabellenzuordnungen können Sie den automatisch generierten Tabellennamen einem Namen zuordnen, der für die Tabelle im **DataSet** angegeben werden soll.  Rufen Sie beispielsweise für eine **SelectCommand**\-Eigenschaft, die die beiden Tabellen **Customers** und **Orders** zurückgibt, die **Fill**\-Methode folgendermaßen auf.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Im **DataSet** werden zwei Tabellen erstellt: **Customers** und **Customers1**.  Mit Tabellenzuordnungen können Sie sicherstellen, dass die zweite Tabelle den Namen **Orders** und nicht **Customers1** erhält.  Zu diesem Zweck ordnen Sie der Quelltabelle **Customers1** die **DataSet**\-Tabelle **Orders** zu, wie es im folgenden Beispiel gezeigt wird.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## Siehe auch  
 [DataAdapter und DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)