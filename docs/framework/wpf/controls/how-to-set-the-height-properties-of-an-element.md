---
title: 'Vorgehensweise: Festlegen der Höheneigenschaften eines Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: be3235d4bf7b5e108420b5ed030157067cacdb8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637048"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="82c6d-102">Vorgehensweise: Festlegen der Höheneigenschaften eines Elements</span><span class="sxs-lookup"><span data-stu-id="82c6d-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="82c6d-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82c6d-103">Example</span></span>  
 <span data-ttu-id="82c6d-104">Dieses Beispiel zeigt die Unterschiede im Renderingverhalten zwischen den vier Höhe-bezogene Eigenschaften im, visuell [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82c6d-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="82c6d-105">Die <xref:System.Windows.FrameworkElement> Klasse stellt vier Eigenschaften, die die Höheneigenschaften eines Elements zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="82c6d-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="82c6d-106">Diese vier Eigenschaften können zu Konflikten führen, und wenn dies der Fall, wird der Wert, der Vorrang wie folgt bestimmt: die <xref:System.Windows.FrameworkElement.MinHeight%2A> Wert hat Vorrang vor den <xref:System.Windows.FrameworkElement.MaxHeight%2A> -Wert, der wiederum Vorrang vor den <xref:System.Windows.FrameworkElement.Height%2A> Wert.</span><span class="sxs-lookup"><span data-stu-id="82c6d-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="82c6d-107">Vierte Eigenschaft <xref:System.Windows.FrameworkElement.ActualHeight%2A>ist schreibgeschützt und gibt die tatsächliche Höhe von Interaktionen mit der Layoutvorgang bestimmt.</span><span class="sxs-lookup"><span data-stu-id="82c6d-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="82c6d-108">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispielen wird eine <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) als untergeordnetes Element des <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="82c6d-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="82c6d-109">Sie können die Höheneigenschaften ändern eine <xref:System.Windows.Shapes.Rectangle> mithilfe einer Reihe von <xref:System.Windows.Controls.ListBox> Elemente, die die Eigenschaftswerte darstellen <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, und <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="82c6d-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="82c6d-110">Auf diese Weise wird die Rangfolge jeder Eigenschaft visuell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c6d-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="82c6d-111">Die Ereignisse behandeln, in den folgenden Code-Behind-Beispielen, die die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="82c6d-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="82c6d-112">Jeder Handler die Eingabe aus der <xref:System.Windows.Controls.ListBox>, analysiert den Wert als eine <xref:System.Double>, und der Wert der angegebenen Höhe bezogene-Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="82c6d-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="82c6d-113">Die Height-Werte sind auch in eine Zeichenfolge konvertiert und in verschiedenen geschrieben <xref:System.Windows.Controls.TextBlock> Elemente (die Definition dieser Elemente wird in der ausgewählten XAML nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="82c6d-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="82c6d-114">Das vollständige Beispiel finden Sie unter [Height-Eigenschaften-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159993).</span><span class="sxs-lookup"><span data-stu-id="82c6d-114">For the complete sample, see [Height Properties Sample](https://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c6d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82c6d-115">See also</span></span>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="82c6d-116">Festlegen der Breiteneigenschaften eines Elements</span><span class="sxs-lookup"><span data-stu-id="82c6d-116">Set the Width Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="82c6d-117">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="82c6d-117">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="82c6d-118">Beispiel der Height-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="82c6d-118">Height Properties Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159993)
