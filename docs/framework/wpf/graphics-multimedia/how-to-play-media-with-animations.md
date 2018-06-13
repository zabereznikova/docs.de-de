---
title: 'Gewusst wie: Wiedergeben von Medien mit Animationen'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 21c9b35828dca03c05def11cff22f1f1e33d45cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560266"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="10981-102">Gewusst wie: Wiedergeben von Medien mit Animationen</span><span class="sxs-lookup"><span data-stu-id="10981-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="10981-103">In diesem Beispiel wird gezeigt, wie für die Wiedergabe von Medien und Animationen gleichzeitig mithilfe der <xref:System.Windows.Media.MediaTimeline> und <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Klassen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="10981-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10981-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10981-104">Example</span></span>  
 <span data-ttu-id="10981-105">Sie können eine oder mehrere <xref:System.Windows.Media.MediaTimeline> Objekte in einer <xref:System.Windows.Media.Animation.Storyboard> zusammen mit anderen <xref:System.Windows.Media.Animation.Timeline> Objekte, z. B. Animationen.</span><span class="sxs-lookup"><span data-stu-id="10981-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="10981-106">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> Eigenschaft von der <xref:System.Windows.Media.Animation.Storyboard> auf einen Wert von `Slip`, was bedeutet, dass die Animation wird erst im Verlauf Mediums (video in diesem Beispiel) nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10981-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="10981-107">Diese Funktionalität ist hilfreich, wenn die Wiedergabe von Medien auf Grund ihrer Ladezeit verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="10981-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="10981-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10981-108">See Also</span></span>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [<span data-ttu-id="10981-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="10981-109">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="10981-110">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="10981-110">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="10981-111">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="10981-111">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="10981-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="10981-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="10981-113">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="10981-113">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
