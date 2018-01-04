---
title: 'Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a751025470b566ef1e735e4ddd192cfd8fc354ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Gewusst wie: Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl
In einem einfachen Master / Detail-Szenario haben Sie ein datengebundenes <xref:System.Windows.Controls.ItemsControl> wie z. B. eine <xref:System.Windows.Controls.ListBox>. Basierend auf der Auswahl des Benutzers, zeigen Sie weitere Informationen zum ausgewählten Element. In diesem Beispiel wird gezeigt, wie dieses Szenario implementiert wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `People` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `Person` Klassen. Dies `Person` Klasse enthält drei Eigenschaften: `FirstName`, `LastName`, und `HomeTown`, alle vom Typ `string`.  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Die <xref:System.Windows.Controls.ContentControl> verwendet die folgenden <xref:System.Windows.DataTemplate> , definiert, wie die Informationen des ein `Person` wird angezeigt:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Im folgenden finden einen Screenshot der Ausgabe des Beispiels. Die <xref:System.Windows.Controls.ContentControl> zeigt die anderen Eigenschaften der ausgewählten Person.  
  
 ![Binden an eine Auflistung](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 Die zwei Punkte zu beachten in diesem Beispiel sind:  
  
1.  Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ContentControl> mit der gleichen Quelle zu binden. Die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften der beiden Bindungen sind nicht angegeben werden, da beide Steuerelemente an das gesamte Collection-Objekt gebunden werden.  
  
2.  Sie müssen festlegen, die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` damit dies funktioniert. Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, es Auswahl und Währung automatisch synchronisiert.  
  
 Beachten Sie, dass die `Person` -Klasse überschreibt die `ToString` Methode wie folgt. Wird standardmäßig die <xref:System.Windows.Controls.ListBox> Aufrufe `ToString` und eine Zeichenfolgendarstellung für jedes Objekt in der gebundenen Auflistung angezeigt. Deshalb jedes `Person` erscheint als erste Name in der <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden des Master-/Detailmusters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
