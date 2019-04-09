---
title: 'Vorgehensweise: Festlegen der Breiteneigenschaften eines Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: a5ed67ba20176398a863a1e9826b1eab71b182f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096874"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Vorgehensweise: Festlegen der Breiteneigenschaften eines Elements
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die Unterschiede im Renderingverhalten zwischen den vier Breite-bezogene Eigenschaften im, visuell [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Die <xref:System.Windows.FrameworkElement> Klasse stellt vier Eigenschaften, die die Breiteneigenschaften eines Elements zu beschreiben. Diese vier Eigenschaften können zu Konflikten führen, und wenn dies der Fall, wird der Wert, der Vorrang wie folgt bestimmt: die <xref:System.Windows.FrameworkElement.MinWidth%2A> Wert hat Vorrang vor den <xref:System.Windows.FrameworkElement.MaxWidth%2A> -Wert, der wiederum Vorrang vor den <xref:System.Windows.FrameworkElement.Width%2A> Wert. Vierte Eigenschaft <xref:System.Windows.FrameworkElement.ActualWidth%2A>ist schreibgeschützt und gibt die tatsächliche Breite von Interaktionen mit der Layoutvorgang bestimmt.  
  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispielen wird eine <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) als untergeordnetes Element des <xref:System.Windows.Controls.Canvas>. Sie können die Breiteneigenschaften ändern eine <xref:System.Windows.Shapes.Rectangle> mithilfe einer Reihe von <xref:System.Windows.Controls.ListBox> Elemente, die die Eigenschaftswerte darstellen <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, und <xref:System.Windows.FrameworkElement.Width%2A>. Auf diese Weise wird die Rangfolge jeder Eigenschaft visuell angezeigt.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 Die Ereignisse behandeln, in den folgenden Code-Behind-Beispielen, die die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignis auslöst. Jede benutzerdefinierte Methode übernimmt die Eingabe von der <xref:System.Windows.Controls.ListBox>, analysiert den Wert als eine <xref:System.Double>, und der Wert der angegebenen Breite bezogene-Eigenschaft angewendet. Die Width-Werte sind auch in eine Zeichenfolge konvertiert und in verschiedenen geschrieben <xref:System.Windows.Controls.TextBlock> Elemente (die Definition dieser Elemente wird in der ausgewählten XAML nicht angezeigt).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Das vollständige Beispiel finden Sie unter [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Festlegen der Höheneigenschaften eines Elements](how-to-set-the-height-properties-of-an-element.md)
- [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050)
