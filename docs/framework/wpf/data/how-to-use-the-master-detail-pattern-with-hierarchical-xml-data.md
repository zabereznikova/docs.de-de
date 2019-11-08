---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733415"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="46f26-102">Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten</span><span class="sxs-lookup"><span data-stu-id="46f26-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="46f26-103">Dieses Beispiel zeigt, wie das Master/Detail-Szenario mit XML-Daten implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="46f26-103">This example shows how to implement the master-detail scenario with XML data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46f26-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46f26-104">Example</span></span>  
 <span data-ttu-id="46f26-105">Dieses Beispiel ist die XML-Daten Version des Beispiels, das unter [Verwenden des Master/Detail-Musters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="46f26-105">This example is the XML data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="46f26-106">In diesem Beispiel werden die Daten aus der Datei `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="46f26-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="46f26-107">Beachten Sie, wie das dritte <xref:System.Windows.Controls.ListBox> Steuerelement die Auswahl Änderungen im zweiten <xref:System.Windows.Controls.ListBox> nachverfolgt, indem es an seine <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="46f26-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="46f26-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46f26-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="46f26-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="46f26-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
