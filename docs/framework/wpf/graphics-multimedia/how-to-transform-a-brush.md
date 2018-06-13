---
title: 'Gewusst wie: Transformieren eines Pinsels'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: 5caa00a378101ff4dff7745a18c3ec8905cc168b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561592"
---
# <a name="how-to-transform-a-brush"></a>Gewusst wie: Transformieren eines Pinsels
Dieses Beispiel zeigt, wie Sie <xref:System.Windows.Media.Brush> Objekte mithilfe von zwei Transformationseigenschaften: <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 Die folgenden Beispiele verwenden eine <xref:System.Windows.Media.RotateTransform> drehen Sie den Inhalt des ein <xref:System.Windows.Media.ImageBrush> um 45 Grad.  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Media.ImageBrush> ohne eine <xref:System.Windows.Media.RotateTransform>, mit der <xref:System.Windows.Media.RotateTransform> angewendet, um die <xref:System.Windows.Media.Brush.RelativeTransform%2A> -Eigenschaft, und mit der <xref:System.Windows.Media.RotateTransform> angewendet der <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaft.  
  
 ![RelativeTransform- und Transform-Pinseleinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "Wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Beispiel  
 Im erste Beispiel gilt eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft ein <xref:System.Windows.Media.ImageBrush>. Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften eine <xref:System.Windows.Media.RotateTransform> -Objekt beide auf 0,5, d. h. die relative Koordinate des Mittelpunkts dieser Inhalt ist festgelegt sind. Daher die <xref:System.Windows.Media.ImageBrush> Inhalte zu ihren Mittelpunkt dreht.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Im zweite Beispiel gilt auch eine <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Media.ImageBrush>, aber in diesem Beispiel verwendet die <xref:System.Windows.Media.Brush.Transform%2A> -Eigenschaft anstelle von der <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft.  
  
 Um den Pinsel über seinen Mittelpunkt zu wechseln, im Beispiel wird die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften der <xref:System.Windows.Media.RotateTransform> Objekts mit absoluten Koordinaten. Da der Pinsel ein Rechteck mit der Größe 175 mal 90 Pixel zeichnet, liegt der Mittelpunkt des Rechtecks bei (87,5/45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Eine Beschreibung, wie das <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaften arbeiten, finden Sie unter der [Pinsel Transformation Overview](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen über Pinsel finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
