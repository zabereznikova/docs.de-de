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
ms.openlocfilehash: ebc8d4c6cb36d76b70691cce183f9e6070d19822
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399426"
---
# <a name="how-to-transform-a-brush"></a>Gewusst wie: Transformieren eines Pinsels
Dieses Beispiel zeigt, wie Sie transformieren <xref:System.Windows.Media.Brush> Objekte mithilfe von zwei Transformationseigenschaften: <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 Die folgenden Beispiele verwenden eine <xref:System.Windows.Media.RotateTransform> so drehen den Inhalt des ein <xref:System.Windows.Media.ImageBrush> um 45 Grad um.  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Media.ImageBrush> ohne eine <xref:System.Windows.Media.RotateTransform>, mit der <xref:System.Windows.Media.RotateTransform> angewendet der <xref:System.Windows.Media.Brush.RelativeTransform%2A> -Eigenschaft, und mit der <xref:System.Windows.Media.RotateTransform> angewendet der <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaft.  
  
 ![RelativeTransform- und Transform-Pinseleinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "Wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Beispiel  
 Im ersten Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft eine <xref:System.Windows.Media.ImageBrush>. Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften eine <xref:System.Windows.Media.RotateTransform> Objekt beide auf 0,5, d.h. die relative des Mittelpunkts dieser Inhalte Koordinate festgelegt sind. Daher die <xref:System.Windows.Media.ImageBrush> Inhalt dreht sich seinen Mittelpunkt.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Im zweite Beispiel gilt auch für eine <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Media.ImageBrush>, aber dieses Beispiel verwendet die <xref:System.Windows.Media.Brush.Transform%2A> -Eigenschaft anstelle von der <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft.  
  
 Um den Pinsel um seinen Mittelpunkt zu drehen, im Beispiel wird die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften der <xref:System.Windows.Media.RotateTransform> -Objekts auf absolute Koordinaten. Da der Pinsel ein Rechteck mit der Größe 175 mal 90 Pixel zeichnet, liegt der Mittelpunkt des Rechtecks bei (87,5/45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Eine Beschreibung dafür, wie die <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaften arbeiten, finden Sie unter den [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen über Pinsel finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
