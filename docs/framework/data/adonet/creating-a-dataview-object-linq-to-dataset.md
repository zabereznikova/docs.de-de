---
title: Erstellen eines DataView-Objekts (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
ms.openlocfilehash: f76574a912128918ed575cbf0eca892041dc354c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148320"
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a>Erstellen eines DataView-Objekts (LINQ to DataSet)

Es gibt zwei Möglichkeiten, eine <xref:System.Data.DataView> im LINQ to DataSet Kontext zu erstellen. Sie können einen <xref:System.Data.DataView> aus einer LINQ to DataSet Abfrage über einen erstellen <xref:System.Data.DataTable> , oder Sie können ihn aus einem typisierten oder nicht typisierten erstellen <xref:System.Data.DataTable> . In beiden Fällen erstellen Sie den <xref:System.Data.DataView> mit einer der <xref:System.Data.DataTableExtensions.AsDataView%2A> Erweiterungs Methoden <xref:System.Data.DataView> . ist nicht direkt im LINQ to DataSet Kontext konstrukbar.  
  
 Nachdem die <xref:System.Data.DataView> erstellt wurde, können Sie sie an ein Benutzeroberflächensteuerelement in einer Windows Forms-Anwendung oder einer ASP.NET-Anwendung binden oder die Filter- und Sortiereinstellungen ändern.  
  
 <xref:System.Data.DataView> erstellt einen Index, der bei Operationen, die diesen Index einsetzen können, wie beim Filtern und Sortieren, zu beträchtlichen Leistungssteigerungen führt. Der Index für eine <xref:System.Data.DataView> wird sowohl dann generiert, wenn die <xref:System.Data.DataView> erstellt wird, als auch dann, wenn Änderungen an den Sortier- oder Filterinformationen vorgenommen werden. Wenn Sie eine <xref:System.Data.DataView> erstellen, ohne gleich auch die Sortier- und Filterinformationen festzulegen, wird der Index mindestens zweimal generiert: das erste Mal, wenn die <xref:System.Data.DataView> erstellt wird, und das zweite Mal, sobald eine der Sortier- oder Filtereigenschaften geändert wird.  
  
 Weitere Informationen zum Filtern und Sortieren mit <xref:System.Data.DataView> finden Sie unter [Filtern mit DataView](filtering-with-dataview-linq-to-dataset.md) und [Sortieren mit DataView](sorting-with-dataview-linq-to-dataset.md).  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a>Erstellen einer "DataView" auf der Grundlage einer LINQ to DataSet-Abfrage  

 Ein- <xref:System.Data.DataView> Objekt kann aus den Ergebnissen einer LINQ to DataSet Abfrage erstellt werden, wobei die Ergebnisse eine Projektion von <xref:System.Data.DataRow> Objekten sind. Die neu erstellte <xref:System.Data.DataView> erbt die Filter- und Sortierinformationen von der Abfrage, auf deren Grundlage sie erstellt wurde.  
  
> [!NOTE]
> In den meisten Fällen haben die für die Filterung und Sortierung verwendeten Ausdrücke keine Nebenwirkungen. Sie müssen deterministisch sein. Die Ausdrücke dürfen darüber hinaus keine Logik enthalten, die auf einer festgelegten Anzahl von Ausführungen beruht, da die Sortier- und Filteroperationen unbegrenzt oft ausgeführt werden können sollen.  
  
 Das Erstellen einer <xref:System.Data.DataView> auf der Grundlage einer Abfrage, die anonyme Typen oder Abfragen zurückgibt, die ihrerseits Joins ausführen, wird nicht unterstützt.  
  
 In einer Abfrage, die die Grundlage für eine <xref:System.Data.DataView> bilden soll, werden nur die folgenden Abfrageoperatoren unterstützt:  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 Beachten Sie Folgendes: Wenn ein <xref:System.Data.DataView> aus einer LINQ to DataSet Abfrage erstellt wird, <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> muss die Methode die endgültige Methode sein, die in der Abfrage aufgerufen wird. Dies wird im folgenden Beispiel gezeigt, mit dem eine von Online Bestellungen erstellt wird, die <xref:System.Data.DataView> nach Gesamtbetrag sortiert sind:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 Sie können auch die Zeichen folgen basierten-Eigenschaft und die-Eigenschaft verwenden <xref:System.Data.DataView.RowFilter%2A> <xref:System.Data.DataView.Sort%2A> , um eine zu filtern und zu sortieren, <xref:System.Data.DataView> nachdem Sie aus einer-Abfrage erstellt wurde. Beachten Sie, dass dabei die von der Abfrage geerbten Sortierungs- und Filterinformationen gelöscht werden. Im folgenden Beispiel wird ein <xref:System.Data.DataView> aus einer LINQ to DataSet Abfrage erstellt, die nach Nachnamen filtert, die mit "s" beginnen. Die zeichenfolgenbasierte <xref:System.Data.DataView.Sort%2A>-Eigenschaft ist so eingerichtet, dass die Nachnamen in aufsteigender Reihenfolge und dann die Vornamen in absteigender Reihenfolge sortiert werden:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a>Erstellen einer "DataView" aus einer "DataTable"  

 Ein-Objekt kann nicht nur aus einer LINQ to DataSet Abfrage erstellt werden, sondern auch <xref:System.Data.DataView> <xref:System.Data.DataTable> mithilfe der- <xref:System.Data.DataTableExtensions.AsDataView%2A> Methode.  
  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage der &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt;-Tabelle erstellt und dann als Datenquelle eines <xref:System.Windows.Forms.BindingSource>-Objekts festgelegt. Dieses Objekt fungiert als Proxy für ein <xref:System.Windows.Forms.DataGridView>-Steuerelement.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 Nachdem die <xref:System.Data.DataView> auf der Grundlage einer <xref:System.Data.DataTable> erstellt wurde, können Filter- und Sortiereigenschaften für sie festgelegt werden. Im folgenden Beispiel wird eine  auf der Grundlage der Contact-Tabelle erstellt und dann die -Eigenschaft so eingerichtet, dass die Nachnamen in aufsteigender und dann die Vornamen in absteigender Reihenfolge sortiert werden:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 Wenn die <xref:System.Data.DataView.RowFilter%2A> auf der Grundlage einer Abfrage erstellt wurde, kommt es jedoch beim Einrichten der Eigenschaft <xref:System.Data.DataView.Sort%2A> bzw. <xref:System.Data.DataView> zu einem Leistungsabfall, weil <xref:System.Data.DataView> einen Index generiert, um die Filter- und Sortieroperationen zu unterstützen. Wenn Sie die Eigenschaft <xref:System.Data.DataView.RowFilter%2A> oder <xref:System.Data.DataView.Sort%2A> festlegen, wird der Index für die Daten neu erstellt, wodurch zusätzlicher Verwaltungsmehraufwand für die Anwendung entsteht und die Arbeitsgeschwindigkeit verringert wird. Es ist daher empfehlenswert, die Filter- und Sortierinformationen schon beim Erstellen der <xref:System.Data.DataView> einzurichten und nachträgliche Änderungen zu vermeiden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Datenbindung und LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Filtern mit DataView](filtering-with-dataview-linq-to-dataset.md)
- [Sortieren mit DataView](sorting-with-dataview-linq-to-dataset.md)
