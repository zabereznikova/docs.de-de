---
title: 'Gewusst wie: Animieren der Position eines Objekts mit PointAnimation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa412a889ee82c9bf20ff1d6420d8a86f339ca6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Gewusst wie: Animieren der Position eines Objekts mit PointAnimation
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.PointAnimation> Klasse, um ein Objekt entlang Animieren einer <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Ellipse, die zusammen eine <xref:System.Windows.Shapes.Path> von einem Punkt auf dem Bildschirm zu einem anderen. Das Beispiel erstellt eine Animation, die Position des ein <xref:System.Windows.Media.EllipseGeometry> mit <xref:System.Windows.Media.Animation.PointAnimation> zum Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [Animation und zeitlichen Steuerung](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
