---
title: 'Vorgehensweise: Animieren einer Rechteckgeometrie mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 03953b79127ffceeb49e4ece2070d09f382448a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010097"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Vorgehensweise: Animieren einer Rechteckgeometrie mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Eigenschaft eine <xref:System.Windows.Media.RectangleGeometry> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Eigenschaft eine <xref:System.Windows.Media.RectangleGeometry>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. In den ersten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearRectKeyFrame> Klasse, um eine schrittweise Änderung der Position, Breite und Höhe eines Rechtecks zu animieren. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearRectKeyFrame> einen glatten, linearen Übergang zwischen Werten zu erstellen.  
  
2. Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> Klasse, um die Höhe des Rechtecks abrupt zu verringern. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> abrupte Veränderungen zwischen Werten, d. h. erstellen, die Verringerung der Höhe tritt schnell auf und ist.  
  
3. In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplineRectKeyFrame> Klasse so ändern Sie das Rechteck zurück in seiner ursprünglichen Größe und Position. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineRectKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel beginnt die Veränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](key-frame-animation-how-to-topics.md)
