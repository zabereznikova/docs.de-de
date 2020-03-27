---
title: 'Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344666"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie eine <xref:System.Windows.Controls.ContentControl.Content%2A> Zeichenfolge, <xref:System.Windows.Controls.Button> die in diesem Beispiel die Eigenschaft eines Steuerelements ist, mithilfe von Schlüsselrahmen animiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> wird die <xref:System.Windows.Controls.ContentControl.Content%2A> Klasse <xref:System.Windows.Controls.Button>verwendet, um die Eigenschaft einer zu animieren.  
  
 Alle Schlüsselbilder in diesem Beispiel verwenden <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> eine Instanz der Klasse, da eine Zeichenfolgenanimation, die mit Schlüsselbildern erstellt wird, nur diskrete Schlüsselrahmen verwenden kann. Diskrete Schlüsselbilder <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> wie plötzliche Sprünge zwischen Werten erstellen, d. h. Änderungen an der Animation treten schnell auf und sind nicht subtil.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
