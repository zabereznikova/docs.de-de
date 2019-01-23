---
title: 'Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 4beb2377fa9740e5103df0a82cfda9bd5f6f4769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550067"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="915e9-102">Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="915e9-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="915e9-103">Dieses Beispiel zeigt, wie Sie das Master / Detail-Szenario mit implementieren [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.</span><span class="sxs-lookup"><span data-stu-id="915e9-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="915e9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="915e9-104">Example</span></span>  
 <span data-ttu-id="915e9-105">In diesem Beispiel wird die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Data-Version des Beispiels ausführlicher [verwenden Sie die Master-/ Detailmusters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="915e9-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="915e9-106">In diesem Beispiel werden die Daten aus der Datei sind `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="915e9-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="915e9-107">Hinweis wie die dritte <xref:System.Windows.Controls.ListBox> Steuerelement verfolgt die Änderungen der Auswahl in der zweiten <xref:System.Windows.Controls.ListBox> durch Bindung an die <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="915e9-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="915e9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="915e9-108">See also</span></span>
- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="915e9-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="915e9-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
