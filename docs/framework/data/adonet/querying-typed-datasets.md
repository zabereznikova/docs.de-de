---
title: "Abfragen von typisierten DataSets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Abfragen von typisierten DataSets
Wenn zum Zeitpunkt der Anwendungskonzeptionierung bereits das <xref:System.Data.DataSet>\-Schema bekannt ist, wird empfohlen, bei der Benutzung von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] mit einem typisierten <xref:System.Data.DataSet> zu arbeiten.  Ein typisiertes <xref:System.Data.DataSet> ist eine Klasse, die von einem <xref:System.Data.DataSet> abgeleitet ist.  Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines <xref:System.Data.DataSet>.  Darüber hinaus stellt ein typisiertes <xref:System.Data.DataSet> stark typisierte Methoden, Ereignisse und Eigenschaften bereit.  Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen.  Dadurch werden Abfragen einfacher und lesbarer.  Weitere Informationen finden Sie unter [Typisierte 'DataSets'](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] unterstützt auch das Abfragen von Daten in einem typisierten <xref:System.Data.DataSet>.  Bei Verwendung eines typisierten <xref:System.Data.DataSet> brauchen Sie nicht auf die generische Methode <xref:System.Data.DataRowExtensions.Field%2A> bzw. <xref:System.Data.DataRowExtensions.SetField%2A> zurückgreifen, um auf Spaltendaten zugreifen zu können.  Eigenschaftennamen sind zum Zeitpunkt der Kompilierung verfügbar, weil die Typinformationen im <xref:System.Data.DataSet> enthalten sind. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] bietet Zugriff auf Spaltenwerte als korrektem Typ, sodass Typenkonfliktfehler bereits bei der Kompilierung und nicht erst zur Laufzeit erkannt werden.  
  
 Bevor Sie mit der Abfrage eines typisierten <xref:System.Data.DataSet> beginnen können, müssen Sie die Klasse mithilfe des DataSet\-Designers in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] generieren.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines typisierten Datasets](../Topic/Create%20and%20configure%20datasets%20in%20Visual%20Studio.md).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Abfrage von Daten in einem typisierten <xref:System.Data.DataSet> veranschaulicht:  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## Siehe auch  
 [Abfragen von 'DataSets'](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Abfragen für mehrere Tabellen](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)   
 [Abfragen für eine einzelne Tabelle](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)