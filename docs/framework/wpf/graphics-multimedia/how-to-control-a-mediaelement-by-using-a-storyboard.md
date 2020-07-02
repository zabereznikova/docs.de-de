---
title: 'Gewusst wie: Steuern eines MediaElement mit einem Storyboard'
description: Steuern der Wiedergabe von Medien mithilfe eines Storyboards in Windows Presentation Foundation (WPF). Sehen Sie sich dieses Beispiel zum Erstellen eines einfachen Media Player an.
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
ms.openlocfilehash: 5a5e41b9a28211495fd3374c1a51a655dd867bca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853736"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Gewusst wie: Steuern eines MediaElement mit einem Storyboard
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.MediaElement> mit einem <xref:System.Windows.Media.MediaTimeline> in einem gesteuert wird <xref:System.Windows.Media.Animation.Storyboard> .  
  
## <a name="example"></a>Beispiel  
 Wenn Sie einen <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard> zum Steuern der zeitliche Steuerung von verwenden, <xref:System.Windows.Controls.MediaElement> ist die-Funktion identisch mit der Funktionalität anderer- <xref:System.Windows.Media.Animation.Timeline> Objekte, z. b. Animationen. Beispielsweise verwendet eine <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.Timeline> Eigenschaften wie die- <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft, um anzugeben, wann ein gestartet werden soll <xref:System.Windows.Controls.MediaElement> (Medienwiedergabe starten). Außerdem wird die- <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft verwendet, um anzugeben, wie lange der <xref:System.Windows.Controls.MediaElement> aktiv ist (Dauer der Medienwiedergabe). Weitere Informationen zum Verwenden von <xref:System.Windows.Media.Animation.Timeline> Objekten mit einem <xref:System.Windows.Media.Animation.Storyboard> finden Sie unter [Übersicht über Storyboards](storyboards-overview.md).  
  
 In diesem Beispiel wird gezeigt, wie ein einfacher Media Player erstellt wird, der einen <xref:System.Windows.Media.MediaTimeline> zum Steuern der Wiedergabe verwendet. Der Media Player umfasst die Schaltflächen wiedergeben, anhalten, fortsetzen und anhalten. Der Player verfügt auch über ein <xref:System.Windows.Controls.Slider> Steuerelement, das als Statusanzeige fungiert.  
  
 Im folgenden Beispiel wird der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für den Media Player erstellt.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 Im folgenden Beispiel werden die Funktionen für die Statusanzeige erstellt.  
  
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
- [Artikel zu Vorgehensweisen](audio-and-video-how-to-topics.md)
- [Grafiken und Multimedia](index.md)
