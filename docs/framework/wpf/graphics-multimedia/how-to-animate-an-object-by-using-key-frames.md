---
title: 'Gewusst wie: Animieren eines Objekts mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344707"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Gewusst wie: Animieren eines Objekts mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Page.Background%2A> Objekt, <xref:System.Windows.Controls.Page> das in diesem Beispiel die Eigenschaft eines Steuerelements ist, mithilfe von Schlüsselrahmen animiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> wird die Klasse <xref:System.Windows.Controls.Page.Background%2A> verwendet, <xref:System.Windows.Controls.Page> um Farbänderungen für die Eigenschaft eines Steuerelements zu animieren. Die Beispielanimation ändert sich in regelmäßigen Abständen in einen anderen Hintergrundpinsel. Diese Animation <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> verwendet die Klasse, um drei verschiedene Schlüsselbilder zu erstellen. Die Animation verwendet Schlüsselbilder auf folgende Weise:  
  
1. Animiert am Ende der ersten Sekunde <xref:System.Windows.Media.LinearGradientBrush> eine Instanz der Klasse. In diesem Beispielabschnitt wird ein linearer Farbverlauf auf die Hintergrundfarbe angewendet, sodass die Farbe von gelb zu orange zu rot übergeht.  
  
2. Animiert am Ende der nächsten Sekunde <xref:System.Windows.Media.RadialGradientBrush> eine Instanz der Klasse. In diesem Beispielabschnitt wird ein radialer Farbverlauf auf die Hintergrundfarbe angewendet, sodass die Farbe von Weiß zu Blau zu Schwarz übergeht.  
  
3. Am Ende der dritten Sekunde wird eine <xref:System.Windows.Media.DrawingBrush> Instanz der Klasse animiert. In diesem Beispielabschnitt wird ein Schachbrettmuster auf den Hintergrund angewendet.  
  
4. Die Animation wird erneut und auf unbestimmte Zeit wiederholt.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>ist der einzige Schlüsselrahmentyp, den <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> Sie mit der Klasse verwenden können. Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> wie erstellen plötzliche Änderungen in Werten, das heißt, die Farbänderungen in diesem Beispiel treten plötzlich auf.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
