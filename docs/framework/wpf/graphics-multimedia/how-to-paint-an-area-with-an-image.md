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
ms.openlocfilehash: 5899531291c22ada76213905d0f2ca6944fcbba7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408019"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Gewusst wie: Zeichnen eines Bereichs mit einem Bild
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.ImageBrush> -Klasse zum Zeichnen eines Bereichs mit einem Bild. Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild, das angegebenen seine <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeichnet die <xref:System.Windows.Controls.Control.Background%2A> einer Schaltfläche mithilfe einer <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Standardmäßig eine <xref:System.Windows.Media.ImageBrush> gestreckt wird, das Image aus, um vollständig auf die Fläche auszufüllen, die Sie zeichnen werden. Im vorhergehenden Beispiel wird das Bild zum Ausfüllen der Schaltfläche gestreckt, wobei das Bild möglicherweise verzerrt wird. Sie können dieses Verhalten steuern, durch Festlegen der <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft <xref:System.Windows.Media.TileBrush> zu <xref:System.Windows.Media.Stretch.Uniform> oder <xref:System.Windows.Media.Stretch.UniformToFill>, der bewirkt, dass des Pinsels das Seitenverhältnis des Bilds beibehalten.  
  
 Setzen Sie die <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaften eine <xref:System.Windows.Media.ImageBrush>, Sie können ein sich wiederholendes Muster erstellen. Im folgenden Beispiel wird eine Schaltfläche mithilfe eines Musters gezeichnet, das auf Basis eines Bilds erstellt wird.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.ImageBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Dieses Codebeispiel ist Teil eines größeren Beispiels, die aus Gründen der <xref:System.Windows.Media.ImageBrush> Klasse. Das vollständige Beispiel finden Sie unter [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
