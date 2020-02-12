---
title: 'Gewusst wie: Festlegen der Höheneigenschaften eines Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124285"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Gewusst wie: Festlegen der Höheneigenschaften eines Elements
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Unterschiede im Renderingverhalten zwischen den vier Höhen bezogenen Eigenschaften in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]visuell dargestellt.  
  
 Die <xref:System.Windows.FrameworkElement>-Klasse macht vier Eigenschaften verfügbar, die die Höhen Merkmale eines Elements beschreiben. Diese vier Eigenschaften können in Konflikt stehen. Wenn Sie dies tun, wird der Wert, der Vorrang hat, wie folgt bestimmt: der <xref:System.Windows.FrameworkElement.MinHeight%2A> Wert hat Vorrang vor dem <xref:System.Windows.FrameworkElement.MaxHeight%2A> Wert, der wiederum Vorrang vor dem <xref:System.Windows.FrameworkElement.Height%2A> Wert hat. Eine vierte Eigenschaft, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, ist schreibgeschützt und meldet die tatsächliche Höhe gemäß der durch Interaktionen mit dem Layoutprozess festgelegten Höhe.  
  
 In den folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispielen wird ein <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) als untergeordnetes Element von <xref:System.Windows.Controls.Canvas>gezeichnet. Sie können die Height-Eigenschaften einer <xref:System.Windows.Shapes.Rectangle> ändern, indem Sie eine Reihe von <xref:System.Windows.Controls.ListBox> Elementen verwenden, die die Eigenschaftswerte <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>und <xref:System.Windows.FrameworkElement.Height%2A>darstellen. Auf diese Weise wird die Rangfolge der einzelnen Eigenschaften visuell angezeigt.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 In den folgenden Code Behind-Beispielen werden die Ereignisse behandelt, die das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>-Ereignis auslöst. Jeder Handler nimmt die Eingabe aus der <xref:System.Windows.Controls.ListBox>, analysiert den Wert als <xref:System.Double>und wendet den Wert auf die angegebene Height-bezogene Eigenschaft an. Die Height-Werte werden auch in eine Zeichenfolge konvertiert und in verschiedene <xref:System.Windows.Controls.TextBlock> Elemente geschrieben (Definition dieser Elemente wird nicht in der ausgewählten XAML angezeigt).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Das komplette Beispiel finden Sie unter [height Properties Sample](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [Festlegen der Breiteneigenschaften eines Elements](how-to-set-the-width-properties-of-an-element.md)
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Beispiel für Height-Eigenschaften](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
