---
title: 'Gewusst wie: Wiedergeben von Medien mit Animationen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44ebb89c25fc37292f82533c929aae44854db5c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-media-with-animations"></a>Gewusst wie: Wiedergeben von Medien mit Animationen
In diesem Beispiel wird gezeigt, wie für die Wiedergabe von Medien und Animationen gleichzeitig mithilfe der <xref:System.Windows.Media.MediaTimeline> und <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Klassen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Beispiel  
 Sie können eine oder mehrere <xref:System.Windows.Media.MediaTimeline> Objekte in einer <xref:System.Windows.Media.Animation.Storyboard> zusammen mit anderen <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> Eigenschaft von der <xref:System.Windows.Media.Animation.Storyboard> auf einen Wert von `Slip`, was bedeutet, dass die Animation wird erst im Verlauf Mediums (video in diesem Beispiel) nicht ausgeführt. Diese Funktionalität ist hilfreich, wenn die Wiedergabe von Medien auf Grund ihrer Ladezeit verzögert wird.  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)
