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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="6eb56-104">Gewusst wie: Steuern eines MediaElement mit einem Storyboard</span><span class="sxs-lookup"><span data-stu-id="6eb56-104">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="6eb56-105">In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.MediaElement> mit einem <xref:System.Windows.Media.MediaTimeline> in einem gesteuert wird <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="6eb56-105">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eb56-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6eb56-106">Example</span></span>  
 <span data-ttu-id="6eb56-107">Wenn Sie einen <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard> zum Steuern der zeitliche Steuerung von verwenden, <xref:System.Windows.Controls.MediaElement> ist die-Funktion identisch mit der Funktionalität anderer- <xref:System.Windows.Media.Animation.Timeline> Objekte, z. b. Animationen.</span><span class="sxs-lookup"><span data-stu-id="6eb56-107">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="6eb56-108">Beispielsweise verwendet eine <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.Timeline> Eigenschaften wie die- <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft, um anzugeben, wann ein gestartet werden soll <xref:System.Windows.Controls.MediaElement> (Medienwiedergabe starten).</span><span class="sxs-lookup"><span data-stu-id="6eb56-108">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="6eb56-109">Außerdem wird die- <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft verwendet, um anzugeben, wie lange der <xref:System.Windows.Controls.MediaElement> aktiv ist (Dauer der Medienwiedergabe).</span><span class="sxs-lookup"><span data-stu-id="6eb56-109">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="6eb56-110">Weitere Informationen zum Verwenden von <xref:System.Windows.Media.Animation.Timeline> Objekten mit einem <xref:System.Windows.Media.Animation.Storyboard> finden Sie unter [Übersicht über Storyboards](storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6eb56-110">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="6eb56-111">In diesem Beispiel wird gezeigt, wie ein einfacher Media Player erstellt wird, der einen <xref:System.Windows.Media.MediaTimeline> zum Steuern der Wiedergabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="6eb56-111">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="6eb56-112">Der Media Player umfasst die Schaltflächen wiedergeben, anhalten, fortsetzen und anhalten.</span><span class="sxs-lookup"><span data-stu-id="6eb56-112">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="6eb56-113">Der Player verfügt auch über ein <xref:System.Windows.Controls.Slider> Steuerelement, das als Statusanzeige fungiert.</span><span class="sxs-lookup"><span data-stu-id="6eb56-113">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="6eb56-114">Im folgenden Beispiel wird der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für den Media Player erstellt.</span><span class="sxs-lookup"><span data-stu-id="6eb56-114">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="6eb56-115">Im folgenden Beispiel werden die Funktionen für die Statusanzeige erstellt.</span><span class="sxs-lookup"><span data-stu-id="6eb56-115">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6eb56-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eb56-116">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="6eb56-117">Steuern eines MediaElement-Objekts (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)</span><span class="sxs-lookup"><span data-stu-id="6eb56-117">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="6eb56-118">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="6eb56-118">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="6eb56-119">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="6eb56-119">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="6eb56-120">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="6eb56-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6eb56-121">Artikel zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="6eb56-121">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="6eb56-122">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="6eb56-122">Graphics and Multimedia</span></span>](index.md)
