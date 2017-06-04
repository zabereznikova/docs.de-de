---
title: "Gewusst wie: Steuern eines MediaElement mit einem Storyboard | Microsoft Docs"
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
  - "Steuern der Medienwiedergabe, Mit Storyboards"
  - "Medien, Steuern der Wiedergabe mit Storyboards"
  - "Multimedia, Steuern der Medienwiedergabe mit Storyboards"
  - "Medienwiedergabe, Steuern mit Storyboards"
  - "Storyboards, Steuern der Medienwiedergabe mit"
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Steuern eines MediaElement mit einem Storyboard
In diesem Beispiel wird das Steuern eines <xref:System.Windows.Controls.MediaElement> unter Verwendung von <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard> gezeigt.  
  
## Beispiel  
 Wenn eine <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard> zur zeitlichen Steuerung eines <xref:System.Windows.Controls.MediaElement> verwendet wird, ist die Funktionalität identisch mit der Funktionalität anderer <xref:System.Windows.Media.Animation.Timeline>\-Objekte, z. B. Animationen.  Eine <xref:System.Windows.Media.MediaTimeline> verwendet beispielsweise <xref:System.Windows.Media.Animation.Timeline>\-Eigenschaften, z. B. die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>\-Eigenschaft, um anzugeben, wann ein <xref:System.Windows.Controls.MediaElement> gestartet werden soll \(Medienwiedergabe starten\).  Weiterhin wird die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>\-Eigenschaft verwendet, um anzugeben, wie lange das <xref:System.Windows.Controls.MediaElement> aktiv ist \(Medienwiedergabedauer\).  Weitere Informationen zum Verwenden von <xref:System.Windows.Media.Animation.Timeline>\-Objekten mit einem <xref:System.Windows.Media.Animation.Storyboard> finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Im folgenden Beispiel wird ein einfacher Media Player erstellt, der zum Steuern der Wiedergabe eine <xref:System.Windows.Media.MediaTimeline> verwendet.  Der Media Player enthält Schaltflächen für Wiedergabe, Pause, Fortsetzen und Beenden.  Der Player verfügt als Statusanzeige zusätzlich über ein <xref:System.Windows.Controls.Slider>\-Steuerelement.  
  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für den Media Player erstellt.  
  
 [!code-xml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 Im folgenden Beispiel werden die Funktionen der Statusanzeige erstellt.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.MediaElement>   
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Steuern eines MediaElement \(Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)