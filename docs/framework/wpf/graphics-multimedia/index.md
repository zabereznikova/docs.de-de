---
title: "Grafiken und Multimedia | Microsoft Docs"
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
  - "Animation, Funktionen"
  - "Grafikfeatures"
  - "Medien, Funktionen"
  - "Soundeffekte"
  - "Übergangseffekte"
  - "Videoeffekte"
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Grafiken und Multimedia
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für Multimedia, Vektorgrafiken, Animation und Inhaltskomposition, wodurch Entwickler auf einfache Weise interessante Benutzeroberflächen und Benutzerinhalte erstellen können.  Mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] können Sie Vektorgrafiken oder komplexe Animationen erstellen und Medien in die Anwendungen integrieren.  
  
 In diesem Thema werden die Grafik\-, Animations\- und Medienfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt, mit denen Sie den Anwendungen Grafiken, Übergangseffekte, Sound und Video hinzufügen können.  
  
> [!NOTE]
>  Es wird dringend davon abgeraten, WPF\-Typen in einem Windows\-Dienst zu verwenden.  Wenn Sie versuchen, WPF\-Typen in einem Windows\-Dienst zu verwenden, funktioniert der Dienst möglicherweise nicht wie erwartet.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## Neue Grafik\- und Multimediafunktionen in WPF 4  
 Mehrere Änderungen wurden im Hinblick auf Grafiken und Animationen vorgenommen.  
  
-   Layoutrundung  
  
     Wenn ein Objektrand in die Mitte eines Pixelgeräts fällt, kann das DPI\-unabhängige Grafiksystem Renderingartefakte erstellen, z. B. verschwommene oder semitransparente Ränder.  Frühere Versionen der WPF haben die Pixelausrichtung für diese Fälle verwendet.  Silverlight 2 hat die Layoutrundung eingeführt, die eine andere Möglichkeit bietet, um Elemente so zu verschieben, dass Ränder auf ganzen Pixelgrenzen liegen.  WPF unterstützt jetzt die Layoutrundung mit der angefügten <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>\-Eigenschaft auf <xref:System.Windows.FrameworkElement>.  
  
-   Zwischengespeicherte Komposition  
  
     Mit den neuen Klassen <xref:System.Windows.Media.BitmapCache> und <xref:System.Windows.Media.BitmapCacheBrush> können Sie einen komplexen Teil der visuellen Struktur als Bitmap zwischenspeichern und die Renderingzeit dadurch erheblich optimieren.  Die Bitmap reagiert weiterhin auf Benutzereingabe, z. B. Mausklicks, und Sie können sie wie jeden Pinsel auf anderen Elementen zeichnen.  
  
-   Unterstützung von Pixel Shader 3  
  
     WPF 4 erweitert die in WPF 3.5 SP1 eingeführte <xref:System.Windows.Media.Effects.ShaderEffect>\-Unterstützung und ermöglicht es Anwendungen, Effekte mit Pixel Shader \(PS\) Version 3.0 zu schreiben.  Das PS 3.0\-Shadermodell ist ausgereifter als PS 2.0 und ermöglicht noch mehr Effekte auf unterstützter Hardware.  
  
-   Beschleunigungsfunktionen  
  
     Sie können Animationen mit Beschleunigungsfunktionen verbessern, die Ihnen zusätzliche Kontrolle über das Verhalten von Animationen geben.  Sie können z. B. eine <xref:System.Windows.Media.Animation.ElasticEase> für eine Animation übernehmen, um der Animation ein Federverhalten zuzuweisen.  Weitere Informationen finden Sie unter den Beschleunigungstypen im <xref:System.Windows.Media.Animation>\-Namespace.  
  
<a name="graphics_and_rendering"></a>   
## Grafiken und Rendering  
 WPF bietet Unterstützung für hochwertige 2D\-Grafiken.  Zu den Funktionen zählen Pinsel, Geometrien, Bilder, Formen und Transformationen.  Weitere Informationen finden Sie unter [Grafiken](../../../../docs/framework/wpf/graphics-multimedia/graphics.md).  Das Rendering von visuellen Elementen basiert auf der <xref:System.Windows.Media.Visual>\-Klasse.  Die Struktur von visuellen Objekten auf dem Bildschirm wird durch die visuelle Struktur beschrieben.  Weitere Informationen finden Sie unter [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
### 2D\-Formen  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enthält eine Bibliothek häufig verwendeter vektorbasierter [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Formen wie Rechtecke und Ellipsen, die in der folgenden Abbildung dargestellt sind.  
  
 ![Ellipsen und Rechtecke](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.png "WPFIntroFigure4")  
  
 Diese systeminternen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Formen sind mehr als nur Formen: Es handelt sich um programmierbare Elemente, die viele der Features implementieren, die Sie von den gebräuchlichsten Steuerelementen erwarten, etwa Tastatur\- und Mauseingaben.  Im folgenden Beispiel wird gezeigt, wie das <xref:System.Windows.UIElement.MouseUp>\-Ereignis behandelt wird, das durch Klicken auf ein <xref:System.Windows.Shapes.Ellipse>\-Element ausgelöst wird.  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  x:Class="Window1" >  
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />  
</Window>  
```  
  
```csharp  
public partial class Window1  : Window  
{  
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)  
    {  
        MessageBox.Show("You clicked the ellipse!");  
    }  
}  
```  
  
```vb  
Partial Public Class Window1  
    Inherits Window  
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)  
        MessageBox.Show("You clicked the ellipse!")  
    End Sub  
