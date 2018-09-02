---
title: 'Gewusst wie: Übersetzen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 04e1e8288bcccc4a310f05abff01fbdf160cdb11
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421002"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="5d2e2-102">Gewusst wie: Übersetzen eines Elements</span><span class="sxs-lookup"><span data-stu-id="5d2e2-102">How to: Translate an Element</span></span>
<span data-ttu-id="5d2e2-103">In diesem Beispiel wird veranschaulicht, wie übersetzt (verschoben) ein Element mit einem <xref:System.Windows.Media.TranslateTransform>.</span><span class="sxs-lookup"><span data-stu-id="5d2e2-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="5d2e2-104">Die <xref:System.Windows.Media.TranslateTransform> Klasse ist besonders nützlich für das Verschieben von Elementen in Bereichen, in denen keine absolute Positionierung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="5d2e2-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="5d2e2-105">Z. B. durch Anwenden einer <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eines Elements, verschieben Sie ein Element in eine <xref:System.Windows.Controls.StackPanel> oder <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="5d2e2-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="5d2e2-106">Verwenden der <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft der <xref:System.Windows.Media.TranslateTransform> , des Werts in Pixel, um das Element entlang der x-Achse verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d2e2-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="5d2e2-107">Verwenden der <xref:System.Windows.Media.TranslateTransform.Y%2A> Eigenschaft des Werts in Pixel, um das Element entlang der y-Achse verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d2e2-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="5d2e2-108">Wenden Sie schließlich die <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.</span><span class="sxs-lookup"><span data-stu-id="5d2e2-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="5d2e2-109">Im folgenden Beispiel wird eine <xref:System.Windows.Media.TranslateTransform> auf ein Element 50 Pixel nach rechts und 50 Pixel nach unten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="5d2e2-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d2e2-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d2e2-110">Example</span></span>  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="5d2e2-111">Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="5d2e2-111">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2e2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d2e2-112">See Also</span></span>  
 [<span data-ttu-id="5d2e2-113">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="5d2e2-113">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
