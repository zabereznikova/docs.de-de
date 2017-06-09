---
title: "Erstellen einer DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Erstellen einer DataTable
Eine <xref:System.Data.DataTable>, die eine Tabelle mit relationalen Daten im Speicher darstellt, kann erstellt und unabhängig verwendet werden. Oder sie kann von anderen .NET Framework\-Objekten, am häufigsten als Member von einem <xref:System.Data.DataSet>, verwendet werden.  
  
 Ein **DataTable**\-Objekt kann mit dem entsprechenden **DataTable**\-Konstruktor erstellt werden.  Es kann dem **DataSet** mit der **Add**\-Methode hinzugefügt werden, um es der **Tables**\-Auflistung des **DataTable**\-Objekts hinzuzufügen.  
  
 **DataTable**\-Objekte können in einem **DataSet** mithilfe der **Fill**\-Methode oder der **FillSchema**\-Methode des **DataAdapter**\-Objekts erstellt werden. Sie können auch aus einem vordefinierten oder hergeleitetem XML\-Schema mithilfe der Methoden **ReadXml**, **ReadXmlSchema** oder **InferXmlSchema** vom **DataSet** erstellt werden.  Beachten Sie Folgendes: Nachdem eine **DataTable** als ein Member der **Tables**\-Auflistung von einem **DataSet** hinzugefügt wurde, kann dieses nicht mehr zu der Auflistung von Tabellen von einem anderen **DataSet** hinzugefügt werden.  
  
 Wenn zuerst eine **DataTable** erstellt wird, verfügt sie nicht über ein Schema \(d. h. eine Struktur\).  Zum Definieren des Schemas einer Tabelle müssen <xref:System.Data.DataColumn>\-Objekte erstellt werden und diese der **Columns**\-Auflistung der Tabelle hinzugefügt werden.  Es kann auch eine Primärschlüsselspalte für die Tabelle definiert werden, und **Constraint**\-Objekte erstellt und diese der **Constraints**\-Auflistung der Tabelle hinzugefügt werden.  Nachdem das Schema für eine **DataTable** definiert wurde, können der Tabelle Zeilen von Daten hinzugefügt werden, indem der **Rows**\-Auflistung der Tabelle **DataRow**\-Objekte hinzugefügt werden.  
  
 Es ist nicht erforderlich, dass ein Wert für die <xref:System.Data.DataTable.TableName%2A>\-Eigenschaft bereitgestellt wird, wenn Sie eine **DataTable** erstellen. Die Eigenschaft kann zu einem späteren Zeitpunkt angegeben werden oder leer bleiben.  Wenn Sie jedoch einem **DataSet** eine Tabelle ohne einen **TableName**\-Wert hinzufügen, erhält die Tabelle den inkrementellen Standardnamen "Table*N*", beginnend mit "Table" für Table0.  
  
> [!NOTE]
>  Es wird davon abgeraten, die Benennungskonvention "Table*N*" zu verwenden, wenn Sie einen **TableName**\-Wert bereitstellen, da der angegebene Name u. U. einen Konflikt mit einem bereits vorhandenen Standardtabellennamen im **DataSet** verursacht.  Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 Im folgenden Beispiel wird eine Instanz des **DataTable**\-Objekts erstellt und dieser der Name "Customers" zugewiesen.  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 Im folgenden Beispiel wird eine Instanz einer **DataTable** erstellt, indem diese der **Tables**\-Auflistung von einem **DataSet** hinzugefügt wird.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## Siehe auch  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataTableCollection>   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Auffüllen eines "DataSets" durch einen "DataAdapter"](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)