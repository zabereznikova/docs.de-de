---
title: 'Vorgehensweise: Filtern von Daten in einer Ansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: a31c07e6be26f67cc29813a14745ecf4a83ab98a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147471"
---
# <a name="how-to-filter-data-in-a-view"></a>Vorgehensweise: Filtern von Daten in einer Ansicht
Dieses Beispiel zeigt, wie Sie Daten in einer Ansicht zu filtern.  
  
## <a name="example"></a>Beispiel  
 Um einen Filter zu erstellen, definieren Sie eine Methode, die Filterlogik bereitstellt. Die Methode, die als Rückruf verwendet wird, und akzeptiert einen Parameter vom Typ `object`. Die folgende Methode gibt alle der `Order` Objekte mit der `filled` -Eigenschaft auf "Nein" können die restlichen Objekte filtern.  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Sie können dann den Filter anwenden, wie im folgenden Beispiel gezeigt. In diesem Beispiel `myCollectionView` ist eine <xref:System.Windows.Data.ListCollectionView> Objekt.  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Um die Filterung rückgängig zu machen, Sie können festlegen, die <xref:System.Windows.Data.CollectionView.Filter%2A> Eigenschaft `null`:  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Weitere Informationen zum Erstellen oder eine Ansicht zu erhalten, finden Sie unter [Abrufen der Standardansicht einer datenauflistung](how-to-get-the-default-view-of-a-data-collection.md). Das vollständige Beispiel finden Sie unter [sortieren und Filtern von Elementen in einem Beispiel für die Ansicht](https://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Wenn Ihr Objekt stammt eine <xref:System.Windows.Data.CollectionViewSource> -Objekts können Sie Filterlogik anwenden, indem Sie einen Ereignishandler für das Festlegen der <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignis. Im folgenden Beispiel `listingDataView` ist eine Instanz der <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Das folgende Beispiel zeigt die Implementierung des Beispiels `ShowOnlyBargainsFilter` Filter-Ereignishandler. Dieser Ereignishandler verwendet die <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> Eigenschaft filtern, die `AuctionItem` Objekte mit einer `CurrentPrice` von 25 $ oder höher.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Übersicht über die Datenbindung](data-binding-overview.md)
- [Sortieren von Daten in einer Ansicht](how-to-sort-data-in-a-view.md)
- [Gewusst wie-Themen](data-binding-how-to-topics.md)
