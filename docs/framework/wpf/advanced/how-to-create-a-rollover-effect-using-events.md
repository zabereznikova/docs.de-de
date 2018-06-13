---
title: 'Gewusst wie: Erstellen eines Rollovereffekts mit Ereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d458d87586614093b35fcd73969dea04fe620351
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543009"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="7a435-102">Gewusst wie: Erstellen eines Rollovereffekts mit Ereignissen</span><span class="sxs-lookup"><span data-stu-id="7a435-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="7a435-103">In diesem Beispiel wird gezeigt, wie die Farbe eines Elements ändern, wie der Mauszeiger die Form eintritt und diese verlässt des Bereichs, der vom Element eingenommene wird.</span><span class="sxs-lookup"><span data-stu-id="7a435-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="7a435-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine Code-Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="7a435-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a435-105">In diesem Beispiel wird veranschaulicht, wie Ereignisse, aber die empfohlene Methode, um diesen Effekt zu erreichen ist die Verwendung einer <xref:System.Windows.Trigger> in einem Format.</span><span class="sxs-lookup"><span data-stu-id="7a435-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="7a435-106">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="7a435-106">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a435-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a435-107">Example</span></span>  
 <span data-ttu-id="7a435-108">Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche, die sich aus <xref:System.Windows.Controls.Border> um eine <xref:System.Windows.Controls.TextBlock>, und fügt die <xref:System.Windows.Input.Mouse.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> Ereignishandler an das <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="7a435-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="7a435-109">Der folgende Code-behind erstellt die <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="7a435-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="7a435-110">Wenn der Mauszeiger wird die <xref:System.Windows.Controls.Border>, den Hintergrund der <xref:System.Windows.Controls.Border> in Rot geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7a435-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="7a435-111">Wenn der Mauszeiger die Form verlässt die <xref:System.Windows.Controls.Border>, den Hintergrund der <xref:System.Windows.Controls.Border> nicht wieder in Weiß geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7a435-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
