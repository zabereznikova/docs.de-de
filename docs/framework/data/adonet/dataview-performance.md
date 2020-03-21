---
title: DataView-Leistung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: 7c81619bf4ac6ed084ea63349345dbf3b7f139b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150687"
---
# <a name="dataview-performance"></a>DataView-Leistung
In diesem Thema wird beschrieben, wie sich die Verwendung der Methoden <xref:System.Data.DataView.Find%2A> und <xref:System.Data.DataView.FindRows%2A> der <xref:System.Data.DataView>-Klasse und die Zwischenspeicherung einer <xref:System.Data.DataView> in einer Webanwendung positiv auf die Arbeitsgeschwindigkeit auswirken können.  
  
## <a name="find-and-findrows"></a>"Find" und "FindRows"  
 <xref:System.Data.DataView> generiert einen Index. Ein Index enthält Schlüssel, die aus einer oder mehreren Spalten in der Tabelle oder Sicht erstellt werden. Diese Schlüssel werden in einer Struktur gespeichert, mit der die <xref:System.Data.DataView> schnell und effizient die Zeile(n) finden kann, die mit den Schlüsselwerten verknüpft sind. Vorgängen, die den Index verwenden, z. B. Filtern und Sortieren, sehen erhebliche Leistungssteigerungen. Der Index für eine <xref:System.Data.DataView> wird sowohl dann generiert, wenn die <xref:System.Data.DataView> erstellt wird, als auch dann, wenn Änderungen an den Sortier- oder Filterinformationen vorgenommen werden. Wenn Sie eine <xref:System.Data.DataView> erstellen, ohne gleich auch die Sortier- und Filterinformationen festzulegen, wird der Index mindestens zweimal generiert: das erste Mal, wenn die <xref:System.Data.DataView> erstellt wird, und das zweite Mal, sobald eine der Sortier- oder Filtereigenschaften geändert wird. Weitere Informationen zum Filtern <xref:System.Data.DataView>und Sortieren mit finden Sie unter [Filtern mit DataView](filtering-with-dataview-linq-to-dataset.md) und [Sortieren mit DataView](sorting-with-dataview-linq-to-dataset.md).  
  
 Wenn Sie die Ergebnisse einer bestimmten Abfrage von Daten zurückgeben möchten, anstatt eine dynamische Ansicht einer Teilmenge von Daten zu erhalten, können Sie die Methode <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> der <xref:System.Data.DataView> verwenden, statt die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft einzurichten. Die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft wird am besten in einer datengebundenen Anwendung verwendet, in der ein gebundenes Steuerelement gefilterte Ergebnisse anzeigt. Wenn Sie die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft festlegen, wird der Index für die Daten neu erstellt, wodurch zusätzlicher Verwaltungsmehraufwand für die Anwendung entsteht und die Arbeitsgeschwindigkeit verringert wird. Die Methoden <xref:System.Data.DataView.Find%2A> und <xref:System.Data.DataView.FindRows%2A> nutzen den aktuellen Index, ohne dass der Index neu erstellt werden muss. Wenn Sie <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> nur einmal aufrufen werden, sollten Sie die vorhandene <xref:System.Data.DataView> verwenden. Wird <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> dagegen mehrmals aufgerufen, empfiehlt sich die Erstellung einer neuen <xref:System.Data.DataView>, um den Index auf der Basis der zu durchsuchenden Spalte neu zu erstellen, und dann die Methode <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> aufzurufen. Weitere Informationen zu <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> den Methoden finden Sie unter [Suchen von Zeilen](./dataset-datatable-dataview/finding-rows.md).  
  
 Im folgenden Beispiel wird die <xref:System.Data.DataView.Find%2A>-Methode verwendet, um einen Kontakt mit dem Nachnamen "Zhu" zu finden.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 Im folgenden Beispiel wird die <xref:System.Data.DataView.FindRows%2A>-Methode verwendet, um alle Produkte mit roter Farbe abzurufen.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a>ASP.NET  
 ASP.NET verfügt über einen Cachemechanismus zur Zwischenspeicherung von Objekten, die die Serverressourcen in starkem Maße beanspruchen. Durch die Zwischenspeicherung dieser Ressourcen kann die Geschwindigkeit Ihrer Anwendung wesentlich verbessert werden. Die Zwischenspeicherung wird von der Klasse <xref:System.Web.Caching.Cache> implementiert. Die dabei zum Einsatz kommenden Cacheinstanzen sind jeweils anwendungsspezifisch und privat. Da das Erstellen eines neuen <xref:System.Data.DataView>-Objekts die Ressourcen stark beanspruchen kann, kann mit der Zwischenspeicherfunktionalität in Webanwendungen verhindert werden, dass die <xref:System.Data.DataView> bei jeder Aktualisierung der Webseite neu erstellt werden muss.  
  
 Im folgenden Beispiel wird die <xref:System.Data.DataView> im Cache zwischengespeichert. So wird dafür gesorgt, dass die Daten nicht neu sortiert werden müssen, wenn die Seite aktualisiert wird.  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Datenbindung und LINQ to DataSet](data-binding-and-linq-to-dataset.md)
