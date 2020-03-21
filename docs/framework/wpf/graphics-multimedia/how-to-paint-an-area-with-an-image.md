---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186054"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Gewusst wie: Zeichnen eines Bereichs mit einem Bild
In diesem Beispiel wird <xref:System.Windows.Media.ImageBrush> gezeigt, wie sie die Klasse zum Zeichnen eines Bereichs mit einem Bild verwendet. Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild <xref:System.Windows.Media.ImageBrush.ImageSource%2A> an, das durch seine Eigenschaft angegeben wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Controls.Control.Background%2A> wird die Schaltfläche <xref:System.Windows.Media.ImageBrush>mithilfe einer gezeichnet.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Standardmäßig dehnt ein <xref:System.Windows.Media.ImageBrush> Bild sein Bild aus, um den Bereich, den Sie malen, vollständig zu füllen. Im vorhergehenden Beispiel wird das Bild zum Ausfüllen der Schaltfläche gestreckt, wobei das Bild möglicherweise verzerrt wird. Sie können dieses Verhalten <xref:System.Windows.Media.TileBrush.Stretch%2A> steuern, <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> indem <xref:System.Windows.Media.Stretch.UniformToFill>Sie die Eigenschaft von oder festlegen, wodurch der Pinsel das Seitenverhältnis des Bildes beibehält.  
  
 Wenn Sie <xref:System.Windows.Media.TileBrush.Viewport%2A> die <xref:System.Windows.Media.TileBrush.TileMode%2A> und <xref:System.Windows.Media.ImageBrush>die Eigenschaften eines festlegen, können Sie ein wiederholtes Muster erstellen. Im folgenden Beispiel wird eine Schaltfläche mithilfe eines Musters gezeichnet, das auf Basis eines Bilds erstellt wird.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.ImageBrush> Klasse finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).  
  
 Dieses Codebeispiel ist Teil eines größeren Beispiels, das für die <xref:System.Windows.Media.ImageBrush> Klasse bereitgestellt wird. Das vollständige Beispiel finden Sie unter [ImageBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Weitere Informationen

- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
