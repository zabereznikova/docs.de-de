---
title: 'Vorgehensweise: Binden an eine Sammlung und Anzeigen von Informationen auf Grundlage der Auswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: bb7d4c89e63982a3052857dcb50d04d36d9517dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314390"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Vorgehensweise: Binden an eine Sammlung und Anzeigen von Informationen auf Grundlage der Auswahl
In einem einfachen Master / Detail-Szenario haben Sie ein datengebundenes <xref:System.Windows.Controls.ItemsControl> wie z. B. eine <xref:System.Windows.Controls.ListBox>. Auf Grundlage der Benutzerauswahl, zeigen Sie weitere Informationen zum ausgewählten Element. Dieses Beispiel zeigt, wie Sie dieses Szenario zu implementieren.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `People` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `Person` Klassen. Dies `Person` -Klasse enthält drei Eigenschaften: `FirstName`, `LastName`, und `HomeTown`, alle Typ `string`.  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Die <xref:System.Windows.Controls.ContentControl> verwendet die folgenden <xref:System.Windows.DataTemplate> , definiert, wie die Informationen des eine `Person` wird angezeigt:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Folgendes ist ein Screenshot der Ausgabe des Beispiels. Die <xref:System.Windows.Controls.ContentControl> zeigt die anderen Eigenschaften der ausgewählten Person.  
  
 ![Binden an eine Auflistung](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 Die beiden in diesem Beispiel sind zu beachten:  
  
1. Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ContentControl> an dieselbe Quelle binden. Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften beide Bindungen sind nicht angegeben werden, da beide Steuerelemente an das gesamte Objekt gebunden werden.  
  
2. Sie müssen festlegen, die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` damit dies funktioniert. Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, diese Auswahl und Aktualität wird automatisch synchronisiert.  
  
 Beachten Sie, dass die `Person` -Klasse überschreibt die `ToString` Methode wie folgt. In der Standardeinstellung die <xref:System.Windows.Controls.ListBox> Aufrufe `ToString` und eine Zeichenfolgendarstellung der einzelnen Objekte in der gebundenen Auflistung angezeigt. Deshalb jedes `Person` wird als einen Vornamen in der <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden des Master-/Detailmusters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Übersicht über Datenvorlagen](data-templating-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
