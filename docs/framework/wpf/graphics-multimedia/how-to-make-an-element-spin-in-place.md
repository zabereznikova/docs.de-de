---
title: 'Gewusst wie: Drehen von Elementen ohne Positionsänderung'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452791"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Gewusst wie: Drehen von Elementen ohne Positionsänderung
In diesem Beispiel wird gezeigt, wie ein Element mit einem <xref:System.Windows.Media.RotateTransform> und einem <xref:System.Windows.Media.Animation.DoubleAnimation>gedreht wird.  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A>-Eigenschaft des-Elements angewendet. Das Beispiel verwendet eine <xref:System.Windows.Media.Animation.DoubleAnimation>, um die <xref:System.Windows.Media.RotateTransform.Angle%2A> der <xref:System.Windows.Media.RotateTransform>zu animieren. Damit das Element gedreht wird, wird im Beispiel die <xref:System.Windows.UIElement.RenderTransformOrigin%2A>-Eigenschaft des-Elements auf den Punkt (0,5, 0,5) festgelegt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Das komplette Beispiel, das weitere Transformations Beispiele enthält, finden Sie unter [Beispiel für 2D-Transformationen](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Transformationen](transforms-overview.md)
