---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 2e7d9ceed3ab8385f07d87ecdb92c0a99d410b40
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459084"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten
Dieses Beispiel zeigt, wie das Master/Detail-Szenario implementiert wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist `LeagueList` eine Auflistung von `Leagues`. Jede `League` verfügt über eine `Name` und eine Auflistung von `Divisions`, und jede `Division` hat einen Namen und eine Auflistung `Teams`. Jede `Team` hat einen Teamnamen.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Im Folgenden finden Sie ein Bildschirmfoto des Beispiels. Der `Divisions` <xref:System.Windows.Controls.ListBox> die Auswahl im `Leagues` <xref:System.Windows.Controls.ListBox> automatisch nachverfolgt, und die entsprechenden Daten werden angezeigt. Der `Teams` <xref:System.Windows.Controls.ListBox> die Auswahl in den beiden anderen <xref:System.Windows.Controls.ListBox>-Steuerelementen nachverfolgt.  
  
 ![Screenshot, der ein Beispiel&#45;für ein Master Detail Szenario anzeigt.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 In diesem Beispiel sind die folgenden zwei Punkte zu beachten:  
  
1. Die drei <xref:System.Windows.Controls.ListBox>-Steuerelemente werden an dieselbe Quelle gebunden. Legen Sie die <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft der Bindung auf fest, um anzugeben, welche Datenebene für die <xref:System.Windows.Controls.ListBox> angezeigt werden soll.  
  
2. Sie müssen die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>-Eigenschaft auf `true` für die <xref:System.Windows.Controls.ListBox> Steuerelemente festlegen, deren Auswahl Sie nachverfolgen. Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>festgelegt ist. Wenn das <xref:System.Windows.Controls.ListBox> die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>abruft, werden die Auswahl und die Währung Alternativ automatisch synchronisiert.  
  
 Das Verfahren unterscheidet sich geringfügig, wenn Sie [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten verwenden. Ein Beispiel finden Sie unter [Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.HierarchicalDataTemplate>
- [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](data-templating-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
