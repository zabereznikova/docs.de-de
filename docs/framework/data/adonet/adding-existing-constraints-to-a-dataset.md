---
title: "Hinzufügen von vorhandenen Einschränkungen zu einem \"DataSet\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e457113eff471c620ccdbf78337d2013d7a62bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"
Die **füllen** Methode der **"DataAdapter"** füllt eine <xref:System.Data.DataSet> nur mit Tabellenspalten und Tabellenzeilen aus einer Datenquelle; jedoch Einschränkungen werden häufig festgelegt, indem die Datenquelle die **Ausfüllen** Methode fügt diese Schemainformationen nicht der **DataSet** standardmäßig. Zum Auffüllen einer **DataSet** mit vorhandenen primary Key-Einschränkungsinformationen aus einer Datenquelle können Sie entweder die **FillSchema** Methode der **"DataAdapter"**, oder legen Sie die **MissingSchemaAction** Eigenschaft von der **"DataAdapter"** auf **AddWithKey** vor dem Aufruf **füllen**. Dadurch wird sichergestellt, dass die Einschränkungen in der **DataSet** in der Datenquelle entsprechen. Foreign Key-Einschränkungsinformationen nicht enthalten ist, und muss entsprechend explizit erstellt werden [DataTable-Einschränkungen](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Schemainformationen Hinzufügen einer **DataSet** , bevor es mit Daten gefüllt wird sichergestellt, dass die primary Key-Einschränkungen enthalten sind die <xref:System.Data.DataTable> Objekte in der **DataSet**. Als Ergebnis bei weiteren Aufrufen zum Füllen der **DataSet** erfolgen, ist das primäre Schlüsselspalteninformationen wird verwendet, um die neue Zeilen aus der Datenquelle mit den aktuellen Zeilen in jeder entsprechen **DataTable**, und aktuellen Daten in die Tabellen mit Daten aus der Datenquelle überschrieben wird. Ohne die Schemainformationen werden die neuen Zeilen aus der Datenquelle angefügt, um die **DataSet**, wodurch doppelte Zeilen.  
  
> [!NOTE]
>  Wenn eine Spalte in einer Datenquelle als automatisch erhöht, identifiziert wird die **FillSchema** -Methode, oder die **ausfüllen** Methode mit einer **MissingSchemaAction** von  **AddWithKey**, erstellt eine **DataColumn** mit einem **AutoIncrement** -Eigenschaftensatz auf `true`. Allerdings müssen Sie legen die **AutoIncrementStep** und **AutoIncrementSeed** Werte selbst. Weitere Informationen zu Spalten automatisch erhöht, finden Sie unter [erstellen "AutoIncrement"-Spalten](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Mit **FillSchema** oder Einstellung der **MissingSchemaAction** auf **AddWithKey** erfordert zusätzliche Verarbeitungsschritte an der Datenquelle um Primärschlüsselspalte Informationen zu erhalten. Diese zusätzlichen Verarbeitungsschritte können zu einem Leistungsabfall führen. Wenn Sie die Primärschlüsselinformationen zur Entwurfszeit kennen, empfiehlt es sich, zum Erzielen einer optimalen Leistung die Primärschlüsselspalte(n) explizit in der richtigen Reihenfolge anzugeben. Informationen zum Primärschlüsselinformationen für eine Tabelle explizit festlegen, finden Sie unter [Primärschlüssel definieren](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 Das folgende Codebeispiel veranschaulicht das Hinzufügen von Schemainformationen zu einer **DataSet** mit **FillSchema**.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 Das folgende Codebeispiel veranschaulicht das Hinzufügen von Schemainformationen eine **DataSet** mithilfe der **MissingSchemaAction.AddWithKey** Eigenschaft von der **füllen** Methode.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>Umgang mit mehreren Resultsets  
 Wenn die **"DataAdapter"** trifft mehrere Resultsets aus der **SelectCommand**, erstellt jedoch mehrere Tabellen in der **DataSet**. Die Tabellen erhält einen standardmäßig nullbasierte Namen von **Tabelle** *N*, beginnend mit **Tabelle** anstelle von "Table0". Wenn ein Tabellenname als Argument übergeben wird die **FillSchema** -Methode, die Tabellen erhält einen nullbasierten Namen **TableName** *N*, beginnend mit **TableName** anstelle von "TableName0".  
  
> [!NOTE]
>  Wenn die **FillSchema** Methode der **OleDbDataAdapter** -Objekts aufgerufen wird, für einen Befehl, der mehrere Resultsets zurückgibt, wird nur die Schemainformationen aus dem ersten Resultset zurückgegeben. Wenn Schemainformationen für mehrere Resultsets Sätze unter Verwendung der **OleDbDataAdapter**, es wird empfohlen, Sie geben eine **MissingSchemaAction** von **AddWithKey** und die Schemainformationen zu erhalten, beim Aufrufen der **füllen** Methode.  
  
## <a name="see-also"></a>Siehe auch  
 ["DataAdapters" und "DataReaders"](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
