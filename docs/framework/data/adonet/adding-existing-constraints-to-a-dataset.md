---
title: "Hinzuf&#252;gen vorhandener Einschr&#228;nkungen zu einem DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Hinzuf&#252;gen vorhandener Einschr&#228;nkungen zu einem DataSet
Die **Fill**\-Methode des **DataAdapter**\-Objekts füllt ein <xref:System.Data.DataSet> nur mit den Tabellenspalten und Tabellenzeilen aus einer Datenquelle. Einschränkungen werden zwar häufig von der Datenquelle festgelegt, die **Fill**\-Methode fügt diese Schemainformationen dem **DataSet** jedoch nicht standardmäßig hinzu.  Wenn Sie die Informationen zu vorhandenen Primärschlüsseleinschränkungen aus einer Datenquelle in ein **DataSet** übernehmen möchten, können Sie vor dem Aufrufen der **Fill**\-Methode entweder die **FillSchema**\-Methode des **DataAdapter**\-Objekts aufrufen oder die **MissingSchemaAction**\-Eigenschaft des **DataAdapter**\-Objekts auf **AddWithKey** festlegen.  Dadurch wird sichergestellt, dass die Primärschlüsseleinschränkungen im **DataSet** denen in der Datenquelle entsprechen.  Informationen zu Fremdschlüsseleinschränkungen sind nicht enthalten und müssen explizit erstellt werden. Dies wird unter ['DataTable'\-Einschränkungen](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md) veranschaulicht.  
  
 Wenn Sie einem **DataSet** vor dem Füllen mit Daten Schemainformationen hinzufügen, wird sichergestellt, dass Primärschlüsseleinschränkungen in den <xref:System.Data.DataTable>\-Objekten des **DataSet** enthalten sind.  Folglich werden mit den Informationen zur Primärschlüsselspalte bei weiteren Aufrufen zum Füllen des **DataSet** neue Zeilen aus der Datenquelle mit den aktuellen Zeilen in jeder **DataTable** abgestimmt. Die aktuellen Daten in den Tabellen werden mit Daten aus der Datenquelle überschrieben.  Ohne die Schemainformationen werden die neuen Zeilen aus der Datenquelle dem **DataSet** angehängt. Das Ergebnis sind Duplikatzeilen.  
  
> [!NOTE]
>  Wenn in einer Datenquelle eine Spalte mit automatischer Erhöhung ermittelt wird, erstellt die **FillSchema**\-Methode bzw. die **Fill**\-Methode, deren **MissingSchemaAction**\-Eigenschaft den Wert **AddWithKey** aufweist, eine **DataColumn**, deren **AutoIncrement**\-Eigenschaft auf `true` festgelegt ist.  Die Werte für **AutoIncrementStep** und **AutoIncrementSeed** müssen Sie jedoch selbst festlegen.  Weitere Informationen zu Spalten, deren Werte sich automatisch erhöhen, finden Sie unter [Erstellen von AutoIncrement\-Spalten](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Wenn Sie die **FillSchema**\-Methode verwenden oder **MissingSchemaAction** auf **AddWithKey** festlegen, sind zum Ermitteln von Informationen zur Primärschlüsselspalte zusätzliche Verarbeitungsschritte an der Datenquelle erforderlich.  Diese zusätzlichen Verarbeitungsschritte können zu einem Leistungsabfall führen.  Wenn Sie die Primärschlüsselinformationen zur Entwurfszeit kennen, empfiehlt es sich, zum Erzielen einer optimalen Leistung die Primärschlüsselspalte\(n\) explizit in der richtigen Reihenfolge anzugeben.  Informationen zum expliziten Festlegen von Primärschlüsselinformationen für eine Tabelle finden Sie unter [Definieren von Primärschlüsseln](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 Im folgenden Codebeispiel wird dargestellt, wie Sie einem **DataSet** mit der **FillSchema**\-Methode Schemainformationen hinzufügen.  
  
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
  
 Im folgenden Codebeispiel wird dargestellt, wie Sie einem **DataSet** mit der **MissingSchemaAction.AddWithKey**\-Eigenschaft der **Fill**\-Methode Schemainformationen hinzufügen.  
  
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
  
## Umgang mit mehreren Resultsets  
 Wenn das **DataAdapter**\-Objekt feststellt, dass mehrere Resultsets von der **SelectCommand**\-Eigenschaft zurückgegeben werden, werden mehrere Tabellen im **DataSet** erstellt.  Diesen Tabellen werden standardmäßig nullbasierte Namen nach dem Schema **Table** *N* zugewiesen \(beginnend mit **Table** für Tabelle0\), die jeweils um eins erhöht werden.  Wenn der Tabellenname als Argument an die **FillSchema**\-Methode übergeben wird, erhalten die Tabellen standardmäßig nullbasierte Namen nach dem Schema **TableName** *N* \(beginnend mit **TableName** für Tabellenname0\), die jeweils um eins erhöht werden.  
  
> [!NOTE]
>  Wenn die **FillSchema**\-Methode des **OleDbDataAdapter**\-Objekts für einen Befehl aufgerufen wird, der mehrere Resultsets zurückgibt, werden nur die Schemainformationen aus dem ersten Resultset zurückgegeben.  Wenn Schemainformationen für mehrere Resultsets mit dem **OleDbDataAdapter** zurückgegeben werden, empfiehlt es sich, eine **MissingSchemaAction** von **AddWithKey** anzugeben und die Schemainformationen beim Aufruf der **Fill**\-Methode abzurufen.  
  
## Siehe auch  
 [DataAdapter und DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)