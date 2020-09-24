---
title: Erstellen einer DataTable aus einer Abfrage (LINQ to DataSet)
description: Erfahren Sie, wie Sie die copytodatabel-Methode verwenden, um die Ergebnisse einer Abfrage zu übernehmen und die Daten in eine Datentabelle zu kopieren, die dann für die Datenbindung verwendet werden kann.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b97afeb-03f8-41e2-8eb3-58aff65f7d18
ms.openlocfilehash: 064688f173e375481373e9a33d66c64666e1583f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148360"
---
# <a name="creating-a-datatable-from-a-query-linq-to-dataset"></a>Erstellen einer DataTable aus einer Abfrage (LINQ to DataSet)

Das <xref:System.Data.DataTable>-Objekt wird häufig zur Datenbindung eingesetzt. Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode kopiert die Ergebnisse einer Abfrage in eine <xref:System.Data.DataTable>, die dann für die Datenbindung verwendet werden kann. Wenn die Datenoperationen ausgeführt wurden, wird die neue <xref:System.Data.DataTable> wieder mit der ursprünglichen <xref:System.Data.DataTable> zusammengeführt.  
  
 Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode verwendet den folgenden Prozess, um aus einer Abfrage eine <xref:System.Data.DataTable> zu erstellen:  
  
1. Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode klont eine <xref:System.Data.DataTable> aus der Quelltabelle (ein <xref:System.Data.DataTable>-Objekt, das die <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert). Die <xref:System.Collections.IEnumerable> Quelle stammt im Allgemeinen von einem LINQ to DataSet Ausdruck oder einer Methoden Abfrage.  
  
2. Das Schema der geklonten <xref:System.Data.DataTable> wird aus den Spalten des ersten aufgezählten <xref:System.Data.DataRow>-Objekts in der Quelltabelle generiert, und als Name für die geklonte Tabelle wird der Name der Quelltabelle mit dem Zusatz "Abfrage" verwendet.  
  
3. Für jede Zeile in der Quelltabelle wird der Inhalt der Zeile in ein neues <xref:System.Data.DataRow>-Objekt kopiert, dass dann in die geklonte Tabelle eingefügt wird. Die Eigenschaften <xref:System.Data.DataRow.RowState%2A> und <xref:System.Data.DataRow.RowError%2A> bleiben beim Kopieren erhalten. Wenn die <xref:System.ArgumentException>-Objekte in der Quelle aus unterschiedlichen Tabellen stammen, wird eine <xref:System.Data.DataRow> ausgelöst.  
  
4. Nachdem alle <xref:System.Data.DataTable>-Objekte in der abfragbaren Eingabetabelle kopiert wurden, wird die geklonte <xref:System.Data.DataRow> zurückgegeben. Wenn die Ausgangsfolge keine <xref:System.Data.DataRow>-Objekte enthält, gibt die Methode eine leere <xref:System.Data.DataTable> zurück.  
  
