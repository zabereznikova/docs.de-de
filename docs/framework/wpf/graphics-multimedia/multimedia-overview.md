---
title: Übersicht über Multimedia
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 66cb28fce9485898711b9029baf8a17dd9b2c011
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62030384"
---
# <a name="multimedia-overview"></a>Übersicht über Multimedia
Die Multimediafunktionen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ermöglichen Ihnen die Integration von Audio- und Videoinhalten in Ihre Anwendungen, um die Benutzerfreundlichkeit zu verbessern. In diesem Thema werden die Multimediafunktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt.  

<a name="mediaapi"></a>   
## <a name="media-api"></a>Medien-API  
 Die <xref:System.Windows.Controls.MediaElement> und <xref:System.Windows.Media.MediaPlayer> Klassen werden verwendet, um Audio-und Videoinhalte zu präsentieren. Diese Klassen können interaktiv oder durch eine Uhr gesteuert werden. Die Klassen können für das [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10-Steuerelement zur Medienwiedergabe verwendet werden. Welche Klasse Sie verwenden, hängt vom Szenario ab.  
  
 <xref:System.Windows.Controls.MediaElement> ist eine <xref:System.Windows.UIElement> , unterstützt durch die [Layout](../advanced/layout.md) und als Inhalt vieler Steuerelemente verwendet werden kann. Es kann auch in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sowie in Code verwendet werden. <xref:System.Windows.Media.MediaPlayer>, auf der anderen Seite ist für das <xref:System.Windows.Media.Drawing> Objekten und bietet keine layoutunterstützung. Mit geladene Medien ein <xref:System.Windows.Media.MediaPlayer> kann nur mit angezeigt werden eine <xref:System.Windows.Media.VideoDrawing> oder durch direkte Interaktion mit einem <xref:System.Windows.Media.DrawingContext>. <xref:System.Windows.Media.MediaPlayer> kann nicht in XAML verwendet werden.  
  
 Weitere Informationen zu Zeichnungsobjekten und zum Zeichnungskontext finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
> [!NOTE]
>  Wenn Sie Medien mit der Anwendung verteilen, ist es nicht möglich, eine Mediendatei als Projektressource zu verwenden. Sie müssen stattdessen in der Projektdatei den Medientyp auf `Content` und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always` festlegen.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>Wiedergabemodi für Medien  
  
> [!NOTE]
>  Beide <xref:System.Windows.Controls.MediaElement> und <xref:System.Windows.Media.MediaPlayer> verfügen über ähnliche Member. Die Links in diesem Abschnitt verweisen auf die <xref:System.Windows.Controls.MediaElement> Klassenmember. Sofern nicht ausdrücklich angegeben ist, verknüpft Member, in der <xref:System.Windows.Controls.MediaElement> Klasse finden Sie auch der <xref:System.Windows.Media.MediaPlayer> Klasse.  
  
 Um die Medienwiedergabe in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu verstehen, sollten Sie mit den verschiedenen Modi vertraut sein, in denen Medien wiedergegeben werden können. Beide <xref:System.Windows.Controls.MediaElement> und <xref:System.Windows.Media.MediaPlayer> kann in zwei verschiedenen Medienmodi unabhängigen Modus oder im Clock-Modus verwendet werden. Der Medienmodus richtet sich nach der <xref:System.Windows.Controls.MediaElement.Clock%2A> Eigenschaft. Wenn <xref:System.Windows.Controls.MediaElement.Clock%2A> ist `null`, das Medienobjekt im unabhängigen Modus ist. Wenn die <xref:System.Windows.Controls.MediaElement.Clock%2A> ist nicht Null ist, das Medienobjekt wird im Clock-Modus. Standardmäßig befinden sich Medienobjekte im unabhängigen Modus.  
  
### <a name="independent-mode"></a>Unabhängiger Modus  
 Im unabhängigen Modus steuert der Medieninhalt die Medienwiedergabe. Im unabhängigen Modus sind die folgenden Optionen aktiviert:  
  
- Medien <xref:System.Uri> kann direkt angegeben werden.  
  
- Die Medienwiedergabe kann direkt gesteuert werden.  
  
- Medien <xref:System.Windows.Controls.MediaElement.Position%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> Eigenschaften geändert werden können.  
  
 Medien werden geladen, entweder durch Festlegen der <xref:System.Windows.Controls.MediaElement> des Objekts <xref:System.Windows.Controls.MediaElement.Source%2A> Eigenschaft oder durch Aufrufen der <xref:System.Windows.Media.MediaPlayer> des Objekts <xref:System.Windows.Media.MediaPlayer.Open%2A> Methode.  
  
 Die Steuerelementmethoden des Medienobjekts können verwendet werden, um die Medienwiedergabe im unabhängigen Modus zu steuern. Die verfügbaren Steuerelementmethoden sind <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A>. Für <xref:System.Windows.Controls.MediaElement>, interaktive Steuerung mit diesen Methoden ist nur verfügbar, wenn die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> nastaven NA hodnotu <xref:System.Windows.Controls.MediaState.Manual>. Diese Methoden sind nicht verfügbar, sich wenn das Medienobjekt im Uhrmodus befindet.  
  
 Ein Beispiel für den unabhängigen Modus finden Sie unter [Steuern eines MediaElement (Wiedergeben, Anhalten, Beenden, Lautstärke und Geschwindigkeit)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### <a name="clock-mode"></a>Uhrmodus  
 Im Uhrmodus befindet eine <xref:System.Windows.Media.MediaTimeline> Laufwerke die Medienwiedergabe. Der Uhrmodus weist folgende Merkmale auf:  
  
- Medien <xref:System.Uri> wird indirekt durch Festlegen einer <xref:System.Windows.Media.MediaTimeline>.  
  
- Die Medienwiedergabe kann von der Uhr gesteuert werden. Die Steuerelementmethoden des Medienobjekts können nicht verwendet werden.  
  
- Medien werden geladen, durch Festlegen einer <xref:System.Windows.Media.MediaTimeline> des Objekts <xref:System.Windows.Media.MediaTimeline.Source%2A> Eigenschaft, die Uhr aus der Zeitachse erstellt, und die Uhr dem Medienobjekt. Medien werden auch auf diese Weise geladen, wenn eine <xref:System.Windows.Media.MediaTimeline> in eine <xref:System.Windows.Media.Animation.Storyboard> Ziele eine <xref:System.Windows.Controls.MediaElement>.  
  
 Zum Steuern der Medienwiedergabe im Uhrmodus befindet die <xref:System.Windows.Media.Animation.ClockController> -Steuerelementmethoden verwendet werden müssen. Ein <xref:System.Windows.Media.Animation.ClockController> aus einer der <xref:System.Windows.Media.Animation.ClockController> Eigenschaft der <xref:System.Windows.Media.MediaClock>. Wenn Sie versuchen, die entweder zu verwenden eine <xref:System.Windows.Controls.MediaElement> oder <xref:System.Windows.Media.MediaPlayer> Objekt im Uhrmodus befindet, wird ein <xref:System.InvalidOperationException> ausgelöst.  
  
 Weitere Informationen zu Uhren und Zeitachsen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Ein Beispiel für den Uhrmodus finden Sie unter [Steuern eines MediaElement mit einem Storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>MediaElement-Klasse  
 Hinzufügen von Medien zu einer Anwendung ist so einfach wie das Hinzufügen einer <xref:System.Windows.Controls.MediaElement> die Steuerung an die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Anwendung und Bereitstellen einer <xref:System.Uri> auf die Medien, die Sie einschließen möchten. Alle von [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 unterstützten Medientypen werden in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] unterstützt. Das folgende Beispiel zeigt eine einfache Verwendung von der <xref:System.Windows.Controls.MediaElement> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In diesem Beispiel werden Medien automatisch wiedergegeben, sobald sie geladen werden. Sobald die Medienwiedergabe abgeschlossen ist, werden die Medium geschlossen und alle Medienressourcen freigegeben (einschließlich Videospeicher). Dies ist das Standardverhalten der <xref:System.Windows.Controls.MediaElement> Objekt aus, und wird gesteuert, indem die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> und <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Eigenschaften.  
  
### <a name="controlling-a-mediaelement"></a>Steuern eines MediaElement  
 Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> und <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Eigenschaften steuern das Verhalten der <xref:System.Windows.Controls.MediaElement> beim <xref:System.Windows.FrameworkElement.IsLoaded%2A> ist `true` oder `false`bzw. Die <xref:System.Windows.Controls.MediaState> die Eigenschaften werden festgelegt, um das Verhalten der Medienwiedergabe auswirken. Z. B. die Standardeinstellung <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Play> und der standardmäßige <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Close>. Dies bedeutet, dass, sobald die <xref:System.Windows.Controls.MediaElement> geladen wird und der Vorlauf abgeschlossen ist, beginnt die Medien wiedergeben. Nach Abschluss der Wiedergabe werden die Medien geschlossen und alle Medienressourcen freigegeben.  
  
 Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> und <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> Eigenschaften sind nicht die einzige Möglichkeit zum Steuern der Medienwiedergabe. Im Uhrmodus befindet, kann die Uhr steuern die <xref:System.Windows.Controls.MediaElement> und haben die interaktive Steuerung Methoden steuern, wann die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Manual>. <xref:System.Windows.Controls.MediaElement> behandelt diese Konkurrenz bei der Steuerung durch die folgenden Prioritäten ausgewertet.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. Vorhanden, wenn Medien entladen werden. Dadurch wird sichergestellt, dass alle Medienressourcen standardmäßig freigegeben werden, auch wenn eine <xref:System.Windows.Media.MediaClock> zugeordnet ist die <xref:System.Windows.Controls.MediaElement>.  
  
2. <xref:System.Windows.Media.MediaClock>. Vorhanden, wenn die Medien ein <xref:System.Windows.Controls.MediaElement.Clock%2A>. Wenn Medien entladen wurde, werden die <xref:System.Windows.Media.MediaClock> werden wirksam, solange die <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Manual>. Der Uhrmodus überschreibt immer das geladene Verhalten für die <xref:System.Windows.Controls.MediaElement>.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. Vorhanden, wenn Medien entladen werden.  
  
4. Interaktive Steuerelementmethoden. Vorhanden, wenn <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> ist <xref:System.Windows.Controls.MediaState.Manual>. Die verfügbaren Steuerelementmethoden sind <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### <a name="displaying-a-mediaelement"></a>Anzeigen eines MediaElement  
 Zum Anzeigen einer <xref:System.Windows.Controls.MediaElement> muss zu rendernden Inhalt und verfügt über seine <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> Eigenschaften festgelegt, um 0 (null) bis der Inhalt geladen wird. Bei ausschließlichen Audioinhalten sind diese Eigenschaften immer null. Für Videoinhalte, sobald die <xref:System.Windows.Controls.MediaElement.MediaOpened> -Ereignis ausgelöst wurde die <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> gibt die Größe der geladenen Medien. Dies bedeutet, dass bis Medien geladen sind, die <xref:System.Windows.Controls.MediaElement> beansprucht nicht physischen Speicherplatz in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , wenn die <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften festgelegt werden.  
  
 Einstellung der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften führt dazu, dass die Medien gestreckt, um den vorgesehenen Bereich füllen die <xref:System.Windows.Controls.MediaElement>. Das Medium für die ursprünglichen Seitenverhältnisse beizubehalten, entweder beibehalten der <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaft fest, jedoch nicht beide werden soll. Einstellung der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften führt dazu, dass die Medien in ein Element mit festgelegter Größe angezeigt, die möglicherweise nicht wünschenswert.  
  
 Um ein Element mit fester Größe zu vermeiden, kann [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] einen Vorlauf für die Medien durchführen. Dies erfolgt durch Festlegen der <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> entweder <xref:System.Windows.Controls.MediaState.Play> oder <xref:System.Windows.Controls.MediaState.Pause>. In einem <xref:System.Windows.Controls.MediaState.Pause> aufweist, die Medien ein Vorlauf durchgeführt und der erste Frame. In einem <xref:System.Windows.Controls.MediaState.Play> aufweist, die Medien ein Vorlauf durchgeführt und die Wiedergabe gestartet werden.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>MediaPlayer-Klasse  
 Wobei die <xref:System.Windows.Controls.MediaElement> Klasse ist ein FrameworkElement, das <xref:System.Windows.Media.MediaPlayer> Klasse in verwendet werden soll <xref:System.Windows.Media.Drawing> Objekte. Zeichnungsobjekte werden verwendet, wenn Sie Frameworkfeatures auf Frameworkebene Leistungsvorteile Opfern können oder Sie müssen <xref:System.Windows.Freezable> Funktionen. <xref:System.Windows.Media.MediaPlayer> können Sie diese Features zu nutzen und die Medieninhalte in Ihren Anwendungen bereitstellen. Wie <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> in unabhängig verwendet werden kann oder nicht clock-Modus, jedoch wird haben die <xref:System.Windows.Controls.MediaElement> Objekt entladenen oder geladenen Zustand. Dies reduziert die Komplexität der Wiedergabesteuerelemente von der <xref:System.Windows.Media.MediaPlayer>.  
  
### <a name="controlling-mediaplayer"></a>Steuern des MediaPlayer  
 Da <xref:System.Windows.Media.MediaPlayer> ist statusfrei, stehen nur zwei Möglichkeiten zum Steuern der Medienwiedergabe.  
  
1. Interaktive Steuerelementmethoden. Im unabhängigen Modus vorhanden (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> Eigenschaft).  
  
2. <xref:System.Windows.Media.MediaClock>. Vorhanden, wenn die Medien ein <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
### <a name="displaying-a-mediaplayer"></a>Anzeigen eines MediaElement  
 Technisch gesehen eine <xref:System.Windows.Media.MediaPlayer> kann nicht angezeigt werden, da es keine physische Darstellung vorhanden ist. Es kann jedoch verwendet werden, zur Darstellung von Medien in einem <xref:System.Windows.Media.Drawing> mithilfe der <xref:System.Windows.Media.VideoDrawing> Klasse. Das folgende Beispiel zeigt die Verwendung von einem <xref:System.Windows.Media.VideoDrawing> Medien angezeigt.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Finden Sie unter den [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md) für Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekte.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.DrawingGroup>
- [Layout](../advanced/layout.md)
- [Themen zu Vorgehensweisen](audio-and-video-how-to-topics.md)
