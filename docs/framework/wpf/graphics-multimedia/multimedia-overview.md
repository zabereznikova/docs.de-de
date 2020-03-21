---
title: Übersicht über Multimedia
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: d4abf4d9fd324ffbf2737dc686c02e50ca1a8a5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181888"
---
# <a name="multimedia-overview"></a>Übersicht über Multimedia
Die Multimediafunktionen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ermöglichen Ihnen die Integration von Audio- und Videoinhalten in Ihre Anwendungen, um die Benutzerfreundlichkeit zu verbessern. In diesem Thema werden die Multimediafunktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt.  

<a name="mediaapi"></a>
## <a name="media-api"></a>Medien-API  
 Die <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> und-Klassen werden verwendet, um Audio- oder Videoinhalte darzustellen. Diese Klassen können interaktiv oder durch eine Uhr gesteuert werden. Diese Klassen können auf dem Microsoft Windows Media Player 10-Steuerelement für die Medienwiedergabe verwendet werden. Welche Klasse Sie verwenden, hängt vom Szenario ab.  
  
 <xref:System.Windows.Controls.MediaElement>ist <xref:System.Windows.UIElement> ein, das vom [Layout](../advanced/layout.md) unterstützt wird und als Inhalt vieler Steuerelemente verwendet werden kann. Es kann auch in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sowie in Code verwendet werden. <xref:System.Windows.Media.MediaPlayer>, auf der anderen Seite, ist für <xref:System.Windows.Media.Drawing> Objekte konzipiert und fehlt Layout-Unterstützung. Mit einem <xref:System.Windows.Media.MediaPlayer> geladene Medien können <xref:System.Windows.Media.VideoDrawing> nur mit einer <xref:System.Windows.Media.DrawingContext>oder durch direkte Interaktion mit einem dargestellt werden. <xref:System.Windows.Media.MediaPlayer>kann nicht in XAML verwendet werden.  
  
 Weitere Informationen zu Zeichnungsobjekten und zum Zeichnungskontext finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
> [!NOTE]
> Wenn Sie Medien mit der Anwendung verteilen, ist es nicht möglich, eine Mediendatei als Projektressource zu verwenden. In der Projektdatei müssen Sie stattdessen den Medientyp auf `Content` festlegen, und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always`.  
  
<a name="mediaplaybackmodes"></a>
## <a name="media-playback-modes"></a>Wiedergabemodi für Medien  
  
> [!NOTE]
> Beide <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> haben ähnliche Mitglieder. Die Links in diesem <xref:System.Windows.Controls.MediaElement> Abschnitt beziehen sich auf die Klassenmitglieder. Sofern nicht ausdrücklich erwähnt, <xref:System.Windows.Controls.MediaElement> können Mitglieder, die <xref:System.Windows.Media.MediaPlayer> mit der Klasse verknüpft sind, auch in der Klasse gefunden werden.  
  
 Um die Medienwiedergabe in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu verstehen, sollten Sie mit den verschiedenen Modi vertraut sein, in denen Medien wiedergegeben werden können. Beide <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> und können in zwei verschiedenen Medienmodi, unabhängigen Modus und Uhrmodus verwendet werden. Der Medienmodus wird <xref:System.Windows.Controls.MediaElement.Clock%2A> durch die Eigenschaft bestimmt. Wenn <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`dies der Zeitpunkt ist, befindet sich das Medienobjekt im unabhängigen Modus. Wenn <xref:System.Windows.Controls.MediaElement.Clock%2A> der nicht NULL ist, befindet sich das Medienobjekt im Uhrzeitmodus. Standardmäßig befinden sich Medienobjekte im unabhängigen Modus.  
  
### <a name="independent-mode"></a>Unabhängiger Modus  
 Im unabhängigen Modus steuert der Medieninhalt die Medienwiedergabe. Im unabhängigen Modus sind die folgenden Optionen aktiviert:  
  
- Medien <xref:System.Uri> können direkt angegeben werden.  
  
- Die Medienwiedergabe kann direkt gesteuert werden.  
  
