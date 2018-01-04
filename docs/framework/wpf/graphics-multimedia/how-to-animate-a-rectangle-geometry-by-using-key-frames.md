---
title: 'Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes'
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
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f110bcea76a61d46932c9e1aacf27f6f3255a91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Eigenschaft eine <xref:System.Windows.Media.RectangleGeometry> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Eigenschaft eine <xref:System.Windows.Media.RectangleGeometry>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  Bei den ersten zwei Sekunden verwendet eine Instanz der <xref:System.Windows.Media.Animation.LinearRectKeyFrame> Klasse, um eine schrittweise Änderung in die Position, Breite und Höhe eines Rechtecks animiert. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearRectKeyFrame> einen smooth linearen Übergang zwischen den Werten zu erstellen.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> Klasse, um die Höhe des Rechtecks abrupt zu verringern. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> , erstellen Sie dabei plötzliche Änderungen zwischen Werten, d. h. die Abnahme der Höhe erfolgt schnell und ist kein feine.  
  
3.  In den letzten zwei Sekunden verwendet eine Instanz der <xref:System.Windows.Media.Animation.SplineRectKeyFrame> Klasse so ändern Sie das Rechteck zurück an seine ursprüngliche Größe und Position. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineRectKeyFrame> erstellen Sie einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel beginnt die Veränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
