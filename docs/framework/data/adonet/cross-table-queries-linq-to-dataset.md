---
title: Tabellenübergreifende Abfragen (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 4ab8eb9988995b4a142b1c02e82476f45285c3b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785621"
---
# <a name="cross-table-queries-linq-to-dataset"></a>Tabellenübergreifende Abfragen (LINQ to DataSet)
Zusätzlich zum Abfragen einer einzelnen Tabelle können Sie auch Tabellen übergreifende Abfragen in LINQ to DataSet durchführen. Dies erfolgt *mithilfe eines Joins*. Bei einem Join werden Objekte in einer Datenquelle mit Objekten in einer anderen Datenquelle, die über ein gemeinsames Attribut (wie Produkt oder Kontakt-ID) verfügen, miteinander verknüpft. Bei der objektorientierten Programmierung ist die Navigation in den Beziehungen zwischen den Objekten relativ einfach, da es in jedem Objekt einen Member gibt, der auf ein anderes Objekt verweist. In externen Datenbanktabellen ist die Navigation zwischen den Beziehungen etwas komplizierter. Datenbanktabellen enthalten keine integrierten Beziehungen. In diesen Fällen kann die JOIN-Operation verwendet werden, um Elemente aus den einzelnen Quellen zu verknüpfen. Wenn Sie z. B. zwei Tabellen haben, die Produktinformationen und Vertriebsinformationen enthalten, könnten Sie mittels einer JOIN-Operation Vertriebsinformationen und Produkte für ein und denselben Auftrag miteinander verknüpfen.  
  
 Das [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]-Framework stellt zwei Joinoperatoren bereit: <xref:System.Linq.Enumerable.Join%2A> und <xref:System.Linq.Enumerable.GroupJoin%2A>. Diese Operatoren führen *Equi-Joins*aus: d. h. Joins, die nur zwei Datenquellen entsprechen, wenn Ihre Schlüssel gleich sind. (Im Gegensatz dazu unterstützt Transact-SQL andere joinoperatoren als `equals`, z. b. den `less than` -Operator.)  
  
 In der Terminologie relationaler Datenbanken implementiert <xref:System.Linq.Enumerable.Join%2A> einen inneren Join. Eine innerer Join ist eine Joinart, bei der nur diejenigen Objekte zurückgegeben werden, für die es im anderen Dataset ein passendes Gegenüber gibt.  
  
 Die <xref:System.Linq.Enumerable.GroupJoin%2A> Operatoren verfügen über keine direkte Entsprechung in relationalen Daten Bank Begriffen; Sie implementieren eine Obermenge innerer Joins und linker äußerer Joins. Ein linker äußerer Join ist ein Join, der jedes Element der ersten (linken) Auflistung zurückgibt, selbst wenn die zweite Auflistung keine zugehörigen Elemente enthält.  
  
 Weitere Informationen zu Joins finden Sie unter [Join-Vorgänge](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120)).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Tabellen `SalesOrderHeader` und `SalesOrderDetail` aus der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank auf herkömmliche Art und Weise miteinander verknüpft, um Onlinebestellungen aus dem Monat August abzurufen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen von DataSets](querying-datasets-linq-to-dataset.md)
- [Abfragen für einzelne Tabellen](single-table-queries-linq-to-dataset.md)
- [Abfragen von typisierten DataSets](querying-typed-datasets.md)
- [Verknüpfungsvorgänge](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))
- [Beispiele für LINQ to DataSet](linq-to-dataset-examples.md)
