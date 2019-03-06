---
title: 'Vorgehensweise: Wiedergeben von Medien mit Animationen'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 0dc39d08ef17a628675018c17602623f2efd0173
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372905"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="35d73-102">Vorgehensweise: Wiedergeben von Medien mit Animationen</span><span class="sxs-lookup"><span data-stu-id="35d73-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="35d73-103">Dieses Beispiel zeigt, wie Sie die Wiedergabe von Medien und Animationen zur gleichen Zeit mit der <xref:System.Windows.Media.MediaTimeline> und <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Klassen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="35d73-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35d73-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35d73-104">Example</span></span>  
 <span data-ttu-id="35d73-105">Sie können eine oder mehrere <xref:System.Windows.Media.MediaTimeline> Objekte in einer <xref:System.Windows.Media.Animation.Storyboard> zusammen mit anderen <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen.</span><span class="sxs-lookup"><span data-stu-id="35d73-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="35d73-106">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> Eigenschaft der <xref:System.Windows.Media.Animation.Storyboard> auf einen Wert von `Slip`, der angibt, dass die Animation keine erst im Laufe Medien (video, in diesem Beispiel) wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="35d73-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="35d73-107">Diese Funktionalität ist hilfreich, wenn die Wiedergabe von Medien auf Grund ihrer Ladezeit verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="35d73-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="35d73-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35d73-108">See also</span></span>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="35d73-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="35d73-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="35d73-110">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="35d73-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="35d73-111">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="35d73-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="35d73-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="35d73-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="35d73-113">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="35d73-113">Graphics and Multimedia</span></span>](index.md)
