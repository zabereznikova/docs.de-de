---
title: "Gewusst wie: Festlegen der Höheneigenschaften eines Elements"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc06eea281f7761abfae74edf1547fc914b5655a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Gewusst wie: Festlegen der Höheneigenschaften eines Elements
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Unterschiede im Renderingverhalten zwischen den vier Höhe-bezogene Eigenschaften im visuell dargestellt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Die <xref:System.Windows.FrameworkElement> Klasse macht vier Eigenschaften, die die Höhenmerkmale eines Elements zu beschreiben. Diese vier Eigenschaften können es zu Konflikten, und wenn dies der Fall, wird der Wert, der Vorrang hat wie folgt bestimmt: die <xref:System.Windows.FrameworkElement.MinHeight%2A> Wert hat Vorrang vor den <xref:System.Windows.FrameworkElement.MaxHeight%2A> -Wert, der wiederum Vorrang vor den <xref:System.Windows.FrameworkElement.Height%2A> Wert. Eine vierte Eigenschaft <xref:System.Windows.FrameworkElement.ActualHeight%2A>ist schreibgeschützt und meldet die tatsächliche Höhe von Interaktionen mit dem Layoutprozess bestimmt.  
  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispielen eine <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) als untergeordnetes Element des <xref:System.Windows.Controls.Canvas>. Sie können die Eigenschaften für die Höhe des ändern eine <xref:System.Windows.Shapes.Rectangle> mithilfe einer Reihe von <xref:System.Windows.Controls.ListBox> Elemente, die die Eigenschaftswerte darstellen <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, und <xref:System.Windows.FrameworkElement.Height%2A>. Auf diese Weise wird die Rangfolge jeder Eigenschaft visuell angezeigt.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 In den folgenden Code-Behind-Beispielen die Ereignisse behandeln, die die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> -Ereignis ausgelöst wird. Jeder Handler verarbeitet die Eingabe aus der <xref:System.Windows.Controls.ListBox>, analysiert den Wert als eine <xref:System.Double>, und der Wert der angegebenen Höhe bezogene-Eigenschaft angewendet. Die Höhenwerte werden auch in eine Zeichenfolge konvertiert und auf verschiedenen festgeschrieben <xref:System.Windows.Controls.TextBlock> Elemente (die Definition dieser Elemente wird in der ausgewählten XAML nicht angezeigt).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Das vollständige Beispiel finden Sie unter [Höhe Eigenschaften Beispiel](http://go.microsoft.com/fwlink/?LinkID=159993).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [Festlegen der Breiteneigenschaften eines Elements](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Beispiel für Höhe](http://go.microsoft.com/fwlink/?LinkID=159993)
