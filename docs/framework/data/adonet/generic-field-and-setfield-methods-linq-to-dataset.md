---
title: "Generische Methoden &#39;Field&#39; und &#39;SetField&#39; (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Generische Methoden &#39;Field&#39; und &#39;SetField&#39; (LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] stellt Erweiterungsmethoden für die <xref:System.Data.DataRow>\-Klasse für den Zugriff auf Spaltenwerte bereit: die <xref:System.Data.DataRowExtensions.Field%2A>\-Methode und die <xref:System.Data.DataRowExtensions.SetField%2A>\-Methode. Diese Methoden erleichtern Entwicklern den Zugriff auf Spaltenwerte, insbesondere hinsichtlich der NULL\-Werte. <xref:System.Data.DataSet> verwendet <xref:System.DBNull.Value> zur Darstellung von NULL\-Werten, während [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] auf die Unterstützung für den in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] eingeführten Typ zurückgreift, der NULL\-Werte zulässt.  Für die Nutzung des schon zuvor vorhandenen Spaltenaccessors in <xref:System.Data.DataRow> müssen Sie das Rückgabeobjekt in den entsprechenden Typ konvertieren.  Falls ein bestimmtes <xref:System.Data.DataRow>\-Feld NULL sein kann, müssen Sie explizit auf einen NULL\-Wert prüfen, da bei der Rückgabe von <xref:System.DBNull.Value> und der impliziten Umwandlung in einen anderen Typ eine <xref:System.InvalidCastException> ausgelöst wird.  Wenn im folgenden Beispiel keine Prüfung auf NULL\-Werte mittels der <xref:System.Data.DataRow.IsNull%2A>\-Methode stattfinden würde und der Indexer <xref:System.DBNull.Value> zurückgeben und versuchen würde, den Rückgabewert in den <xref:System.String>\-Typ umzuwandeln, würde eine Ausnahme ausgelöst werden.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Die <xref:System.Data.DataRowExtensions.Field%2A>\-Methode bietet Zugriff auf die Spaltenwerte einer <xref:System.Data.DataRow>, und die <xref:System.Data.DataRowExtensions.SetField%2A>\-Methode gibt Spaltenwerte in einer <xref:System.Data.DataRow> an.  Sowohl die <xref:System.Data.DataRowExtensions.Field%2A>\-Methode als auch die <xref:System.Data.DataRowExtensions.SetField%2A>\-Methode kümmern sich um Typen, die NULL zulassen, sodass die explizite Prüfung auf NULL\-Werte \(wie im Beispiel oben\) entfallen kann.  Beide Methoden sind darüber hinaus generische Methoden. Der Rückgabetyp muss also nicht konvertiert werden.  
  
 Im folgenden Beispiel wird die <xref:System.Data.DataRowExtensions.Field%2A>\-Methode verwendet:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Beachten Sie, dass der im generischen Parameter `T` der Methoden <xref:System.Data.DataRowExtensions.Field%2A> und <xref:System.Data.DataRowExtensions.SetField%2A> angegebene Datentyp mit dem Typ des zugrunde liegenden Werts übereinstimmen muss.  Anderenfalls wird eine <xref:System.InvalidCastException> ausgelöst.  Der angegebene Spaltenname muss außerdem mit dem Namen einer <xref:System.Data.DataSet>\-Spalte übereinstimmen. Wenn dies nicht der Fall ist, wird eine <xref:System.ArgumentException> ausgelöst.  In beiden Fällen wird die Ausnahme bei der Datenenumeration zur Laufzeit ausgelöst, wenn die Abfrage ausgeführt wird.  
  
 Die <xref:System.Data.DataRowExtensions.SetField%2A>\-Methode selbst führt keine Typkonvertierungen aus.  Dies bedeutet jedoch nicht, dass keinerlei Typkonvertierung auftritt.  Die <xref:System.Data.DataRowExtensions.SetField%2A>\-Methode macht das [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]\-Verhalten der <xref:System.Data.DataRow>\-Klasse verfügbar.  Eine Typkonvertierung könnte vom <xref:System.Data.DataRow>\-Objekt ausgeführt werden, wobei der konvertierte Wert dann im <xref:System.Data.DataRow>\-Objekt gespeichert werden würde.  
  
## Siehe auch  
 <xref:System.Data.DataRowExtensions>