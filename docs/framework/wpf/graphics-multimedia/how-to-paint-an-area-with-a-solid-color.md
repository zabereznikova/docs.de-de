---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: 7e8e3fa5a379f02c3bb126c17bbe37fc0f3d57cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561330"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="ea318-102">Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe</span><span class="sxs-lookup"><span data-stu-id="ea318-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="ea318-103">Um einen Bereich mit einer Volltonfarbe zu zeichnen, können Sie einen vordefinierten Systempinsel, z. B. <xref:System.Windows.Media.Brushes.Red%2A> oder <xref:System.Windows.Media.Brushes.Blue%2A>, oder erstellen Sie ein neues <xref:System.Windows.Media.SolidColorBrush> und eine Beschreibung für die <xref:System.Windows.Media.SolidColorBrush.Color%2A> mit alpha, Rot-, Grün- und Blau-Werte.</span><span class="sxs-lookup"><span data-stu-id="ea318-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="ea318-104">In XAML können Sie einen Bereich mit einer Volltonfarbe auch mit der Hexadezimalschreibweise zeichnen.</span><span class="sxs-lookup"><span data-stu-id="ea318-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="ea318-105">Im folgenden Beispiel wird jede dieser Techniken zum Zeichnen einer <xref:System.Windows.Shapes.Rectangle> Blau.</span><span class="sxs-lookup"><span data-stu-id="ea318-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea318-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea318-106">Example</span></span>  
 <span data-ttu-id="ea318-107">**Verwenden eines vordefinierten Pinsels**</span><span class="sxs-lookup"><span data-stu-id="ea318-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="ea318-108">Im folgenden Beispiel wird den vordefinierten Pinsel <xref:System.Windows.Media.Brushes.Blue%2A> ein Rechteck blauen gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ea318-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="ea318-109">**Hexadezimalnotation**</span><span class="sxs-lookup"><span data-stu-id="ea318-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="ea318-110">Im nächsten Beispiel wird die Hexadezimalschreibweise mit acht Ziffern verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea318-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="ea318-111">**Verwenden der ARGB-Werte**</span><span class="sxs-lookup"><span data-stu-id="ea318-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="ea318-112">Im nächste Beispiel erstellt eine <xref:System.Windows.Media.SolidColorBrush> und beschreibt dessen <xref:System.Windows.Media.SolidColorBrush.Color%2A> mithilfe der ARGB-Werte für die Farbe Blau.</span><span class="sxs-lookup"><span data-stu-id="ea318-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="ea318-113">Andere Möglichkeiten zur Beschreibung der Farbe, finden Sie unter der <xref:System.Windows.Media.Color> Struktur.</span><span class="sxs-lookup"><span data-stu-id="ea318-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="ea318-114">**Verwandte Themen**</span><span class="sxs-lookup"><span data-stu-id="ea318-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="ea318-115">Weitere Informationen zu <xref:System.Windows.Media.SolidColorBrush> und weitere Beispiele finden Sie unter der [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) (Übersicht).</span><span class="sxs-lookup"><span data-stu-id="ea318-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="ea318-116">Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels für die <xref:System.Windows.Media.SolidColorBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ea318-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="ea318-117">Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="ea318-117">For the complete sample, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea318-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea318-118">See Also</span></span>  
 <xref:System.Windows.Media.Brushes>
