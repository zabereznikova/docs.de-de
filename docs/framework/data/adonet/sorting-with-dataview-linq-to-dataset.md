---
title: Sortieren mit DataView (LINQ to DataSet)
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
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e8eda365fa1970f4fa836440151cc1ba0d3ae9dd
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>Sortieren mit DataView (LINQ to DataSet)
Die Möglichkeit, Daten nach bestimmten Kriterien zu sortieren und dann über ein UI-Steuerelement für einen Client bereitzustellen, ist ein wichtiger Aspekt der Datenbindung. <xref:System.Data.DataView> bietet mehrere Möglichkeiten, Daten zu sortieren und nach bestimmten Sortierkriterien geordnete Datenzeilen zurückzugeben. Neben den zeichenfolgenbasierten Sortierfunktionen <xref:System.Data.DataView> auch können Sie [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Ausdrücke für die Kriterien sortieren. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Ausdrücke ermöglichen wesentlich komplexere und leistungsfähigere Sortieroperationen als die zeichenfolgenbasierte Sortierung. In diesem Thema werden beide Ansätze für die Sortierung mit <xref:System.Data.DataView> beschrieben.  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>Erstellen einer "DataView" auf der Grundlage einer Abfrage mit Sortierinformationen  
 Ein <xref:System.Data.DataView>-Objekt kann auf der Grundlage einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfrage erstellt werden. Wenn diese Abfrage enthält eine <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A>, oder <xref:System.Linq.Enumerable.ThenByDescending%2A> Klausel, die die Ausdrücke in diesen Klauseln als Grundlage dienen für die Sortierung der Daten in der <xref:System.Data.DataView>. Wenn die Abfrage enthält z. B. die `Order By…`und `Then By…` Klauseln, die den resultierenden <xref:System.Data.DataView> würden die Daten nach beiden angegebenen Spalten sortieren.  
  
 Die ausdrucksbasierte Sortierung bietet leistungsfähigere und komplexere Sortierfunktionen als die einfachere zeichenfolgenbasierten Sortierung. Beachten Sie, dass sich die zeichenfolgenbasierte und die ausdrucksbasierte Sortierung gegenseitig ausschließen. Wenn mit <xref:System.Data.DataView.Sort%2A> die zeichenfolgenbasierte Sortierung festgelegt wird, nachdem eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt wurde, wird der ausdrucksbasierte Filter gelöscht, der aus der Abfrage abgeleitet wurde. Er kann dann nicht wiederhergestellt werden.  
  
 Der Index für eine <xref:System.Data.DataView> wird sowohl dann generiert, wenn die <xref:System.Data.DataView> erstellt wird, als auch dann, wenn Änderungen an den Sortier- oder Filterinformationen vorgenommen werden. Zur Vermeidung von Einbußen bei der Arbeitsgeschwindigkeit empfiehlt es sich, die Sortierkriterien bereits in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfrage anzugeben, auf deren Grundlage die <xref:System.Data.DataView> erstellt wird, und diese Sortierinformationen später nicht mehr zu ändern. Weitere Informationen finden Sie unter [DataView-Leistung](../../../../docs/framework/data/adonet/dataview-performance.md).  
  
> [!NOTE]
>  In den meisten Fällen dürften die für die Sortierung verwendeten Ausdrücke keine Nebenwirkungen haben. Sie müssen deterministisch sein. Die Ausdrücke dürfen darüber hinaus keine Logik enthalten, die auf einer festgelegten Anzahl von Ausführungen beruht, da die Sortieroperationen unbegrenzt oft ausgeführt werden können sollen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <legacyBold>SalesOrderHeader</legacyBold>-Tabelle abgefragt, und die zurückgegebenen Zeilen werden nach dem Auftragsdatum sortiert. Danach wird auf der Grundlage dieser Abfrage eine <xref:System.Data.DataView> erstellt. Die <xref:System.Data.DataView> wird anschließend an eine <xref:System.Windows.Forms.BindingSource> gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <legacyBold>SalesOrderHeader</legacyBold>-Tabelle abgefragt, und die zurückgegebene Zeile wird nach dem fälligen Gesamtbetrag sortiert. Danach wird auf der Grundlage dieser Abfrage eine <xref:System.Data.DataView> erstellt. Diese <xref:System.Data.DataView> wird anschließend an eine <xref:System.Windows.Forms.BindingSource> gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <legacyBold>SalesOrderDetail</legacyBold>-Tabelle abgefragt, und die zurückgegebenen Zeilen werden nach Bestellmenge und dann nach Auftrags-ID sortiert. Danach wird auf der Grundlage dieser Abfrage eine <xref:System.Data.DataView> erstellt. Diese <xref:System.Data.DataView> wird anschließend an eine <xref:System.Windows.Forms.BindingSource> gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>Verwenden der Eigenschaft für die zeichenfolgenbasierte Sortierung  
 Die <xref:System.Data.DataView>-Funktion zur zeichenfolgenbasierten Sortierung funktioniert auch mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] noch. Nachdem auf der Grundlage einer <xref:System.Data.DataView>-Abfrage eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] erstellt wurde, können Sie die <xref:System.Data.DataView.Sort%2A>-Eigenschaft verwenden, um die Sortierung für die <xref:System.Data.DataView> festzulegen.  
  
 Die zeichenfolgenbasierte und die ausdrucksbasierte Sortierung schließen sich gegenseitig aus. Durch die Einrichtung der <xref:System.Data.DataView.Sort%2A>-Eigenschaft wird die ausdrucksbasierte Sortierung gelöscht, die von der Abfrage geerbt wurde, auf der die <xref:System.Data.DataView> basiert.  
  
 Weitere Informationen zu zeichenfolgenbasierten <xref:System.Data.DataView.Sort%2A> Filtern finden Sie unter [sortieren und Filtern von Daten](../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird auf der Grundlage der <legacyBold>Contact</legacyBold>-Tabelle eine <xref:System.Data.DataView> erstellt. Anschließend werden die Zeilen nach dem Nachnamen in absteigender und dann nach dem Vornamen in aufsteigender Richtung sortiert:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel fragt die <legacyBold>Contact</legacyBold>-Tabelle nach Nachnamen ab, die mit dem Buchstaben "S" beginnen.  Auf der Grundlage dieser Abfrage wird eine <xref:System.Data.DataView> erstellt und an ein <xref:System.Windows.Forms.BindingSource>-Objekt gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a>Löschen der Sortierinformationen  
 Die Sortierinformationen für eine <xref:System.Data.DataView> können mit der <xref:System.Data.DataView.Sort%2A>-Eigenschaft gelöscht werden. Es gibt zwei Möglichkeiten, die Sortierinformationen in <xref:System.Data.DataView> zu löschen:  
  
-   Legen Sie die <xref:System.Data.DataView.Sort%2A>-Eigenschaft auf `null` fest.  
  
-   indem für die <xref:System.Data.DataView.Sort%2A>-Eigenschaft eine leere Zeichenfolge festgelegt wird  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt, und die Sortierinformationen werden gelöscht, indem für die <xref:System.Data.DataView.Sort%2A>-Eigenschaft eine leere Zeichenfolge festgelegt wird:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage der <legacyBold>Contact</legacyBold>-Tabelle erstellt und dann die <xref:System.Data.DataView.Sort%2A>-Eigenschaft so eingerichtet, dass die Ergebnisse in absteigender Reihenfolge nach dem Nachnamen sortiert werden. Anschließend werden die Sortierinformationen gelöscht, indem die <xref:System.Data.DataView.Sort%2A>-Eigenschaft auf `null` gesetzt wird:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbindung und LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 [Filtern mit DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 [Sortieren von Daten](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48)
