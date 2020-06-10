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
ms.openlocfilehash: ecc54ad9453343f6306b0133fa180abd0db46f82
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596422"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="62431-102">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="62431-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="62431-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für Multimedia, Vektorgrafiken, Animation und Inhaltskomposition und erleichtert Entwicklern das Erstellen interessanter Benutzeroberflächen und Inhalte.</span><span class="sxs-lookup"><span data-stu-id="62431-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="62431-104">Mithilfe von Visual Studio können Sie Vektorgrafiken oder komplexe Animationen erstellen und Medien in Ihre Anwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="62431-104">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="62431-105">In diesem Thema werden die Grafik-, Animations- und Medienfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt, mit denen Sie den Anwendungen Grafiken, Übergangseffekte, Ton und Videos hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="62431-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="62431-106">Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="62431-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="62431-107">Wenn Sie versuchen, WPF-Typen in einem Windows-Dienst zu verwenden, funktioniert der Dienst möglicherweise nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="62431-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="62431-108">Neue Grafik. und Multimediafunktionen in WPF 4</span><span class="sxs-lookup"><span data-stu-id="62431-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="62431-109">Im Zusammenhang mit Grafiken und Animationen wurden mehrere Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="62431-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="62431-110">Layoutglättung</span><span class="sxs-lookup"><span data-stu-id="62431-110">Layout Rounding</span></span>

  <span data-ttu-id="62431-111">Wenn ein Objektrand in die Mitte eines Pixelgeräts fällt, kann das DPI-unabhängige Grafiksystem Renderingartefakte erstellen, z.B. verschwommene oder semitransparente Ränder.</span><span class="sxs-lookup"><span data-stu-id="62431-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="62431-112">Frühere Versionen der WPF haben die Pixelausrichtung für diese Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="62431-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="62431-113">Silverlight 2 hat die Layoutglättung eingeführt, die eine andere Möglichkeit bietet, um Elemente so zu verschieben, dass Ränder auf ganzen Pixelgrenzen liegen.</span><span class="sxs-lookup"><span data-stu-id="62431-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="62431-114">WPF unterstützt jetzt die Layoutrundung mit der <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> angefügten-Eigenschaft für <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="62431-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="62431-115">Zwischengespeicherte Komposition</span><span class="sxs-lookup"><span data-stu-id="62431-115">Cached Composition</span></span>

  <span data-ttu-id="62431-116">Mithilfe der neuen <xref:System.Windows.Media.BitmapCache> -Klasse und der- <xref:System.Windows.Media.BitmapCacheBrush> Klasse können Sie einen komplexen Teil der visuellen Struktur als Bitmap Zwischenspeichern und die Renderingzeit erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="62431-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="62431-117">Die Bitmap reagiert weiterhin auf Benutzereingaben wie Mausklicks, und Sie können sie wie jeden Pinsel auf anderen Elementen zeichnen.</span><span class="sxs-lookup"><span data-stu-id="62431-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="62431-118">Unterstützung von Pixel Shader 3</span><span class="sxs-lookup"><span data-stu-id="62431-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="62431-119">WPF 4 basiert auf der <xref:System.Windows.Media.Effects.ShaderEffect> Unterstützung, die in WPF 3,5 SP1 eingeführt wurde, indem Anwendungen das Schreiben von Effekten mithilfe von Pixel-Shader (PS) Version 3,0 ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="62431-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="62431-120">Das PS 3.0-Shadermodell ist ausgereifter als PS 2.0 und ermöglicht noch mehr Effekte auf unterstützter Hardware.</span><span class="sxs-lookup"><span data-stu-id="62431-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="62431-121">Beschleunigungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="62431-121">Easing Functions</span></span>

  <span data-ttu-id="62431-122">Sie können Animationen mit Beschleunigungsfunktionen verbessern, die Ihnen zusätzliche Kontrolle über das Verhalten von Animationen geben.</span><span class="sxs-lookup"><span data-stu-id="62431-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="62431-123">Beispielsweise können Sie eine <xref:System.Windows.Media.Animation.ElasticEase> auf eine Animation anwenden, um der Animation ein springisierungsverhalten zu geben.</span><span class="sxs-lookup"><span data-stu-id="62431-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="62431-124">Weitere Informationen finden Sie unter Beschleunigungs Typen im- <xref:System.Windows.Media.Animation> Namespace.</span><span class="sxs-lookup"><span data-stu-id="62431-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="62431-125">Grafiken und Rendering</span><span class="sxs-lookup"><span data-stu-id="62431-125">Graphics and Rendering</span></span>

