---
title: Grafiken und Multimedia
description: Entdecken Sie die Medien Features von Windows Presentation Foundation (WPF). Fügen Sie Ihren Anwendungen Grafiken, Übergangseffekte, Sound und Video hinzu.
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
ms.openlocfilehash: ba52e78564484f7714ab0035a5e1861766b72bbf
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853685"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="b914d-104">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="b914d-104">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="b914d-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für Multimedia, Vektorgrafiken, Animation und Inhaltskomposition und erleichtert Entwicklern das Erstellen interessanter Benutzeroberflächen und Inhalte.</span><span class="sxs-lookup"><span data-stu-id="b914d-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="b914d-106">Mithilfe von Visual Studio können Sie Vektorgrafiken oder komplexe Animationen erstellen und Medien in Ihre Anwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="b914d-106">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="b914d-107">In diesem Thema werden die Grafik-, Animations- und Medienfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt, mit denen Sie den Anwendungen Grafiken, Übergangseffekte, Ton und Videos hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="b914d-107">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="b914d-108">Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b914d-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="b914d-109">Wenn Sie versuchen, WPF-Typen in einem Windows-Dienst zu verwenden, funktioniert der Dienst möglicherweise nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="b914d-109">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="b914d-110">Neue Grafik. und Multimediafunktionen in WPF 4</span><span class="sxs-lookup"><span data-stu-id="b914d-110">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="b914d-111">Im Zusammenhang mit Grafiken und Animationen wurden mehrere Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="b914d-111">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="b914d-112">Layoutglättung</span><span class="sxs-lookup"><span data-stu-id="b914d-112">Layout Rounding</span></span>

  <span data-ttu-id="b914d-113">Wenn ein Objektrand in die Mitte eines Pixelgeräts fällt, kann das DPI-unabhängige Grafiksystem Renderingartefakte erstellen, z.B. verschwommene oder semitransparente Ränder.</span><span class="sxs-lookup"><span data-stu-id="b914d-113">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="b914d-114">Frühere Versionen der WPF haben die Pixelausrichtung für diese Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="b914d-114">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="b914d-115">Silverlight 2 hat die Layoutglättung eingeführt, die eine andere Möglichkeit bietet, um Elemente so zu verschieben, dass Ränder auf ganzen Pixelgrenzen liegen.</span><span class="sxs-lookup"><span data-stu-id="b914d-115">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="b914d-116">WPF unterstützt jetzt die Layoutrundung mit der <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> angefügten-Eigenschaft für <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="b914d-116">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="b914d-117">Zwischengespeicherte Komposition</span><span class="sxs-lookup"><span data-stu-id="b914d-117">Cached Composition</span></span>

  <span data-ttu-id="b914d-118">Mithilfe der neuen <xref:System.Windows.Media.BitmapCache> -Klasse und der- <xref:System.Windows.Media.BitmapCacheBrush> Klasse können Sie einen komplexen Teil der visuellen Struktur als Bitmap Zwischenspeichern und die Renderingzeit erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="b914d-118">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="b914d-119">Die Bitmap reagiert weiterhin auf Benutzereingaben wie Mausklicks, und Sie können sie wie jeden Pinsel auf anderen Elementen zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b914d-119">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="b914d-120">Unterstützung von Pixel Shader 3</span><span class="sxs-lookup"><span data-stu-id="b914d-120">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="b914d-121">WPF 4 basiert auf der <xref:System.Windows.Media.Effects.ShaderEffect> Unterstützung, die in WPF 3,5 SP1 eingeführt wurde, indem Anwendungen das Schreiben von Effekten mithilfe von Pixel-Shader (PS) Version 3,0 ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b914d-121">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="b914d-122">Das PS 3.0-Shadermodell ist ausgereifter als PS 2.0 und ermöglicht noch mehr Effekte auf unterstützter Hardware.</span><span class="sxs-lookup"><span data-stu-id="b914d-122">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="b914d-123">Beschleunigungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="b914d-123">Easing Functions</span></span>

  <span data-ttu-id="b914d-124">Sie können Animationen mit Beschleunigungsfunktionen verbessern, die Ihnen zusätzliche Kontrolle über das Verhalten von Animationen geben.</span><span class="sxs-lookup"><span data-stu-id="b914d-124">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="b914d-125">Beispielsweise können Sie eine <xref:System.Windows.Media.Animation.ElasticEase> auf eine Animation anwenden, um der Animation ein springisierungsverhalten zu geben.</span><span class="sxs-lookup"><span data-stu-id="b914d-125">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="b914d-126">Weitere Informationen finden Sie unter Beschleunigungs Typen im- <xref:System.Windows.Media.Animation> Namespace.</span><span class="sxs-lookup"><span data-stu-id="b914d-126">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="b914d-127">Grafiken und Rendering</span><span class="sxs-lookup"><span data-stu-id="b914d-127">Graphics and Rendering</span></span>

