---
title: Generische Field- und SetField-Methoden (LINQ to DataSet)
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
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7f71a6e380730ce3d622437b28a3722793524968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Generische Field- und SetField-Methoden (LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] stellt der <xref:System.Data.DataRow>-Klasse Erweiterungsmethoden für den Zugriff auf Spaltenwerte zur Verfügung: die <xref:System.Data.DataRowExtensions.Field%2A>-Methode und die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode. Diese Methoden erleichtern Entwicklern den Zugriff auf Spaltenwerte, besonders hinsichtlich der NULL-Werte. Das <xref:System.Data.DataSet> verwendet <xref:System.DBNull.Value>, um NULL-Werte darzustellen, während [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] auf die Unterstützung für den in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] eingeführten Typ zurückgreift, der NULL-Werte zulässt. Verwenden den schon vorhandenen Spaltenaccessor in <xref:System.Data.DataRow> erfordert, dass Sie das Rückgabeobjekt in den entsprechenden Typ umwandeln. Wenn ein bestimmtes Feld in einem <xref:System.Data.DataRow> null sein kann, müssen Sie explizit für einen null-Wert überprüfen, da zurückgeben <xref:System.DBNull.Value> und impliziten Umwandlung in einen anderen Typ löst eine <xref:System.InvalidCastException>. Im folgenden Beispiel wenn die <xref:System.Data.DataRow.IsNull%2A> Methode wurde nicht zum Prüfen auf einen null-Wert, eine Ausnahme wird ausgelöst, wenn der Indexer zurückgegeben <xref:System.DBNull.Value> und es wurde versucht,-Typ umzuwandeln eine <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Die <xref:System.Data.DataRowExtensions.Field%2A>-Methode bietet Zugriff auf die Spaltenwerte einer <xref:System.Data.DataRow>, und die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode gibt Spaltenwerte in einer <xref:System.Data.DataRow> an. Sowohl die <xref:System.Data.DataRowExtensions.Field%2A>-Methode als auch die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode kümmern sich um Typen, die NULL zulassen, sodass die explizite Prüfung auf NULL-Werte (wie im Beispiel oben) entfallen kann. Beide Methoden sind darüber hinaus generische Methoden. Der Rückgabetyp muss also nicht konvertiert werden.  
  
 Im folgenden Beispiel wird die <xref:System.Data.DataRowExtensions.Field%2A>-Methode verwendet:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Beachten Sie, dass der im generischen Parameter `T` der Methoden <xref:System.Data.DataRowExtensions.Field%2A> und <xref:System.Data.DataRowExtensions.SetField%2A> angegebene Datentyp mit dem Typ des zugrunde liegenden Werts übereinstimmen muss. Anderenfalls wird eine <xref:System.InvalidCastException> ausgelöst. Der angegebene Spaltenname muss außerdem mit dem Namen einer <xref:System.Data.DataSet>-Spalte übereinstimmen. Wenn dies nicht der Fall ist, wird eine <xref:System.ArgumentException> ausgelöst. In beiden Fällen wird die Ausnahme bei der Datenenumeration zur Laufzeit ausgelöst, wenn die Abfrage ausgeführt wird.  
  
 Die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode selbst führt keine Typkonvertierungen aus. Dies bedeutet jedoch nicht, dass keinerlei Typkonvertierung auftritt. Die <xref:System.Data.DataRowExtensions.SetField%2A> Methode macht die [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] Verhalten der <xref:System.Data.DataRow> Klasse. Eine Konvertierung vom Typ ausgeführt werden konnte die <xref:System.Data.DataRow> -Objekt und der konvertierte Wert würde dann zum gespeichert werden die <xref:System.Data.DataRow> Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataRowExtensions>
