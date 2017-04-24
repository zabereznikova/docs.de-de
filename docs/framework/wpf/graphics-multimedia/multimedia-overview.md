---
title: "&#220;bersicht &#252;ber Multimedia | Microsoft Docs"
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
  - "Medien"
  - "Multimedia"
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# &#220;bersicht &#252;ber Multimedia
Mit den Multimediafunktionen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Audio\- und Videoinhalte in Ihre Anwendungen integrieren, um die Benutzerfreundlichkeit zu verbessern. In diesem Thema werden die Multimediafunktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt.  
  
   
  
<a name="mediaapi"></a>   
## Medien\-API  
 Die <xref:System.Windows.Controls.MediaElement>\- und <xref:System.Windows.Media.MediaPlayer>\-Klassen werden verwendet, um Audio\- und Videoinhalte zu präsentieren.  Diese Klassen können interaktiv oder von einer Uhr gesteuert werden.  Die Klassen können für das [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10\-Steuerelement zur Medienwiedergabe verwendet werden. Welche Klasse verwendet wird, hängt vom Szenario ab.  
  
 <xref:System.Windows.Controls.MediaElement> ist ein <xref:System.Windows.UIElement>, das vom [Layout](../../../../docs/framework/wpf/advanced/layout.md) unterstützt wird und als Inhalt vieler Steuerelemente verwendet werden kann.  Es kann in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und in Code verwendet werden. <xref:System.Windows.Media.MediaPlayer> hingegen ist für <xref:System.Windows.Media.Drawing>\-Objekte konzipiert und bietet keine Layoutunterstützung.  Medien, die mit dem <xref:System.Windows.Media.MediaPlayer> geladen werden, können nur mithilfe von <xref:System.Windows.Media.VideoDrawing> oder durch direkte Interaktion mit einem <xref:System.Windows.Media.DrawingContext> angezeigt werden.  <xref:System.Windows.Media.MediaPlayer> kann in XAML nicht verwendet werden.  
  
 Weitere Informationen zu Zeichnungsobjekten und zum Zeichnungskontext finden Sie unter [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
> [!NOTE]
>  Wenn Sie mit der Anwendung Medien verteilen, ist es nicht möglich, eine Mediendatei als Projektressource zu verwenden.  Sie müssen stattdessen in der Projektdatei den Medientyp auf `Content` und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always` festlegen.  
  
<a name="mediaplaybackmodes"></a>   
## Wiedergabemodi für Medien  
  
> [!NOTE]
>  <xref:System.Windows.Controls.MediaElement> und <xref:System.Windows.Media.MediaPlayer> verfügen über ähnliche Member.  Die Links in diesem Abschnitt verweisen auf die <xref:System.Windows.Controls.MediaElement>\-Klassenmember.  Wenn nicht ausdrücklich anders angegeben, sind Member, für die in der <xref:System.Windows.Controls.MediaElement>\-Klasse Verknüpfungen enthalten sind, auch in der <xref:System.Windows.Media.MediaPlayer>\-Klasse enthalten.  
  
 Um die Medienwiedergabe in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu verstehen, sollten Sie mit den verschiedenen Modi vertraut sein, in denen Medien wiedergegeben werden können.  Sowohl <xref:System.Windows.Controls.MediaElement> als auch <xref:System.Windows.Media.MediaPlayer> können in zwei verschiedenen Medienmodi verwendet werden: im unabhängigen Modus oder im Uhrmodus.  Der Medienmodus wird durch die <xref:System.Windows.Controls.MediaElement.Clock%2A>\-Eigenschaft bestimmt.  Wenn <xref:System.Windows.Controls.MediaElement.Clock%2A> `null` ist, befindet sich das Medienobjekt im unabhängigen Modus.  Wenn <xref:System.Windows.Controls.MediaElement.Clock%2A> nicht NULL ist, befindet sich das Medienobjekt im Uhrmodus.  Standardmäßig befinden sich Medienobjekte im unabhängigen Modus.  
  
### Unabhängiger Modus  
 Im unabhängigen Modus steuert der Medieninhalt die Medienwiedergabe.  Im unabhängigen Modus sind die folgenden Optionen aktiviert:  
  
-   Der <xref:System.Uri> von Medien kann direkt angegeben werden.  
  
-   Die Medienwiedergabe kann direkt gesteuert werden.  
  
-   Die <xref:System.Windows.Controls.MediaElement.Position%2A>\-Eigenschaft und die <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>\-Eigenschaft von Medien können geändert werden.  
  
 Medien werden geladen, indem entweder die <xref:System.Windows.Controls.MediaElement.Source%2A>\-Eigenschaft des <xref:System.Windows.Controls.MediaElement>\-Objekts festgelegt oder die <xref:System.Windows.Media.MediaPlayer.Open%2A>\-Methode des <xref:System.Windows.Media.MediaPlayer>\-Objekts aufgerufen wird.  
  
 Die Steuerelementmethoden des Medienobjekts können verwendet werden, um die Medienwiedergabe im unabhängigen Modus zu steuern.  Die verfügbaren Steuerelementmethoden sind <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A> und <xref:System.Windows.Controls.MediaElement.Stop%2A>.  Für <xref:System.Windows.Controls.MediaElement> ist die interaktive Steuerung mit diesen Methoden nur verfügbar, wenn das <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> auf <xref:System.Windows.Controls.MediaState> festgelegt wird.  Diese Methoden sind nicht verfügbar, wenn sich das Medienobjekt im Uhrmodus befindet.  
  
 Ein Beispiel für den unabhängigen Modus finden Sie unter [Steuern eines MediaElement \(Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md).  
  
### Uhrmodus  
 Im Uhrmodus steuert eine <xref:System.Windows.Media.MediaTimeline> die Medienwiedergabe.  Der Uhrmodus weist folgende Merkmale auf:  
  
-   Der <xref:System.Uri> von Medien wird indirekt durch eine <xref:System.Windows.Media.MediaTimeline> festgelegt.  
  
-   Die Medienwiedergabe kann von der Uhr gesteuert werden.  Die Steuerelementmethoden des Medienobjekts können nicht verwendet werden.  
  
-   Medien werden geladen, indem die <xref:System.Windows.Media.MediaTimeline.Source%2A>\-Eigenschaft eines <xref:System.Windows.Media.MediaTimeline>\-Objekts festgelegt, die Uhr aus der Zeitachse erstellt und die Uhr dem Medienobjekt zugeordnet wird.  Medien werden auch auf diese Weise geladen, wenn eine <xref:System.Windows.Media.MediaTimeline> in einem <xref:System.Windows.Media.Animation.Storyboard> auf ein <xref:System.Windows.Controls.MediaElement> ausgerichtet ist.  
  
 Um die Medienwiedergabe im Uhrmodus zu steuern, müssen die <xref:System.Windows.Media.Animation.ClockController>\-Steuerelementmethoden verwendet werden.  Ein <xref:System.Windows.Media.Animation.ClockController> wird von der <xref:System.Windows.Media.Animation.ClockController>\-Eigenschaft der <xref:System.Windows.Media.MediaClock> abgerufen.  Wenn Sie versuchen, die Steuerelementmethoden eines <xref:System.Windows.Controls.MediaElement>\-Objekts oder eines <xref:System.Windows.Media.MediaPlayer>\-Objekts zu verwenden, während es sich im Uhrmodus befindet, wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
 Weitere Informationen zu Uhren und Zeitachsen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Ein Beispiel für den Uhrmodus finden Sie unter [Steuern eines MediaElement mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md).  
  
<a name="mediaelement"></a>   
## MediaElement\-Klasse  
 Wenn Sie Medien zu einer Anwendung hinzufügen möchten, müssen Sie lediglich ein <xref:System.Windows.Controls.MediaElement>\-Steuerelement zur [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Anwendung hinzufügen und einen <xref:System.Uri> für die Medien bereitstellen, die Sie aufnehmen möchten.  Alle von [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 unterstützten Medientypen werden in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] unterstützt. Das folgende Beispiel zeigt eine einfache Verwendung von <xref:System.Windows.Controls.MediaElement> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 In diesem Beispiel werden Medien automatisch wiedergegeben, sobald sie geladen werden.  Sobald die Medienwiedergabe abgeschlossen ist, werden die Medien geschlossen und alle Medienressourcen freigegeben \(einschließlich des Videospeichers\).  Dies ist das Standardverhalten des <xref:System.Windows.Controls.MediaElement>\-Objekts und wird von der <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>\-Eigenschaft und der <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>\-Eigenschaft gesteuert.  
  
### MediaElement\-Steuerung  
 Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>\-Eigenschaft bzw. die <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>\-Eigenschaft steuert das <xref:System.Windows.Controls.MediaElement>\-Verhalten, wenn <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` bzw. `false` ist.  Der <xref:System.Windows.Controls.MediaState>, auf den die Eigenschaften festgelegt werden, beeinflusst das Verhalten der Medienwiedergabe.  Beispielsweise ist <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> standardmäßig <xref:System.Windows.Controls.MediaState>, und <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> ist standardmäßig <xref:System.Windows.Controls.MediaState>.  Dies bedeutet, dass die Medien wiedergegeben werden, sobald das <xref:System.Windows.Controls.MediaElement> geladen wird und der [Vorlauf](GTMT) beendet ist.  Sobald die Wiedergabe abgeschlossen ist, werden die Medien geschlossen und alle Medienressourcen freigegeben.  
  
 Es gibt auch andere Möglichkeiten, die Medienwiedergabe zu steuern, als mit der <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>\-Eigenschaft und der <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>\-Eigenschaft.  Im Uhrmodus kann die Uhr das <xref:System.Windows.Controls.MediaElement> steuern, und die interaktiven Steuerelementmethoden übernehmen die Steuerung, wenn die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>\-Eigenschaft <xref:System.Windows.Controls.MediaState> ist.  <xref:System.Windows.Controls.MediaElement> behandelt diese Konkurrenz bei der Steuerung, indem die folgenden Prioritäten ausgewertet werden.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  Vorhanden, wenn Medien entladen werden.  Dies stellt sicher, dass alle Medienressourcen standardmäßig freigegeben werden, auch wenn eine <xref:System.Windows.Media.MediaClock> mit dem <xref:System.Windows.Controls.MediaElement> verknüpft ist.  
  
2.  <xref:System.Windows.Media.MediaClock>.  Vorhanden, wenn Medien über eine <xref:System.Windows.Controls.MediaElement.Clock%2A>\-Eigenschaft verfügen.  Wenn Medien entladen werden, ist die <xref:System.Windows.Media.MediaClock> wirksam, solange das <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A><xref:System.Windows.Controls.MediaState> ist.  Der Uhrmodus überschreibt immer das LoadedBehavior für das <xref:System.Windows.Controls.MediaElement>.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>.  Vorhanden, wenn Medien geladen werden.  
  
4.  Interaktive Steuerelementmethoden  Vorhanden, wenn <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A><xref:System.Windows.Controls.MediaState> ist.  Die verfügbaren Steuerelementmethoden sind <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A> und <xref:System.Windows.Controls.MediaElement.Stop%2A>.  
  
### MediaElement\-Anzeige  
 Um ein <xref:System.Windows.Controls.MediaElement> anzuzeigen, muss dieses Element Inhalt besitzen, der gerendert werden kann. Die <xref:System.Windows.FrameworkElement.ActualWidth%2A>\-Eigenschaft und die <xref:System.Windows.FrameworkElement.ActualHeight%2A>\-Eigenschaft werden auf 0 \(null\) festgelegt, bis Inhalt geladen wird.  Bei ausschließlichen Audioinhalten sind diese Eigenschaften immer 0 \(null\).  Für Videoinhalte wird gleich nach dem Auslösen des <xref:System.Windows.Controls.MediaElement.MediaOpened>\-Ereignisses von <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> die Größe der geladenen Medien angegeben.  Bis die Medien geladen sind, benötigt das <xref:System.Windows.Controls.MediaElement> also keinen Speicherplatz in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], es sei denn, die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft oder die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft wird festgelegt.  
  
 Wenn sowohl die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft als auch die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft festgelegt ist, werden die Medien gestreckt, sodass sie den Bereich ausfüllen, der für das <xref:System.Windows.Controls.MediaElement> bereitgestellt wurde.  Um das ursprüngliche [Seitenverhältnis](GTMT) der Medien beizubehalten, legen Sie entweder die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft oder die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft fest, jedoch nicht beide Eigenschaften gleichzeitig.  Wenn Sie sowohl die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft als auch die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft festlegen, werden die Medien in einem Element mit festgelegter Größe angezeigt. Dies ist u. U. nicht wünschenswert.  
  
 Um ein Element mit fester Größe zu vermeiden, kann [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] einen [Vorlauf](GTMT) für die Medien durchführen.  Legen Sie hierzu das <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> auf <xref:System.Windows.Controls.MediaState> oder auf <xref:System.Windows.Controls.MediaState> fest.  In einem <xref:System.Windows.Controls.MediaState>\-Zustand wird für die Medien ein Vorlauf durchgeführt und der erste Frame angezeigt.  In einem <xref:System.Windows.Controls.MediaState>\-Zustand wird für die Medien ein [Vorlauf](GTMT) durchgeführt und die Wiedergabe gestartet.  
  
<a name="mediaplayer"></a>   
## MediaPlayer\-Klasse  
 Während es sich bei der <xref:System.Windows.Controls.MediaElement>\-Klasse um ein Frameworkelement handelt, ist die <xref:System.Windows.Media.MediaPlayer>\-Klasse auf die Verwendung in <xref:System.Windows.Media.Drawing>\-Objekten ausgerichtet.  Zeichnungsobjekte werden verwendet, wenn Sie zur Leistungsverbesserung Features auf Frameworkebene opfern können oder wenn Sie <xref:System.Windows.Freezable>\-Features benötigen.  Das <xref:System.Windows.Media.MediaPlayer>\-Element ermöglicht Ihnen, diese Features zu nutzen, wenn Sie Medieninhalte in Ihren Anwendungen bereitstellen.  Wie das <xref:System.Windows.Controls.MediaElement> kann <xref:System.Windows.Media.MediaPlayer> im unabhängigen Modus oder im Uhrmodus verwendet werden, verfügt jedoch nicht über den entladenen oder geladenen Zustand des <xref:System.Windows.Controls.MediaElement>\-Objekts.  Dies reduziert die Komplexität der Wiedergabesteuerelemente von <xref:System.Windows.Media.MediaPlayer>.  
  
### MediaPlayer\-Steuerung  
 Da <xref:System.Windows.Media.MediaPlayer> statusfrei ist, gibt es nur zwei Möglichkeiten, die Medienwiedergabe zu steuern.  
  
1.  Interaktive Steuerelementmethoden  Im unabhängigen Modus vorhanden \(`null`<xref:System.Windows.Media.MediaPlayer.Clock%2A>\-Eigenschaft\).  
  
2.  <xref:System.Windows.Media.MediaClock>.  Vorhanden, wenn Medien über eine <xref:System.Windows.Media.MediaPlayer.Clock%2A>\-Eigenschaft verfügen.  
  
### MediaPlayer\-Anzeige  
 Technisch gesehen kann <xref:System.Windows.Media.MediaPlayer> nicht angezeigt werden, da keine physische Darstellung vorhanden ist.  MediaPlayer kann jedoch verwendet werden, um mithilfe der <xref:System.Windows.Media.VideoDrawing>\-Klasse Medien in einer <xref:System.Windows.Media.Drawing> anzuzeigen.  Im folgenden Beispiel wird veranschaulicht, wie mit einer <xref:System.Windows.Media.VideoDrawing> Medien angezeigt werden.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Weitere Informationen über <xref:System.Windows.Media.Drawing>\-Objekte finden Sie unter [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingGroup>   
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)