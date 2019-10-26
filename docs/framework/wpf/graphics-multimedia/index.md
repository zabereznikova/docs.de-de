---
title: Grafiken und Multimedia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: 150b742c2195c07abf2b2823871627b0ba827580
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919994"
---
# <a name="graphics-and-multimedia"></a>Grafiken und Multimedia

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für Multimedia, Vektorgrafiken, Animationen und Inhalts Komposition, sodass Entwickler auf einfache Weise interessante Benutzeroberflächen und Inhalte erstellen können. Mithilfe von Visual Studio können Sie Vektorgrafiken oder komplexe Animationen erstellen und Medien in Ihre Anwendungen integrieren.

In diesem Thema werden die Grafik-, Animations- und Medienfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt, mit denen Sie den Anwendungen Grafiken, Übergangseffekte, Ton und Videos hinzufügen können.

> [!NOTE]
> Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden. Wenn Sie versuchen, WPF-Typen in einem Windows-Dienst zu verwenden, funktioniert der Dienst möglicherweise nicht wie erwartet.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Neue Grafik. und Multimediafunktionen in WPF 4

Im Zusammenhang mit Grafiken und Animationen wurden mehrere Änderungen vorgenommen.

- Layoutglättung

  Wenn ein Objektrand in die Mitte eines Pixelgeräts fällt, kann das DPI-unabhängige Grafiksystem Renderingartefakte erstellen, z.B. verschwommene oder semitransparente Ränder. Frühere Versionen der WPF haben die Pixelausrichtung für diese Fälle verwendet. Silverlight 2 hat die Layoutglättung eingeführt, die eine andere Möglichkeit bietet, um Elemente so zu verschieben, dass Ränder auf ganzen Pixelgrenzen liegen. WPF unterstützt jetzt die Layoutrundung mit der <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> angefügten Eigenschaft auf <xref:System.Windows.FrameworkElement>.

- Zwischengespeicherte Komposition

  Mithilfe der neuen Klassen <xref:System.Windows.Media.BitmapCache> und <xref:System.Windows.Media.BitmapCacheBrush> können Sie einen komplexen Teil der visuellen Struktur als Bitmap Zwischenspeichern und die Renderingzeit erheblich verbessern. Die Bitmap reagiert weiterhin auf Benutzereingaben wie Mausklicks, und Sie können sie wie jeden Pinsel auf anderen Elementen zeichnen.

- Unterstützung von Pixel Shader 3

  WPF 4 basiert auf der <xref:System.Windows.Media.Effects.ShaderEffect> Unterstützung, die in WPF 3,5 SP1 eingeführt wurde, indem Anwendungen das Schreiben von Effekten mithilfe von Pixel-Shader (PS) Version 3,0 ermöglichen. Das PS 3.0-Shadermodell ist ausgereifter als PS 2.0 und ermöglicht noch mehr Effekte auf unterstützter Hardware.

- Beschleunigungsfunktionen

  Sie können Animationen mit Beschleunigungsfunktionen verbessern, die Ihnen zusätzliche Kontrolle über das Verhalten von Animationen geben. Beispielsweise können Sie eine <xref:System.Windows.Media.Animation.ElasticEase> auf eine Animation anwenden, um der Animation ein springisierungsverhalten zu geben. Weitere Informationen finden Sie unter Beschleunigungs Typen im <xref:System.Windows.Media.Animation>-Namespace.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Grafiken und Rendering

WPF unterstützt hochwertige 2D-Grafiken. Die Funktionalität umfasst die Pinsel, Geometrien, Bilder, Formen und Transformationen. Weitere Informationen finden Sie unter [Grafik](graphics.md). Das Rendering grafischer Elemente basiert auf der <xref:System.Windows.Media.Visual>-Klasse. Die Struktur von visuellen Objekten auf dem Bildschirm wird durch die visuelle Struktur beschrieben. Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md).

### <a name="2-d-shapes"></a>2D-Formen

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt eine Bibliothek häufig verwendeter vektorbasierter 2D-Formen bereit, wie z. b. Rechtecke und Ellipsen, die in der folgenden Abbildung dargestellt sind.

