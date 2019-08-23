---
title: 'Vorgehensweise: Wiedergeben von Medien mit einer VideoDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956956"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>Vorgehensweise: Wiedergeben von Medien mit einer VideoDrawing
Um eine Audiodatei oder Videodatei wiederzugeben, verwenden <xref:System.Windows.Media.VideoDrawing> Sie eine <xref:System.Windows.Media.MediaPlayer>und eine. Es gibt zwei Methoden zum Laden und Wiedergeben von Medien. Der erste besteht darin, ein <xref:System.Windows.Media.MediaPlayer> und ein <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> eigenständig zu verwenden, und die zweite Möglichkeit besteht darin, <xref:System.Windows.Media.MediaTimeline> einen eigenen zu erstellen, <xref:System.Windows.Media.VideoDrawing>der mit und verwendet werden kann.  
  
> [!NOTE]
> Wenn Sie Medien mit Ihrer Anwendung verteilen, können Sie keine Mediendatei als Ressource verwenden, wie Sie das mit einem Bild machen würden. In der Projektdatei müssen Sie stattdessen den Medientyp auf `Content` festlegen, und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.VideoDrawing> und ein <xref:System.Windows.Media.MediaPlayer> verwendet, um eine Videodatei einmal wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Verwenden Sie ein <xref:System.Windows.Media.MediaTimeline> -Objekt mit dem-Objekt und dem <xref:System.Windows.Media.MediaPlayer> - <xref:System.Windows.Media.VideoDrawing> Objekt, um zusätzliche zeitliche Steuerung des Mediums zu erhalten. Mit <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video wiederholt werden soll.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.MediaTimeline> -Objekt <xref:System.Windows.Media.MediaPlayer> mit <xref:System.Windows.Media.VideoDrawing> dem-Objekt und dem-Objekt verwendet, um ein Video wiederholt  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass Sie, wenn <xref:System.Windows.Media.MediaTimeline>Sie einen verwenden, die <xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.MediaClock> von der <xref:System.Windows.Media.Animation.Clock.Controller%2A> -Eigenschaft von zurückgegebene interaktive verwenden, um die Medienwiedergabe anstelle der <xref:System.Windows.Media.MediaPlayer>interaktiven Methoden von zu steuern.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.VideoDrawing>
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