End Class  
  
```  
  
 In der folgenden Abbildung wird die Ausgabe für das vorangehende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup und Code\-Behind dargestellt.  
  
 ![Ein Fenster mit dem Text "you clicked the ellipse&#33;"](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Weitere Informationen finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  Ein einführendes Beispiel finden Sie unter [Beispiel für Formelemente](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
### 2D\-Geometrien  
 Wenn die von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bereitgestellten [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Formen nicht ausreichen, können Sie mit der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Unterstützung für Geometrien und Pfade eigene Formen erstellen.  In der folgenden Abbildung wird verdeutlicht, wie Sie mit Geometrien Formen, etwa einen Zeichenpinsel, erstellen und andere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Elemente ausschneiden können.  
  
 ![Verschiedene Einsatzbereiche eines Pfades](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.png "WPFIntroFigure5")  
  
 Weitere Informationen finden Sie unter [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  Ein einführendes Beispiel finden Sie unter [Beispiele zu Geometrie](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
### 2D\-Effekte  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt eine Bibliothek von [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Klassen bereit, mit denen Sie eine Vielzahl von Effekten erstellen können.  Die [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Renderingfunktion von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die Möglichkeit, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente, die Farbverläufe, Bitmaps, Zeichnungen und Videos aufweisen, zu zeichnen und durch Drehen, Skalieren und [Neigen](GTMT) zu bearbeiten.  Die folgende Abbildung zeigt ein Beispiel für die vielen Effekte, die Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Pinseln erreichen können.  
  
 ![Darstellung unterschiedlicher Pinsel](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.png "WPFIntroFigure6")  
  
 Weitere Informationen finden Sie unter [Übersicht über WPF\-Pinsel](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  Ein einführendes Beispiel finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
<a name="rendering"></a>   
## 3D\-Rendering  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enthält eine Reihe von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Renderingfunktionen, die in der [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Grafikunterstützung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integriert sind, damit Sie Layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und Datenvisualisierung noch ansprechender gestalten können.  Mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können Sie sogar [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Bilder auf den Oberflächen von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Formen rendern, was in der folgenden Abbildung veranschaulicht wird.  
  
 ![Bildschirmabbildung für Visual3D&#45;Beispiel](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Weitere Informationen finden Sie unter [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  Ein einführendes Beispiel finden Sie unter [Beispiel zu 3D\-Festkörpern](http://go.microsoft.com/fwlink/?LinkID=159964).  
  
<a name="animation"></a>   
## Animation  
 Mit Animation können Sie Steuerelemente und Elemente wachsen, bewegen, drehen sowie ein\- und ausblenden lassen und z. B. interessante Seitenübergänge erzeugen.  Da Sie mit[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die meisten Eigenschaften animieren können, können Sie nicht nur die meisten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Objekte animieren, sondern Sie können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] auch verwenden, um benutzerdefinierte Objekte, die Sie erstellen, zu animieren.  
  
 ![Bilder eines animierten Cubes](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Ein einführendes Beispiel finden Sie unter [Beispielsammlung zu Animationen](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
<a name="media"></a>   
## Medien  
 Bilder, Video und Audio bieten eine umfangreiche Medienunterstützung, um Informationen zu vermitteln und für Benutzerfreundlichkeit zu sorgen.  
  
### Bilder  
 Bilder, dazu zählen Symbole, Hintergründe und sogar Teile von Animationen, sind ein Hauptbestandteil der meisten Anwendungen.  Da Sie häufig Bilder verwenden müssen, bietet [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die Möglichkeit, sie auf vielfältige Weise einzusetzen.  In der folgenden Abbildung wird lediglich eine der Möglichkeiten dargestellt.  
  
 ![Bildschirmabbildung für Formatierungsbeispiel](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro\_EventTriggers")  
  
 Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### Video und Audio  
 Ein Hauptfeature der Grafikfunktionen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] besteht in der systemeigenen Unterstützung für die Arbeit mit Multimedia, z. B. Video und Audio.  Das folgende Beispiel zeigt, wie ein Media Player in eine Anwendung eingefügt wird.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 Mit dem <xref:System.Windows.Controls.MediaElement> können Video und Audio wiedergegeben werden. Es lässt sich so erweitern, dass benutzerdefinierte [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] leicht erstellt werden können.  
  
 Weitere Informationen finden Sie unter [Übersicht über Multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Media3D>   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Animation and Timing](http://msdn.microsoft.com/de-de/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [3\-D Graphics](http://msdn.microsoft.com/de-de/565c1f3c-235b-47de-b05b-3b53ed63f1b8)   
 [Multimedia](http://msdn.microsoft.com/de-de/44a8dcd0-80cb-4db0-a222-87cde68c2fac)