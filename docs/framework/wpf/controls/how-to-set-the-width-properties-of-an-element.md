---
title: 'Gewusst wie: Festlegen der Breiteneigenschaften eines Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 682929625612114d042e4619d8388617988b3c48
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124272"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Gewusst wie: Festlegen der Breiteneigenschaften eines Elements
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Unterschiede im Renderingverhalten zwischen den vier breiten bezogenen Eigenschaften in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]visuell dargestellt.  
  
 Die <xref:System.Windows.FrameworkElement>-Klasse macht vier Eigenschaften verfügbar, die die Breite Merkmale eines Elements beschreiben. Diese vier Eigenschaften können in Konflikt stehen. Wenn Sie dies tun, wird der Wert, der Vorrang hat, wie folgt bestimmt: der <xref:System.Windows.FrameworkElement.MinWidth%2A> Wert hat Vorrang vor dem <xref:System.Windows.FrameworkElement.MaxWidth%2A> Wert, der wiederum Vorrang vor dem <xref:System.Windows.FrameworkElement.Width%2A> Wert hat. Eine vierte Eigenschaft, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, ist schreibgeschützt und meldet die tatsächliche Breite, die durch Interaktionen mit dem Layoutprozess festgelegt wird.  
  
 In den folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispielen wird ein <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) als untergeordnetes Element von <xref:System.Windows.Controls.Canvas>gezeichnet. Sie können die Width-Eigenschaften einer <xref:System.Windows.Shapes.Rectangle> ändern, indem Sie eine Reihe von <xref:System.Windows.Controls.ListBox> Elementen verwenden, die die Eigenschaftswerte <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>und <xref:System.Windows.FrameworkElement.Width%2A>darstellen. Auf diese Weise wird die Rangfolge der einzelnen Eigenschaften visuell angezeigt.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 In den folgenden Code Behind-Beispielen werden die Ereignisse behandelt, die das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>-Ereignis auslöst. Jede benutzerdefinierte Methode nimmt die Eingabe aus der <xref:System.Windows.Controls.ListBox>, analysiert den Wert als <xref:System.Double>und wendet den Wert auf die angegebene Eigenschaft für die Breite an. Die Width-Werte werden auch in eine Zeichenfolge konvertiert und in verschiedene <xref:System.Windows.Controls.TextBlock> Elemente geschrieben (Definition dieser Elemente wird nicht in der ausgewählten XAML angezeigt).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Das komplette Beispiel finden Sie unter [Width Properties Comparison Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Festlegen der Höheneigenschaften eines Elements](how-to-set-the-height-properties-of-an-element.md)
- [Vergleichsbeispiel für Width Properties](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
