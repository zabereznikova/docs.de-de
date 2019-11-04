---
title: 'Gewusst wie: Filtern von Daten in einer Ansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: ea49897ca5e9cb6b639cf7d98ff05bd287c51761
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453486"
---
# <a name="how-to-filter-data-in-a-view"></a>Gewusst wie: Filtern von Daten in einer Ansicht
In diesem Beispiel wird gezeigt, wie Daten in einer Ansicht gefiltert werden.  
  
## <a name="example"></a>Beispiel  
 Zum Erstellen eines Filters definieren Sie eine Methode, die die Filter Logik bereitstellt. Die-Methode wird als Rückruf verwendet und akzeptiert einen Parameter vom Typ `object`. Die folgende Methode gibt alle `Order`-Objekte zurück, bei denen die `filled`-Eigenschaft auf "No" festgelegt ist, wobei die restlichen Objekte herausgefiltert werden.  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Sie können dann den Filter anwenden, wie im folgenden Beispiel gezeigt. In diesem Beispiel ist `myCollectionView` ein <xref:System.Windows.Data.ListCollectionView>-Objekt.  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Um das Filtern rückgängig zu machen, können Sie die <xref:System.Windows.Data.CollectionView.Filter%2A>-Eigenschaft auf `null`festlegen:  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Weitere Informationen zum Erstellen oder Abrufen einer Ansicht finden Sie unter Abrufen [der Standardansicht einer Datensammlung](how-to-get-the-default-view-of-a-data-collection.md). Das komplette Beispiel finden Sie unter [Sortieren und Filtern von Elementen in einem Ansichts](https://go.microsoft.com/fwlink/?LinkID=160040)Beispiel.  
  
 Wenn das View-Objekt aus einem <xref:System.Windows.Data.CollectionViewSource>-Objekt stammt, wenden Sie Filter Logik an, indem Sie einen Ereignishandler für das <xref:System.Windows.Data.CollectionViewSource.Filter>-Ereignis festlegen. Im folgenden Beispiel ist `listingDataView` eine Instanz von <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Der folgende Code zeigt die Implementierung des Beispiels `ShowOnlyBargainsFilter` Filter Ereignishandler. Dieser Ereignishandler verwendet die <xref:System.Windows.Data.FilterEventArgs.Accepted%2A>-Eigenschaft, um `AuctionItem` Objekte mit einem `CurrentPrice` von $25 oder höher herauszufiltern.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Sortieren von Daten in einer Ansicht](how-to-sort-data-in-a-view.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
