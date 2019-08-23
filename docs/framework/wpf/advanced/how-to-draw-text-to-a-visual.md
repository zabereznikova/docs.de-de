---
title: 'Vorgehensweise: Zeichnen von Text in grafischen Elementen'
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
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963849"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="c73e3-102">Vorgehensweise: Zeichnen von Text in grafischen Elementen</span><span class="sxs-lookup"><span data-stu-id="c73e3-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="c73e3-103">Im folgenden Beispiel wird gezeigt, wie Sie mithilfe eines <xref:System.Windows.Media.DrawingVisual> <xref:System.Windows.Media.DrawingContext> -Objekts Text in einen zeichnen können.</span><span class="sxs-lookup"><span data-stu-id="c73e3-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="c73e3-104">Ein Zeichnungs Kontext wird zurückgegeben, indem <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> die-Methode <xref:System.Windows.Media.DrawingVisual> eines-Objekts aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c73e3-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="c73e3-105">Sie können Grafiken und Text in einem Zeichnungs Kontext zeichnen.</span><span class="sxs-lookup"><span data-stu-id="c73e3-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="c73e3-106">Um Text in den Zeichen Kontext zu zeichnen, verwenden <xref:System.Windows.Media.DrawingContext.DrawText%2A> Sie die- <xref:System.Windows.Media.DrawingContext> Methode eines-Objekts.</span><span class="sxs-lookup"><span data-stu-id="c73e3-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="c73e3-107">Wenn Sie mit dem Zeichnen von Inhalten in den Zeichen Kontext fertig sind <xref:System.Windows.Media.DrawingContext.Close%2A> , müssen Sie die-Methode zum Schließen des Zeichen Kontexts und zum Speichern des Inhalts abrufen.</span><span class="sxs-lookup"><span data-stu-id="c73e3-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c73e3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c73e3-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="c73e3-109">Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="c73e3-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
