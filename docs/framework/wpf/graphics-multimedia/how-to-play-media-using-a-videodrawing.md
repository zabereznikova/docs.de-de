---
title: 'Gewusst wie: Wiedergeben von Medien mit einer VideoDrawing'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2753db8e06c8c1b50c6e5cee17330d421e88511f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="f222e-102">Gewusst wie: Wiedergeben von Medien mit einer VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="f222e-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="f222e-103">Um eine Audio- oder eine Datei wiederzugeben, verwenden Sie eine <xref:System.Windows.Media.VideoDrawing> und ein <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="f222e-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="f222e-104">Es gibt zwei Methoden zum Laden und Wiedergeben von Medien.</span><span class="sxs-lookup"><span data-stu-id="f222e-104">There are two ways to load and play media.</span></span> <span data-ttu-id="f222e-105">Der erste Schritt besteht im Verwenden einer <xref:System.Windows.Media.MediaPlayer> und ein <xref:System.Windows.Media.VideoDrawing> von selbst, während die zweite besteht darin, Ihre eigenen erstellen <xref:System.Windows.Media.MediaTimeline> für die Verwendung mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="f222e-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f222e-106">Wenn Sie Medien mit Ihrer Anwendung verteilen, können Sie keine Mediendatei als Ressource verwenden, wie Sie das mit einem Bild machen würden.</span><span class="sxs-lookup"><span data-stu-id="f222e-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="f222e-107">In der Projektdatei müssen Sie stattdessen den Medientyp auf `Content` festlegen, und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always`.</span><span class="sxs-lookup"><span data-stu-id="f222e-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f222e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f222e-108">Example</span></span>  
 <span data-ttu-id="f222e-109">Im folgenden Beispiel wird eine <xref:System.Windows.Media.VideoDrawing> und ein <xref:System.Windows.Media.MediaPlayer> einmal eine Videodatei wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="f222e-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="f222e-110">Um zusätzliche Timing Kontrolle über die Medien zu erhalten, verwenden Sie eine <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing> Objekte.</span><span class="sxs-lookup"><span data-stu-id="f222e-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="f222e-111">Die <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video wiederholt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f222e-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f222e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f222e-112">Example</span></span>  
 <span data-ttu-id="f222e-113">Im folgenden Beispiel wird eine <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing> -Objekten, die wiederholt ein Video abspielen.</span><span class="sxs-lookup"><span data-stu-id="f222e-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="f222e-114">Beachten Sie, dass bei der Verwendung ein <xref:System.Windows.Media.MediaTimeline>, verwenden Sie die interaktive <xref:System.Windows.Media.Animation.ClockController> Merry der <xref:System.Windows.Media.Animation.Clock.Controller%2A> Eigenschaft der <xref:System.Windows.Media.MediaClock> Medien Wiedergabe anstelle der interaktiven Methoden der <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="f222e-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f222e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f222e-115">See Also</span></span>  
 <xref:System.Windows.Media.VideoDrawing>  
 [<span data-ttu-id="f222e-116">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="f222e-116">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
