---
title: "Sortieren mit &#39;DataView&#39; (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Sortieren mit &#39;DataView&#39; (LINQ to DataSet)
Die Möglichkeit, Daten nach bestimmten Kriterien zu sortieren und dann über ein UI\-Steuerelement für einen Client bereitzustellen, ist ein wichtiger Aspekt der Datenbindung.  <xref:System.Data.DataView> bietet mehrere Möglichkeiten, Daten zu sortieren und nach bestimmten Sortierkriterien geordnete Datenzeilen zurückzugeben.  Neben den zeichenfolgenbasierten Sortierfunktionen bietet <xref:System.Data.DataView> auch die Möglichkeit, [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]\-Ausdrücke als Sortierkriterien zu verwenden. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Ausdrücke ermöglichen wesentlich komplexere und leistungsfähigere Sortieroperationen als die zeichenfolgenbasierte Sortierung.  In diesem Thema werden beide Ansätze für die Sortierung mit <xref:System.Data.DataView> beschrieben.  
  
## Erstellen einer "DataView" auf der Grundlage einer Abfrage mit Sortierinformationen  
 Ein <xref:System.Data.DataView>\-Objekt kann auf der Grundlage einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage erstellt werden.  Wenn diese Abfrage eine <xref:System.Linq.Enumerable.OrderBy%2A>\-, eine <xref:System.Linq.Enumerable.OrderByDescending%2A>\-, eine <xref:System.Linq.Enumerable.ThenBy%2A>\- oder eine <xref:System.Linq.Enumerable.ThenByDescending%2A>\-Klausel enthält, werden die Ausdrücke in diesen Klauseln als Basis für die Sortierung der Daten in der <xref:System.Data.DataView> verwendet.  Wenn die Abfrage z. B. die Klauseln `Order By…`und `Then By…` enthält, würden die Daten in der resultierenden <xref:System.Data.DataView> nach beiden angegebenen Spalten geordnet werden.  
  
 Die ausdrucksbasierte Sortierung bietet leistungsfähigere und komplexere Sortierfunktionen als die einfachere zeichenfolgenbasierten Sortierung.  Beachten Sie, dass sich die zeichenfolgenbasierte und die ausdrucksbasierte Sortierung gegenseitig ausschließen.  Wenn mit <xref:System.Data.DataView.Sort%2A> die zeichenfolgenbasierte Sortierung festgelegt wird, nachdem eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt wurde, wird der ausdrucksbasierte Filter gelöscht, der aus der Abfrage abgeleitet wurde. Er kann dann nicht wiederhergestellt werden.  
  
 Der Index für eine <xref:System.Data.DataView> wird sowohl dann generiert, wenn die <xref:System.Data.DataView> erstellt wird, als auch dann, wenn Änderungen an den Sortier\- oder Filterinformationen vorgenommen werden.  Zur Vermeidung von Einbußen bei der Arbeitsgeschwindigkeit empfiehlt es sich, die Sortierkriterien bereits in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage anzugeben, auf deren Grundlage die <xref:System.Data.DataView> erstellt wird, und diese Sortierinformationen später nicht mehr zu ändern.  Weitere Informationen finden Sie unter ['DataView'\-Arbeitsgeschwindigkeit](../../../../docs/framework/data/adonet/dataview-performance.md).  
  
> [!NOTE]
>  In den meisten Fällen dürften die für die Sortierung verwendeten Ausdrücke keine Nebenwirkungen haben. Sie müssen deterministisch sein.  Die Ausdrücke dürfen darüber hinaus keine Logik enthalten, die auf einer festgelegten Anzahl von Ausführungen beruht, da die Sortieroperationen unbegrenzt oft ausgeführt werden können sollen.  
  
