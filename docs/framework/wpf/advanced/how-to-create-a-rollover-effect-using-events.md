---
title: 'Vorgehensweise: Erstellen eines Rollovereffekts mit Ereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960384"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="5b32d-102">Vorgehensweise: Erstellen eines Rollovereffekts mit Ereignissen</span><span class="sxs-lookup"><span data-stu-id="5b32d-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="5b32d-103">Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern können, wenn der Mauszeiger in den Bereich wechselt, der vom-Element belegt wird.</span><span class="sxs-lookup"><span data-stu-id="5b32d-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="5b32d-104">Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei und einer Code Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="5b32d-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b32d-105">In diesem Beispiel wird veranschaulicht, wie Ereignisse verwendet werden, aber die empfohlene Vorgehensweise zum Erreichen desselben Effekts ist <xref:System.Windows.Trigger> die Verwendung von in einem Stil.</span><span class="sxs-lookup"><span data-stu-id="5b32d-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="5b32d-106">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="5b32d-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b32d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b32d-107">Example</span></span>  
 <span data-ttu-id="5b32d-108">Im folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] wird die Benutzeroberfläche erstellt, die <xref:System.Windows.Controls.Border> aus einem <xref:System.Windows.Controls.TextBlock>besteht, und die <xref:System.Windows.Input.Mouse.MouseEnter> Ereignishandler <xref:System.Windows.UIElement.MouseLeave> und an den <xref:System.Windows.Controls.Border>anfügt.</span><span class="sxs-lookup"><span data-stu-id="5b32d-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="5b32d-109">Der folgende Code Behind erstellt die <xref:System.Windows.UIElement.MouseEnter> Ereignis <xref:System.Windows.UIElement.MouseLeave> Handler und.</span><span class="sxs-lookup"><span data-stu-id="5b32d-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="5b32d-110">Wenn der Mauszeiger in den <xref:System.Windows.Controls.Border>eintritt, <xref:System.Windows.Controls.Border> wird der Hintergrund der in rot geändert.</span><span class="sxs-lookup"><span data-stu-id="5b32d-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="5b32d-111">Wenn der Mauszeiger das <xref:System.Windows.Controls.Border>-Zeichen verlässt, <xref:System.Windows.Controls.Border> wird der Hintergrund von wieder in weiß geändert.</span><span class="sxs-lookup"><span data-stu-id="5b32d-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
