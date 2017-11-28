---
title: "Gewusst wie: Drehen von Elementen ohne Positionsänderung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7dac2b1afb9d0ed385f3c25c2e30a93ea8a24f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-an-element-spin-in-place"></a>Gewusst wie: Drehen von Elementen ohne Positionsänderung
Dieses Beispiel zeigt, wie Sie ein Element mit spin eine <xref:System.Windows.Media.RotateTransform> und ein <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Das folgende Beispiel wendet die <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements. Im Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> zum Animieren der <xref:System.Windows.Media.RotateTransform.Angle%2A> von der <xref:System.Windows.Media.RotateTransform>. Um das Element an der Stelle zu machen, die im Beispiel wird die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft des Elements, das den Punkt (0,5, 0,5).  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Enthält weitere Beispiele für die Transformation für das vollständige Beispiel finden Sie unter [2D-Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
