---
title: 'Gewusst wie: Übersetzen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 0089f294c54662d1ea4929ec25c08464072cbdde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-translate-an-element"></a>Gewusst wie: Übersetzen eines Elements
Dieses Beispiel zeigt, wie übersetzt (verschoben) ein Element mit einem <xref:System.Windows.Media.TranslateTransform>.  
  
 Die <xref:System.Windows.Media.TranslateTransform> Klasse ist besonders nützlich zum Verschieben von Elementen in Bereichen, die absolute Positionierung nicht unterstützen. Z. B. durch Anwenden einer <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eines Elements, verschieben Sie ein Element in einer <xref:System.Windows.Controls.StackPanel> oder <xref:System.Windows.Controls.DockPanel>.  
  
 Verwenden der <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft von der <xref:System.Windows.Media.TranslateTransform> an die Größe in Pixel, um das Element entlang der x-Achse verschoben. Verwenden der <xref:System.Windows.Media.TranslateTransform.Y%2A> Eigenschaft, um die Größe in Pixel, um das Element entlang der y-Achse verschoben anzugeben. Wenden Sie schließlich die <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.TranslateTransform> auf ein Element 50 Pixel nach rechts und 50 Pixel nach unten zu verschieben.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
