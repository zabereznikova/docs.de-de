---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten'
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
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0ef460664b3701f4942b8c28b8e39f891d7c871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
