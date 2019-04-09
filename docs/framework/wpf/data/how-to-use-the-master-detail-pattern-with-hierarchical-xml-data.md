---
title: 'Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: ba6c932f519ffa5c3c70ecb21eb9b5d08c40fb28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086259"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="a2d78-102">Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="a2d78-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="a2d78-103">Dieses Beispiel zeigt, wie Sie das Master / Detail-Szenario mit implementieren [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.</span><span class="sxs-lookup"><span data-stu-id="a2d78-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2d78-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2d78-104">Example</span></span>  
 <span data-ttu-id="a2d78-105">In diesem Beispiel wird die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Data-Version des Beispiels ausführlicher [verwenden Sie die Master-/ Detailmusters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="a2d78-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="a2d78-106">In diesem Beispiel werden die Daten aus der Datei sind `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="a2d78-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="a2d78-107">Hinweis wie die dritte <xref:System.Windows.Controls.ListBox> Steuerelement verfolgt die Änderungen der Auswahl in der zweiten <xref:System.Windows.Controls.ListBox> durch Bindung an die <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a2d78-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="a2d78-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2d78-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="a2d78-109">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="a2d78-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
