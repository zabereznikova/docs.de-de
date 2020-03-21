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
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187338"
---
# <a name="how-to-transform-a-brush"></a>Gewusst wie: Transformieren eines Pinsels
In diesem Beispiel <xref:System.Windows.Media.Brush> wird gezeigt, wie Objekte <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A>mithilfe ihrer beiden Transformationseigenschaften transformiert werden: und .  
  
 In den folgenden <xref:System.Windows.Media.RotateTransform> Beispielen wird <xref:System.Windows.Media.ImageBrush> ein verwendet, um den Inhalt eines um 45 Grad zu drehen.  
  
 Die folgende Abbildung <xref:System.Windows.Media.ImageBrush> zeigt <xref:System.Windows.Media.RotateTransform>die <xref:System.Windows.Media.RotateTransform> ohne a, wobei die auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft angewendet und die <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaft angewendet wird.  
  
 ![RelativeTransform- und Transform-Pinseleinstellungen](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Beispiel  
 Das erste Beispiel <xref:System.Windows.Media.RotateTransform> wendet <xref:System.Windows.Media.Brush.RelativeTransform%2A> eine <xref:System.Windows.Media.ImageBrush>auf die Eigenschaft einer an. Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> und Eigenschaften <xref:System.Windows.Media.RotateTransform> eines Objekts sind beide auf 0,5 festgelegt, was die relative Koordinate des Mittelpunkts dieses Inhalts ist. Dadurch dreht sich <xref:System.Windows.Media.ImageBrush> der Inhalt um seine Mitte.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Das zweite Beispiel <xref:System.Windows.Media.RotateTransform> gilt <xref:System.Windows.Media.ImageBrush>auch für eine ; In diesem Beispiel <xref:System.Windows.Media.Brush.Transform%2A> wird jedoch <xref:System.Windows.Media.Brush.RelativeTransform%2A> die Eigenschaft anstelle der Eigenschaft verwendet.  
  
 Um den Pinsel um seine Mitte <xref:System.Windows.Media.RotateTransform.CenterX%2A> zu <xref:System.Windows.Media.RotateTransform.CenterY%2A> drehen, <xref:System.Windows.Media.RotateTransform> legt das Beispiel die und die Eigenschaften des Objekts auf absolute Koordinaten fest. Da der Pinsel ein Rechteck mit der Größe 175 mal 90 Pixel zeichnet, liegt der Mittelpunkt des Rechtecks bei (87,5/45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Eine Beschreibung der <xref:System.Windows.Media.Brush.RelativeTransform%2A> Funktionsweise <xref:System.Windows.Media.Brush.Transform%2A> und der Eigenschaften finden Sie in der [Pinseltransformationsübersicht](brush-transformation-overview.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Weitere Informationen über Pinsel finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Pinseltransformationen](brush-transformation-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über Transformationen](transforms-overview.md)
