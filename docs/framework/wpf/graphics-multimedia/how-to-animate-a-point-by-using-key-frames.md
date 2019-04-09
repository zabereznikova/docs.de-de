---
title: 'Vorgehensweise: Animieren eines Point mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: 2e34ba035c8d7f9132915a9269d545f32033cbed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132586"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Vorgehensweise: Animieren eines Point mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> -Klasse zum Animieren einer <xref:System.Windows.Point>.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Ellipse entlang eines dreieckigen Pfads verschoben. Im Beispiel wird die <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft eine <xref:System.Windows.Media.EllipseGeometry>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In der ersten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearPointKeyFrame> Klasse, um die Ellipse entlang eines Pfads von der Startposition mit konstanter Geschwindigkeit zu verschieben. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearPointKeyFrame> eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> Klasse, um die Ellipse entlang des Pfads abrupt an die nächste Position zu bewegen. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> ermöglichen abrupte Sprünge zwischen Werten.  
  
3.  In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplinePointKeyFrame> Klasse, um die Ellipse zurück an seine Ausgangsposition zu verschieben. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplinePointKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel beginnt die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Verwenden Sie für Konsistenz mit anderen Animationsbeispielen die Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard> Objekt anzuwendende der <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>. Beim Anwenden einer Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
