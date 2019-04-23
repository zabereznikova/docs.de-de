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
ms.openlocfilehash: 33b98024699a88f56d27b7e5ab8d5216c906e7ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190768"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="2614f-102">Vorgehensweise: Erstellen und Verwenden eines Canvas</span><span class="sxs-lookup"><span data-stu-id="2614f-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="2614f-103">Dieses Beispiel zeigt das Erstellen und verwenden Sie eine Instanz des <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="2614f-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2614f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2614f-104">Example</span></span>  
 <span data-ttu-id="2614f-105">Im folgenden Beispiel wird explizit positioniert, zwei <xref:System.Windows.Controls.TextBlock> Elemente mithilfe der <xref:System.Windows.Controls.Canvas.SetTop%2A> und <xref:System.Windows.Controls.Canvas.SetLeft%2A> Methoden <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="2614f-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="2614f-106">Im Beispiel weist auch eine <xref:System.Windows.Controls.Control.Background%2A> Farbe des `LightSteelBlue` auf die <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="2614f-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2614f-107">Bei Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] an Position <xref:System.Windows.Controls.TextBlock> Elemente verwenden, die <xref:System.Windows.Controls.Canvas.Top%2A> und <xref:System.Windows.Controls.Canvas.Left%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="2614f-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2614f-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2614f-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="2614f-109">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="2614f-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="2614f-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2614f-110">How-to Topics</span></span>](canvas-how-to-topics.md)
