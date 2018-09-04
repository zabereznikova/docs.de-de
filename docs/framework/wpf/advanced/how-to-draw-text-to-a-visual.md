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
ms.openlocfilehash: bc7a4f989137ec2b021d27a6e112ff1aebd99d07
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523242"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="62774-102">Gewusst wie: Zeichnen von Text in grafischen Elementen</span><span class="sxs-lookup"><span data-stu-id="62774-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="62774-103">Das folgende Beispiel zeigt das Zeichnen von Text auf einer <xref:System.Windows.Media.DrawingVisual> mithilfe einer <xref:System.Windows.Media.DrawingContext> Objekt.</span><span class="sxs-lookup"><span data-stu-id="62774-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="62774-104">Ein Zeichnungskontext wird zurückgegeben, indem die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> Methode eine <xref:System.Windows.Media.DrawingVisual> Objekt.</span><span class="sxs-lookup"><span data-stu-id="62774-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="62774-105">Sie können Grafiken und Text in einen Zeichnungskontext zeichnen.</span><span class="sxs-lookup"><span data-stu-id="62774-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="62774-106">Verwenden Sie zum Zeichnen von Text in den Zeichnungskontext der <xref:System.Windows.Media.DrawingContext.DrawText%2A> Methode eine <xref:System.Windows.Media.DrawingContext> Objekt.</span><span class="sxs-lookup"><span data-stu-id="62774-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="62774-107">Wenn Sie das Zeichnen von Inhalten in den Zeichnungskontext fertig sind, rufen Sie die <xref:System.Windows.Media.DrawingContext.Close%2A> Methode, um den Zeichnungskontext schließen und den Inhalt beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="62774-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62774-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62774-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="62774-109">Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="62774-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
