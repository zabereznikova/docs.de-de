---
title: Übersicht über Multimedia
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 42d0d388e859b556d23b7fc81931cd61470ba541
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039800"
---
# <a name="multimedia-overview"></a>Übersicht über Multimedia
Die Multimediafunktionen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ermöglichen Ihnen die Integration von Audio- und Videoinhalten in Ihre Anwendungen, um die Benutzerfreundlichkeit zu verbessern. In diesem Thema werden die Multimediafunktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt.  

<a name="mediaapi"></a>   
## <a name="media-api"></a>Medien-API  
 Die Klassen <xref:System.Windows.Controls.MediaElement> und <xref:System.Windows.Media.MediaPlayer> werden verwendet, um Audioinhalte oder Videoinhalte darzustellen. Diese Klassen können interaktiv oder durch eine Uhr gesteuert werden. Diese Klassen können für die Medienwiedergabe im Microsoft Windows Media Player 10-Steuerelement verwenden. Welche Klasse Sie verwenden, hängt vom Szenario ab.  
  
 <xref:System.Windows.Controls.MediaElement> ist eine <xref:System.Windows.UIElement>, die vom [Layout](../advanced/layout.md) unterstützt wird und als Inhalt vieler Steuerelemente verwendet werden kann. Es kann auch in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sowie in Code verwendet werden. <xref:System.Windows.Media.MediaPlayer>hingegen ist für <xref:System.Windows.Media.Drawing> Objekte konzipiert und unterstützt keine Layoutunterstützung. Medien, die mit einem <xref:System.Windows.Media.MediaPlayer> geladen werden, können nur mit einem <xref:System.Windows.Media.VideoDrawing> oder direkt mit einem <xref:System.Windows.Media.DrawingContext>dargestellt werden. <xref:System.Windows.Media.MediaPlayer> kann nicht in XAML verwendet werden.  
  
 Weitere Informationen zu Zeichnungsobjekten und zum Zeichnungskontext finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
> [!NOTE]
> Wenn Sie Medien mit der Anwendung verteilen, ist es nicht möglich, eine Mediendatei als Projektressource zu verwenden. Sie müssen stattdessen in der Projektdatei den Medientyp auf `Content` und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always` festlegen.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Wiedergabemodi für Medien  
  
> [!NOTE]
> Sowohl <xref:System.Windows.Controls.MediaElement> als auch <xref:System.Windows.Media.MediaPlayer> haben ähnliche Member. Die Links in diesem Abschnitt beziehen sich auf die Member der <xref:System.Windows.Controls.MediaElement>-Klasse. Sofern nicht ausdrücklich angegeben, können Member, die mit in der <xref:System.Windows.Controls.MediaElement>-Klasse verknüpft sind, auch in der <xref:System.Windows.Media.MediaPlayer>-Klasse gefunden werden.  
  
 Um die Medienwiedergabe in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu verstehen, sollten Sie mit den verschiedenen Modi vertraut sein, in denen Medien wiedergegeben werden können. Sowohl <xref:System.Windows.Controls.MediaElement> als auch <xref:System.Windows.Media.MediaPlayer> können in zwei verschiedenen Medien Modi verwendet werden: im unabhängigen Modus und im Uhrmodus. Der Medien Modus wird durch die <xref:System.Windows.Controls.MediaElement.Clock%2A>-Eigenschaft bestimmt. Wenn <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`ist, befindet sich das Medienobjekt im unabhängigen Modus. Wenn die <xref:System.Windows.Controls.MediaElement.Clock%2A> nicht NULL ist, befindet sich das Medienobjekt im Uhrmodus. Standardmäßig befinden sich Medienobjekte im unabhängigen Modus.  
  
### <a name="independent-mode"></a>Unabhängiger Modus  
 Im unabhängigen Modus steuert der Medieninhalt die Medienwiedergabe. Im unabhängigen Modus sind die folgenden Optionen aktiviert:  
  
- Die <xref:System.Uri> des Mediums können direkt angegeben werden.  
  
- Die Medienwiedergabe kann direkt gesteuert werden.  
  