<span data-ttu-id="b914d-128">WPF bietet Unterstützung für qualitativ hochwertige 2D-Grafiken.</span><span class="sxs-lookup"><span data-stu-id="b914d-128">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="b914d-129">Die Funktionalität umfasst die Pinsel, Geometrien, Bilder, Formen und Transformationen.</span><span class="sxs-lookup"><span data-stu-id="b914d-129">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="b914d-130">Weitere Informationen finden Sie unter [Grafik](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-130">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="b914d-131">Das Rendering grafischer Elemente basiert auf der- <xref:System.Windows.Media.Visual> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b914d-131">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="b914d-132">Die Struktur von visuellen Objekten auf dem Bildschirm wird durch die visuelle Struktur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b914d-132">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="b914d-133">Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-133">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="b914d-134">2D-Formen</span><span class="sxs-lookup"><span data-stu-id="b914d-134">2D Shapes</span></span>

<span data-ttu-id="b914d-135">WPF stellt eine Bibliothek häufig verwendeter vektorbasierter 2D-Formen dar, wie z. b. Rechtecke und Ellipsen, die in der folgenden Abbildung gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b914d-135">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Das Diagramm zeigt Ellipsen und Rechtecke an.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="b914d-137">Diese systeminternen WPF-Formen sind nicht nur Formen: Sie sind programmierbare Elemente, die viele der Features implementieren, die Sie von den gängigsten Steuerelementen erwarten, einschließlich Tastatur-und Maus Eingaben.</span><span class="sxs-lookup"><span data-stu-id="b914d-137">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="b914d-138">Das folgende Beispiel zeigt, wie das- <xref:System.Windows.UIElement.MouseUp> Ereignis behandelt wird, das durch Klicken auf ein-Element ausgelöst wird <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="b914d-138">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

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

<span data-ttu-id="b914d-139">Die folgende Abbildung zeigt die Ausgabe für das vorangehende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup und CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="b914d-139">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Ein Meldungs Feld, das besagt, dass Sie auf die Ellipse geklickt haben! "](./media/index/messagebox-text-output.png)

<span data-ttu-id="b914d-141">Weitere Informationen finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-141">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="b914d-142">Ein einführendes Beispiel finden Sie unter [Beispiel für Formelemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="b914d-142">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="b914d-143">2D-Geometrien</span><span class="sxs-lookup"><span data-stu-id="b914d-143">2D Geometries</span></span>

<span data-ttu-id="b914d-144">Wenn die von WPF bereitgestellten 2D-Formen nicht ausreichen, können Sie die WPF-Unterstützung für Geometrien und Pfade verwenden, um Ihre eigenen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b914d-144">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="b914d-145">In der folgenden Abbildung wird veranschaulicht, wie Geometrien verwendet werden können, um Formen, als Zeichnungs Pinsel und andere WPF-Elemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b914d-145">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![Screenshot, der zeigt, wie Geometrien verwendet werden können, um Formen zu erstellen.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="b914d-147">Weitere Informationen finden Sie unter [Übersicht über die Geometrie](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-147">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="b914d-148">Ein einführendes Beispiel finden Sie unter [Beispiele zu Geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="b914d-148">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="b914d-149">2D-Effekte</span><span class="sxs-lookup"><span data-stu-id="b914d-149">2D Effects</span></span>

<span data-ttu-id="b914d-150">WPF stellt eine Bibliothek von 2D-Klassen bereit, die Sie verwenden können, um eine Vielzahl von Effekten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b914d-150">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="b914d-151">Die 2D-Renderingfunktion von WPF bietet die Möglichkeit, Elemente mit Farb [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Verläufen, Bitmaps, Zeichnungen und Videos zu zeichnen und diese mithilfe von Drehung, Skalierung und Neigung zu manipulieren.</span><span class="sxs-lookup"><span data-stu-id="b914d-151">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="b914d-152">Die folgende Abbildung zeigt ein Beispiel für die zahlreichen Effekte, die Sie durch die Verwendung von WPF-Pinseln erreichen können.</span><span class="sxs-lookup"><span data-stu-id="b914d-152">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![Die Abbildung zeigt die verschiedenen WPF-Pinsel und-Elemente.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="b914d-154">Weitere Informationen finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-154">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="b914d-155">Ein einführendes Beispiel finden Sie unter [Pinselbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="b914d-155">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="b914d-156">3D-Rendering</span><span class="sxs-lookup"><span data-stu-id="b914d-156">3D Rendering</span></span>

<span data-ttu-id="b914d-157">WPF bietet eine Reihe von 3D-Renderingfunktionen, die mit der Unterstützung von 2D-Grafiken in WPF integriert werden, damit Sie eine genauere Darstellung von Layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Daten und Datenvisualisierung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="b914d-157">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="b914d-158">An einem Ende des Spektrums können Sie mithilfe von WPF 2D-Bilder auf den Oberflächen von 3D-Formen darstellen, die in der folgenden Abbildung veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="b914d-158">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![Screenshot eines Beispiels, das 3D-Formen mit unterschiedlichen Texturen anzeigt.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="b914d-160">Weitere Informationen finden Sie unter [Übersicht über 3D-Grafiken](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-160">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="b914d-161">Ein Einführ Endes Beispiel finden Sie unter [Beispiel für 3D-](https://go.microsoft.com/fwlink/?LinkID=159964)Daten.</span><span class="sxs-lookup"><span data-stu-id="b914d-161">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="b914d-162">Animation</span><span class="sxs-lookup"><span data-stu-id="b914d-162">Animation</span></span>

<span data-ttu-id="b914d-163">Mit Animation können Sie Steuerelemente und Elemente wachsen, bewegen, drehen sowie ein- und ausblenden lassen und z.B. interessante Seitenübergänge erzeugen.</span><span class="sxs-lookup"><span data-stu-id="b914d-163">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="b914d-164">Da WPF Ihnen ermöglicht, die meisten Eigenschaften zu animieren, können Sie nicht nur die meisten WPF-Objekte animieren, sondern auch WPF verwenden, um von Ihnen erstellte benutzerdefinierte Objekte zu animieren.</span><span class="sxs-lookup"><span data-stu-id="b914d-164">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![Screenshot eines animierten Cubes.](./media/index/animate-custom-objects.png)

<span data-ttu-id="b914d-166">Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-166">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="b914d-167">Ein einführendes Beispiel finden Sie unter [Beispielsammlung zu Animationen](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="b914d-167">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="b914d-168">Medien</span><span class="sxs-lookup"><span data-stu-id="b914d-168">Media</span></span>

<span data-ttu-id="b914d-169">Bilder, Videos und Audiodateien bieten eine umfangreiche Medienunterstützung, um Informationen zu vermitteln und für Benutzerfreundlichkeit zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="b914d-169">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="b914d-170">Bilder</span><span class="sxs-lookup"><span data-stu-id="b914d-170">Images</span></span>

<span data-ttu-id="b914d-171">Bilder, z.B. Symbole, Hintergründe und sogar Teile von Animationen, sind ein wesentlicher Bestandteil der meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b914d-171">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="b914d-172">Da Sie häufig Images verwenden müssen, bietet WPF eine Vielzahl von Möglichkeiten, um mit Ihnen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b914d-172">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="b914d-173">In der folgenden Abbildung wird lediglich eine der Möglichkeiten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b914d-173">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="b914d-174">![Screenshot: Stilbeispiel](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="b914d-174">![Styling sample screenshot](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="b914d-175">Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-175">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="b914d-176">Video und Audio</span><span class="sxs-lookup"><span data-stu-id="b914d-176">Video and Audio</span></span>

<span data-ttu-id="b914d-177">Ein zentrales Feature der Grafikfunktionen von WPF besteht darin, systemeigene Unterstützung für die Arbeit mit Multimedia zu bieten, die Video-und Audiodaten umfasst.</span><span class="sxs-lookup"><span data-stu-id="b914d-177">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="b914d-178">Im folgenden Beispiel wird veranschaulicht, wie einen MediaPlayer in eine Anwendung eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b914d-178">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="b914d-179"><xref:System.Windows.Controls.MediaElement>kann sowohl Video als auch Audiodaten abspielen und ist erweiterbar, um die einfache Erstellung benutzerdefinierter Benutzeroberflächen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b914d-179"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="b914d-180">Weitere Informationen finden Sie unter [Übersicht über Multimedia](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b914d-180">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b914d-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b914d-181">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="b914d-182">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="b914d-182">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="b914d-183">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="b914d-183">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="b914d-184">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="b914d-184">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="b914d-185">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="b914d-185">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="b914d-186">Gewusst-wie-Themen zu Animation und Zeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="b914d-186">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="b914d-187">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="b914d-187">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="b914d-188">Übersicht über Multimedia</span><span class="sxs-lookup"><span data-stu-id="b914d-188">Multimedia Overview</span></span>](multimedia-overview.md)
