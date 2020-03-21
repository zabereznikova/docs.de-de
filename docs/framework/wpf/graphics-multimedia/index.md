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
ms.openlocfilehash: 8636afcc5b63b71dc729812a7f3eb4945ba49494
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112036"
---
# <a name="graphics-and-multimedia"></a>Grafiken und Multimedia

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für Multimedia, Vektorgrafiken, Animation und Inhaltskomposition und erleichtert Entwicklern das Erstellen interessanter Benutzeroberflächen und Inhalte. Mit Visual Studio können Sie Vektorgrafiken oder komplexe Animationen erstellen und Medien in Ihre Anwendungen integrieren.

In diesem Thema werden die Grafik-, Animations- und Medienfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt, mit denen Sie den Anwendungen Grafiken, Übergangseffekte, Ton und Videos hinzufügen können.

> [!NOTE]
> Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden. Wenn Sie versuchen, WPF-Typen in einem Windows-Dienst zu verwenden, funktioniert der Dienst möglicherweise nicht wie erwartet.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Neue Grafik. und Multimediafunktionen in WPF 4

Im Zusammenhang mit Grafiken und Animationen wurden mehrere Änderungen vorgenommen.

- Layoutglättung

  Wenn ein Objektrand in die Mitte eines Pixelgeräts fällt, kann das DPI-unabhängige Grafiksystem Renderingartefakte erstellen, z.B. verschwommene oder semitransparente Ränder. Frühere Versionen der WPF haben die Pixelausrichtung für diese Fälle verwendet. Silverlight 2 hat die Layoutglättung eingeführt, die eine andere Möglichkeit bietet, um Elemente so zu verschieben, dass Ränder auf ganzen Pixelgrenzen liegen. WPF unterstützt jetzt die <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> Layoutrundung <xref:System.Windows.FrameworkElement>mit der angefügten Eigenschaft auf .

- Zwischengespeicherte Komposition

  Mithilfe der <xref:System.Windows.Media.BitmapCache> neuen <xref:System.Windows.Media.BitmapCacheBrush> Undklassen können Sie einen komplexen Teil der visuellen Struktur als Bitmap zwischenspeichern und die Renderzeit erheblich verbessern. Die Bitmap reagiert weiterhin auf Benutzereingaben wie Mausklicks, und Sie können sie wie jeden Pinsel auf anderen Elementen zeichnen.

- Unterstützung von Pixel Shader 3

  WPF 4 baut auf <xref:System.Windows.Media.Effects.ShaderEffect> der in WPF 3.5 SP1 eingeführten Unterstützung auf, indem Anwendungen effekte mithilfe von Pixel Shader (PS) Version 3.0 schreiben können. Das PS 3.0-Shadermodell ist ausgereifter als PS 2.0 und ermöglicht noch mehr Effekte auf unterstützter Hardware.

- Beschleunigungsfunktionen

  Sie können Animationen mit Beschleunigungsfunktionen verbessern, die Ihnen zusätzliche Kontrolle über das Verhalten von Animationen geben. Sie können z. <xref:System.Windows.Media.Animation.ElasticEase> B. eine auf eine Animation anwenden, um der Animation ein frühlingshaftes Verhalten zu verleihen. Weitere Informationen finden Sie unter <xref:System.Windows.Media.Animation> die Beschleunigungstypen im Namespace.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Grafiken und Rendering

WPF unterstützt hochwertige 2D-Grafiken. Die Funktionalität umfasst die Pinsel, Geometrien, Bilder, Formen und Transformationen. Weitere Informationen finden Sie unter [Grafik](graphics.md). Das Rendern von grafischen <xref:System.Windows.Media.Visual> Elementen basiert auf der Klasse. Die Struktur von visuellen Objekten auf dem Bildschirm wird durch die visuelle Struktur beschrieben. Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](wpf-graphics-rendering-overview.md).

### <a name="2d-shapes"></a>2D-Shapes

WPF bietet eine Bibliothek mit häufig verwendeten, vektorgezeichneten 2D-Shapes, z. B. Rechtecken und Ellipsen, die in der folgenden Abbildung gezeigt werden.

![Diagramm mit Ellipsen und Rechtecken.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Diese intrinsischen WPF-Shapes sind nicht nur Shapes: Sie sind programmierbare Elemente, die viele der Features implementieren, die Sie von den gängigsten Steuerelementen erwarten, einschließlich Tastatur- und Mauseingabe. Das folgende Beispiel zeigt, <xref:System.Windows.UIElement.MouseUp> wie das ausgelöste Ereignis behandelt wird, indem Sie auf ein <xref:System.Windows.Shapes.Ellipse> Element klicken.

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

![Ein Meldungsfeld mit der Aufschrift "Du hast auf die Ellipse geklickt!"](./media/index/messagebox-text-output.png)

Weitere Informationen finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiel für Formelemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).

