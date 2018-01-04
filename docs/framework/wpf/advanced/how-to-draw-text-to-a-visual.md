---
title: 'Gewusst wie: Zeichnen von Text in grafischen Elementen'
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
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765d2102bc4466c2b194e03c9688212e04005ca2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="97961-102">Gewusst wie: Zeichnen von Text in grafischen Elementen</span><span class="sxs-lookup"><span data-stu-id="97961-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="97961-103">Im folgende Beispiel wird gezeigt, wie Zeichnen von Text um eine <xref:System.Windows.Media.DrawingVisual> mithilfe einer <xref:System.Windows.Media.DrawingContext> Objekt.</span><span class="sxs-lookup"><span data-stu-id="97961-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="97961-104">Ein Zeichnung Kontext wird zurückgegeben, indem die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> Methode eine <xref:System.Windows.Media.DrawingVisual> Objekt.</span><span class="sxs-lookup"><span data-stu-id="97961-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="97961-105">Sie können Text und Grafiken in einem zeichnen Kontext zeichnen.</span><span class="sxs-lookup"><span data-stu-id="97961-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="97961-106">Verwenden Sie zum Zeichnen von Text in den Kontext zeichnen die <xref:System.Windows.Media.DrawingContext.DrawText%2A> Methode von einer <xref:System.Windows.Media.DrawingContext> Objekt.</span><span class="sxs-lookup"><span data-stu-id="97961-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="97961-107">Rufen Sie abschließend Zeichnungsinhalt in den zeichnen-Kontext, der <xref:System.Windows.Media.DrawingContext.Close%2A> -Methode zum Zeichnen verwendeten Kontext zu schließen und den Inhalt beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="97961-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97961-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97961-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="97961-109">Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="97961-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
