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
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="b3f43-102">Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="b3f43-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="b3f43-103">In diesem Beispiel wird gezeigt, wie das Master / Detail-Szenario mit implementiert [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.</span><span class="sxs-lookup"><span data-stu-id="b3f43-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3f43-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3f43-104">Example</span></span>  
 <span data-ttu-id="b3f43-105">In diesem Beispiel wird die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Data-Version des Beispiels im erläutert [verwenden Sie das Master / Detail-Muster mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="b3f43-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="b3f43-106">In diesem Beispiel werden die Daten aus der Datei `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="b3f43-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="b3f43-107">Hinweis wie das dritte <xref:System.Windows.Controls.ListBox> -Steuerelement verfolgt Menüauswahl ändert sich in der zweiten <xref:System.Windows.Controls.ListBox> durch Bindung an ihre <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b3f43-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="b3f43-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3f43-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="b3f43-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b3f43-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
