---
title: 'Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl'
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
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459145"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl
In einem einfachen Master/Detail-Szenario verfügen Sie über eine Daten gebundene <xref:System.Windows.Controls.ItemsControl> z. b. eine <xref:System.Windows.Controls.ListBox>. Basierend auf der Benutzer Auswahl zeigen Sie weitere Informationen über das ausgewählte Element an. In diesem Beispiel wird gezeigt, wie dieses Szenario implementiert wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist `People` ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `Person` Klassen. Diese `Person` Klasse enthält drei Eigenschaften: `FirstName`, `LastName`und `HomeTown`, alle vom Typ `string`.  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Der <xref:System.Windows.Controls.ContentControl> verwendet den folgenden <xref:System.Windows.DataTemplate>, der definiert, wie die Informationen eines `Person` dargestellt werden:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Im folgenden finden Sie einen Screenshot der Ergebnisse des Beispiels. In der <xref:System.Windows.Controls.ContentControl> werden die anderen Eigenschaften der ausgewählten Person angezeigt.  
  
 ![Binden an eine Sammlung](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 In diesem Beispiel sind die folgenden zwei Punkte zu beachten:  
  
1. Der <xref:System.Windows.Controls.ListBox> und das <xref:System.Windows.Controls.ContentControl> an dieselbe Quelle gebunden. Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften beider Bindungen werden nicht angegeben, weil beide Steuerelemente an das gesamte Sammlungsobjekt gebunden werden.  
  
2. Sie müssen die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>-Eigenschaft auf `true` festlegen, damit dies funktioniert. Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>festgelegt ist. Wenn das <xref:System.Windows.Controls.ListBox> die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>abruft, werden die Auswahl und die Währung Alternativ automatisch synchronisiert.  
  
 Beachten Sie, dass die `Person`-Klasse die `ToString`-Methode wie folgt überschreibt. Standardmäßig ruft der <xref:System.Windows.Controls.ListBox> `ToString` auf und zeigt eine Zeichen folgen Darstellung jedes Objekts in der gebundenen Auflistung an. Aus diesem Grund wird jede `Person` als Vorname in der <xref:System.Windows.Controls.ListBox>angezeigt.  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden des Master-/Detailmusters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](data-templating-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
