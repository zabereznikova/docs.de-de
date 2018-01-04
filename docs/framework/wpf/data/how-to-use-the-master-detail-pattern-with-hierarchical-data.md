---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e392b47682d1bf53dc31073920bdf212fb7d997
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten
In diesem Beispiel wird gezeigt, wie das Master / Detail-Szenario implementiert wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `LeagueList` ist eine Sammlung von `Leagues`. Jede `League` verfügt über eine `Name` und eine Auflistung von `Divisions`, und jede `Division` hat einen Namen und eine Auflistung von `Teams`. Jede `Team` hat einen Teamnamen ein.  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Im Folgenden finden Sie ein Bildschirmfoto des Beispiels. Die `Divisions` <xref:System.Windows.Controls.ListBox> verfolgt automatisch die Auswahlmöglichkeiten in den `Leagues` <xref:System.Windows.Controls.ListBox> und zeigt entsprechende Daten. Die `Teams` <xref:System.Windows.Controls.ListBox> verfolgt die Auswahlmöglichkeiten in den anderen beiden <xref:System.Windows.Controls.ListBox> Steuerelemente.  
  
 ![Master &#45; Detail-Beispiel](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 Die zwei Punkte zu beachten in diesem Beispiel sind:  
  
1.  Die drei <xref:System.Windows.Controls.ListBox> Steuerelemente mit der gleichen Quelle zu binden. Festlegen der <xref:System.Windows.Data.Binding.Path%2A> -Eigenschaft der Bindung, um anzugeben, welche Stufe von Daten soll die <xref:System.Windows.Controls.ListBox> angezeigt.  
  
2.  Müssen Sie festlegen der <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` auf die <xref:System.Windows.Controls.ListBox> Steuerelemente, von denen die Auswahl, die Sie verfolgen. Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, es Auswahl und Währung automatisch synchronisiert.  
  
 Das Verfahren unterscheidet sich geringfügig bei Verwendung von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten. Ein Beispiel finden Sie unter [verwenden das Master / Detail-Musters mit hierarchischen XML-Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