<span data-ttu-id="62431-126">WPF bietet Unterstützung für qualitativ hochwertige 2D-Grafiken.</span><span class="sxs-lookup"><span data-stu-id="62431-126">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="62431-127">Die Funktionalität umfasst die Pinsel, Geometrien, Bilder, Formen und Transformationen.</span><span class="sxs-lookup"><span data-stu-id="62431-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="62431-128">Weitere Informationen finden Sie unter [Grafik](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="62431-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="62431-129">Das Rendering grafischer Elemente basiert auf der- <xref:System.Windows.Media.Visual> Klasse.</span><span class="sxs-lookup"><span data-stu-id="62431-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="62431-130">Die Struktur von visuellen Objekten auf dem Bildschirm wird durch die visuelle Struktur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62431-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="62431-131">Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="62431-132">2D-Formen</span><span class="sxs-lookup"><span data-stu-id="62431-132">2D Shapes</span></span>

<span data-ttu-id="62431-133">WPF stellt eine Bibliothek häufig verwendeter vektorbasierter 2D-Formen dar, wie z. b. Rechtecke und Ellipsen, die in der folgenden Abbildung gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="62431-133">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Das Diagramm zeigt Ellipsen und Rechtecke an.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="62431-135">Diese systeminternen WPF-Formen sind nicht nur Formen: Sie sind programmierbare Elemente, die viele der Features implementieren, die Sie von den gängigsten Steuerelementen erwarten, einschließlich Tastatur-und Maus Eingaben.</span><span class="sxs-lookup"><span data-stu-id="62431-135">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="62431-136">Das folgende Beispiel zeigt, wie das- <xref:System.Windows.UIElement.MouseUp> Ereignis behandelt wird, das durch Klicken auf ein-Element ausgelöst wird <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="62431-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

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

<span data-ttu-id="62431-137">Die folgende Abbildung zeigt die Ausgabe für das vorangehende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup und CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="62431-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Ein Meldungs Feld, das besagt, dass Sie auf die Ellipse geklickt haben! "](./media/index/messagebox-text-output.png)