### Beispiel  
 Im folgenden Beispiel wird die \<legacyBold\>SalesOrderHeader\<\/legacyBold\>\-Tabelle abgefragt, und die zurückgegebenen Zeilen werden nach dem Auftragsdatum sortiert. Danach wird auf der Grundlage dieser Abfrage eine <xref:System.Data.DataView> erstellt. Die <xref:System.Data.DataView> wird anschließend an eine <xref:System.Windows.Forms.BindingSource> gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### Beispiel  
 Im folgenden Beispiel wird die \<legacyBold\>SalesOrderHeader\<\/legacyBold\>\-Tabelle abgefragt, und die zurückgegebene Zeile wird nach dem fälligen Gesamtbetrag sortiert. Danach wird auf der Grundlage dieser Abfrage eine <xref:System.Data.DataView> erstellt. Diese <xref:System.Data.DataView> wird anschließend an eine <xref:System.Windows.Forms.BindingSource> gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### Beispiel  
 Im folgenden Beispiel wird die \<legacyBold\>SalesOrderDetail\<\/legacyBold\>\-Tabelle abgefragt, und die zurückgegebenen Zeilen werden nach Bestellmenge und dann nach Auftrags\-ID sortiert. Danach wird auf der Grundlage dieser Abfrage eine <xref:System.Data.DataView> erstellt. Diese <xref:System.Data.DataView> wird anschließend an eine <xref:System.Windows.Forms.BindingSource> gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## Verwenden der Eigenschaft für die zeichenfolgenbasierte Sortierung  
 Die <xref:System.Data.DataView>\-Funktion zur zeichenfolgenbasierten Sortierung funktioniert auch mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] noch.  Nachdem auf der Grundlage einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage eine <xref:System.Data.DataView> erstellt wurde, können Sie die <xref:System.Data.DataView.Sort%2A>\-Eigenschaft verwenden, um die Sortierung für die <xref:System.Data.DataView> festzulegen.  
  
 Die zeichenfolgenbasierte und die ausdrucksbasierte Sortierung schließen sich gegenseitig aus.  Durch die Einrichtung der <xref:System.Data.DataView.Sort%2A>\-Eigenschaft wird die ausdrucksbasierte Sortierung gelöscht, die von der Abfrage geerbt wurde, auf der die <xref:System.Data.DataView> basiert.  
  
 Weitere Informationen zur zeichenfolgenbasierten <xref:System.Data.DataView.Sort%2A>\-Filterung finden Sie unter [Sortieren und Filtern von Daten](../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
### Beispiel  
 Im folgenden Beispiel wird auf der Grundlage der \<legacyBold\>Contact\<\/legacyBold\>\-Tabelle eine <xref:System.Data.DataView> erstellt. Anschließend werden die Zeilen nach dem Nachnamen in absteigender und dann nach dem Vornamen in aufsteigender Richtung sortiert:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### Beispiel  
 Das folgende Beispiel fragt die \<legacyBold\>Contact\<\/legacyBold\>\-Tabelle nach Nachnamen ab, die mit dem Buchstaben "S" beginnen.  Auf der Grundlage dieser Abfrage wird eine <xref:System.Data.DataView> erstellt und an ein <xref:System.Windows.Forms.BindingSource>\-Objekt gebunden.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## Löschen der Sortierinformationen  
 Die Sortierinformationen für eine <xref:System.Data.DataView> können mit der <xref:System.Data.DataView.Sort%2A>\-Eigenschaft gelöscht werden.  Es gibt zwei Möglichkeiten, die Sortierinformationen in <xref:System.Data.DataView> zu löschen:  
  
-   Legen Sie die <xref:System.Data.DataView.Sort%2A>\-Eigenschaft auf `null` fest.  
  
-   indem für die <xref:System.Data.DataView.Sort%2A>\-Eigenschaft eine leere Zeichenfolge festgelegt wird  
  
### Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt, und die Sortierinformationen werden gelöscht, indem für die <xref:System.Data.DataView.Sort%2A>\-Eigenschaft eine leere Zeichenfolge festgelegt wird:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage der \<legacyBold\>Contact\<\/legacyBold\>\-Tabelle erstellt und dann die <xref:System.Data.DataView.Sort%2A>\-Eigenschaft so eingerichtet, dass die Ergebnisse in absteigender Reihenfolge nach dem Nachnamen sortiert werden.  Anschließend werden die Sortierinformationen gelöscht, indem die <xref:System.Data.DataView.Sort%2A>\-Eigenschaft auf `null` gesetzt wird:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## Siehe auch  
 [Datenbindung und LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)   
 [Filtern mit 'DataView'](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)   
 [Sorting Data](../../../../ocs/visual-basic/programming-guide/concepts/linq/sorting-data.md)