---
title: Grafiken und Multimedia
ms.date: 03/30/2017
dev_langs:
  - csharp
  - vb
helpviewer_keywords:
  - 'media [WPF], features'
  - 'video effects [WPF]'
  - 'sound effects [WPF]'
  - 'animation [WPF], features'
  - 'graphics features [WPF]'
  - 'transition effects [WPF]'
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
---
# <a name="graphics-and-multimedia"></a>Grafiken und Multimedia
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für Multimedia, Vektorgrafiken, Animation und Inhaltskomposition, erleichtert Entwicklern das Erstellen interessanter Benutzeroberflächen und Inhalte. Mithilfe von [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] können Sie Vektorgrafiken oder komplexe Animationen erstellen und Medien in Ihre Anwendung integrieren.  
  
 In diesem Thema werden die Grafik-, Animations- und Medienfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt, mit denen Sie den Anwendungen Grafiken, Übergangseffekte, Ton und Videos hinzufügen können.  
  
> [!NOTE]
>  Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden. Wenn Sie versuchen, WPF-Typen in einem Windows-Dienst zu verwenden, funktioniert der Dienst möglicherweise nicht wie erwartet.   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Neue Grafik. und Multimediafunktionen in WPF 4  
 Im Zusammenhang mit Grafiken und Animationen wurden mehrere Änderungen vorgenommen.  
  
-   Layoutglättung  
  
     Wenn ein Objektrand in die Mitte eines Pixelgeräts fällt, kann das DPI-unabhängige Grafiksystem Renderingartefakte erstellen, z.B. verschwommene oder semitransparente Ränder. Frühere Versionen der WPF haben die Pixelausrichtung für diese Fälle verwendet. Silverlight 2 hat die Layoutglättung eingeführt, die eine andere Möglichkeit bietet, um Elemente so zu verschieben, dass Ränder auf ganzen Pixelgrenzen liegen. WPF unterstützt jetzt die layoutglättung mit der <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> angefügte Eigenschaft auf <xref:System.Windows.FrameworkElement>.  
  
-   Zwischengespeicherte Komposition  
  
     Mit dem neuen <xref:System.Windows.Media.BitmapCache> und <xref:System.Windows.Media.BitmapCacheBrush> Klassen, können Sie einen komplexen Teil der visuellen Struktur als Bitmap Zwischenspeichern und Renderingzeit dadurch erheblich optimieren. Die Bitmap reagiert weiterhin auf Benutzereingaben wie Mausklicks, und Sie können sie wie jeden Pinsel auf anderen Elementen zeichnen.  
  
-   Unterstützung von Pixel Shader 3  
  
     WPF 4 basiert auf der die <xref:System.Windows.Media.Effects.ShaderEffect> Unterstützung in WPF 3.5 SP1 eingeführt werden, indem ermöglicht es Anwendungen, Effekte mit Pixel Shader (PS) Version 3.0 zu schreiben. Das PS 3.0-Shadermodell ist ausgereifter als PS 2.0 und ermöglicht noch mehr Effekte auf unterstützter Hardware.  
  
-   Beschleunigungsfunktionen  
  
     Sie können Animationen mit Beschleunigungsfunktionen verbessern, die Ihnen zusätzliche Kontrolle über das Verhalten von Animationen geben. Sie können z. B. Anwenden einer <xref:System.Windows.Media.Animation.ElasticEase> für eine Animation, der Animation ein Federverhalten zuzuweisen. Weitere Informationen finden Sie unter den Beschleunigungstypen im der <xref:System.Windows.Media.Animation> Namespace.  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a>Grafiken und Rendering  
 WPF unterstützt hochwertige 2D-Grafiken. Die Funktionalität umfasst die Pinsel, Geometrien, Bilder, Formen und Transformationen. Weitere Informationen finden Sie unter [Grafik](../../../../docs/framework/wpf/graphics-multimedia/graphics.md). Das Rendering von visuellen Elementen basiert auf der <xref:System.Windows.Media.Visual> Klasse. Die Struktur von visuellen Objekten auf dem Bildschirm wird durch die visuelle Struktur beschrieben. Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
