---
title: 'Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 1b55afd5938073a326789e67b66fec9cfce12015
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43868522"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie eine Zeichenfolge, animieren, die in diesem Beispiel wird die <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button> -Steuerelement, mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button>.  
  
 Alle Keyframes in diesem Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> Klasse, da die Animation einer Zeichenfolge, die mit Keyframes erstellt wird nur diskrete Keyframes verwenden kann. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> abrupte Sprünge zwischen Werten, d. h. erstellen, Änderungen an der Animation schnell erfolgen und nicht subtil.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