### <a name="2d-geometries"></a>2D-Geometrien

Wenn die von WPF zur Verfügung gestellten 2D-Shapes nicht ausreichen, können Sie die WPF-Unterstützung für Geometrien und Pfade verwenden, um eigene zu erstellen. Die folgende Abbildung zeigt, wie Sie Geometrien verwenden können, um Formen als Zeichnungspinsel zu erstellen und andere WPF-Elemente zu beschneiden.

![Screenshot, der zeigt, wie Sie Geometrien zum Erstellen von Shapes verwenden können.](./media/index/use-geometries-create-shapes.png)

Weitere Informationen finden Sie unter [Übersicht über die Geometrie](geometry-overview.md). Ein einführendes Beispiel finden Sie unter [Beispiele zu Geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).

### <a name="2d-effects"></a>2D-Effekte

WPF stellt eine Bibliothek mit 2D-Klassen bereit, mit der Sie eine Vielzahl von Effekten erstellen können. Die 2D-Renderingfunktion von WPF [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] bietet die Möglichkeit, Elemente mit Farbverläufen, Bitmaps, Zeichnungen und Videos zu zeichnen. und sie mithilfe von Rotation, Skalierung und Schiefe zu manipulieren. Die folgende Abbildung zeigt ein Beispiel für die vielen Effekte, die Sie mit WPF-Pinsel erzielen können.

![Abbildung mit den verschiedenen WPF-Pinseln und Farbelementen.](./media/index/brushes-paint-elements.png)

Weitere Informationen finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md). Ein einführendes Beispiel finden Sie unter [Pinselbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).

<a name="rendering"></a>

## <a name="3d-rendering"></a>3D-Rendering

WPF bietet eine Reihe von 3D-Rendering-Funktionen, die in die 2D-Grafikunterstützung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]in WPF integriert werden, damit Sie spannendere Layout-, - und Datenvisualisierung erstellen können. An einem Ende des Spektrums können Sie mit WPF 2D-Bilder auf den Oberflächen von 3D-Shapes rendern, was in der folgenden Abbildung veranschaulicht wird.

![Screenshot eines Beispiels mit 3D-Shapes mit unterschiedlichen Texturen.](./media/index/visual-three-dimensional-shape.png)

Weitere Informationen finden Sie unter [Übersicht über 3D-Grafiken](3-d-graphics-overview.md). Ein Einführungsbeispiel finden Sie unter [3D-Volumenkörperbeispiel](https://go.microsoft.com/fwlink/?LinkID=159964).

<a name="animation"></a>

## <a name="animation"></a>Animation

Mit Animation können Sie Steuerelemente und Elemente wachsen, bewegen, drehen sowie ein- und ausblenden lassen und z.B. interessante Seitenübergänge erzeugen. Da WPF es Ihnen ermöglicht, die meisten Eigenschaften zu animieren, können Sie nicht nur die meisten WPF-Objekte animieren, sondern auch WPF verwenden, um benutzerdefinierte Objekte zu animieren, die Sie erstellen.

![Screenshot eines animierten Cubes.](./media/index/animate-custom-objects.png)

Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md). Ein einführendes Beispiel finden Sie unter [Beispielsammlung zu Animationen](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).

<a name="media"></a>

## <a name="media"></a>Medien

Bilder, Videos und Audiodateien bieten eine umfangreiche Medienunterstützung, um Informationen zu vermitteln und für Benutzerfreundlichkeit zu sorgen.

### <a name="images"></a>Bilder

Bilder, z.B. Symbole, Hintergründe und sogar Teile von Animationen, sind ein wesentlicher Bestandteil der meisten Anwendungen. Da Sie häufig Bilder verwenden müssen, stellt WPF die Möglichkeit zur Verfügung, auf verschiedene Weise mit ihnen zu arbeiten. In der folgenden Abbildung wird lediglich eine der Möglichkeiten dargestellt.

![Styling-Beispiel-Screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](imaging-overview.md).

### <a name="video-and-audio"></a>Video und Audio

Ein Kernmerkmal der Grafikfunktionen von WPF ist die native Unterstützung für die Arbeit mit Multimedia, einschließlich Video und Audio. Im folgenden Beispiel wird veranschaulicht, wie einen MediaPlayer in eine Anwendung eingefügt wird.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>ist in der Lage, sowohl Video als auch Audio abzuspielen, und ist erweiterbar genug, um die einfache Erstellung von benutzerdefinierten Benutzerandis zu ermöglichen.

Weitere Informationen finden Sie unter [Übersicht über Multimedia](multimedia-overview.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Gewusst-wie-Themen zu Animation und Zeitsteuerung](animation-and-timing-how-to-topics.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Übersicht über Multimedia](multimedia-overview.md)
