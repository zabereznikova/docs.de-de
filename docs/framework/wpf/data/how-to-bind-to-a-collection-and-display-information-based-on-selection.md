---
title: 'Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl'
description: In diesem Beispiel erfahren Sie, wie Sie eine Bindung an eine Sammlung durchführen und Informationen basierend auf der Auswahl im Windows Presentation Foundation (WPF) anzeigen.
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
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619610"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl
In einem einfachen Master/Detail-Szenario verfügen Sie über eine Daten gebundene, <xref:System.Windows.Controls.ItemsControl> z <xref:System.Windows.Controls.ListBox> . b.. Basierend auf der Benutzer Auswahl zeigen Sie weitere Informationen über das ausgewählte Element an. In diesem Beispiel wird gezeigt, wie dieses Szenario implementiert wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `People` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von- `Person` Klassen. Diese `Person` Klasse enthält drei Eigenschaften: `FirstName` , `LastName` und `HomeTown` alle vom Typ `string` .  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Der <xref:System.Windows.Controls.ContentControl> verwendet Folgendes <xref:System.Windows.DataTemplate> , das definiert, wie die Informationen eines `Person` dargestellt werden:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Im folgenden finden Sie einen Screenshot der Ergebnisse des Beispiels. Die <xref:System.Windows.Controls.ContentControl> zeigt die anderen Eigenschaften der ausgewählten Person an.  
  
 ![Binden an eine Auflistung](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 In diesem Beispiel sind die folgenden zwei Punkte zu beachten:  
  
1. <xref:System.Windows.Controls.ListBox>Und die <xref:System.Windows.Controls.ContentControl> an dieselbe Quelle binden. Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften beider Bindungen werden nicht angegeben, weil beide Steuerelemente an das gesamte Sammlungsobjekt gebunden werden.  
  
2. Sie müssen die- <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft auf festlegen, damit `true` Dies funktioniert. Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als festgelegt ist <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> . Wenn die <xref:System.Windows.Controls.ListBox> Daten aus einem abruft, werden die <xref:System.Windows.Data.CollectionViewSource> Auswahl und die Währung Alternativ automatisch synchronisiert.  
  
 Beachten Sie, dass die-Klasse die- `Person` `ToString` Methode wie folgt überschreibt. Standardmäßig wird von <xref:System.Windows.Controls.ListBox> aufgerufen `ToString` und eine Zeichen folgen Darstellung der einzelnen Objekte in der gebundenen Auflistung angezeigt. Daher wird jeder `Person` als Vorname in der angezeigt <xref:System.Windows.Controls.ListBox> .  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden des Master/Detail-Musters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](data-templating-overview.md)
- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
