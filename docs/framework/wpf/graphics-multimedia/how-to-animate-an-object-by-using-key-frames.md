---
title: "Gewusst wie: Animieren eines Objekts mithilfe von Keyframes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation, Objekte mit Keyframes"
  - "Keyframes, Animieren von Objekten mit"
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Animieren eines Objekts mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie ein Objekt mithilfe von Keyframes animiert wird. Es handelt sich in diesem Fall um die <xref:System.Windows.Controls.Page.Background%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Page>\-Steuerelements.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>\-Klasse verwendet, um Farbwechsel für die <xref:System.Windows.Controls.Page.Background%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Page>\-Steuerelements zu animieren.  Die Beispielanimation ändert in regelmäßigen Abständen den Hintergrundpinsel.  Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>\-Klasse, um drei verschiedene Keyframes zu erstellen.  Die Animation verwendet Keyframes wie folgt:  
  
1.  Am Ende der ersten Sekunde wird eine Instanz der <xref:System.Windows.Media.LinearGradientBrush>\-Klasse animiert.  In diesem Abschnitt des Beispiels wird ein linearer Farbverlauf auf die Hintergrundfarbe angewendet, sodass die Farbe von gelb über orange zu rot wechselt.  
  
2.  Am Ende der letzten Sekunde wird eine Instanz der <xref:System.Windows.Media.RadialGradientBrush>\-Klasse animiert.  In diesem Abschnitt des Beispiels wird ein strahlenförmiger Farbverlauf auf die Hintergrundfarbe angewendet, sodass die Farbe von weiß über blau zu schwarz wechselt.  
  
3.  Am Ende der dritten Sekunde wird eine Instanz der <xref:System.Windows.Media.DrawingBrush>\-Klasse animiert.  In diesem Abschnitt des Beispiels wird ein Schachbrettmuster für den Hintergrund verwendet.  
  
4.  Die Animation startet erneut und wird endlos wiederholt.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> ist der einzige Keyframetyp, der mit der <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>\-Klasse verwendet werden kann.  Keyframes wie <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> führen zu abrupten Werteänderungen, d. h. die Farbwechsel in diesem Beispiel erfolgen ruckartig.  
  
 [!code-xml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.Page.Background%2A>   
 <xref:System.Windows.Controls.Page>   
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)