- Die Eigenschaften "<xref:System.Windows.Controls.MediaElement.Position%2A>" und "<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>" des Mediums können geändert werden.  
  
 Die Medien werden entweder durch Festlegen der <xref:System.Windows.Controls.MediaElement.Source%2A>-Eigenschaft des <xref:System.Windows.Controls.MediaElement> Objekts oder durch Aufrufen der <xref:System.Windows.Media.MediaPlayer.Open%2A>-Methode des <xref:System.Windows.Media.MediaPlayer>-Objekts geladen.  
  
 Die Steuerelementmethoden des Medienobjekts können verwendet werden, um die Medienwiedergabe im unabhängigen Modus zu steuern. Die verfügbaren Steuerungsmethoden sind <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>und <xref:System.Windows.Controls.MediaElement.Stop%2A>. Für <xref:System.Windows.Controls.MediaElement>ist das interaktive Steuerelement, das diese Methoden verwendet, nur verfügbar, wenn die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> auf <xref:System.Windows.Controls.MediaState.Manual>festgelegt ist. Diese Methoden sind nicht verfügbar, sich wenn das Medienobjekt im Uhrmodus befindet.  
  
 Ein Beispiel für den unabhängigen Modus finden Sie unter [Steuern eines MediaElement (Wiedergeben, Anhalten, Beenden, Lautstärke und Geschwindigkeit)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Uhrmodus  
 Im Uhrmodus steuert ein <xref:System.Windows.Media.MediaTimeline> die Medienwiedergabe. Der Uhrmodus weist folgende Merkmale auf:  
  
- Die <xref:System.Uri> des Mediums wird indirekt über eine <xref:System.Windows.Media.MediaTimeline>festgelegt.  
  
- Die Medienwiedergabe kann von der Uhr gesteuert werden. Die Steuerelementmethoden des Medienobjekts können nicht verwendet werden.  
  
- Medien werden geladen, indem die <xref:System.Windows.Media.MediaTimeline.Source%2A>-Eigenschaft eines <xref:System.Windows.Media.MediaTimeline> Objekts festgelegt wird, die Uhr aus der Zeitachse erstellt und die Uhr dem Medienobjekt zugewiesen wird. Medien werden auch auf diese Weise geladen, wenn ein <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard> auf eine <xref:System.Windows.Controls.MediaElement>abzielt.  
  
 Um die Medienwiedergabe im Uhrmodus zu steuern, müssen die <xref:System.Windows.Media.Animation.ClockController> Steuerungsmethoden verwendet werden. Eine <xref:System.Windows.Media.Animation.ClockController> wird von der <xref:System.Windows.Media.Animation.ClockController>-Eigenschaft der <xref:System.Windows.Media.MediaClock>abgerufen. Wenn Sie versuchen, die Steuer Methoden einer <xref:System.Windows.Controls.MediaElement> oder <xref:System.Windows.Media.MediaPlayer> Objekt im Uhrmodus zu verwenden, wird ein <xref:System.InvalidOperationException> ausgelöst.  
  
 Weitere Informationen zu Uhren und Zeitachsen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Ein Beispiel für den Uhrmodus finden Sie unter [Steuern eines MediaElement mit einem Storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>MediaElement-Klasse  
 Das Hinzufügen von Medien zu einer Anwendung ist so einfach wie das Hinzufügen eines <xref:System.Windows.Controls.MediaElement>-Steuer Elements zum [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Anwendung und das Bereitstellen eines <xref:System.Uri> an die Medien, die Sie einschließen möchten. Alle von Microsoft Windows Media Player 10 unterstützten Medientypen werden in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]unterstützt. Das folgende Beispiel zeigt eine einfache Verwendung der <xref:System.Windows.Controls.MediaElement> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In diesem Beispiel werden Medien automatisch wiedergegeben, sobald sie geladen werden. Sobald die Medienwiedergabe abgeschlossen ist, werden die Medium geschlossen und alle Medienressourcen freigegeben (einschließlich Videospeicher). Dies ist das Standardverhalten des <xref:System.Windows.Controls.MediaElement> Objekts und wird durch die Eigenschaften <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> und <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> gesteuert.  
  
### <a name="controlling-a-mediaelement"></a>Steuern eines MediaElement  
 Die Eigenschaften <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> und <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> steuern das Verhalten der <xref:System.Windows.Controls.MediaElement>, wenn <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` bzw. `false`ist. Der <xref:System.Windows.Controls.MediaState> die Eigenschaften festgelegt werden, um das Verhalten der Medienwiedergabe zu beeinflussen. Beispielsweise ist die Standard <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Play>, und der Standard <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Close>. Dies bedeutet, dass die Medien wiedergegeben werden, sobald die <xref:System.Windows.Controls.MediaElement> geladen und die Vorabversion fertig ist. Nach Abschluss der Wiedergabe werden die Medien geschlossen und alle Medienressourcen freigegeben.  
  
 Die Eigenschaften "<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>" und "<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>" sind nicht die einzige Möglichkeit zum Steuern der Medienwiedergabe. Im Uhrmodus kann die Uhr die <xref:System.Windows.Controls.MediaElement> steuern, und die interaktiven Steuerelement Methoden steuern, wenn die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>wird. <xref:System.Windows.Controls.MediaElement> behandelt diesen Wettbewerb zur Steuerung, indem die folgenden Prioritäten ausgewertet werden.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Vorhanden, wenn Medien entladen werden. Dadurch wird sichergestellt, dass alle Medienressourcen standardmäßig freigegeben werden, auch wenn ein <xref:System.Windows.Media.MediaClock> dem <xref:System.Windows.Controls.MediaElement>zugeordnet ist.  
  
2. <xref:System.Windows.Media.MediaClock> Vorhanden, wenn Medien über eine <xref:System.Windows.Controls.MediaElement.Clock%2A>verfügen. Wenn Medien entladen werden, wird der <xref:System.Windows.Media.MediaClock> wirksam, solange der <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>wird. Der Uhrmodus überschreibt immer das geladene Verhalten der <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Vorhanden, wenn Medien entladen werden.  
  
4. Interaktive Steuerelementmethoden. Vorhanden, wenn <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>ist. Die verfügbaren Steuerungsmethoden sind <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>und <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Anzeigen eines MediaElement  
 Um einen <xref:System.Windows.Controls.MediaElement> anzuzeigen, muss er über Inhalte zum Rendering verfügen, und seine <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> Eigenschaften werden auf 0 festgelegt, bis der Inhalt geladen wird. Bei ausschließlichen Audioinhalten sind diese Eigenschaften immer null. Bei Videoinhalten melden <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> die Größe der geladenen Medien, sobald das <xref:System.Windows.Controls.MediaElement.MediaOpened>-Ereignis ausgelöst wurde. Dies bedeutet, dass der <xref:System.Windows.Controls.MediaElement> den physischen Speicherplatz im [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] nur dann annimmt, wenn die Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A> festgelegt sind.  
  
 Das Festlegen der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> bewirkt, dass die Medien gestreckt werden, um den für die <xref:System.Windows.Controls.MediaElement>bereitgestellten Bereich auszufüllen. Um das ursprüngliche Seitenverhältnis des Mediums beizubehalten, sollte entweder die <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft oder die <xref:System.Windows.FrameworkElement.Height%2A>-Eigenschaft festgelegt werden, aber nicht beides. Das Festlegen der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> bewirkt, dass das Medium in einer festgelegten Elementgröße vorhanden ist, die möglicherweise nicht wünschenswert ist.  
  
 Um ein Element mit fester Größe zu vermeiden, kann [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] einen Vorlauf für die Medien durchführen. Dies erfolgt durch Festlegen der <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> auf <xref:System.Windows.Controls.MediaState.Play> oder <xref:System.Windows.Controls.MediaState.Pause>. In einem <xref:System.Windows.Controls.MediaState.Pause> Status wird das Medium vorab erstellt, und der erste Frame wird angezeigt. In einem <xref:System.Windows.Controls.MediaState.Play> Status wird das Medium vorab gestartet und mit der Wiedergabe begonnen.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>MediaPlayer-Klasse  
 Da es sich bei der <xref:System.Windows.Controls.MediaElement> Klasse um ein FrameworkElement handelt, ist die <xref:System.Windows.Media.MediaPlayer> Klasse so konzipiert, dass Sie in <xref:System.Windows.Media.Drawing> Objekten verwendet wird. Zeichnungsobjekte werden verwendet, wenn Sie Features auf Frameworkebene Opfern können, um Leistungsvorteile zu erzielen, oder wenn Sie <xref:System.Windows.Freezable> Features benötigen. <xref:System.Windows.Media.MediaPlayer> ermöglicht es Ihnen, diese Features zu nutzen, während Sie Medieninhalte in Ihren Anwendungen bereitstellen. Wie <xref:System.Windows.Controls.MediaElement>können <xref:System.Windows.Media.MediaPlayer> im unabhängigen Modus oder im Uhrmodus verwendet werden, aber nicht die entladen und geladenen Zustände des <xref:System.Windows.Controls.MediaElement> Objekts. Dadurch wird die Komplexität der Wiedergabe Steuerelemente des <xref:System.Windows.Media.MediaPlayer>reduziert.  
  
### <a name="controlling-mediaplayer"></a>Steuern des MediaPlayer  
 Da <xref:System.Windows.Media.MediaPlayer> zustandslos ist, gibt es nur zwei Möglichkeiten, die Medienwiedergabe zu steuern.  
  
1. Interaktive Steuerelementmethoden. Direkt im unabhängigen Modus (`null`<xref:System.Windows.Media.MediaPlayer.Clock%2A>-Eigenschaft).  
  
2. <xref:System.Windows.Media.MediaClock> Vorhanden, wenn Medien über eine <xref:System.Windows.Media.MediaPlayer.Clock%2A>verfügen.  
  
### <a name="displaying-a-mediaplayer"></a>Anzeigen eines MediaElement  
 Technisch gesehen kann eine <xref:System.Windows.Media.MediaPlayer> nicht angezeigt werden, da Sie keine physische Darstellung hat. Sie kann jedoch verwendet werden, um Medien in einem <xref:System.Windows.Media.Drawing> mithilfe der <xref:System.Windows.Media.VideoDrawing>-Klasse darzustellen. Im folgenden Beispiel wird die Verwendung eines <xref:System.Windows.Media.VideoDrawing> zum Anzeigen von Medien veranschaulicht.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md) .  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [Themen zu Vorgehensweisen](audio-and-video-how-to-topics.md)
