---
title: 'Gewusst wie: Drehen von Elementen ohne Positionsänderung'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 56385d7c31465e25f19486ea5cdaa8876cdb30ff
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43461630"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Gewusst wie: Drehen von Elementen ohne Positionsänderung
Dieses Beispiel zeigt, wie Sie ein Element, das Starten mit einem <xref:System.Windows.Media.RotateTransform> und <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements. Im Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> zum Animieren der <xref:System.Windows.Media.RotateTransform.Angle%2A> von der <xref:System.Windows.Media.RotateTransform>. Damit wird das Element an der Stelle, im Beispiel wird die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft des Elements, das den Punkt (0,5, 0,5).  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Enthält weitere Beispiele für die Transformation für das vollständige Beispiel finden Sie unter [2D-Transformationen Beispiel](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
