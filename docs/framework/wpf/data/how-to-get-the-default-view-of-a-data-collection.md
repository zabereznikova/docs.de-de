---
title: 'Gewusst wie: Abrufen der Standardansicht einer Datenauflistung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459118"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Gewusst wie: Abrufen der Standardansicht einer Datenauflistung
In Sichten kann die gleiche Datensammlung je nach Sortier-, Filter-oder Gruppierungs Kriterien auf unterschiedliche Weise angezeigt werden. Jede Sammlung verfügt über eine freigegebene Standardansicht, die als tatsächliche Bindungs Quelle verwendet wird, wenn eine Bindung eine Auflistung als Quelle angibt. Dieses Beispiel zeigt, wie Sie die Standardansicht einer Auflistung erhalten.  
  
## <a name="example"></a>Beispiel  
 Um die Ansicht zu erstellen, benötigen Sie einen Objekt Verweis auf die Auflistung. Dieses Datenobjekt kann abgerufen werden, indem Sie auf Ihr eigenes Code-Behind-Objekt verweisen, indem Sie den Datenkontext erhalten, indem Sie eine Eigenschaft der Datenquelle erhalten oder eine Eigenschaft der Bindung erhalten. Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.FrameworkElement.DataContext%2A> eines Datenobjekts abrufen und verwenden können, um die Standard Auflistungs Ansicht für diese Auflistung direkt abzurufen.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In diesem Beispiel ist das Stamm Element eine <xref:System.Windows.Controls.StackPanel>. Der <xref:System.Windows.FrameworkElement.DataContext%2A> wird auf *MyDatasource*festgelegt, was auf einen Datenanbieter verweist, bei dem es sich um einen <xref:System.Collections.ObjectModel.ObservableCollection%601> von *Order* -Objekten handelt.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Alternativ können Sie mit der <xref:System.Windows.Data.CollectionViewSource>-Klasse instanziieren und an Ihre eigene Auflistungs Ansicht binden. Diese Auflistungs Ansicht wird nur von Steuerelementen gemeinsam genutzt, die direkt an Sie gebunden werden. Ein Beispiel finden Sie im Abschnitt How to Create a View in der [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).  
  
 Beispiele für die von einer Auflistungs Ansicht bereitgestellte Funktionalität finden Sie unter [Sortieren von Daten in einer Ansicht](how-to-sort-data-in-a-view.md), [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md)und [Navigieren durch die Objekte in einer Daten CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