<span data-ttu-id="62431-139">Weitere Informationen finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="62431-140">Ein einführendes Beispiel finden Sie unter [Beispiel für Formelemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="62431-140">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="62431-141">2D-Geometrien</span><span class="sxs-lookup"><span data-stu-id="62431-141">2D Geometries</span></span>

<span data-ttu-id="62431-142">Wenn die von WPF bereitgestellten 2D-Formen nicht ausreichen, können Sie die WPF-Unterstützung für Geometrien und Pfade verwenden, um Ihre eigenen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62431-142">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="62431-143">In der folgenden Abbildung wird veranschaulicht, wie Geometrien verwendet werden können, um Formen, als Zeichnungs Pinsel und andere WPF-Elemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62431-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![Screenshot, der zeigt, wie Geometrien verwendet werden können, um Formen zu erstellen.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="62431-145">Weitere Informationen finden Sie unter [Übersicht über die Geometrie](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="62431-146">Ein einführendes Beispiel finden Sie unter [Beispiele zu Geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="62431-146">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="62431-147">2D-Effekte</span><span class="sxs-lookup"><span data-stu-id="62431-147">2D Effects</span></span>

<span data-ttu-id="62431-148">WPF stellt eine Bibliothek von 2D-Klassen bereit, die Sie verwenden können, um eine Vielzahl von Effekten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62431-148">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="62431-149">Die 2D-Renderingfunktion von WPF bietet die Möglichkeit, Elemente mit Farb [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Verläufen, Bitmaps, Zeichnungen und Videos zu zeichnen und diese mithilfe von Drehung, Skalierung und Neigung zu manipulieren.</span><span class="sxs-lookup"><span data-stu-id="62431-149">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="62431-150">Die folgende Abbildung zeigt ein Beispiel für die zahlreichen Effekte, die Sie durch die Verwendung von WPF-Pinseln erreichen können.</span><span class="sxs-lookup"><span data-stu-id="62431-150">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![Die Abbildung zeigt die verschiedenen WPF-Pinsel und-Elemente.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="62431-152">Weitere Informationen finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="62431-153">Ein einführendes Beispiel finden Sie unter [Pinselbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="62431-153">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="62431-154">3D-Rendering</span><span class="sxs-lookup"><span data-stu-id="62431-154">3D Rendering</span></span>

<span data-ttu-id="62431-155">WPF bietet eine Reihe von 3D-Renderingfunktionen, die mit der Unterstützung von 2D-Grafiken in WPF integriert werden, damit Sie eine genauere Darstellung von Layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Daten und Datenvisualisierung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="62431-155">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="62431-156">An einem Ende des Spektrums können Sie mithilfe von WPF 2D-Bilder auf den Oberflächen von 3D-Formen darstellen, die in der folgenden Abbildung veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="62431-156">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![Screenshot eines Beispiels, das 3D-Formen mit unterschiedlichen Texturen anzeigt.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="62431-158">Weitere Informationen finden Sie unter [Übersicht über 3D-Grafiken](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-158">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="62431-159">Ein Einführ Endes Beispiel finden Sie unter [Beispiel für 3D-](https://go.microsoft.com/fwlink/?LinkID=159964)Daten.</span><span class="sxs-lookup"><span data-stu-id="62431-159">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="62431-160">Animation</span><span class="sxs-lookup"><span data-stu-id="62431-160">Animation</span></span>

<span data-ttu-id="62431-161">Mit Animation können Sie Steuerelemente und Elemente wachsen, bewegen, drehen sowie ein- und ausblenden lassen und z.B. interessante Seitenübergänge erzeugen.</span><span class="sxs-lookup"><span data-stu-id="62431-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="62431-162">Da WPF Ihnen ermöglicht, die meisten Eigenschaften zu animieren, können Sie nicht nur die meisten WPF-Objekte animieren, sondern auch WPF verwenden, um von Ihnen erstellte benutzerdefinierte Objekte zu animieren.</span><span class="sxs-lookup"><span data-stu-id="62431-162">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![Screenshot eines animierten Cubes.](./media/index/animate-custom-objects.png)

<span data-ttu-id="62431-164">Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="62431-165">Ein einführendes Beispiel finden Sie unter [Beispielsammlung zu Animationen](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="62431-165">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="62431-166">Medien</span><span class="sxs-lookup"><span data-stu-id="62431-166">Media</span></span>

<span data-ttu-id="62431-167">Bilder, Videos und Audiodateien bieten eine umfangreiche Medienunterstützung, um Informationen zu vermitteln und für Benutzerfreundlichkeit zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="62431-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="62431-168">Bilder</span><span class="sxs-lookup"><span data-stu-id="62431-168">Images</span></span>

<span data-ttu-id="62431-169">Bilder, z.B. Symbole, Hintergründe und sogar Teile von Animationen, sind ein wesentlicher Bestandteil der meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="62431-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="62431-170">Da Sie häufig Images verwenden müssen, bietet WPF eine Vielzahl von Möglichkeiten, um mit Ihnen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="62431-170">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="62431-171">In der folgenden Abbildung wird lediglich eine der Möglichkeiten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="62431-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="62431-172">![Screenshot: Stilbeispiel](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="62431-172">![Styling sample screenshot](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="62431-173">Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="62431-174">Video und Audio</span><span class="sxs-lookup"><span data-stu-id="62431-174">Video and Audio</span></span>

<span data-ttu-id="62431-175">Ein zentrales Feature der Grafikfunktionen von WPF besteht darin, systemeigene Unterstützung für die Arbeit mit Multimedia zu bieten, die Video-und Audiodaten umfasst.</span><span class="sxs-lookup"><span data-stu-id="62431-175">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="62431-176">Im folgenden Beispiel wird veranschaulicht, wie einen MediaPlayer in eine Anwendung eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="62431-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="62431-177"><xref:System.Windows.Controls.MediaElement>kann sowohl Video als auch Audiodaten abspielen und ist erweiterbar, um die einfache Erstellung benutzerdefinierter Benutzeroberflächen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="62431-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="62431-178">Weitere Informationen finden Sie unter [Übersicht über Multimedia](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62431-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="62431-179">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62431-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="62431-180">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="62431-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="62431-181">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="62431-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="62431-182">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="62431-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="62431-183">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="62431-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="62431-184">Gewusst-wie-Themen zu Animation und Zeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="62431-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="62431-185">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="62431-185">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="62431-186">Übersicht über Multimedia</span><span class="sxs-lookup"><span data-stu-id="62431-186">Multimedia Overview</span></span>](multimedia-overview.md)
