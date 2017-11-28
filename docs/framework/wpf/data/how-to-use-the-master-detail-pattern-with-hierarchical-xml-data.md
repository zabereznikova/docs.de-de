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
ms.openlocfilehash: 5b28a2220b5fc86654fe054deb9180450025f72f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="b3daf-102">Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="b3daf-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="b3daf-103">In diesem Beispiel wird gezeigt, wie das Master / Detail-Szenario mit implementiert [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.</span><span class="sxs-lookup"><span data-stu-id="b3daf-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3daf-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3daf-104">Example</span></span>  
 <span data-ttu-id="b3daf-105">In diesem Beispiel wird die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Data-Version des Beispiels im erläutert [verwenden Sie das Master / Detail-Muster mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="b3daf-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="b3daf-106">In diesem Beispiel werden die Daten aus der Datei `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="b3daf-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="b3daf-107">Hinweis wie das dritte <xref:System.Windows.Controls.ListBox> -Steuerelement verfolgt Menüauswahl ändert sich in der zweiten <xref:System.Windows.Controls.ListBox> durch Bindung an ihre <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b3daf-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="b3daf-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3daf-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="b3daf-109">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="b3daf-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
