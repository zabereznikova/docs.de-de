---
title: 'Vorgehensweise: Sortieren von Daten in einer Ansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 41ee5cded04559acac5e7270c5e1a2450c70a5aa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377118"
---
# <a name="how-to-sort-data-in-a-view"></a>Vorgehensweise: Sortieren von Daten in einer Ansicht
In diesem Beispiel wird das Sortieren von Daten in einer Ansicht beschreibt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine einfache <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der Schaltfläche enthält Logik zum Sortieren der Elemente in der <xref:System.Windows.Controls.ListBox> in absteigender Reihenfolge. Hierzu können Sie da Hinzufügen von Elementen auf eine <xref:System.Windows.Controls.ListBox> auf diese Weise hinzugefügt der <xref:System.Windows.Controls.ItemCollection> von der <xref:System.Windows.Controls.ListBox>, und <xref:System.Windows.Controls.ItemCollection> leitet sich von der <xref:System.Windows.Data.CollectionView> Klasse. Wenn die Bindung wird Ihrer <xref:System.Windows.Controls.ListBox> zu einer Auflistung mithilfe der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft, können Sie das gleiche Verfahren zum Sortieren verwenden.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Solange Sie einen Verweis auf das Objekt haben, können Sie das gleiche Verfahren, zum Sortieren des Inhalts einer anderen sammlungsansichten. Ein Beispiel, wie Sie eine Ansicht zu erhalten, finden Sie unter [Abrufen der Standardansicht einer datenauflistung](how-to-get-the-default-view-of-a-data-collection.md). Ein weiteres Beispiel finden Sie unter [Sortieren einer GridView Spalte bei der ein Header geklickt wird](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Weitere Informationen zu Ansichten finden Sie unter Binden an Auflistungen in [Übersicht über die Datenbindung](data-binding-overview.md).  
  
 Ein Beispiel für die Sortierfunktionen in anwenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], finden Sie unter [sortieren und Daten mithilfe einer Ansicht in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
