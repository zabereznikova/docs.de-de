---
title: "Erstellen eines &#39;DataView&#39;-Objekts (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Erstellen eines &#39;DataView&#39;-Objekts (LINQ to DataSet)
Es gibt zwei Möglichkeiten, im [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Kontext eine <xref:System.Data.DataView> zu erstellen.  Sie können das <xref:System.Data.DataView>\-Objekt auf der Grundlage einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage einer <xref:System.Data.DataTable> erstellen, oder Sie können es auf der Grundlage einer typisierten oder nicht typisierten <xref:System.Data.DataTable> erstellen.  In beiden Fällen erstellen Sie die <xref:System.Data.DataView> mithilfe einer der <xref:System.Data.DataTableExtensions.AsDataView%2A>\-Erweiterungsmethoden. Im [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Kontext ist es nicht möglich, <xref:System.Data.DataView>\-Objekte direkt und ohne Grundlage zu konstruieren.  
  
 Nachdem die <xref:System.Data.DataView> erstellt wurde, können Sie sie an ein Benutzeroberflächensteuerelement in einer Windows Forms\-Anwendung oder einer ASP.NET\-Anwendung binden oder die Filter\- und Sortiereinstellungen ändern.  
  
 <xref:System.Data.DataView> erstellt einen Index, der bei Operationen, die diesen Index einsetzen können, wie beim Filtern und Sortieren, zu beträchtlichen Leistungssteigerungen führt.  Der Index für eine <xref:System.Data.DataView> wird sowohl dann generiert, wenn die <xref:System.Data.DataView> erstellt wird, als auch dann, wenn Änderungen an den Sortier\- oder Filterinformationen vorgenommen werden.  Wenn Sie eine <xref:System.Data.DataView> erstellen, ohne gleich auch die Sortier\- und Filterinformationen festzulegen, wird der Index mindestens zweimal generiert: das erste Mal, wenn die <xref:System.Data.DataView> erstellt wird, und das zweite Mal, sobald eine der Sortier\- oder Filtereigenschaften geändert wird.  
  
 Weitere Informationen zum Filtern und Sortieren mit <xref:System.Data.DataView> finden Sie unter [Filtern mit 'DataView'](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) und [Sortieren mit 'DataView'](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).  
  
## Erstellen einer "DataView" auf der Grundlage einer LINQ to DataSet\-Abfrage  
 Ein <xref:System.Data.DataView>\-Objekt kann auf der Grundlage der Ergebnisse einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage erstellt werden, wobei es sich bei den Ergebnissen um eine Projektion von <xref:System.Data.DataRow>\-Objekten handelt.  Die neu erstellte <xref:System.Data.DataView> erbt die Filter\- und Sortierinformationen von der Abfrage, auf deren Grundlage sie erstellt wurde.  
  
> [!NOTE]
>  In den meisten Fällen haben die für die Filterung und Sortierung verwendeten Ausdrücke keine Nebenwirkungen. Sie müssen deterministisch sein.  Die Ausdrücke dürfen darüber hinaus keine Logik enthalten, die auf einer festgelegten Anzahl von Ausführungen beruht, da die Sortier\- und Filteroperationen unbegrenzt oft ausgeführt werden können sollen.  
  
 Das Erstellen einer <xref:System.Data.DataView> auf der Grundlage einer Abfrage, die anonyme Typen oder Abfragen zurückgibt, die ihrerseits Joins ausführen, wird nicht unterstützt.  
  
 In einer Abfrage, die die Grundlage für eine <xref:System.Data.DataView> bilden soll, werden nur die folgenden Abfrageoperatoren unterstützt:  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 Beachten Sie, dass beim Erstellen einer <xref:System.Data.DataView> durch eine [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage die <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>\-Methode die letzte in der Abfrage aufgerufene Methode sein muss. Dies wird im folgenden Beispiel verdeutlicht, bei dem eine <xref:System.Data.DataView> von Onlinebestellungen erstellt wird, die nach Gesamtbetrag sortiert sind:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 Sie können auch die zeichenfolgenbasierten Eigenschaften <xref:System.Data.DataView.RowFilter%2A> und <xref:System.Data.DataView.Sort%2A> verwenden, um die Einträge in einer <xref:System.Data.DataView> zu filtern und zu sortieren, die auf der Grundlage einer Abfrage erstellt wurde.  Beachten Sie, dass dabei die von der Abfrage geerbten Sortierungs\- und Filterinformationen gelöscht werden.  Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage erstellt, bei der nur die Einträge angezeigt werden, bei denen der Nachname mit "S" beginnt.  Die zeichenfolgenbasierte <xref:System.Data.DataView.Sort%2A>\-Eigenschaft ist so eingerichtet, dass die Nachnamen in aufsteigender Reihenfolge und dann die Vornamen in absteigender Reihenfolge sortiert werden:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## Erstellen einer "DataView" aus einer "DataTable"  
 Ein <xref:System.Data.DataView>\-Objekt kann nicht nur auf der Grundlage einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfrage erstellt werden, sondern auch auf der Grundlage einer <xref:System.Data.DataTable>, wobei die <xref:System.Data.DataTableExtensions.AsDataView%2A>\-Methode zum Einsatz kommt.  
  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage der \<legacyBold\>SalesOrderDetail\<\/legacyBold\>\-Tabelle erstellt und dann als Datenquelle eines <xref:System.Windows.Forms.BindingSource>\-Objekts festgelegt.  Dieses Objekt fungiert als Proxy für ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 Nachdem die <xref:System.Data.DataView> auf der Grundlage einer <xref:System.Data.DataTable> erstellt wurde, können Filter\- und Sortiereigenschaften für sie festgelegt werden.  Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage der \<legacyBold\>Contact\<\/legacyBold\>\-Tabelle erstellt und dann die <xref:System.Data.DataView.Sort%2A>\-Eigenschaft so eingerichtet, dass die Nachnamen in aufsteigender und dann die Vornamen in absteigender Reihenfolge sortiert werden:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 Wenn die <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt wurde, kommt es jedoch beim Einrichten der Eigenschaft <xref:System.Data.DataView.RowFilter%2A> bzw. <xref:System.Data.DataView.Sort%2A> zu einem Leistungsabfall, weil <xref:System.Data.DataView> einen Index generiert, um die Filter\- und Sortieroperationen zu unterstützen.  Wenn Sie die Eigenschaft <xref:System.Data.DataView.RowFilter%2A> oder <xref:System.Data.DataView.Sort%2A> festlegen, wird der Index für die Daten neu erstellt, wodurch zusätzlicher Verwaltungsmehraufwand für die Anwendung entsteht und die Arbeitsgeschwindigkeit verringert wird.  Es ist daher empfehlenswert, die Filter\- und Sortierinformationen schon beim Erstellen der <xref:System.Data.DataView> einzurichten und nachträgliche Änderungen zu vermeiden.  
  
## Siehe auch  
 [Datenbindung und LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)   
 [Filtern mit 'DataView'](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)   
 [Sortieren mit 'DataView'](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)