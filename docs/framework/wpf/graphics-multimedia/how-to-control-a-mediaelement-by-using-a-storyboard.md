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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100313"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="819eb-102">Vorgehensweise: Steuern eines MediaElement-Objekts mit einem Storyboard</span><span class="sxs-lookup"><span data-stu-id="819eb-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="819eb-103">Dieses Beispiel zeigt, wie Sie steuern eine <xref:System.Windows.Controls.MediaElement> mithilfe einer <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="819eb-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="819eb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="819eb-104">Example</span></span>  
 <span data-ttu-id="819eb-105">Bei Verwendung einer <xref:System.Windows.Media.MediaTimeline> in einer <xref:System.Windows.Media.Animation.Storyboard> zeitlich steuern eine <xref:System.Windows.Controls.MediaElement>, die Funktionalität ist identisch mit der Funktionalität von anderen <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen.</span><span class="sxs-lookup"><span data-stu-id="819eb-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="819eb-106">Z. B. eine <xref:System.Windows.Media.MediaTimeline> verwendet <xref:System.Windows.Media.Animation.Timeline> Eigenschaften wie die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft, um anzugeben, wann zu einem <xref:System.Windows.Controls.MediaElement> (Starten der Wiedergabe von Medien).</span><span class="sxs-lookup"><span data-stu-id="819eb-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="819eb-107">Darüber hinaus verwendet er die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> -Eigenschaft an wie lange der <xref:System.Windows.Controls.MediaElement> aktiv ist (Dauer der Wiedergabe von Medien).</span><span class="sxs-lookup"><span data-stu-id="819eb-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="819eb-108">Weitere Informationen zur Verwendung von <xref:System.Windows.Media.Animation.Timeline> Objekte mit einem <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter [Übersicht über Storyboards](storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="819eb-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="819eb-109">In diesem Beispiel wird gezeigt, wie Sie einen einfachen MediaPlayer erstellen, verwendet eine <xref:System.Windows.Media.MediaTimeline> zum Steuern der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="819eb-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="819eb-110">Der MediaPlayer enthält Wiedergabe, anhalten, fortsetzen und beenden Sie die Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="819eb-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="819eb-111">Der Player verfügt auch über eine <xref:System.Windows.Controls.Slider> -Steuerelement, das als eine Statusanzeige fungiert.</span><span class="sxs-lookup"><span data-stu-id="819eb-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="819eb-112">Das folgende Beispiel erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für MediaPlayer.</span><span class="sxs-lookup"><span data-stu-id="819eb-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="819eb-113">Das folgende Beispiel erstellt die Funktionalität für die Statusanzeige.</span><span class="sxs-lookup"><span data-stu-id="819eb-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="819eb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="819eb-114">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="819eb-115">Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)</span><span class="sxs-lookup"><span data-stu-id="819eb-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="819eb-116">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="819eb-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="819eb-117">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="819eb-117">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="819eb-118">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="819eb-118">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="819eb-119">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="819eb-119">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="819eb-120">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="819eb-120">Graphics and Multimedia</span></span>](index.md)
