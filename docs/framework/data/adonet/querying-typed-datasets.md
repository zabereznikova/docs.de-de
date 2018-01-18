---
title: Abfragen von typisierten DataSets
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
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fff678a54416e72f4be8c3fdfdcacec5a7d90af7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="querying-typed-datasets"></a>Abfragen von typisierten DataSets
Wenn zum Zeitpunkt der Anwendungskonzeptionierung bereits das <xref:System.Data.DataSet>-Schema bekannt ist, wird empfohlen, bei der Benutzung von <xref:System.Data.DataSet> mit einem typisierten [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] zu arbeiten. Eine typisierte <xref:System.Data.DataSet> ist eine Klasse, die von abgeleitet ist eine <xref:System.Data.DataSet>. Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines <xref:System.Data.DataSet>. Darüber hinaus eine typisierte <xref:System.Data.DataSet> stellt stark typisierte Methoden, Ereignisse und Eigenschaften bereit. Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen. Dadurch werden Abfragen einfacher und lesbarer. Weitere Informationen finden Sie unter [typisierter DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]unterstützt auch das Abfragen von Daten in einem typisierten <xref:System.Data.DataSet>. Mit einer typisierten <xref:System.Data.DataSet>, Sie müssen nicht die generischen <xref:System.Data.DataRowExtensions.Field%2A> Methode oder <xref:System.Data.DataRowExtensions.SetField%2A> Methode, um Spaltendaten zugreifen zu können.  Eigenschaftennamen sind zum Zeitpunkt der Kompilierung verfügbar, da die Typinformationen, in enthalten ist der <xref:System.Data.DataSet>. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]bietet Zugriff auf Spaltenwerte den richtigen Typ aufweist, sodass Typfehler-Konflikt beim Kompilieren des Codes statt zur Laufzeit abgefangen werden.  
  
 Bevor Sie mit der Abfrage eines typisierten <xref:System.Data.DataSet> beginnen können, müssen Sie die Klasse mithilfe des DataSet-Designers in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] generieren.  Weitere Informationen finden Sie unter [Erstellen und Konfigurieren von Datasets in Visual Studio](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).  
  
## <a name="example"></a>Beispiel  
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
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen von DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Tabellenübergreifende Abfragen](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [Abfragen für einzelne Tabellen](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
