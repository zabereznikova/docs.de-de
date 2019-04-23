---
title: 'Vorgehensweise: Sicherstellen, dass ein GridSplitter sichtbar ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147146"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="94fa1-102">Vorgehensweise: Sicherstellen, dass ein GridSplitter sichtbar ist</span><span class="sxs-lookup"><span data-stu-id="94fa1-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="94fa1-103">Dieses Beispiel zeigt, wie Sie sicherstellen, eine <xref:System.Windows.Controls.GridSplitter> Steuerelement wird nicht von den anderen Steuerelementen im ausgeblendet eine <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="94fa1-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94fa1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94fa1-104">Example</span></span>  
 <span data-ttu-id="94fa1-105">Die <xref:System.Windows.Controls.Panel.Children%2A> von einem <xref:System.Windows.Controls.Grid> Steuerelement gerendert werden, in der Reihenfolge, die sie in Markup oder Code definiert sind.</span><span class="sxs-lookup"><span data-stu-id="94fa1-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="94fa1-106"><xref:System.Windows.Controls.GridSplitter> Steuerelemente können von anderen Steuerelementen ausgeblendet werden, wenn Sie diese nicht als die letzten Elemente im Definieren der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung oder wenn Sie anderen Steuerelementen einen höheren <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="94fa1-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="94fa1-107">Um zu verhindern, dass ausgeblendete <xref:System.Windows.Controls.GridSplitter> -Steuerelemente, führen Sie einen der folgenden.</span><span class="sxs-lookup"><span data-stu-id="94fa1-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="94fa1-108">Stellen Sie sicher, dass <xref:System.Windows.Controls.GridSplitter> Steuerelemente sind die letzten <xref:System.Windows.Controls.Panel.Children%2A> hinzugefügt, die <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="94fa1-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="94fa1-109">Das folgende Beispiel zeigt die <xref:System.Windows.Controls.GridSplitter> als das letzte Element in der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von der <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="94fa1-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="94fa1-110">Legen Sie die <xref:System.Windows.Controls.Panel.ZIndexProperty> auf die <xref:System.Windows.Controls.GridSplitter> auf mehr als ein Steuerelement, das andernfalls verdecken würde.</span><span class="sxs-lookup"><span data-stu-id="94fa1-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="94fa1-111">Das folgende Beispiel zeigt die <xref:System.Windows.Controls.GridSplitter> steuern, eine höhere <xref:System.Windows.Controls.Panel.ZIndexProperty> als die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="94fa1-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="94fa1-112">Festlegen von Rändern des Steuerelements, das andernfalls verdecken würde die <xref:System.Windows.Controls.GridSplitter> , damit die <xref:System.Windows.Controls.GridSplitter> verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="94fa1-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="94fa1-113">Im folgenden Beispiel wird die Ränder auf ein Steuerelement, das andernfalls überlagern würde, und verbergen die <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="94fa1-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="94fa1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94fa1-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="94fa1-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="94fa1-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
