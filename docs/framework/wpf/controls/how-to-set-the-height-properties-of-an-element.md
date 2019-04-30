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
ms.openlocfilehash: fb655630336c3b69afdc726a2e3c5a2cb8838667
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024416"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Vorgehensweise: Festlegen der Höheneigenschaften eines Elements
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die Unterschiede im Renderingverhalten zwischen den vier Höhe-bezogene Eigenschaften im, visuell [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Die <xref:System.Windows.FrameworkElement> Klasse stellt vier Eigenschaften, die die Höheneigenschaften eines Elements zu beschreiben. Diese vier Eigenschaften können zu Konflikten führen, und wenn dies der Fall, wird der Wert, der Vorrang wie folgt bestimmt: die <xref:System.Windows.FrameworkElement.MinHeight%2A> Wert hat Vorrang vor den <xref:System.Windows.FrameworkElement.MaxHeight%2A> -Wert, der wiederum Vorrang vor den <xref:System.Windows.FrameworkElement.Height%2A> Wert. Vierte Eigenschaft <xref:System.Windows.FrameworkElement.ActualHeight%2A>ist schreibgeschützt und gibt die tatsächliche Höhe von Interaktionen mit der Layoutvorgang bestimmt.  
  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispielen wird eine <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) als untergeordnetes Element des <xref:System.Windows.Controls.Canvas>. Sie können die Höheneigenschaften ändern eine <xref:System.Windows.Shapes.Rectangle> mithilfe einer Reihe von <xref:System.Windows.Controls.ListBox> Elemente, die die Eigenschaftswerte darstellen <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, und <xref:System.Windows.FrameworkElement.Height%2A>. Auf diese Weise wird die Rangfolge jeder Eigenschaft visuell angezeigt.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Die Ereignisse behandeln, in den folgenden Code-Behind-Beispielen, die die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignis auslöst. Jeder Handler die Eingabe aus der <xref:System.Windows.Controls.ListBox>, analysiert den Wert als eine <xref:System.Double>, und der Wert der angegebenen Höhe bezogene-Eigenschaft angewendet. Die Height-Werte sind auch in eine Zeichenfolge konvertiert und in verschiedenen geschrieben <xref:System.Windows.Controls.TextBlock> Elemente (die Definition dieser Elemente wird in der ausgewählten XAML nicht angezeigt).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Das vollständige Beispiel finden Sie unter [Height-Eigenschaften-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159993).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [Festlegen der Breiteneigenschaften eines Elements](how-to-set-the-width-properties-of-an-element.md)
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Beispiel der Height-Eigenschaften](https://go.microsoft.com/fwlink/?LinkID=159993)
