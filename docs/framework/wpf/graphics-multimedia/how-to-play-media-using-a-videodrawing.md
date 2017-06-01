---
title: "Gewusst wie: Wiedergeben von Medien mit einer VideoDrawing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Klassen, MediaPlayer"
  - "Klassen, VideoDrawing"
  - "MediaPlayer-Klasse"
  - "Medienwiedergabe"
  - "VideoDrawing-Klasse"
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Wiedergeben von Medien mit einer VideoDrawing
Um eine Audio\- oder Videodatei wiederzugeben, verwenden Sie eine <xref:System.Windows.Media.VideoDrawing> und einen <xref:System.Windows.Media.MediaPlayer>.  Es gibt zwei Möglichkeiten, Medien zu laden und wiederzugeben.  Sie können entweder einen <xref:System.Windows.Media.MediaPlayer> und eine <xref:System.Windows.Media.VideoDrawing> alleine verwenden, oder Sie erstellen eine eigene <xref:System.Windows.Media.MediaTimeline> und setzen diese zusammen mit dem <xref:System.Windows.Media.MediaPlayer> und der <xref:System.Windows.Media.VideoDrawing> ein.  
  
> [!NOTE]
>  Wenn Sie Medien mit der Anwendung verteilen, können Sie eine Mediendatei, im Gegensatz zu einem Bild, nicht als Projektressource verwenden.  Sie müssen stattdessen in der Projektdatei den Medientyp auf `Content` und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always` festlegen.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Videodatei mit einer <xref:System.Windows.Media.VideoDrawing> und einem <xref:System.Windows.Media.MediaPlayer> einmal wiedergegeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Um eine zusätzliche Zeitsteuerungskontrolle über die Medien zu erhalten, verwenden Sie eine <xref:System.Windows.Media.MediaTimeline> mit dem <xref:System.Windows.Media.MediaPlayer>\-Objekt und dem <xref:System.Windows.Media.VideoDrawing>\-Objekt.  Mit der <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video erneut wiedergegeben werden soll.  
  
## Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.MediaTimeline> mit dem <xref:System.Windows.Media.MediaPlayer>\- und <xref:System.Windows.Media.VideoDrawing>\-Objekt zur wiederholten Wiedergabe eines Videos verwendet.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass Sie bei der Verwendung einer <xref:System.Windows.Media.MediaTimeline> statt der interaktiven Methoden von <xref:System.Windows.Media.MediaPlayer> den interaktiven <xref:System.Windows.Media.Animation.ClockController> verwenden, der von der <xref:System.Windows.Media.Animation.Clock.Controller%2A>\-Eigenschaft der <xref:System.Windows.Media.MediaClock> zurückgegeben wird, um die Medienwiedergabe zu steuern.  
  
## Siehe auch  
 <xref:System.Windows.Media.VideoDrawing>   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)