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
ms.openlocfilehash: 806056397200fa5c567e83227499ba721544f523
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005180"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="f570a-102">Vorgehensweise: Erstellen eines Rollovereffekts mit Ereignissen</span><span class="sxs-lookup"><span data-stu-id="f570a-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="f570a-103">Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern können, wenn der Mauszeiger in den Bereich wechselt, der vom-Element belegt wird.</span><span class="sxs-lookup"><span data-stu-id="f570a-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="f570a-104">Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Datei und einer Code Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="f570a-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f570a-105">In diesem Beispiel wird veranschaulicht, wie Ereignisse verwendet werden, aber die empfohlene Vorgehensweise zum Erreichen desselben Effekts ist die Verwendung einer <xref:System.Windows.Trigger> in einem Stil.</span><span class="sxs-lookup"><span data-stu-id="f570a-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="f570a-106">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="f570a-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f570a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f570a-107">Example</span></span>  
 <span data-ttu-id="f570a-108">Der folgende XAML-Code erstellt die Benutzeroberfläche, die aus <xref:System.Windows.Controls.Border> um einen <xref:System.Windows.Controls.TextBlock> besteht und die <xref:System.Windows.Input.Mouse.MouseEnter>-und <xref:System.Windows.UIElement.MouseLeave>-Ereignishandler an den <xref:System.Windows.Controls.Border> anfügt.</span><span class="sxs-lookup"><span data-stu-id="f570a-108">The following XAML creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="f570a-109">Der folgende Code Behind erstellt die Ereignishandler <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave>.</span><span class="sxs-lookup"><span data-stu-id="f570a-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="f570a-110">Wenn der Mauszeiger in den <xref:System.Windows.Controls.Border> eintritt, wird der Hintergrund des <xref:System.Windows.Controls.Border> in rot geändert.</span><span class="sxs-lookup"><span data-stu-id="f570a-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="f570a-111">Wenn der Mauszeiger den <xref:System.Windows.Controls.Border> verlässt, wird der Hintergrund des <xref:System.Windows.Controls.Border> wieder in weiß geändert.</span><span class="sxs-lookup"><span data-stu-id="f570a-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
