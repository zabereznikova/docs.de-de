---
title: 'Gewusst wie: Sicherstellen, dass ein GridSplitter sichtbar ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 926df118bfd8e7ab3d1f0c953d0b6debafd59073
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554819"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="870d3-102">Gewusst wie: Sicherstellen, dass ein GridSplitter sichtbar ist</span><span class="sxs-lookup"><span data-stu-id="870d3-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="870d3-103">Dieses Beispiel zeigt, wie Sie sicherstellen, eine <xref:System.Windows.Controls.GridSplitter> -Steuerelement nicht ausgeblendet ist, durch den andere Steuerelemente in einem <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="870d3-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="870d3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="870d3-104">Example</span></span>  
 <span data-ttu-id="870d3-105">Die <xref:System.Windows.Controls.Panel.Children%2A> von einem <xref:System.Windows.Controls.Grid> Steuerelement gerendert werden, in der Reihenfolge, in der sie im Markup oder-Code definiert sind.</span><span class="sxs-lookup"><span data-stu-id="870d3-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="870d3-106"><xref:System.Windows.Controls.GridSplitter> Steuerelemente können von anderen Steuerelementen ausgeblendet werden, wenn Sie diese nicht als die letzten Elemente im Definieren der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung oder wenn Sie anderen Steuerelementen einen höheren <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="870d3-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="870d3-107">Um zu verhindern, dass ausgeblendete <xref:System.Windows.Controls.GridSplitter> Steuerelemente, führen Sie eine der folgenden.</span><span class="sxs-lookup"><span data-stu-id="870d3-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="870d3-108">Stellen Sie sicher, dass <xref:System.Windows.Controls.GridSplitter> Steuerelemente werden als letzte <xref:System.Windows.Controls.Panel.Children%2A> hinzugefügt, um die <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="870d3-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="870d3-109">Das folgende Beispiel zeigt die <xref:System.Windows.Controls.GridSplitter> als das letzte Element in der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von der <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="870d3-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="870d3-110">Legen Sie die <xref:System.Windows.Controls.Panel.ZIndexProperty> auf die <xref:System.Windows.Controls.GridSplitter> höher als ein Steuerelement sein, die andernfalls ausblendet.</span><span class="sxs-lookup"><span data-stu-id="870d3-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="870d3-111">Das folgende Beispiel gibt die <xref:System.Windows.Controls.GridSplitter> steuern eine höhere <xref:System.Windows.Controls.Panel.ZIndexProperty> als die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="870d3-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="870d3-112">Legen Sie Seitenränder für das Steuerelement, das andernfalls verdecken würde die <xref:System.Windows.Controls.GridSplitter> , damit die <xref:System.Windows.Controls.GridSplitter> verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="870d3-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="870d3-113">Im folgenden Beispiel wird die Ränder auf ein Steuerelement, das andernfalls überlagert würde und Ausblenden der <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="870d3-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="870d3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="870d3-114">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="870d3-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="870d3-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
