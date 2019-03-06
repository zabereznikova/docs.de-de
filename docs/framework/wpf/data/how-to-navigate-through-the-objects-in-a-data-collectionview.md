---
title: 'Vorgehensweise: Navigieren durch die Objekte in einer Datenauflistungsansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 9272a2f635a62abdac2746f2c8cce515812706f6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355778"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Vorgehensweise: Navigieren durch die Objekte in einer Datenauflistungsansicht
Sichten können die Datenerfassung auf unterschiedliche Weise je nach Sortierung, Filterung oder Gruppierung angezeigt werden. Ansichten auch ein Konzept für aktuellen Datensatz Zeiger bereitstellen und aktivieren Sie den Zeiger bewegen. Dieses Beispiel zeigt, wie Sie das aktuelle Objekt abgerufen sowie zum Navigieren durch die Objekte in einer Datensammlung, die die Funktion verwenden, der <xref:System.Windows.Data.CollectionView> Klasse.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `myCollectionView` ist eine <xref:System.Windows.Data.CollectionView> -Objekt, das eine Ansicht für eine gebundene Auflistung ist.  
  
 Im folgenden Beispiel `OnButton` ist ein Ereignishandler für die `Previous` und `Next` Schaltflächen in einer Anwendung, die Schaltflächen sind, mit denen den Benutzer die Datensammlung navigieren können. Beachten Sie, dass die <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> und <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> Eigenschaften Berichten, ob der Zeiger für der aktuelle Datensatz am Anfang und Ende der Liste also, das hat <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> und <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> kann je nach Bedarf aufgerufen werden.  
  
 Die <xref:System.Windows.Data.CollectionView.CurrentItem%2A> -Eigenschaft der Ansicht umgewandelt ist ein `Order` auf das aktuelle Element der Reihenfolge in der Auflistung zurückzugeben.  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Sortieren von Daten in einer Ansicht](how-to-sort-data-in-a-view.md)
- [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md)
- [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
