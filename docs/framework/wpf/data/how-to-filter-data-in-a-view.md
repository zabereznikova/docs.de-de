---
title: "Gewusst wie: Filtern von Daten in einer Ansicht | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenbindung, Filtern von Daten Daten in Ansichten"
  - "Filtern von Daten Daten in Ansichten"
  - "Ansichten, Filtern von Daten"
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Filtern von Daten in einer Ansicht
Dieses Beispiel zeigt, wie Daten in einer Ansicht gefiltert werden.  
  
## Beispiel  
 Um einen Filter zu erstellen, definieren Sie eine Methode, die die Filterlogik bereitstellt.  Die Methode wird als Rückruf verwendet und akzeptiert einen Parameter vom Typ `object`.  Die folgende Methode gibt alle `Order`\-Objekte zurück, deren `filled`\-Eigenschaft auf "No" festgelegt ist. Der Rest der Objekte wird herausgefiltert.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Sie können dann den Filter anwenden, wie im folgenden Beispiel gezeigt.  In diesem Beispiel ist `myCollectionView` ein <xref:System.Windows.Data.ListCollectionView>\-Objekt.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Um die Filterung rückgängig zu machen, können Sie die <xref:System.Windows.Data.CollectionView.Filter%2A>\-Eigenschaft auf `null` festlegen:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Informationen über das Erstellen oder Abrufen einer Ansicht finden Sie unter [Abrufen der Standardansicht einer Datenauflistung](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  Das vollständige Beispiel finden Sie unter [Beispiel zum Sortieren und Filtern von Elementen in einer Ansicht](http://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Wenn das Ansichtsobjekt aus einem <xref:System.Windows.Data.CollectionViewSource>\-Objekt stammt, wenden Sie Filterlogik an, indem Sie einen Ereignishandler für das <xref:System.Windows.Data.CollectionViewSource.Filter>\-Ereignis festlegen.  Im folgenden Beispiel ist `listingDataView` eine Instanz von <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Im Folgenden wird die Implementierung des Beispiels für den `ShowOnlyBargainsFilter`\-Filterereignishandler veranschaulicht.  Dieser Ereignishandler filtert anhand der <xref:System.Windows.Data.FilterEventArgs.Accepted%2A>\-Eigenschaft die `AuctionItem`\-Objekte heraus, deren `CurrentPrice` 25 $ oder mehr beträgt.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## Siehe auch  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>   
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)