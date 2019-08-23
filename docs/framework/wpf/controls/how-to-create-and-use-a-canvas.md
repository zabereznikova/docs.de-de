---
title: 'Vorgehensweise: Erstellen und Verwenden eines Canvas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: edef660b2da2f09e0a6edbc0a87f0d1f26eb03da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964220"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="d7088-102">Vorgehensweise: Erstellen und Verwenden eines Canvas</span><span class="sxs-lookup"><span data-stu-id="d7088-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="d7088-103">In diesem Beispiel wird gezeigt, wie eine Instanz von <xref:System.Windows.Controls.Canvas>erstellt und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7088-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7088-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7088-104">Example</span></span>  
 <span data-ttu-id="d7088-105">Im folgenden <xref:System.Windows.Controls.TextBlock> Beispiel werden zwei-Elemente explizit mithilfe der <xref:System.Windows.Controls.Canvas.SetTop%2A> -Methode und der- <xref:System.Windows.Controls.Canvas.SetLeft%2A> Methode von <xref:System.Windows.Controls.Canvas>positioniert.</span><span class="sxs-lookup"><span data-stu-id="d7088-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="d7088-106">Im Beispiel wird auch eine <xref:System.Windows.Controls.Control.Background%2A> Farbe von `LightSteelBlue` <xref:System.Windows.Controls.Canvas>zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d7088-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7088-107">Wenn Sie zum [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] positionieren <xref:System.Windows.Controls.TextBlock> von Elementen verwenden, verwenden <xref:System.Windows.Controls.Canvas.Top%2A> Sie <xref:System.Windows.Controls.Canvas.Left%2A> die-Eigenschaft und die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d7088-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d7088-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7088-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="d7088-109">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="d7088-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="d7088-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="d7088-110">How-to Topics</span></span>](canvas-how-to-topics.md)
