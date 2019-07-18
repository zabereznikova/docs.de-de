---
title: 'Vorgehensweise: Animieren eines Objekts mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: b0a0f7c00125a43228a2658415b72f4d541f37be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020152"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Vorgehensweise: Animieren eines Objekts mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie zum Animieren eines Objekts, die in diesem Beispiel wird die <xref:System.Windows.Controls.Page.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Page> -Steuerelement, mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> -Klasse zum Animieren der Farbe ändert, für die <xref:System.Windows.Controls.Page.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Page> Steuerelement. Beispiel ändert sich die Animation in einen anderen Hintergrundpinsel in regelmäßigen Abständen. Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> Klasse, um drei verschiedene Keyframes zu erstellen. Die Animation werden Keyframes folgendermaßen verwendet:  
  
1. Am Ende der ersten Sekunde, eine Animation auf eine Instanz von der <xref:System.Windows.Media.LinearGradientBrush> Klasse. In diesem Abschnitt des Beispiels gilt die Farbe des Hintergrunds ein lineares Farbverlaufs, damit die Farbe von Gelb zu Orange zu rot ändert.  
  
2. Am Ende der nächsten Sekunde, eine Animation auf eine Instanz von der <xref:System.Windows.Media.RadialGradientBrush> Klasse. In diesem Abschnitt des Beispiels gilt die Farbe des Hintergrunds ein radiales Farbverlaufs, damit die Farbe von weiß zu Schwarz Blau wechselt.  
  
3. Am Ende des dritten zweiten, eine Animation auf eine Instanz von der <xref:System.Windows.Media.DrawingBrush> Klasse. In diesem Abschnitt des Beispiels wird ein Schachbrettmuster in den Hintergrund.  
  
4. Die Animation erneut gestartet, und es wird auf unbestimmte Zeit wiederholt.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> ist die einzige Art des Keyframes, mit denen Sie mit der <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> Klasse. Schlüssel wie frames <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> können abrupte Veränderungen in den Werten, d. h., ändert sich die Farbe, in diesem Beispiel treten plötzlich.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](key-frame-animation-how-to-topics.md)