- Medien <xref:System.Windows.Controls.MediaElement.Position%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> Eigenschaften können geändert werden.  
  
 Medien wird geladen, <xref:System.Windows.Controls.MediaElement> indem entweder <xref:System.Windows.Controls.MediaElement.Source%2A> die Eigenschaft <xref:System.Windows.Media.MediaPlayer> des Objekts oder die Methode des Objekts <xref:System.Windows.Media.MediaPlayer.Open%2A> aufgerufen wird.  
  
 Die Steuerelementmethoden des Medienobjekts können verwendet werden, um die Medienwiedergabe im unabhängigen Modus zu steuern. Die verfügbaren Steuerungsmethoden <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>sind <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Stop%2A>, , und . Für <xref:System.Windows.Controls.MediaElement>ist ein interaktives Steuerelement mit <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> diesen <xref:System.Windows.Controls.MediaState.Manual>Methoden nur verfügbar, wenn der auf festgelegt ist. Diese Methoden sind nicht verfügbar, sich wenn das Medienobjekt im Uhrmodus befindet.  
  
 Ein Beispiel für den unabhängigen Modus finden Sie unter [Steuern eines MediaElement (Wiedergeben, Anhalten, Beenden, Lautstärke und Geschwindigkeit)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Uhrmodus  
 Im Uhrzeigersinn <xref:System.Windows.Media.MediaTimeline> wird die Medienwiedergabe von medienunterstützt. Der Uhrmodus weist folgende Merkmale auf:  
  
- Medien <xref:System.Uri> werden indirekt durch <xref:System.Windows.Media.MediaTimeline>eine gesetzt.  
  
- Die Medienwiedergabe kann von der Uhr gesteuert werden. Die Steuerelementmethoden des Medienobjekts können nicht verwendet werden.  
  
- Medien werden geladen, <xref:System.Windows.Media.MediaTimeline> indem <xref:System.Windows.Media.MediaTimeline.Source%2A> die Eigenschaft eines Objekts festgelegt, die Uhr aus der Zeitachse erstellt und dem Medienobjekt die Uhr zugewiesen wird. Medien werden auch auf <xref:System.Windows.Media.MediaTimeline> diese <xref:System.Windows.Media.Animation.Storyboard> Weise <xref:System.Windows.Controls.MediaElement>geladen, wenn ein Inneres eine anvisiert.  
  
 Um die Medienwiedergabe im Taktmodus zu steuern, müssen die <xref:System.Windows.Media.Animation.ClockController> Steuerungsmethoden verwendet werden. A <xref:System.Windows.Media.Animation.ClockController> wird aus <xref:System.Windows.Media.Animation.ClockController> dem <xref:System.Windows.Media.MediaClock>Eigentum der erhalten. Wenn Sie versuchen, die Steuerungsmethoden <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> eines oder eines Objekts im Uhrzeigersinn zu verwenden, wird ein <xref:System.InvalidOperationException> ausgelöst.  
  
 Weitere Informationen zu Uhren und Zeitachsen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Ein Beispiel für den Uhrmodus finden Sie unter [Steuern eines MediaElement mit einem Storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>
## <a name="mediaelement-class"></a>MediaElement-Klasse  
 Das Hinzufügen von Medien zu einer <xref:System.Windows.Controls.MediaElement> Anwendung [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] ist so einfach <xref:System.Uri> wie das Hinzufügen eines Steuerelements zum Steuerelement der Anwendung und das Bereitstellen eines Steuerelements für die Medien, die Sie einschließen möchten. Alle von Microsoft Windows Media Player 10 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]unterstützten Medientypen werden in unterstützt. Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.MediaElement> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]einfache Verwendung der in .  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In diesem Beispiel werden Medien automatisch wiedergegeben, sobald sie geladen werden. Sobald die Medienwiedergabe abgeschlossen ist, werden die Medium geschlossen und alle Medienressourcen freigegeben (einschließlich Videospeicher). Dies ist das <xref:System.Windows.Controls.MediaElement> Standardverhalten des Objekts und wird von den <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> und-Eigenschaften <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> gesteuert.  
  
