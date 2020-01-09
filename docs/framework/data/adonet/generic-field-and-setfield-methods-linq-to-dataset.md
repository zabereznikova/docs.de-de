---
title: Generische Field- und SetField-Methoden (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 310eb3ccecc3159234ed362ed044be7ad704dde4
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634832"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Generische Field- und SetField-Methoden (LINQ to DataSet)
LINQ to DataSet stellt Erweiterungs Methoden für die <xref:System.Data.DataRow>-Klasse für den Zugriff auf Spaltenwerte bereit: die <xref:System.Data.DataRowExtensions.Field%2A>-Methode und die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode. Diese Methoden erleichtern Entwicklern den Zugriff auf Spaltenwerte, besonders hinsichtlich der NULL-Werte. Der <xref:System.Data.DataSet> verwendet <xref:System.DBNull.Value?displayProperty=nameWithType>, um NULL-Werte darzustellen, während LINQ die <xref:System.Nullable> und <xref:System.Nullable%601> Typen verwendet. Wenn Sie den bereits vorhandenen Spalten Accessor in <xref:System.Data.DataRow> verwenden, müssen Sie das Rückgabe Objekt in den entsprechenden Typ umwandeln. Wenn ein bestimmtes Feld in einem <xref:System.Data.DataRow> NULL sein kann, müssen Sie explizit auf einen NULL-Wert überprüfen, da die Rückgabe <xref:System.DBNull.Value?displayProperty=nameWithType> und die implizite Umwandlung in einen anderen Typ eine <xref:System.InvalidCastException>auslöst. Im folgenden Beispiel wird eine Ausnahme ausgelöst, wenn die <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType>-Methode nicht für die Überprüfung auf einen NULL-Wert verwendet wurde, wenn der Indexer <xref:System.DBNull.Value?displayProperty=nameWithType> zurückgegeben hat und versucht hat, ihn in eine <xref:System.String>umzuwandeln.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Die <xref:System.Data.DataRowExtensions.Field%2A>-Methode bietet Zugriff auf die Spaltenwerte einer <xref:System.Data.DataRow>, und die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode gibt Spaltenwerte in einer <xref:System.Data.DataRow> an. Sowohl die <xref:System.Data.DataRowExtensions.Field%2A>-Methode als auch die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode kümmern sich um Typen, die NULL zulassen, sodass die explizite Prüfung auf NULL-Werte (wie im Beispiel oben) entfallen kann. Beide Methoden sind darüber hinaus generische Methoden. Der Rückgabetyp muss also nicht konvertiert werden.  
  
 Im folgenden Beispiel wird die <xref:System.Data.DataRowExtensions.Field%2A>-Methode verwendet:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Beachten Sie, dass der im generischen Parameter `T` der Methoden <xref:System.Data.DataRowExtensions.Field%2A> und <xref:System.Data.DataRowExtensions.SetField%2A> angegebene Datentyp mit dem Typ des zugrunde liegenden Werts übereinstimmen muss. Anderenfalls wird eine <xref:System.InvalidCastException> ausgelöst. Der angegebene Spaltenname muss außerdem mit dem Namen einer <xref:System.Data.DataSet>-Spalte übereinstimmen. Wenn dies nicht der Fall ist, wird eine <xref:System.ArgumentException> ausgelöst. In beiden Fällen wird die Ausnahme bei der Datenenumeration zur Laufzeit ausgelöst, wenn die Abfrage ausgeführt wird.  
  
 Die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode selbst führt keine Typkonvertierungen aus. Dies bedeutet jedoch nicht, dass keinerlei Typkonvertierung auftritt. Die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode macht das ADO.net-Verhalten der <xref:System.Data.DataRow>-Klasse verfügbar. Eine Typkonvertierung kann durch das <xref:System.Data.DataRow>-Objekt durchgeführt werden, und der konvertierte Wert würde dann im <xref:System.Data.DataRow> Objekt gespeichert werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataRowExtensions>
