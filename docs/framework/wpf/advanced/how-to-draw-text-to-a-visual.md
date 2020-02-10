---
title: 'Gewusst wie: Zeichnen von Text in grafischen Elementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094552"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="a691b-102">Gewusst wie: Zeichnen von Text in grafischen Elementen</span><span class="sxs-lookup"><span data-stu-id="a691b-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="a691b-103">Im folgenden Beispiel wird gezeigt, wie Sie mit einem <xref:System.Windows.Media.DrawingContext>-Objekt Text in eine <xref:System.Windows.Media.DrawingVisual> zeichnen.</span><span class="sxs-lookup"><span data-stu-id="a691b-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="a691b-104">Ein Zeichnungs Kontext wird zurückgegeben, indem die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>-Methode eines <xref:System.Windows.Media.DrawingVisual> Objekts aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a691b-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="a691b-105">Sie können Grafiken und Text in einem Zeichnungs Kontext zeichnen.</span><span class="sxs-lookup"><span data-stu-id="a691b-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="a691b-106">Um Text in den Zeichen Kontext zu zeichnen, verwenden Sie die <xref:System.Windows.Media.DrawingContext.DrawText%2A>-Methode eines <xref:System.Windows.Media.DrawingContext> Objekts.</span><span class="sxs-lookup"><span data-stu-id="a691b-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="a691b-107">Wenn Sie mit dem Zeichnen von Inhalten in den Zeichnungs Kontext fertig sind, können Sie die <xref:System.Windows.Media.DrawingContext.Close%2A>-Methode zum Schließen des Zeichen Kontexts und zum Beibehalten des Inhalts abrufen.</span><span class="sxs-lookup"><span data-stu-id="a691b-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a691b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a691b-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="a691b-109">Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).</span><span class="sxs-lookup"><span data-stu-id="a691b-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).</span></span>
