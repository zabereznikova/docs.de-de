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
ms.openlocfilehash: 87740a215136863199d962a2704cf691f27fc3bc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369096"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="79b91-102">Vorgehensweise: Erstellen eines Rollovereffekts mit Ereignissen</span><span class="sxs-lookup"><span data-stu-id="79b91-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="79b91-103">Dieses Beispiel zeigt, wie Sie die Farbe eines Elements zu ändern, während der Mauszeiger wechselt und den Bereich verlässt, der vom Element eingenommene.</span><span class="sxs-lookup"><span data-stu-id="79b91-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="79b91-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine CodeBehind-Datei.</span><span class="sxs-lookup"><span data-stu-id="79b91-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79b91-105">In diesem Beispiel wird veranschaulicht, wie Ereignisse, aber die empfohlene Methode, um diesen Effekt zu erreichen ist die Verwendung einer <xref:System.Windows.Trigger> in einem Stil.</span><span class="sxs-lookup"><span data-stu-id="79b91-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="79b91-106">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="79b91-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79b91-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79b91-107">Example</span></span>  
 <span data-ttu-id="79b91-108">Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche besteht aus <xref:System.Windows.Controls.Border> rund um einen <xref:System.Windows.Controls.TextBlock>, und fügt die <xref:System.Windows.Input.Mouse.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> Ereignishandler die <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="79b91-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="79b91-109">Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="79b91-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="79b91-110">Wenn der Mauszeiger wechselt der <xref:System.Windows.Controls.Border>, den Hintergrund der <xref:System.Windows.Controls.Border> in Rot geändert wird.</span><span class="sxs-lookup"><span data-stu-id="79b91-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="79b91-111">Wenn der Mauszeiger fortbewegt der <xref:System.Windows.Controls.Border>, den Hintergrund der <xref:System.Windows.Controls.Border> wieder auf Weiß geändert wird.</span><span class="sxs-lookup"><span data-stu-id="79b91-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
