---
title: 'Gewusst wie: Steuern eines MediaElement mit einem Storyboard'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2341d2814e5bd42c652865c76d115defcc5b15b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="78395-102">Gewusst wie: Steuern eines MediaElement mit einem Storyboard</span><span class="sxs-lookup"><span data-stu-id="78395-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="78395-103">In diesem Beispiel wird gezeigt, wie zur Steuerung einer <xref:System.Windows.Controls.MediaElement> mithilfe einer <xref:System.Windows.Media.MediaTimeline> in eine <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="78395-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78395-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78395-104">Example</span></span>  
 <span data-ttu-id="78395-105">Bei Verwendung einer <xref:System.Windows.Media.MediaTimeline> in einer <xref:System.Windows.Media.Animation.Storyboard> zeitlich steuern eine <xref:System.Windows.Controls.MediaElement>, die Funktionalität ist identisch mit der Funktionalität anderer <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen.</span><span class="sxs-lookup"><span data-stu-id="78395-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="78395-106">Z. B. eine <xref:System.Windows.Media.MediaTimeline> verwendet <xref:System.Windows.Media.Animation.Timeline> Eigenschaften, z. B. die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft angeben, wann Starten einer <xref:System.Windows.Controls.MediaElement> (Medienwiedergabe starten).</span><span class="sxs-lookup"><span data-stu-id="78395-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="78395-107">Darüber hinaus verwendet der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft an, wie lange der <xref:System.Windows.Controls.MediaElement> aktiv ist (Dauer Medienwiedergabe).</span><span class="sxs-lookup"><span data-stu-id="78395-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="78395-108">Weitere Informationen zur Verwendung von <xref:System.Windows.Media.Animation.Timeline> Objekte mit einem <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78395-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="78395-109">In diesem Beispiel wird gezeigt, wie Sie einen einfachen MediaPlayer erstellen, verwendet eine <xref:System.Windows.Media.MediaTimeline> zum Steuern der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="78395-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="78395-110">Der Media-Player enthält wiedergeben, anhalten, fortsetzen und beenden Sie die Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="78395-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="78395-111">Der Player verfügt auch über eine <xref:System.Windows.Controls.Slider> Steuerelement, das als eine Statusanzeige fungiert.</span><span class="sxs-lookup"><span data-stu-id="78395-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="78395-112">Das folgende Beispiel erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für Media-Player.</span><span class="sxs-lookup"><span data-stu-id="78395-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="78395-113">Im folgende Beispiel wird die Funktionalität für die Statusanzeige erstellt.</span><span class="sxs-lookup"><span data-stu-id="78395-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="78395-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78395-114">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="78395-115">Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)</span><span class="sxs-lookup"><span data-stu-id="78395-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [<span data-ttu-id="78395-116">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="78395-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="78395-117">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="78395-117">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="78395-118">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="78395-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="78395-119">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="78395-119">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="78395-120">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="78395-120">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
