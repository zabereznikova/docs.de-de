---
title: 'Gewusst wie: Animieren eines Point mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344880"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Gewusst wie: Animieren eines Point mithilfe von Keyframes
In diesem Beispiel wird <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> gezeigt, <xref:System.Windows.Point>wie die Klasse zum Animieren einer verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Ellipse entlang eines dreieckigen Pfads verschoben. Im Beispiel <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.EllipseGeometry.Center%2A> Klasse verwendet, um die Eigenschaft einer <xref:System.Windows.Media.EllipseGeometry>zu animieren. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. Verwendet in der ersten Hälfte eine <xref:System.Windows.Media.Animation.LinearPointKeyFrame> Instanz der Klasse, um die Ellipse mit einer konstanten Geschwindigkeit von ihrer Ausgangsposition aus entlang eines Pfads zu bewegen. Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearPointKeyFrame> erstellen eine glatte lineare Interpolation zwischen Werten.  
  
2. Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> eine Instanz der Klasse, um die Ellipse plötzlich auf dem Pfad zur nächsten Position zu verschieben. Diskrete Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> wie erstellen plötzliche Sprünge zwischen Werten.  
  
3. Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplinePointKeyFrame> eine Instanz der Klasse, um die Ellipse wieder in ihre Ausgangsposition zu verschieben. Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplinePointKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> zwischen Werten entsprechend den Werten der Eigenschaft. In diesem Beispiel beginnt die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Aus Gründen der Konsistenz mit anderen Animationsbeispielen <xref:System.Windows.Media.Animation.Storyboard> verwenden die <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>Codeversionen dieses Beispiels ein Objekt, um die anzuwenden. Wenn Sie jedoch eine einzelne Animation im Code anwenden, ist es einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>zu verwenden. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Verwendung eines Storyboards](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