![Das Diagramm zeigt Ellipsen und Rechtecke an.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Diese systeminternen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Formen sind mehr als nur Formen: Es handelt sich um programmierbare Elemente, die viele der Features implementieren, die Sie von den gebräuchlichsten Steuerelementen erwarten, etwa Tastatur- und Mauseingaben. Im folgenden Beispiel wird gezeigt, wie das <xref:System.Windows.UIElement.MouseUp> Ereignis behandelt wird, das durch Klicken auf ein <xref:System.Windows.Shapes.Ellipse>-Element ausgelöst wird.

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

![Ein Meldungs Feld, das besagt, dass Sie auf die Ellipse geklickt haben! "](./media/index/messagebox-text-output.png)

Weitere Informationen finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiel für Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).

### <a name="2-d-geometries"></a>2D-Geometrien

Wenn die von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bereitgestellten 2D-Formen nicht ausreichen, können Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Unterstützung für Geometrien und Pfade verwenden, um Ihre eigenen zu erstellen. Die folgende Abbildung zeigt, wie Sie Geometrien nutzen können, um Formen zu erstellen, wie etwa einen Zeichenpinsel, und andere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elemente ausschneiden zu können.

![Screenshot, der zeigt, wie Geometrien verwendet werden können, um Formen zu erstellen.](./media/index/use-geometries-create-shapes.png)

Weitere Informationen finden Sie unter [Übersicht über die Geometrie](geometry-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).

### <a name="2-d-effects"></a>2D-Effekte

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt eine Bibliothek mit 2D-Klassen bereit, die Sie verwenden können, um eine Vielzahl von Effekten zu erstellen. Die 2D-Renderingfunktion von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die Möglichkeit, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente zu zeichnen, die Farbverläufe, Bitmaps, Zeichnungen und Videos enthalten. und um diese mithilfe von Drehung, Skalierung und Neigung zu manipulieren. Die folgende Abbildung zeigt ein Beispiel für die vielen Effekte, die Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Pinsels erreichen können.

![Die Abbildung zeigt die verschiedenen WPF-Pinsel und-Elemente.](./media/index/brushes-paint-elements.png)

Weitere Informationen finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md). Ein einführendes Beispiel finden Sie unter [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).

<a name="rendering"></a>

## <a name="3-d-rendering"></a>3D-Rendering

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet eine Reihe von 3D-Renderingfunktionen, die mit der Unterstützung von 2D-Grafiken in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integriert sind, damit Sie eine genauere Darstellung von Layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]und Daten erstellen können. An einem Ende des Spektrums können Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 2D-Bilder auf den Oberflächen von 3D-Formen darstellen, die in der folgenden Abbildung veranschaulicht werden.

![Screenshot eines Beispiels, das 3D-Formen mit unterschiedlichen Texturen anzeigt.](./media/index/visual-three-dimensional-shape.png)

Weitere Informationen finden Sie unter [Übersicht über 3D-Grafiken](3-d-graphics-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiel zu 3D-Festkörpern](https://go.microsoft.com/fwlink/?LinkID=159964).

<a name="animation"></a>

## <a name="animation"></a>Animation

Mit Animation können Sie Steuerelemente und Elemente wachsen, bewegen, drehen sowie ein- und ausblenden lassen und z.B. interessante Seitenübergänge erzeugen. Da Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die meisten Eigenschaften animieren können, können Sie nicht nur die meisten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Objekte animieren, sondern Sie können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] auch verwenden, um benutzerdefinierte Objekte, die Sie erstellen, zu animieren.

![Screenshot eines animierten Cubes.](./media/index/animate-custom-objects.png)

Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md). Ein einführendes Beispiel finden Sie unter [Beispielsammlung zu Animationen](https://go.microsoft.com/fwlink/?LinkID=159969).

<a name="media"></a>

## <a name="media"></a>Medien

Bilder, Videos und Audiodateien bieten eine umfangreiche Medienunterstützung, um Informationen zu vermitteln und für Benutzerfreundlichkeit zu sorgen.

### <a name="images"></a>Bilder

Bilder, z.B. Symbole, Hintergründe und sogar Teile von Animationen, sind ein wesentlicher Bestandteil der meisten Anwendungen. Da Sie häufig Bilder verwenden müssen, bietet [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die Möglichkeit, sie auf vielfältige Weise einzusetzen. In der folgenden Abbildung wird lediglich eine der Möglichkeiten dargestellt.

![Screenshot des Beispiel Formats](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](imaging-overview.md).

### <a name="video-and-audio"></a>Video und Audio

Ein Hauptfeature der Grafikfunktionen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] besteht in der nativen Unterstützung für die Arbeit mit Multimedia, z.B. Video und Audio. Im folgenden Beispiel wird veranschaulicht, wie einen MediaPlayer in eine Anwendung eingefügt wird.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement> kann sowohl Video-als auch Audiodaten abspielen und ist erweiterbar genug, um die einfache Erstellung benutzerdefinierter Benutzeroberflächen zu ermöglichen.

Weitere Informationen finden Sie unter [Übersicht über Multimedia](multimedia-overview.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Gewusst-wie-Themen zu Animation und zeitliche Steuerung](animation-and-timing-how-to-topics.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
- [Übersicht über Multimedia](multimedia-overview.md)
