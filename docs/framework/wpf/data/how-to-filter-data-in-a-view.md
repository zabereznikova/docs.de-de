---
title: 'Gewusst wie: Filtern von Daten in einer Ansicht'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17b7fc68319552a7b31d5eaf7826146de5c41aa5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-filter-data-in-a-view"></a>Gewusst wie: Filtern von Daten in einer Ansicht
Dieses Beispiel zeigt, wie Daten in einer Ansicht zu filtern.  
  
## <a name="example"></a>Beispiel  
 Um einen Filter zu erstellen, definieren Sie eine Methode, die die Filterlogik bereitstellt. Die Methode wird als Rückruf verwendet und akzeptiert einen Parameter vom Typ `object`. Die folgende Methode gibt alle dem `Order` Objekte mit der `filled` -Eigenschaft auf "Nein", die übrigen Objekte herausfiltern.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Sie können dann den Filter anwenden, wie im folgenden Beispiel gezeigt. In diesem Beispiel `myCollectionView` ist ein <xref:System.Windows.Data.ListCollectionView> Objekt.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Um die Filterung rückgängig zu machen, können Sie festlegen der <xref:System.Windows.Data.CollectionView.Filter%2A> Eigenschaft `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Informationen zum Erstellen oder Abrufen einer Ansicht finden Sie unter [die Standardansicht einer Datensammlung erhalten](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Das vollständige Beispiel finden Sie unter [sortieren und Filtern von Elementen in einer Viewer-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Wenn das Ansichtsobjekt stammen eine <xref:System.Windows.Data.CollectionViewSource> -Objekts können Sie Filterlogik anwenden, indem ein Ereignishandler für das Festlegen der <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignis. Im folgenden Beispiel `listingDataView` ist eine Instanz der <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Nachstehend sehen Sie die Implementierung des Beispiels `ShowOnlyBargainsFilter` Filter-Ereignishandler. Dieser Ereignishandler verwendet die <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> Eigenschaft filtern `AuctionItem` Objekte mit einem `CurrentPrice` $25 oder mehr.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>  
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
