---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849521"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="67882-102">Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe</span><span class="sxs-lookup"><span data-stu-id="67882-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="67882-103">Um einen Bereich mit einer Volltonfarbe zu malen, <xref:System.Windows.Media.Brushes.Red%2A> <xref:System.Windows.Media.Brushes.Blue%2A>können Sie einen vordefinierten Systempinsel verwenden, z. B. oder , oder Sie können einen neuen <xref:System.Windows.Media.SolidColorBrush> erstellen und seine <xref:System.Windows.Media.SolidColorBrush.Color%2A> mit Alpha-, Rot-, Grün- und Blauwerten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="67882-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="67882-104">In XAML können Sie einen Bereich mit einer Volltonfarbe auch mit der Hexadezimalschreibweise zeichnen.</span><span class="sxs-lookup"><span data-stu-id="67882-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="67882-105">In den folgenden Beispielen wird <xref:System.Windows.Shapes.Rectangle> jede dieser Techniken verwendet, um ein Blau zu malen.</span><span class="sxs-lookup"><span data-stu-id="67882-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67882-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67882-106">Example</span></span>  
 <span data-ttu-id="67882-107">**Verwenden eines vordefinierten Pinsels**</span><span class="sxs-lookup"><span data-stu-id="67882-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="67882-108">Im folgenden Beispiel wird der <xref:System.Windows.Media.Brushes.Blue%2A> vordefinierte Pinsel verwendet, um ein Rechteck blau zu malen.</span><span class="sxs-lookup"><span data-stu-id="67882-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="67882-109">**Hexadezimalnotation**</span><span class="sxs-lookup"><span data-stu-id="67882-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="67882-110">Im nächsten Beispiel wird die Hexadezimalschreibweise mit acht Ziffern verwendet.</span><span class="sxs-lookup"><span data-stu-id="67882-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="67882-111">**Verwenden der ARGB-Werte**</span><span class="sxs-lookup"><span data-stu-id="67882-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="67882-112">Im nächsten Beispiel <xref:System.Windows.Media.SolidColorBrush> wird <xref:System.Windows.Media.SolidColorBrush.Color%2A> eine erstellt und die Verwendung der ARGB-Werte für die Farbe Blau beschrieben.</span><span class="sxs-lookup"><span data-stu-id="67882-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="67882-113">Weitere Möglichkeiten, Farbe zu <xref:System.Windows.Media.Color> beschreiben, finden Sie in der Struktur.</span><span class="sxs-lookup"><span data-stu-id="67882-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="67882-114">**Ähnliche Themen**</span><span class="sxs-lookup"><span data-stu-id="67882-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="67882-115">Weitere Informationen <xref:System.Windows.Media.SolidColorBrush> zu und weitere Beispiele finden Sie in der [Übersicht "Gemälde mit Volltonfarben und Farbverläufen".](painting-with-solid-colors-and-gradients-overview.md)</span><span class="sxs-lookup"><span data-stu-id="67882-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="67882-116">Dieses Codebeispiel ist Teil eines größeren <xref:System.Windows.Media.SolidColorBrush> Beispiels, das für die Klasse bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="67882-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="67882-117">Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="67882-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67882-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67882-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
