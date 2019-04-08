---
title: 'Vorgehensweise: Steuern eines MediaElement-Objekts mit einem Storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
ms.openlocfilehash: ae785e11b1da0f2c408b24021ad46ab071419378
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100313"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Vorgehensweise: Steuern eines MediaElement-Objekts mit einem Storyboard
Dieses Beispiel zeigt, wie Sie steuern eine <xref:System.Windows.Controls.MediaElement> mithilfe einer <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Beispiel  
 Bei Verwendung einer <xref:System.Windows.Media.MediaTimeline> in einer <xref:System.Windows.Media.Animation.Storyboard> zeitlich steuern eine <xref:System.Windows.Controls.MediaElement>, die Funktionalität ist identisch mit der Funktionalität von anderen <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen. Z. B. eine <xref:System.Windows.Media.MediaTimeline> verwendet <xref:System.Windows.Media.Animation.Timeline> Eigenschaften wie die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft, um anzugeben, wann zu einem <xref:System.Windows.Controls.MediaElement> (Starten der Wiedergabe von Medien). Darüber hinaus verwendet er die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> -Eigenschaft an wie lange der <xref:System.Windows.Controls.MediaElement> aktiv ist (Dauer der Wiedergabe von Medien). Weitere Informationen zur Verwendung von <xref:System.Windows.Media.Animation.Timeline> Objekte mit einem <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter [Übersicht über Storyboards](storyboards-overview.md).  
  
 In diesem Beispiel wird gezeigt, wie Sie einen einfachen MediaPlayer erstellen, verwendet eine <xref:System.Windows.Media.MediaTimeline> zum Steuern der Wiedergabe. Der MediaPlayer enthält Wiedergabe, anhalten, fortsetzen und beenden Sie die Schaltflächen. Der Player verfügt auch über eine <xref:System.Windows.Controls.Slider> -Steuerelement, das als eine Statusanzeige fungiert.  
  
 Das folgende Beispiel erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für MediaPlayer.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 Das folgende Beispiel erstellt die Funktionalität für die Statusanzeige.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Steuern eines MediaElement-Objekts (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [Übersicht über Storyboards](storyboards-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Übersicht über Animationen](animation-overview.md)
- [Gewusst wie-Themen](audio-and-video-how-to-topics.md)
- [Grafiken und Multimedia](index.md)
