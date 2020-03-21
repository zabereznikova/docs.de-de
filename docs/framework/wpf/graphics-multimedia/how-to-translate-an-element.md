---
title: 'Gewusst wie: Übersetzen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111971"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="f53b2-102">Gewusst wie: Übersetzen eines Elements</span><span class="sxs-lookup"><span data-stu-id="f53b2-102">How to: Translate an Element</span></span>
<span data-ttu-id="f53b2-103">Dieses Beispiel zeigt, wie ein Element mithilfe <xref:System.Windows.Media.TranslateTransform>einer übersetzt (verschiebt) wird.</span><span class="sxs-lookup"><span data-stu-id="f53b2-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="f53b2-104">Die <xref:System.Windows.Media.TranslateTransform> Klasse ist besonders nützlich für das Verschieben von Elementen innerhalb von Panels, die keine absolute Positionierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f53b2-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="f53b2-105">Wenn Sie z. <xref:System.Windows.Media.TranslateTransform> B. eine auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eines <xref:System.Windows.Controls.StackPanel> Elements <xref:System.Windows.Controls.DockPanel>anwenden, können Sie ein Element innerhalb eines oder verschieben.</span><span class="sxs-lookup"><span data-stu-id="f53b2-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="f53b2-106">Verwenden <xref:System.Windows.Media.TranslateTransform.X%2A> Sie die <xref:System.Windows.Media.TranslateTransform> Eigenschaft des, um den Betrag in Pixel anzugeben, um das Element entlang der x-Achse zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="f53b2-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="f53b2-107">Verwenden <xref:System.Windows.Media.TranslateTransform.Y%2A> Sie die Eigenschaft, um den Betrag in Pixel anzugeben, um das Element entlang der y-Achse zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="f53b2-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="f53b2-108">Wenden Sie <xref:System.Windows.Media.TranslateTransform> schließlich <xref:System.Windows.UIElement.RenderTransform%2A> die auf die Eigenschaft des Elements an.</span><span class="sxs-lookup"><span data-stu-id="f53b2-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="f53b2-109">Im folgenden Beispiel <xref:System.Windows.Media.TranslateTransform> wird ein verwendet, um ein Element 50 Pixel nach rechts und 50 Pixel nach unten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="f53b2-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f53b2-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f53b2-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="f53b2-111">Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="f53b2-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53b2-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f53b2-112">See also</span></span>

- [<span data-ttu-id="f53b2-113">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="f53b2-113">Transforms Overview</span></span>](transforms-overview.md)
