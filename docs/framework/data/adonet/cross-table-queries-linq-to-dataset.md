---
title: "Tabellenübergreifende Abfragen (LINQ to DataSet)"
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
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 059dd39f3583c3b8fcf6736e514b9cc4870d3ad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cross-table-queries-linq-to-dataset"></a>Tabellenübergreifende Abfragen (LINQ to DataSet)
Zusätzlich zum Abfragen einer einzelnen Tabelle können Sie in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] auch Abfragen für mehrere Tabellen (tabellenübergreifende Abfragen) ausführen. Dies erfolgt mithilfe einer *Join*. Bei einem Join werden Objekte in einer Datenquelle mit Objekten in einer anderen Datenquelle, die über ein gemeinsames Attribut (wie Produkt oder Kontakt-ID) verfügen, miteinander verknüpft. Bei der objektorientierten Programmierung ist die Navigation in den Beziehungen zwischen den Objekten relativ einfach, da es in jedem Objekt einen Member gibt, der auf ein anderes Objekt verweist. In externen Datenbanktabellen ist die Navigation zwischen den Beziehungen etwas komplizierter. Datenbanktabellen enthalten keine integrierten Beziehungen. In diesen Fällen kann die JOIN-Operation verwendet werden, um Elemente aus den einzelnen Quellen zu verknüpfen. Wenn Sie z. B. zwei Tabellen haben, die Produktinformationen und Vertriebsinformationen enthalten, könnten Sie mittels einer JOIN-Operation Vertriebsinformationen und Produkte für ein und denselben Auftrag miteinander verknüpfen.  
  
 Das [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]-Framework stellt zwei Joinoperatoren bereit: <xref:System.Linq.Enumerable.Join%2A> und <xref:System.Linq.Enumerable.GroupJoin%2A>. Diese Operatoren führen *gleichheitsjoins*: d. h. Joins, die zwei Datenabgleich Datenquellen nur ab, wenn die Schlüssel gleich sind. (Im Gegensatz dazu unterstützt [!INCLUDE[tsql](../../../../includes/tsql-md.md)] auch andere Joinoperatoren als `equals`, wie z. B. den `less than`-Operator.)  
  
 In der Terminologie relationaler Datenbanken implementiert <xref:System.Linq.Enumerable.Join%2A> einen inneren Join. Eine innerer Join ist eine Joinart, bei der nur diejenigen Objekte zurückgegeben werden, für die es im anderen Dataset ein passendes Gegenüber gibt.  
  
 Die <xref:System.Linq.Enumerable.GroupJoin%2A> Operatoren haben keine direkte Entsprechung in relationale Datenbanken bedeutet dies, sie implementieren eine übergeordnete Menge innerer und linker äußerer Verknüpfungen. Ein linker äußerer Join ist ein Join, der jedes Element der ersten (linken) Auflistung zurückgibt, selbst wenn die zweite Auflistung keine zugehörigen Elemente enthält.  
  
 Weitere Informationen zu Joins finden Sie unter [Join-Vorgänge](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Tabellen `SalesOrderHeader` und `SalesOrderDetail` aus der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank auf herkömmliche Art und Weise miteinander verknüpft, um Onlinebestellungen aus dem Monat August abzurufen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen von DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Abfragen für einzelne Tabellen](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 [Abfragen von typisierten DataSets](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [Verknüpfungsvorgänge](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)  
 [Beispiele für LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
