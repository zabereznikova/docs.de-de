---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 5b3a9d83dcec169fd9607c84b0a66eab0098b238
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten
In diesem Beispiel wird gezeigt, wie das Master / Detail-Szenario mit implementiert [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Data-Version des Beispiels im erläutert [verwenden Sie das Master / Detail-Muster mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). In diesem Beispiel werden die Daten aus der Datei `League.xml`. Hinweis wie das dritte <xref:System.Windows.Controls.ListBox> -Steuerelement verfolgt Menüauswahl ändert sich in der zweiten <xref:System.Windows.Controls.ListBox> durch Bindung an ihre <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Eigenschaft.  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
