---
title: 'Gewusst wie: Steuern eines MediaElement mit einem Storyboard'
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
ms.openlocfilehash: 88124d5b26a991a10b470c8cf0e587a5c7a4b10a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561591"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Gewusst wie: Steuern eines MediaElement mit einem Storyboard
In diesem Beispiel wird gezeigt, wie zur Steuerung einer <xref:System.Windows.Controls.MediaElement> mithilfe einer <xref:System.Windows.Media.MediaTimeline> in eine <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Beispiel  
 Bei Verwendung einer <xref:System.Windows.Media.MediaTimeline> in einer <xref:System.Windows.Media.Animation.Storyboard> zeitlich steuern eine <xref:System.Windows.Controls.MediaElement>, die Funktionalität ist identisch mit der Funktionalität anderer <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen. Z. B. eine <xref:System.Windows.Media.MediaTimeline> verwendet <xref:System.Windows.Media.Animation.Timeline> Eigenschaften, z. B. die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft angeben, wann Starten einer <xref:System.Windows.Controls.MediaElement> (Medienwiedergabe starten). Darüber hinaus verwendet der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft an, wie lange der <xref:System.Windows.Controls.MediaElement> aktiv ist (Dauer Medienwiedergabe). Weitere Informationen zur Verwendung von <xref:System.Windows.Media.Animation.Timeline> Objekte mit einem <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 In diesem Beispiel wird gezeigt, wie Sie einen einfachen MediaPlayer erstellen, verwendet eine <xref:System.Windows.Media.MediaTimeline> zum Steuern der Wiedergabe. Der Media-Player enthält wiedergeben, anhalten, fortsetzen und beenden Sie die Schaltflächen. Der Player verfügt auch über eine <xref:System.Windows.Controls.Slider> Steuerelement, das als eine Statusanzeige fungiert.  
  
 Das folgende Beispiel erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für Media-Player.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 Im folgende Beispiel wird die Funktionalität für die Statusanzeige erstellt.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)