### <a name="controlling-a-mediaelement"></a>Steuern eines MediaElement  
 Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> und Eigenschaften steuern <xref:System.Windows.Controls.MediaElement> das <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` Verhalten `false`der wann ist bzw. . Die <xref:System.Windows.Controls.MediaState> Eigenschaften werden so festgelegt, dass sie sich auf das Medienwiedergabeverhalten auswirken. Der Standardwert <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Play> z. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Close>B. . Das bedeutet, dass, <xref:System.Windows.Controls.MediaElement> sobald die geladen und die Preroll abgeschlossen ist, das Medium zu spielen beginnt. Nach Abschluss der Wiedergabe werden die Medien geschlossen und alle Medienressourcen freigegeben.  
  
 Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> und Eigenschaften sind nicht die einzige Möglichkeit, die Medienwiedergabe zu steuern. Im Uhrzeigersinn kann die <xref:System.Windows.Controls.MediaElement> Uhr die steuerung und <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> die <xref:System.Windows.Controls.MediaState.Manual>interaktiven Steuerungsmethoden haben die Steuerung, wenn die ist . <xref:System.Windows.Controls.MediaElement>diesen Kontrollwettbewerb durch Bewertung der folgenden Prioritäten abwickelt.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Vorhanden, wenn Medien entladen werden. Dadurch wird sichergestellt, dass alle Medienressourcen <xref:System.Windows.Media.MediaClock> standardmäßig freigegeben <xref:System.Windows.Controls.MediaElement>werden, auch wenn eine mit der verknüpft ist.  
  
2. <xref:System.Windows.Media.MediaClock>. An Ort und <xref:System.Windows.Controls.MediaElement.Clock%2A>Stelle, wenn Medien eine haben. Wenn Medien entladen werden, wird die <xref:System.Windows.Media.MediaClock> swirksam, solange die <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> . <xref:System.Windows.Controls.MediaState.Manual> Der Uhrmodus überschreibt immer <xref:System.Windows.Controls.MediaElement>das geladene Verhalten der .  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Vorhanden, wenn Medien entladen werden.  
  
4. Interaktive Steuerelementmethoden. An Ort <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>und Stelle, wenn ist . Die verfügbaren Steuerungsmethoden <xref:System.Windows.Controls.MediaElement.Pause%2A> <xref:System.Windows.Controls.MediaElement.Close%2A>sind <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Stop%2A>, , und .  
  
### <a name="displaying-a-mediaelement"></a>Anzeigen eines MediaElement  
 Um eine <xref:System.Windows.Controls.MediaElement> anzuzeigen, muss es Inhalt zum <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A> Rendern haben, und es wird seine und Eigenschaften auf Null gesetzt, bis Inhalt geladen wird. Bei ausschließlichen Audioinhalten sind diese Eigenschaften immer null. Bei Videoinhalten wird <xref:System.Windows.Controls.MediaElement.MediaOpened> nach dem <xref:System.Windows.FrameworkElement.ActualWidth%2A> Hochspringen des Ereignisses die <xref:System.Windows.FrameworkElement.ActualHeight%2A> Größe der geladenen Medien gemeldet. Dies bedeutet, dass bis <xref:System.Windows.Controls.MediaElement> zum Laden des Mediums [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kein <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> physischer Speicherplatz in der oder die Eigenschaften festgelegt sind.  
  
 Wenn Sie <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> sowohl die als auch die Eigenschaften festlegen, <xref:System.Windows.Controls.MediaElement>wird das Medium gestreckt, um den für die bereitgestellten Bereich zu füllen. Um das ursprüngliche Seitenverhältnis des Mediums beizubehalten, sollte entweder die <xref:System.Windows.FrameworkElement.Width%2A> oder-Eigenschaft <xref:System.Windows.FrameworkElement.Height%2A> festgelegt werden, jedoch nicht beides. Wenn Sie <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> sowohl die als auch die Eigenschaften festlegen, werden die Medien in einer festen Elementgröße angezeigt, die möglicherweise nicht wünschenswert ist.  
  
 Um ein Element mit fester Größe zu vermeiden, kann [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] einen Vorlauf für die Medien durchführen. Dies geschieht, <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> indem <xref:System.Windows.Controls.MediaState.Play> Sie <xref:System.Windows.Controls.MediaState.Pause>die einstellung auf oder . In <xref:System.Windows.Controls.MediaState.Pause> einem Zustand werden die Medien vorab rollen und den ersten Frame präsentieren. In <xref:System.Windows.Controls.MediaState.Play> einem Zustand werden die Medien vorrollen und beginnen zu spielen.  
  
<a name="mediaplayer"></a>
## <a name="mediaplayer-class"></a>MediaPlayer-Klasse  
 Wobei die <xref:System.Windows.Controls.MediaElement> Klasse ein Frameworkelement <xref:System.Windows.Media.MediaPlayer> ist, ist die <xref:System.Windows.Media.Drawing> Klasse so konzipiert, dass sie in Objekten verwendet wird. Zeichnungsobjekte werden verwendet, wenn Sie Features auf Frameworkebene <xref:System.Windows.Freezable> opfern können, um Leistungsvorteile zu erzielen, oder wenn Sie Features benötigen. <xref:System.Windows.Media.MediaPlayer>ermöglicht es Ihnen, diese Funktionen zu nutzen und gleichzeitig Medieninhalte in Ihren Anwendungen bereitzustellen. Like <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> , kann im unabhängigen modus oder im <xref:System.Windows.Controls.MediaElement> Uhrtaktmodus verwendet werden, hat jedoch nicht die entladenen und geladenen Zustände des Objekts. Dies reduziert die Komplexität <xref:System.Windows.Media.MediaPlayer>der Wiedergabesteuerung der .  
  
### <a name="controlling-mediaplayer"></a>Steuern des MediaPlayer  
 Da <xref:System.Windows.Media.MediaPlayer> es zustandslos ist, gibt es nur zwei Möglichkeiten, die Medienwiedergabe zu steuern.  
  
1. Interaktive Steuerelementmethoden. Im unabhängigen Modus (Eigenschaft).`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A>  
  
2. <xref:System.Windows.Media.MediaClock>. An Ort und <xref:System.Windows.Media.MediaPlayer.Clock%2A>Stelle, wenn Medien eine haben.  
  
### <a name="displaying-a-mediaplayer"></a>Anzeigen eines MediaElement  
 Technisch kann <xref:System.Windows.Media.MediaPlayer> eine nicht angezeigt werden, da sie keine physische Darstellung hat. Es kann jedoch verwendet werden, <xref:System.Windows.Media.Drawing> um <xref:System.Windows.Media.VideoDrawing> Medien in einer Verwendung der Klasse darzustellen. Im folgenden Beispiel wird <xref:System.Windows.Media.VideoDrawing> die Verwendung eines zum Anzeigen von Medien veranschaulicht.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Weitere Informationen <xref:System.Windows.Media.Drawing> zu Objekten finden Sie in der Übersicht über [Zeichnungsobjekte.](drawing-objects-overview.md)  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [How-to-Themen](audio-and-video-how-to-topics.md)
