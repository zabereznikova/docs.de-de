---
title: "Gewusst wie: Festlegen der Flächengröße für ein TileBrush-Objekt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e9b746fe66635054dbd35463f727d28a8abd3d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Gewusst wie: Festlegen der Flächengröße für ein TileBrush-Objekt
In diesem Beispiel wird gezeigt, wie zum Festlegen der Kachelgröße für ein <xref:System.Windows.Media.TileBrush>. Wird standardmäßig ein <xref:System.Windows.Media.TileBrush> eine einzige Kachel, die vollständig auf den Bereich ausfüllt, der zu zeichnenden erzeugt. Sie können dieses Verhalten außer Kraft setzen, durch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften.  
  
 Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft gibt die Kachelgröße für ein <xref:System.Windows.Media.TileBrush>. Standardmäßig wird der Wert des der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft ist relativ zur Größe des Clientbereichs gezeichnet wird. Vornehmen der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft geben Sie eine absolute Flächengröße Festlegen der <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush>, einen Typ von <xref:System.Windows.Media.TileBrush>, um ein Rechteck mit Kacheln zu zeichnen. In diesem Beispiel werden die Seiten der einzelnen Flächen auf 50 x 50 Prozent der Seiten des Ausgabebereichs (des Rechtecks) festgelegt. Als Ergebnis wird das Rechteck mit vier Projektionen des Bilds gezeichnet.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.
  
 ![Beispiel für die Anordnung mit einem Bildpinsel](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 Im nächste Beispiel wird erstellt ein <xref:System.Windows.Media.ImageBrush>, legt seine <xref:System.Windows.Media.TileBrush.Viewport%2A> auf `0,0,25,25` und seine <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> auf <xref:System.Windows.Media.BrushMappingMode.Absolute>, und verwendet, um einen anderen Rechteck gezeichnet. Als Ergebnis erzeugt der Pinsel Flächen mit einer Breite und Höhe von 25 Pixeln.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Flächen mit einem Viewport von 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Die vorangehenden Beispiele sind Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Obwohl in diesem Beispiel verwendet die <xref:System.Windows.Media.ImageBrush> -Klasse, die <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften verhalten sich identisch, für die anderen <xref:System.Windows.Media.TileBrush> Objekte aufweist, d. h. für <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>. Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und die andere <xref:System.Windows.Media.TileBrush> anzuzeigen, [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.TileBrush>  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
