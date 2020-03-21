---
title: 'Gewusst wie: Drehen von Elementen ohne Positionsänderung'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112075"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Gewusst wie: Drehen von Elementen ohne Positionsänderung
Dieses Beispiel zeigt, wie ein Element <xref:System.Windows.Media.RotateTransform> mithilfe <xref:System.Windows.Media.Animation.DoubleAnimation>von a und a gespinnt wird.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.RotateTransform> wird <xref:System.Windows.UIElement.RenderTransform%2A> die Eigenschaft des Elements angewendet. Im Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> wird a <xref:System.Windows.Media.RotateTransform.Angle%2A> verwendet, um die der <xref:System.Windows.Media.RotateTransform>zu animieren. Um das Element an Ort und <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Stelle zu drehen, legt das Beispiel die Eigenschaft des Elements auf den Punkt (0,5, 0,5) fest.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Das vollständige Beispiel, das weitere Transformationsbeispiele enthält, finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Transformationen](transforms-overview.md)
