---
title: 'Vorgehensweise: Wiedergeben von Medien mit Animationen'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921666"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="3bf52-102">Vorgehensweise: Wiedergeben von Medien mit Animationen</span><span class="sxs-lookup"><span data-stu-id="3bf52-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="3bf52-103">Dieses Beispiel zeigt, wie Sie die Wiedergabe von Medien und Animationen zur gleichen Zeit mit der <xref:System.Windows.Media.MediaTimeline> und <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Klassen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="3bf52-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bf52-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3bf52-104">Example</span></span>  
 <span data-ttu-id="3bf52-105">Sie können eine oder mehrere <xref:System.Windows.Media.MediaTimeline> Objekte in einer <xref:System.Windows.Media.Animation.Storyboard> zusammen mit anderen <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen.</span><span class="sxs-lookup"><span data-stu-id="3bf52-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="3bf52-106">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> Eigenschaft der <xref:System.Windows.Media.Animation.Storyboard> auf einen Wert von `Slip`, der angibt, dass die Animation keine erst im Laufe Medien (video, in diesem Beispiel) wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3bf52-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="3bf52-107">Diese Funktionalität ist hilfreich, wenn die Wiedergabe von Medien auf Grund ihrer Ladezeit verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="3bf52-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3bf52-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bf52-108">See also</span></span>

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="3bf52-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="3bf52-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="3bf52-110">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="3bf52-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="3bf52-111">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="3bf52-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="3bf52-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="3bf52-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3bf52-113">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="3bf52-113">Graphics and Multimedia</span></span>](index.md)
