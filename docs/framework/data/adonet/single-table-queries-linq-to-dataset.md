---
title: "Abfragen f&#252;r eine einzelne Tabelle (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Abfragen f&#252;r eine einzelne Tabelle (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] fragt Arbeit an Datenquellen ab, die die <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle oder die <xref:System.Query.IQueryable%601>\-Schnittstelle implementieren.  Die <xref:System.Data.DataTable>\-Klasse implementiert keine dieser beiden Schnittstellen, sodass Sie die <xref:System.Data.DataTableExtensions.AsEnumerable%2A>\-Methode aufrufen müssen, wenn Sie die <xref:System.Data.DataTable> als Quelle in die `From`\-Klausel einer [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Abfrage aufnehmen möchten.  
  
 Das folgende Beispiel ruft alle Onlinebestellungen aus der Tabelle \<legacyBold\>SalesOrderHeader\<\/legacyBold\> ab und zeigt in der Konsole die Auftrags\-ID, das Auftragsdatum und die Auftragsnummer an.  
  
 [!code-csharp[dp linq to dataset examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]
 [!code-vb[dp linq to dataset examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]  
  
 Die Abfrage der lokalen Variable wird mit einem Abfrageausdruck initialisiert, der eine oder mehrere Informationsquellen abfragt, indem ein oder mehrere Abfrageoperatoren angewendet werden. Bei diesen Operatoren handelt es sich entweder um Standardabfrageoperatoren oder, im Fall von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], um Operatoren, die für die <xref:System.Data.DataSet>\-Klasse spezifisch sind.  Der Abfrageausdruck im vorherigen Beispiel verwendet zwei der Standardabfrageoperatoren: `Where` und `Select`.  
  
 Die `Where`\-Klausel filtert die Reihenfolge auf der Basis einer Bedingung. In diesem Fall lautet die Bedingung, dass für `OnlineOrderFlag` der Wert `true` gilt.  Der `Select`\-Operator ordnet ein aufzählbares Objekt zu, das die an den Operator übergebenen Argumente erfasst, und gibt das Objekt zurück.  Im Beispiel oben wird ein anonymer Typ mit drei Eigenschaften erstellt: `SalesOrderID`, `OrderDate` und `SalesOrderNumber`.  Als Werte für diese drei Eigenschaften werden die Werte der Spalten `SalesOrderID`, `OrderDate` und `SalesOrderNumber` aus der `SalesOrderHeader`\-Tabelle verwendet.  
  
 Die `foreach`\-Schleife zählt dann das von `Select` zurückgegebene aufzählbare Objekt auf und gibt die Abfrageergebnisse aus.  Da es sich bei der Abfrage um eine <xref:System.Linq.Enumerable>\-Abfrage handelt, die die <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle implementiert, wird die Auswertung der Abfrage so lange verzögert, bis die Abfragevariable mit der `foreach`\-Schleife durchlaufen wird.  Durch die verzögerte Abfrageauswertung können die Abfragen als Werte erhalten werden, die mehrere Male ausgewertet werden und dabei potenziell jedes Mal ein anderes Ergebnis erbringen können.  
  
 Die <xref:System.Data.DataRowExtensions.Field%2A>\-Methode bietet Zugriff auf die Spaltenwerte einer <xref:System.Data.DataRow>, und das <xref:System.Data.DataRowExtensions.SetField%2A> \(im Beispiel oben nicht dargestellt\) gibt Spaltenwerte in einer <xref:System.Data.DataRow> an.  Sowohl die <xref:System.Data.DataRowExtensions.Field%2A>\-Methode als auch die <xref:System.Data.DataRowExtensions.SetField%2A>\-Methode kümmern sich um Typen, die NULL zulassen, sodass die explizite Prüfung auf NULL\-Werte entfallen kann.  Beide Methoden sind darüber hinaus generische Methoden. Der Rückgabetyp muss also nicht umgewandelt werden.  Sie könnten den schon vorhandenen Spaltenaccessor in <xref:System.Data.DataRow> \(z. B. `o["OrderDate"]`\) verwenden, müssten dann aber das Rückgabeobjekt in den entsprechenden Typ umwandeln.  Wenn die Spalte auf NULL gesetzt werden kann, müssen Sie mit der <xref:System.Data.DataRow.IsNull%2A>\-Methode prüfen, ob der Wert NULL ist.  Weitere Informationen finden Sie unter [Generische Methoden 'Field' und 'SetField'](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md).  
  
 Beachten Sie, dass der im generischen `T`\-Parameter der <xref:System.Data.DataRowExtensions.Field%2A>\-Methode und der <xref:System.Data.DataRowExtensions.SetField%2A>\-Methode angegebene Datentyp mit dem Typ des zugrunde liegenden Werts übereinstimmen muss. Anderenfalls wird eine <xref:System.InvalidCastException> ausgelöst.  Der angegebene Spaltenname muss außerdem mit dem Namen einer <xref:System.Data.DataSet>\-Spalte übereinstimmen. Wenn dies nicht der Fall ist, wird eine <xref:System.ArgumentException> ausgelöst.  Die Auslösung der Ausnahme erfolgt in beiden Fällen bei der Datenenumeration zur Laufzeit, wenn die Abfrage ausgeführt wird.  
  
## Siehe auch  
 [Abfragen für mehrere Tabellen](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)   
 [Abfragen von typisierten DataSets](../../../../docs/framework/data/adonet/querying-typed-datasets.md)   
 [Generische Methoden 'Field' und 'SetField'](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)