Das Aufrufen der- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> Methode bewirkt, dass die an die Quell Tabelle gebundene Abfrage ausgeführt wird.  
  
 Wenn die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode in einer Zeile der Quelltabelle auf einen NULL-Verweis oder einen Wert trifft, der NULL zulässt, wird der Wert durch <xref:System.DBNull.Value> ersetzt. Auf diese Weise werden die NULL-Werte in der zurückgegebenen <xref:System.Data.DataTable> korrekt behandelt.  
  
 Hinweis: Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode akzeptiert eine Abfrage, die Zeilen aus mehreren <xref:System.Data.DataTable>-Objekten oder <xref:System.Data.DataSet>-Objekten zurückgeben kann. Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode kopiert die Daten, jedoch nicht die Eigenschaften, aus dem <xref:System.Data.DataTable>-Quellobjekt oder <xref:System.Data.DataSet>-Quellobjekt zum zurückgegebenen <xref:System.Data.DataTable>-Objekt. Sie müssen die Eigenschaften explizit für das zurückgegebene <xref:System.Data.DataTable>-Objekt festlegen, z. B. <xref:System.Data.DataTable.Locale%2A> und <xref:System.Data.DataTable.TableName%2A>.  
  
 Im folgenden Beispiel wird die Tabelle "SalesOrderHeader" nach Aufträgen abgefragt, die nach dem 8. August 2001 eingegangen sind. Dabei kommt die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode zum Einsatz, um aus dieser Abfrage eine <xref:System.Data.DataTable> zu erstellen. Die <xref:System.Data.DataTable> wird dann an eine <xref:System.Windows.Forms.BindingSource> gebunden, die als Proxy für eine <xref:System.Windows.Forms.DataGridView> fungiert.  
  
 [!code-csharp[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#copytodatatable1)]
 [!code-vb[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#copytodatatable1)]  
  
## <a name="creating-a-custom-copytodatatablet-method"></a>Erstellen einer benutzerdefinierten copydedatdatababel- \<T> Methode  

 Die vorhandenen <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methoden arbeiten nur mit einer <xref:System.Collections.Generic.IEnumerable%601>-Quelle, bei der der generische Parameter `T` den Typ <xref:System.Data.DataRow> aufweist. Obwohl dies hilfreich ist, können Tabellen dabei nicht aus einer Sequenz von Skalartypen, aus Abfragen, die anonyme Typen zurückgeben, oder aus Abfragen, die Tabellenjoins durchführen, erstellt werden. Ein Beispiel für die Implementierung von zwei benutzerdefinierten `CopyToDataTable` Methoden, die eine Tabelle aus einer Sequenz von skalaren oder anonymen Typen laden, finden Sie unter Gewusst [wie: Implementieren von copytodatable, \<T> wobei der generische Typ T keine DataRow s ist](implement-copytodatatable-where-type-not-a-datarow.md).  
  
 Für die Beispiele in diesem Abschnitt werden die folgenden benutzerdefinierten Typen verwendet:  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#itemclass)]
 [!code-vb[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#itemclass)]  
  
### <a name="example"></a>Beispiel  

 In diesem Beispiel werden die Tabellen `SalesOrderHeader` und `SalesOrderDetail` durch eine JOIN-Operation miteinander verknüpft, um die Onlinebestellungen für den Monat August abzurufen und aus der Abfrage eine Tabelle zu erstellen.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#join)]
 [!code-vb[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#join)]  
  
### <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine Auflistung für Artikel abgefragt, deren Preis mehr als $ 9,99 beträgt, und eine Tabelle aus den Abfrageergebnissen erstellt.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintotable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintotable)]  
  
### <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine Auflistung für Artikel abgefragt, deren Preis mehr als $ 9,99 beträgt, und anschließend werden die Ergebnisse dargestellt. Die zurückgegebene Sequenz anonymer Typen wird in eine bestehende Tabelle geladen.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintoexistingtable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintoexistingtable)]  
  
### <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine Auflistung für Artikel abgefragt, deren Preis mehr als $ 9,99 beträgt, und anschließend werden die Ergebnisse dargestellt. Die zurückgegebene Sequenz anonymer Typen wird in eine bestehende Tabelle geladen. Das Tabellenschema wird automatisch erweitert, da die Typen `Book` und `Movies` vom `Item`-Typ abgeleitet sind.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsexpandschema)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsexpandschema)]  
  
### <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine Auflistung für Artikel abgefragt, deren Preis mehr als $ 9,99 beträgt, und eine Sequenz von <xref:System.Double> zurückgegeben, die in eine neue Tabelle geladen wird.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loadscalarsequence)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loadscalarsequence)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Programmierhandbuch](programming-guide-linq-to-dataset.md)
- [Generische Field- und SetField-Methoden](generic-field-and-setfield-methods-linq-to-dataset.md)
- [Beispiele für LINQ to DataSet](linq-to-dataset-examples.md)
