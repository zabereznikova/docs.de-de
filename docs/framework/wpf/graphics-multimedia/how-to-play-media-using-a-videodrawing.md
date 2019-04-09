---
title: 'Vorgehensweise: Wiedergeben von Medien mit einer VideoDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 186c9ae8167dafd09f029418c1d23f81f7a9e906
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203612"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>Vorgehensweise: Wiedergeben von Medien mit einer VideoDrawing
Um eine Audio- oder Videodatei wiederzugeben, die Sie verwenden eine <xref:System.Windows.Media.VideoDrawing> und <xref:System.Windows.Media.MediaPlayer>. Es gibt zwei Methoden zum Laden und Wiedergeben von Medien. Die erste ist die Verwendung einer <xref:System.Windows.Media.MediaPlayer> und ein <xref:System.Windows.Media.VideoDrawing> von selbst, und die zweite besteht darin, Ihre eigenen erstellen <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Wenn Sie Medien mit Ihrer Anwendung verteilen, können Sie keine Mediendatei als Ressource verwenden, wie Sie das mit einem Bild machen würden. In der Projektdatei müssen Sie stattdessen den Medientyp auf `Content` festlegen, und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.VideoDrawing> und <xref:System.Windows.Media.MediaPlayer> , eine Videodatei wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Um zeitlich steuern die Medien zu erhalten, verwenden Sie eine <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing> Objekte. Die <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video wiederholt werden soll.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing> Objekte, die ein Video wiederholt abzuspielen.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass bei der Verwendung einer <xref:System.Windows.Media.MediaTimeline>, verwenden Sie die interaktive <xref:System.Windows.Media.Animation.ClockController> Merry der <xref:System.Windows.Media.Animation.Clock.Controller%2A> Eigenschaft der <xref:System.Windows.Media.MediaClock> zum Steuern der Medienwiedergabe anstelle der interaktiven Methoden der <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.VideoDrawing>
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
