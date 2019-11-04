---
title: 'Gewusst wie: Sortieren von Daten in einer Ansicht'
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
ms.openlocfilehash: 14314ed019f9194a657787bd767ae68615e94ac7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454824"
---
# <a name="how-to-sort-data-in-a-view"></a>Gewusst wie: Sortieren von Daten in einer Ansicht
In diesem Beispiel wird beschrieben, wie Daten in einer Ansicht sortiert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden eine einfache <xref:System.Windows.Controls.ListBox> und eine <xref:System.Windows.Controls.Button>erstellt:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignishandler der Schaltfläche enthält Logik zum Sortieren der Elemente in der <xref:System.Windows.Controls.ListBox> in absteigender Reihenfolge. Dies ist möglich, weil Sie Elemente zu einem <xref:System.Windows.Controls.ListBox> hinzufügen, um diese auf diese Weise dem <xref:System.Windows.Controls.ItemCollection> des <xref:System.Windows.Controls.ListBox>hinzuzufügen, und <xref:System.Windows.Controls.ItemCollection> von der <xref:System.Windows.Data.CollectionView> Klasse abgeleitet ist. Wenn Sie die <xref:System.Windows.Controls.ListBox> mit der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>-Eigenschaft an eine Sammlung binden, können Sie das gleiche Verfahren für die Sortierung verwenden.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Solange Sie über einen Verweis auf das Ansichts Objekt verfügen, können Sie das gleiche Verfahren verwenden, um den Inhalt anderer Auflistungs Ansichten zu sortieren. Ein Beispiel zum Abrufen einer Ansicht finden Sie unter Abrufen [der Standardansicht einer Datensammlung](how-to-get-the-default-view-of-a-data-collection.md). Ein weiteres Beispiel finden Sie unter [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Weitere Informationen zu Ansichten finden Sie unterbinden an Auflistungen in der Übersicht über die [Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).  
  
 Ein Beispiel für das Anwenden von Sortier Logik in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]finden Sie unter [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
