---
title: 'Gewusst wie: Erstellen und Verwenden eines Canvas'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 562531f75d6a800ff93a02709a053b790de52ea2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="390a6-102">Gewusst wie: Erstellen und Verwenden eines Canvas</span><span class="sxs-lookup"><span data-stu-id="390a6-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="390a6-103">In diesem Beispiel wird gezeigt, wie zum Erstellen und Verwenden einer Instanz von <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="390a6-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="390a6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="390a6-104">Example</span></span>  
 <span data-ttu-id="390a6-105">Das folgende Beispiel positioniert zwei explizit <xref:System.Windows.Controls.TextBlock> Elemente mithilfe der <xref:System.Windows.Controls.Canvas.SetTop%2A> und <xref:System.Windows.Controls.Canvas.SetLeft%2A> Methoden der <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="390a6-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="390a6-106">Im Beispiel weist auch eine <xref:System.Windows.Controls.Control.Background%2A> Farbe des `LightSteelBlue` auf die <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="390a6-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="390a6-107">Bei Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Position <xref:System.Windows.Controls.TextBlock> verwenden Sie die Elemente, die <xref:System.Windows.Controls.Canvas.Top%2A> und <xref:System.Windows.Controls.Canvas.Left%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="390a6-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="390a6-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="390a6-108">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.TextBlock>  
 <xref:System.Windows.Controls.Canvas.SetTop%2A>  
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 [<span data-ttu-id="390a6-109">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="390a6-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="390a6-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="390a6-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
