---
title: "Gewusst wie: Wiedergeben von Medien mit Animationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Multimedia, Wiedergabe mit Animation"
  - "Bei der Wiedergabe von Medien mit Animationen"
  - "Wiedergabe von Medien mit Animationen"
  - "Medien, Wiedergabe mit Animation"
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Wiedergeben von Medien mit Animationen
Dieses Beispiel veranschaulicht die Wiedergabe von Medien und Animationen gleichzeitig mit der <xref:System.Windows.Media.MediaTimeline> und <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Klassen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Beispiel  
 Können Sie eine oder mehrere <xref:System.Windows.Media.MediaTimeline> Objekte in einem <xref:System.Windows.Media.Animation.Storyboard> zusammen mit anderen <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> Eigenschaft der <xref:System.Windows.Media.Animation.Storyboard> auf einen Wert von `Slip`, die angibt, dass die Animation bis verläuft die Medien (video in diesem Beispiel) wird nicht ausgeführt. Diese Funktionalität kann erforderlich sein, wenn die Medienwiedergabe aufgrund der Ladezeit verzögert wird.  
  
 [!code-xml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>   
 [Gewusst-wie-Themen](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Übersicht über Keyframe Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)