### <a name="2-d-shapes"></a>2D-Formen  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enthält eine Bibliothek häufig verwendeter vektorbasierter [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Formen wie Rechtecke und Ellipsen, die in der folgenden Abbildung dargestellt sind.  
  
 ![Ellipsen und Rechtecke](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.PNG "WPFIntroFigure4")  
  
 Diese systeminternen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Formen sind mehr als nur Formen: Es handelt sich um programmierbare Elemente, die viele der Features implementieren, die Sie von den gebräuchlichsten Steuerelementen erwarten, etwa Tastatur- und Mauseingaben. Das folgende Beispiel zeigt, wie Sie behandelt die <xref:System.Windows.UIElement.MouseUp> Ereignis ausgelöst wird, indem Sie auf eine <xref:System.Windows.Shapes.Ellipse> Element.  
  
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
  
 Die folgende Abbildung zeigt die Ausgabe für das vorangehende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup und CodeBehind.  
  
 ![Ein Fenster mit dem Text „you clicked the ellipse&#33;“](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Weitere Informationen finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiel für Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
### <a name="2-d-geometries"></a>2D-Geometrien  
 Wenn die [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Formen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] nicht ausreichen, können Sie mit der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Unterstützung für Geometrien und Pfade eigene Formen erstellen. Die folgende Abbildung zeigt, wie Sie Geometrien nutzen können, um Formen zu erstellen, wie etwa einen Zeichenpinsel, und andere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elemente ausschneiden zu können.  
  
 ![Verschiedene Einsatzbereiche eines Pfads](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.PNG "WPFIntroFigure5")  
  
 Weitere Informationen finden Sie unter [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
### <a name="2-d-effects"></a>2D-Effekte  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt eine Bibliothek mit [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Klassen zur Verfügung, mit denen Sie verschiedene Effekte erstellen können. Die [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Renderingfunktion von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die Möglichkeit, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente mit Farbverläufen, Bitmaps, Zeichnungen und Videos zu zeichnen, und diese durch Drehung, Skalierung und Neigung zu bearbeiten. Die folgende Abbildung zeigt ein Beispiel für die vielen Effekte, die Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Pinsels erreichen können.  
  
 ![Darstellung unterschiedlicher Pinsel](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.PNG "WPFIntroFigure6")  
  
 Weitere Informationen finden Sie unter [Übersicht über WPF-Pinsel](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md). Ein einführendes Beispiel finden Sie unter [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a>3D-Rendering  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet eine Reihe von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Renderingfunktionen, die in der [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Grafikunterstützung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integriert sind, damit Sie Layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und Datenvisualisierung noch ansprechender gestalten können. Mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können Sie sogar [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Bilder auf den Oberflächen von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Formen rendern, was die folgende Abbildung veranschaulicht.  
  
 ![Visual3D-Beispielscreenshot](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Weitere Informationen finden Sie unter [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiel zu 3D-Festkörpern](https://go.microsoft.com/fwlink/?LinkID=159964).  
  
<a name="animation"></a>   
## <a name="animation"></a>Animation  
 Mit Animation können Sie Steuerelemente und Elemente wachsen, bewegen, drehen sowie ein- und ausblenden lassen und z.B. interessante Seitenübergänge erzeugen. Da Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die meisten Eigenschaften animieren können, können Sie nicht nur die meisten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Objekte animieren, sondern Sie können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] auch verwenden, um benutzerdefinierte Objekte, die Sie erstellen, zu animieren.  
  
 ![Bilder eines animierten Würfels](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Ein einführendes Beispiel finden Sie unter [Beispielsammlung zu Animationen](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
<a name="media"></a>   
## <a name="media"></a>Medien  
 Bilder, Videos und Audiodateien bieten eine umfangreiche Medienunterstützung, um Informationen zu vermitteln und für Benutzerfreundlichkeit zu sorgen.  
  
### <a name="images"></a>Bilder  
 Bilder, z.B. Symbole, Hintergründe und sogar Teile von Animationen, sind ein wesentlicher Bestandteil der meisten Anwendungen. Da Sie häufig Bilder verwenden müssen, bietet [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die Möglichkeit, sie auf vielfältige Weise einzusetzen. In der folgenden Abbildung wird lediglich eine der Möglichkeiten dargestellt.  
  
 ![Bildschirmabbildung für Formatierungsbeispiel](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
 Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### <a name="video-and-audio"></a>Video und Audio  
 Ein Hauptfeature der Grafikfunktionen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] besteht in der nativen Unterstützung für die Arbeit mit Multimedia, z.B. Video und Audio. Im folgenden Beispiel wird veranschaulicht, wie einen MediaPlayer in eine Anwendung eingefügt wird.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement> kann sowohl video als auch audio wiedergegeben, und ist erweiterbar genug, um die einfache Erstellung von benutzerdefinierten ermöglichen [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].  
  
 Weitere Informationen finden Sie unter [Übersicht über Multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Animations- und Zeitsteuerungssystem](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [3D-Grafiken](https://msdn.microsoft.com/library/565c1f3c-235b-47de-b05b-3b53ed63f1b8)
- [Multimedia](https://msdn.microsoft.com/library/44a8dcd0-80cb-4db0-a222-87cde68c2fac)
