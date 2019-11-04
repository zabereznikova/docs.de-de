---
title: 'Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 5ca386db89dcaa66d364d2ed7169c67393cebead
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459705"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht
Sichten ermöglichen, dass dieselbe Datensammlung in Abhängigkeit von Sortierung, Filterung oder Gruppierung auf verschiedene Weise angezeigt wird. Sichten stellen auch ein Aktuelles Datensatz-Zeiger Konzept bereit und ermöglichen das Verschieben des Zeigers. Dieses Beispiel zeigt, wie das aktuelle-Objekt und die Objekte in einer Datensammlung mithilfe der in der <xref:System.Windows.Data.CollectionView>-Klasse bereitgestellten Funktionalität angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist `myCollectionView` ein <xref:System.Windows.Data.CollectionView> Objekt, das eine Ansicht über eine gebundene Auflistung ist.  
  
 Im folgenden Beispiel ist `OnButton` ein Ereignishandler für die Schaltflächen `Previous` und `Next` in einer Anwendung, die Schaltflächen sind, mit denen der Benutzer in der Datensammlung navigieren kann. Beachten Sie, dass die Eigenschaften <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> und <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> melden, ob der aktuelle Daten Satz Zeiger am Anfang und am Ende der Liste steht, sodass <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> und <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> entsprechend aufgerufen werden können.  
  
 Die <xref:System.Windows.Data.CollectionView.CurrentItem%2A>-Eigenschaft der Sicht wird als `Order` umgewandelt, um das aktuelle Bestell Element in der Auflistung zurückzugeben.  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Sortieren von Daten in einer Ansicht](how-to-sort-data-in-a-view.md)
- [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md)
- [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
