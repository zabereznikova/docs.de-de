---
title: Übersicht über Multimedia
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 44059fe96a0deeda18f0abd9079100b55be98e77
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929621"
---
# <a name="multimedia-overview"></a>Übersicht über Multimedia
Die Multimediafunktionen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ermöglichen Ihnen die Integration von Audio- und Videoinhalten in Ihre Anwendungen, um die Benutzerfreundlichkeit zu verbessern. In diesem Thema werden die Multimediafunktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt.  

<a name="mediaapi"></a>   
## <a name="media-api"></a>Medien-API  
 Die <xref:System.Windows.Controls.MediaElement> Klassen <xref:System.Windows.Media.MediaPlayer> und werden verwendet, um Audioinhalte oder Videoinhalte darzustellen. Diese Klassen können interaktiv oder durch eine Uhr gesteuert werden. Die Klassen können für das [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10-Steuerelement zur Medienwiedergabe verwendet werden. Welche Klasse Sie verwenden, hängt vom Szenario ab.  
  
 <xref:System.Windows.Controls.MediaElement>ist eine <xref:System.Windows.UIElement> , die vom [Layout](../advanced/layout.md) unterstützt wird und als Inhalt von vielen Steuerelementen verwendet werden kann. Es kann auch in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sowie in Code verwendet werden. <xref:System.Windows.Media.MediaPlayer>auf der anderen Seite ist für <xref:System.Windows.Media.Drawing> -Objekte konzipiert und unterstützt keine Layoutunterstützung. Medien, die mit <xref:System.Windows.Media.MediaPlayer> einem geladen werden, können nur <xref:System.Windows.Media.VideoDrawing> mithilfe von oder über eine direkte <xref:System.Windows.Media.DrawingContext>Interaktion mit einem angezeigt werden. <xref:System.Windows.Media.MediaPlayer>kann nicht in XAML verwendet werden.  
  
 Weitere Informationen zu Zeichnungsobjekten und zum Zeichnungskontext finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
> [!NOTE]
> Wenn Sie Medien mit der Anwendung verteilen, ist es nicht möglich, eine Mediendatei als Projektressource zu verwenden. Sie müssen stattdessen in der Projektdatei den Medientyp auf `Content` und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always` festlegen.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Wiedergabemodi für Medien  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement> Und<xref:System.Windows.Media.MediaPlayer> weisen ähnliche Member auf. Die Links in diesem Abschnitt beziehen sich auf <xref:System.Windows.Controls.MediaElement> die Klassenmember. Sofern nicht ausdrücklich angegeben, können Member, die <xref:System.Windows.Controls.MediaElement> mit in der-Klasse verknüpft sind <xref:System.Windows.Media.MediaPlayer> , auch in der-Klasse gefunden werden.  
  
 Um die Medienwiedergabe in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu verstehen, sollten Sie mit den verschiedenen Modi vertraut sein, in denen Medien wiedergegeben werden können. <xref:System.Windows.Controls.MediaElement> Und<xref:System.Windows.Media.MediaPlayer> können in zwei verschiedenen Medien Modi verwendet werden: im unabhängigen Modus und im Uhrmodus. Der Medien Modus wird von der <xref:System.Windows.Controls.MediaElement.Clock%2A> -Eigenschaft bestimmt. Wenn <xref:System.Windows.Controls.MediaElement.Clock%2A>den Wert hat,befindetsichdasMedienobjektimunabhängigenModus.`null` Wenn nicht NULL ist, befindet sich das Medienobjekt im Uhrmodus. <xref:System.Windows.Controls.MediaElement.Clock%2A> Standardmäßig befinden sich Medienobjekte im unabhängigen Modus.  
  
### <a name="independent-mode"></a>Unabhängiger Modus  
 Im unabhängigen Modus steuert der Medieninhalt die Medienwiedergabe. Im unabhängigen Modus sind die folgenden Optionen aktiviert:  
  
- Die <xref:System.Uri> Medien können direkt angegeben werden.  
  
- Die Medienwiedergabe kann direkt gesteuert werden.  
  
- Die- <xref:System.Windows.Controls.MediaElement.Position%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> -Eigenschaften des Mediums können geändert werden.  
  
 Die Medien werden entweder durch Festlegen der <xref:System.Windows.Controls.MediaElement> - <xref:System.Windows.Controls.MediaElement.Source%2A> Eigenschaft des-Objekts oder durch <xref:System.Windows.Media.MediaPlayer> Aufrufen der <xref:System.Windows.Media.MediaPlayer.Open%2A> -Methode des-Objekts geladen.  
  
 Die Steuerelementmethoden des Medienobjekts können verwendet werden, um die Medienwiedergabe im unabhängigen Modus zu steuern. Die verfügbaren Steuerungsmethoden <xref:System.Windows.Controls.MediaElement.Play%2A>sind <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A>. Für <xref:System.Windows.Controls.MediaElement>ist das interaktive Steuerelement, das <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> diese Methoden verwendet, nur verfügbar, <xref:System.Windows.Controls.MediaState.Manual>wenn auf festgelegt ist. Diese Methoden sind nicht verfügbar, sich wenn das Medienobjekt im Uhrmodus befindet.  
  
 Ein Beispiel für den unabhängigen Modus finden Sie unter [Steuern eines MediaElement (Wiedergeben, Anhalten, Beenden, Lautstärke und Geschwindigkeit)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Uhrmodus  
 Im Uhrmodus steuert eine <xref:System.Windows.Media.MediaTimeline> Medienwiedergabe. Der Uhrmodus weist folgende Merkmale auf:  
  
- Medien werden indirekt durch ein <xref:System.Windows.Media.MediaTimeline>festgelegt. <xref:System.Uri>  
  
- Die Medienwiedergabe kann von der Uhr gesteuert werden. Die Steuerelementmethoden des Medienobjekts können nicht verwendet werden.  
  
- Medien werden geladen, indem die <xref:System.Windows.Media.MediaTimeline> -Eigenschaft <xref:System.Windows.Media.MediaTimeline.Source%2A> eines-Objekts festgelegt wird, die Uhr aus der Zeitachse erstellt und die Uhr dem Medienobjekt zugewiesen wird. Medien werden auch auf diese Weise geladen, <xref:System.Windows.Media.MediaTimeline> wenn ein <xref:System.Windows.Media.Animation.Storyboard> in einer <xref:System.Windows.Controls.MediaElement>auf einen abzielt.  
  
 Um die Medienwiedergabe im Uhrmodus zu steuern <xref:System.Windows.Media.Animation.ClockController> , müssen die Steuerelement Methoden verwendet werden. Eine <xref:System.Windows.Media.Animation.ClockController> wird aus der <xref:System.Windows.Media.Animation.ClockController> -Eigenschaft des <xref:System.Windows.Media.MediaClock>-Objekts abgerufen. Wenn Sie versuchen, die Steuer Methoden eines <xref:System.Windows.Controls.MediaElement> -Objekts oder <xref:System.Windows.Media.MediaPlayer> eines-Objekts im Uhrmodus zu verwenden <xref:System.InvalidOperationException> , wird eine ausgelöst.  
  
 Weitere Informationen zu Uhren und Zeitachsen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Ein Beispiel für den Uhrmodus finden Sie unter [Steuern eines MediaElement mit einem Storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>MediaElement-Klasse  
 Das Hinzufügen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] von Medien zu einer Anwendung ist so einfach <xref:System.Windows.Controls.MediaElement> wie das Hinzufügen eines Steuer Elements zum der <xref:System.Uri> Anwendung und das Bereitstellen eines-Steuer Elements für die Medien, die Sie einschließen möchten. Alle von [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 unterstützten Medientypen werden in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] unterstützt. Das folgende Beispiel zeigt eine einfache Verwendung von <xref:System.Windows.Controls.MediaElement> in. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In diesem Beispiel werden Medien automatisch wiedergegeben, sobald sie geladen werden. Sobald die Medienwiedergabe abgeschlossen ist, werden die Medium geschlossen und alle Medienressourcen freigegeben (einschließlich Videospeicher). Dies ist das Standardverhalten des <xref:System.Windows.Controls.MediaElement> -Objekts, das durch die-Eigenschaft und die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> - <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Eigenschaft gesteuert wird.  
  
### <a name="controlling-a-mediaelement"></a>Steuern eines MediaElement  
 Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> - <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Eigenschaft und die-Eigenschaft <xref:System.Windows.Controls.MediaElement> steuern das <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` Verhalten`false`von, wenn bzw. ist. Die <xref:System.Windows.Controls.MediaState> Eigenschaften werden festgelegt, um das Verhalten der Medienwiedergabe zu beeinflussen. Beispielsweise ist <xref:System.Windows.Controls.MediaState.Play> der Standard <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Wert, und der <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Standard <xref:System.Windows.Controls.MediaState.Close>Wert ist. Dies bedeutet, dass die Medien wieder <xref:System.Windows.Controls.MediaElement> gegeben werden, sobald das geladen ist und die Vorabversion fertig ist. Nach Abschluss der Wiedergabe werden die Medien geschlossen und alle Medienressourcen freigegeben.  
  
 Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> - <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Eigenschaft und die-Eigenschaft sind nicht die einzige Möglichkeit zum Steuern der Medienwiedergabe. Im Uhrmodus kann die Uhr die Steuern <xref:System.Windows.Controls.MediaElement> und die interaktiven Steuerelement Methoden steuern, wenn <xref:System.Windows.Controls.MediaState.Manual>den <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Wert hat. <xref:System.Windows.Controls.MediaElement>behandelt diese Wettbewerbskontrolle, indem die folgenden Prioritäten ausgewertet werden.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Vorhanden, wenn Medien entladen werden. Dadurch wird sichergestellt, dass alle Medienressourcen standardmäßig freigegeben werden <xref:System.Windows.Media.MediaClock> , auch wenn ein <xref:System.Windows.Controls.MediaElement>zugeordnet ist.  
  
2. <xref:System.Windows.Media.MediaClock> Vorhanden, wenn Medien über einen <xref:System.Windows.Controls.MediaElement.Clock%2A>verfügen. Wenn Medien entladen werden, wird <xref:System.Windows.Media.MediaClock> der wirksam, solange der <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Manual>. Der Uhrmodus überschreibt immer das geladene Verhalten von <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Vorhanden, wenn Medien entladen werden.  
  
4. Interaktive Steuerelementmethoden. Vorhanden, wenn <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Manual>. Die verfügbaren Steuerungsmethoden <xref:System.Windows.Controls.MediaElement.Play%2A>sind <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Anzeigen eines MediaElement  
 Zum Anzeigen eines <xref:System.Windows.Controls.MediaElement> muss Inhalt vorhanden sein, der gerengt werden kann <xref:System.Windows.FrameworkElement.ActualWidth%2A> , <xref:System.Windows.FrameworkElement.ActualHeight%2A> und die-Eigenschaft und die-Eigenschaft werden auf 0 festgelegt, bis der Inhalt geladen Bei ausschließlichen Audioinhalten sind diese Eigenschaften immer null. Wenn das <xref:System.Windows.Controls.MediaElement.MediaOpened> <xref:System.Windows.FrameworkElement.ActualWidth%2A> - Ereignisausgelöstwurde,wirdfürVideoinhaltedieGrößedergeladenenMediengemeldet.<xref:System.Windows.FrameworkElement.ActualHeight%2A> Dies bedeutet, dass, bis Medien geladen werden <xref:System.Windows.Controls.MediaElement> , der keinen physischen Speicherplatz [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] in Anspruch nimmt, es <xref:System.Windows.FrameworkElement.Width%2A> sei <xref:System.Windows.FrameworkElement.Height%2A> denn, die-Eigenschaft oder die-Eigenschaft ist festgelegt.  
  
 Das Festlegen der <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.MediaElement>-Eigenschaft und der-Eigenschaft bewirkt, dass die Medien gestreckt werden, um den für das angegebene Bereich auszufüllen. <xref:System.Windows.FrameworkElement.Width%2A> Um das ursprüngliche Seitenverhältnis des Mediums beizubehalten, muss entweder <xref:System.Windows.FrameworkElement.Width%2A> die <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaft oder die-Eigenschaft festgelegt werden, aber nicht beides. Das Festlegen der <xref:System.Windows.FrameworkElement.Width%2A> - <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft und der-Eigenschaft bewirkt, dass das Medium in einer festgelegten Elementgröße vorhanden ist, die möglicherweise nicht erwünscht ist.  
  
 Um ein Element mit fester Größe zu vermeiden, kann [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] einen Vorlauf für die Medien durchführen. Dies erfolgt durch Festlegen <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> von <xref:System.Windows.Controls.MediaState.Play> auf oder <xref:System.Windows.Controls.MediaState.Pause>. In einem <xref:System.Windows.Controls.MediaState.Pause> Zustand wird das Medium vorab erstellt, und der erste Frame wird angezeigt. In einem <xref:System.Windows.Controls.MediaState.Play> Zustand wird das Medium vorab erstellt und beginnt mit der Wiedergabe.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>MediaPlayer-Klasse  
 Da <xref:System.Windows.Controls.MediaElement> die-Klasse ein Framework-Element ist, <xref:System.Windows.Media.MediaPlayer> ist die-Klasse für die Verwendung <xref:System.Windows.Media.Drawing> in-Objekten konzipiert. Zeichnungsobjekte werden verwendet, wenn Sie Features auf Frameworkebene Opfern können, um Leistungsvorteile <xref:System.Windows.Freezable> zu erzielen, oder wenn Sie Funktionen benötigen. <xref:System.Windows.Media.MediaPlayer>ermöglicht es Ihnen, diese Features zu nutzen, während Sie Medieninhalte in Ihren Anwendungen bereitstellen. Ebenso <xref:System.Windows.Controls.MediaElement>wie <xref:System.Windows.Media.MediaPlayer> kann im unabhängigen Modus oder im Uhrmodus verwendet werden, verfügt jedoch <xref:System.Windows.Controls.MediaElement> nicht über die nicht geladenen und geladenen Zustände des Objekts. Dadurch wird die Komplexität <xref:System.Windows.Media.MediaPlayer>der Wiedergabe Steuerelemente verringert.  
  
### <a name="controlling-mediaplayer"></a>Steuern des MediaPlayer  
 Da <xref:System.Windows.Media.MediaPlayer> zustandslos ist, gibt es nur zwei Möglichkeiten, die Medienwiedergabe zu steuern.  
  
1. Interaktive Steuerelementmethoden. Direkt im unabhängigen Modus (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> Eigenschaft).  
  
2. <xref:System.Windows.Media.MediaClock> Vorhanden, wenn Medien über einen <xref:System.Windows.Media.MediaPlayer.Clock%2A>verfügen.  
  
### <a name="displaying-a-mediaplayer"></a>Anzeigen eines MediaElement  
 Technisch gesehen kann <xref:System.Windows.Media.MediaPlayer> eine nicht angezeigt werden, da Sie keine physische Darstellung hat. Sie kann jedoch verwendet werden, um Medien in einem <xref:System.Windows.Media.Drawing> mithilfe der <xref:System.Windows.Media.VideoDrawing> -Klasse darzustellen. Im folgenden Beispiel wird die Verwendung eines <xref:System.Windows.Media.VideoDrawing> zum Anzeigen von Medien veranschaulicht.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Weitere Informationen zu Objekten finden Sie unter Übersicht über <xref:System.Windows.Media.Drawing> [Zeichnungsobjekte](drawing-objects-overview.md) .  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [Themen zu Vorgehensweisen](audio-and-video-how-to-topics.md)
