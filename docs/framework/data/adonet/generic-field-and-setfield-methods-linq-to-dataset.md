---
title: Generische Field- und SetField-Methoden (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: d7ddee775e91c6be6166a091997afd58113cfe6b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249102"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Generische Field- und SetField-Methoden (LINQ to DataSet)
LINQ to DataSet stellt <xref:System.Data.DataRow> Erweiterungsmethoden für die <xref:System.Data.DataRowExtensions.Field%2A> Klasse für <xref:System.Data.DataRowExtensions.SetField%2A> den Zugriff auf Spaltenwerte bereit: die Methode und die Methode. Diese Methoden erleichtern Entwicklern den Zugriff auf Spaltenwerte, besonders hinsichtlich der NULL-Werte. Die <xref:System.Data.DataSet> <xref:System.DBNull.Value?displayProperty=nameWithType> verwendet, um NULL-Werte darzustellen, <xref:System.Nullable> <xref:System.Nullable%601> während LINQ die und-Typen verwendet. Wenn Sie den bereits <xref:System.Data.DataRow> vorhandenen Spaltenaccessor in verwenden, müssen Sie das Rückgabeobjekt in den entsprechenden Typ umwerfen. Wenn ein bestimmtes <xref:System.Data.DataRow> Feld in einem NULL sein kann, müssen <xref:System.DBNull.Value?displayProperty=nameWithType> Sie explizit nach einem NULL-Wert suchen, da das Zurückgeben und implizite Umsetzen in einen anderen Typ eine <xref:System.InvalidCastException>auslöst. Wenn die <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> Methode im folgenden Beispiel nicht zum Überprüfen nach einem NULL-Wert verwendet <xref:System.DBNull.Value?displayProperty=nameWithType> wurde, wird eine <xref:System.String>Ausnahme ausgelöst, wenn der Indexer zurückgegeben und versucht hat, sie in einen zu setzen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Die <xref:System.Data.DataRowExtensions.Field%2A>-Methode bietet Zugriff auf die Spaltenwerte einer <xref:System.Data.DataRow>, und die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode gibt Spaltenwerte in einer <xref:System.Data.DataRow> an. Sowohl <xref:System.Data.DataRowExtensions.Field%2A> die <xref:System.Data.DataRowExtensions.SetField%2A> Methode als auch die Methode behandeln nullfähige Werttypen, sodass Sie nicht wie im vorherigen Beispiel explizit nach NULL-Werten suchen müssen. Beide Methoden sind darüber hinaus generische Methoden. Der Rückgabetyp muss also nicht konvertiert werden.  
  
 Im folgenden Beispiel wird die <xref:System.Data.DataRowExtensions.Field%2A>-Methode verwendet:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Beachten Sie, dass der im generischen Parameter `T` der Methoden <xref:System.Data.DataRowExtensions.Field%2A> und <xref:System.Data.DataRowExtensions.SetField%2A> angegebene Datentyp mit dem Typ des zugrunde liegenden Werts übereinstimmen muss. Anderenfalls wird eine <xref:System.InvalidCastException> ausgelöst. Der angegebene Spaltenname muss außerdem mit dem Namen einer <xref:System.Data.DataSet>-Spalte übereinstimmen. Wenn dies nicht der Fall ist, wird eine <xref:System.ArgumentException> ausgelöst. In beiden Fällen wird die Ausnahme bei der Datenenumeration zur Laufzeit ausgelöst, wenn die Abfrage ausgeführt wird.  
  
 Die <xref:System.Data.DataRowExtensions.SetField%2A>-Methode selbst führt keine Typkonvertierungen aus. Dies bedeutet jedoch nicht, dass keinerlei Typkonvertierung auftritt. Die <xref:System.Data.DataRowExtensions.SetField%2A> Methode macht das ADO.NET <xref:System.Data.DataRow> Verhalten der Klasse verfügbar. Eine Typkonvertierung kann vom <xref:System.Data.DataRow> Objekt durchgeführt werden, und der <xref:System.Data.DataRow> konvertierte Wert wird dann im Objekt gespeichert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataRowExtensions>
