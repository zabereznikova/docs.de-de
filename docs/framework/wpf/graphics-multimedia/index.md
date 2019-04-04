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
ms.openlocfilehash: cc97fda98badfc27e8b92a0dde6d5e419575ac6c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379561"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="cc7dd-102">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="cc7dd-102">Graphics and Multimedia</span></span>
<a name="introduction"></a>
<span data-ttu-id="cc7dd-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für Multimedia, Vektorgrafiken, Animation und Inhaltskomposition, erleichtert Entwicklern das Erstellen interessanter Benutzeroberflächen und Inhalte.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="cc7dd-104">Mithilfe von [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] können Sie Vektorgrafiken oder komplexe Animationen erstellen und Medien in Ihre Anwendung integrieren.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-104">Using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you can create vector graphics or complex animations and integrate media into your applications.</span></span>  
  
 <span data-ttu-id="cc7dd-105">In diesem Thema werden die Grafik-, Animations- und Medienfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt, mit denen Sie den Anwendungen Grafiken, Übergangseffekte, Ton und Videos hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc7dd-106">Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="cc7dd-107">Wenn Sie versuchen, WPF-Typen in einem Windows-Dienst zu verwenden, funktioniert der Dienst möglicherweise nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="cc7dd-108">Neue Grafik. und Multimediafunktionen in WPF 4</span><span class="sxs-lookup"><span data-stu-id="cc7dd-108">What's New with Graphics and Multimedia in WPF 4</span></span>  
 <span data-ttu-id="cc7dd-109">Im Zusammenhang mit Grafiken und Animationen wurden mehrere Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-109">Several changes have been made related to graphics and animations.</span></span>  
  
-   <span data-ttu-id="cc7dd-110">Layoutglättung</span><span class="sxs-lookup"><span data-stu-id="cc7dd-110">Layout Rounding</span></span>  
  
     <span data-ttu-id="cc7dd-111">Wenn ein Objektrand in die Mitte eines Pixelgeräts fällt, kann das DPI-unabhängige Grafiksystem Renderingartefakte erstellen, z.B. verschwommene oder semitransparente Ränder.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="cc7dd-112">Frühere Versionen der WPF haben die Pixelausrichtung für diese Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="cc7dd-113">Silverlight 2 hat die Layoutglättung eingeführt, die eine andere Möglichkeit bietet, um Elemente so zu verschieben, dass Ränder auf ganzen Pixelgrenzen liegen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="cc7dd-114">WPF unterstützt jetzt die layoutglättung mit der <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> angefügte Eigenschaft auf <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>  
  
-   <span data-ttu-id="cc7dd-115">Zwischengespeicherte Komposition</span><span class="sxs-lookup"><span data-stu-id="cc7dd-115">Cached Composition</span></span>  
  
     <span data-ttu-id="cc7dd-116">Mit dem neuen <xref:System.Windows.Media.BitmapCache> und <xref:System.Windows.Media.BitmapCacheBrush> Klassen, können Sie einen komplexen Teil der visuellen Struktur als Bitmap Zwischenspeichern und Renderingzeit dadurch erheblich optimieren.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="cc7dd-117">Die Bitmap reagiert weiterhin auf Benutzereingaben wie Mausklicks, und Sie können sie wie jeden Pinsel auf anderen Elementen zeichnen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>  
  
-   <span data-ttu-id="cc7dd-118">Unterstützung von Pixel Shader 3</span><span class="sxs-lookup"><span data-stu-id="cc7dd-118">Pixel Shader 3 Support</span></span>  
  
     <span data-ttu-id="cc7dd-119">WPF 4 basiert auf der die <xref:System.Windows.Media.Effects.ShaderEffect> Unterstützung in WPF 3.5 SP1 eingeführt werden, indem ermöglicht es Anwendungen, Effekte mit Pixel Shader (PS) Version 3.0 zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="cc7dd-120">Das PS 3.0-Shadermodell ist ausgereifter als PS 2.0 und ermöglicht noch mehr Effekte auf unterstützter Hardware.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>  
  
-   <span data-ttu-id="cc7dd-121">Beschleunigungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="cc7dd-121">Easing Functions</span></span>  
  
     <span data-ttu-id="cc7dd-122">Sie können Animationen mit Beschleunigungsfunktionen verbessern, die Ihnen zusätzliche Kontrolle über das Verhalten von Animationen geben.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="cc7dd-123">Sie können z. B. Anwenden einer <xref:System.Windows.Media.Animation.ElasticEase> für eine Animation, der Animation ein Federverhalten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="cc7dd-124">Weitere Informationen finden Sie unter den Beschleunigungstypen im der <xref:System.Windows.Media.Animation> Namespace.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a><span data-ttu-id="cc7dd-125">Grafiken und Rendering</span><span class="sxs-lookup"><span data-stu-id="cc7dd-125">Graphics and Rendering</span></span>  
 <span data-ttu-id="cc7dd-126">WPF unterstützt hochwertige 2D-Grafiken.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-126">WPF includes support for high quality 2-D graphics.</span></span> <span data-ttu-id="cc7dd-127">Die Funktionalität umfasst die Pinsel, Geometrien, Bilder, Formen und Transformationen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="cc7dd-128">Weitere Informationen finden Sie unter [Grafik](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="cc7dd-129">Das Rendering von visuellen Elementen basiert auf der <xref:System.Windows.Media.Visual> Klasse.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="cc7dd-130">Die Struktur von visuellen Objekten auf dem Bildschirm wird durch die visuelle Struktur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="cc7dd-131">Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
### <a name="2-d-shapes"></a><span data-ttu-id="cc7dd-132">2D-Formen</span><span class="sxs-lookup"><span data-stu-id="cc7dd-132">2-D Shapes</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="cc7dd-133">enthält eine Bibliothek häufig verwendeter vektorbasierter [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Formen wie Rechtecke und Ellipsen, die in der folgenden Abbildung dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-133">provides a library of commonly used, vector-drawn [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>  
  
 <span data-ttu-id="cc7dd-134">![Ellipsen und Rechtecke](./media/wpfintrofigure4.PNG "WPFIntroFigure4")</span><span class="sxs-lookup"><span data-stu-id="cc7dd-134">![Ellipses and rectangles](./media/wpfintrofigure4.PNG "WPFIntroFigure4")</span></span>  
  
 <span data-ttu-id="cc7dd-135">Diese systeminternen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Formen sind mehr als nur Formen: Es handelt sich um programmierbare Elemente, die viele der Features implementieren, die Sie von den gebräuchlichsten Steuerelementen erwarten, etwa Tastatur- und Mauseingaben.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-135">These intrinsic [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="cc7dd-136">Das folgende Beispiel zeigt, wie Sie behandelt die <xref:System.Windows.UIElement.MouseUp> Ereignis ausgelöst wird, indem Sie auf eine <xref:System.Windows.Shapes.Ellipse> Element.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>  
  
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
  
 <span data-ttu-id="cc7dd-137">Die folgende Abbildung zeigt die Ausgabe für das vorangehende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup und CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>  
  
 <span data-ttu-id="cc7dd-138">![Ein Fenster mit dem Text „you clicked the ellipse&#33;“](./media/wpfintrofigure12.png "WPFIntroFigure12")</span><span class="sxs-lookup"><span data-stu-id="cc7dd-138">![A window with the text "you clicked the ellipse&#33;"](./media/wpfintrofigure12.png "WPFIntroFigure12")</span></span>  
  
 <span data-ttu-id="cc7dd-139">Weitere Informationen finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="cc7dd-140">Ein einführendes Beispiel finden Sie unter [Beispiel für Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-140">For an introductory sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
### <a name="2-d-geometries"></a><span data-ttu-id="cc7dd-141">2D-Geometrien</span><span class="sxs-lookup"><span data-stu-id="cc7dd-141">2-D Geometries</span></span>  
 <span data-ttu-id="cc7dd-142">Wenn die [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Formen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] nicht ausreichen, können Sie mit der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Unterstützung für Geometrien und Pfade eigene Formen erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-142">When the [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides are not sufficient, you can use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] support for geometries and paths to create your own.</span></span> <span data-ttu-id="cc7dd-143">Die folgende Abbildung zeigt, wie Sie Geometrien nutzen können, um Formen zu erstellen, wie etwa einen Zeichenpinsel, und andere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elemente ausschneiden zu können.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elements.</span></span>  
  
 <span data-ttu-id="cc7dd-144">![Verschiedene Einsatzbereiche eines Pfads](./media/wpfintrofigure5.PNG "WPFIntroFigure5")</span><span class="sxs-lookup"><span data-stu-id="cc7dd-144">![Various uses of a Path](./media/wpfintrofigure5.PNG "WPFIntroFigure5")</span></span>  
  
 <span data-ttu-id="cc7dd-145">Weitere Informationen finden Sie unter [Übersicht über die Geometrie](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="cc7dd-146">Ein einführendes Beispiel finden Sie unter [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-146">For an introductory sample, see [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
### <a name="2-d-effects"></a><span data-ttu-id="cc7dd-147">2D-Effekte</span><span class="sxs-lookup"><span data-stu-id="cc7dd-147">2-D Effects</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="cc7dd-148">stellt eine Bibliothek mit [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Klassen zur Verfügung, mit denen Sie verschiedene Effekte erstellen können.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-148">provides a library of [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="cc7dd-149">Die [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Renderingfunktion von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet die Möglichkeit, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente mit Farbverläufen, Bitmaps, Zeichnungen und Videos zu zeichnen, und diese durch Drehung, Skalierung und Neigung zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-149">The [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] rendering capability of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="cc7dd-150">Die folgende Abbildung zeigt ein Beispiel für die vielen Effekte, die Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Pinsels erreichen können.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-150">The following illustration gives an example of the many effects you can achieve by using [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] brushes.</span></span>  
  
 <span data-ttu-id="cc7dd-151">![Darstellung unterschiedlicher Pinsel](./media/wpfintrofigure6.PNG "WPFIntroFigure6")</span><span class="sxs-lookup"><span data-stu-id="cc7dd-151">![Illustration of different brushes](./media/wpfintrofigure6.PNG "WPFIntroFigure6")</span></span>  
  
 <span data-ttu-id="cc7dd-152">Weitere Informationen finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="cc7dd-153">Ein einführendes Beispiel finden Sie unter [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-153">For an introductory sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a><span data-ttu-id="cc7dd-154">3D-Rendering</span><span class="sxs-lookup"><span data-stu-id="cc7dd-154">3-D Rendering</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="cc7dd-155">bietet eine Reihe von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Renderingfunktionen, die in der [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Grafikunterstützung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integriert sind, damit Sie Layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und Datenvisualisierung noch ansprechender gestalten können.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-155">provides a set of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] rendering capabilities that integrate with [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] graphics support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="cc7dd-156">Mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können Sie sogar [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Bilder auf den Oberflächen von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Formen rendern, was die folgende Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-156">At one end of the spectrum, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to render [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] images onto the surfaces of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] shapes, which the following illustration demonstrates.</span></span>  
  
 <span data-ttu-id="cc7dd-157">![Visual3D-Beispielscreenshot](./media/wpfintrofigure13.png "WPFIntroFigure13")</span><span class="sxs-lookup"><span data-stu-id="cc7dd-157">![Visual3D sample screen shot](./media/wpfintrofigure13.png "WPFIntroFigure13")</span></span>  
  
 <span data-ttu-id="cc7dd-158">Weitere Informationen finden Sie unter [Übersicht über 3D-Grafiken](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-158">For more information, see [3-D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="cc7dd-159">Ein einführendes Beispiel finden Sie unter [Beispiel zu 3D-Festkörpern](https://go.microsoft.com/fwlink/?LinkID=159964).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-159">For an introductory sample, see [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>  
  
<a name="animation"></a>   
## <a name="animation"></a><span data-ttu-id="cc7dd-160">Animation</span><span class="sxs-lookup"><span data-stu-id="cc7dd-160">Animation</span></span>  
 <span data-ttu-id="cc7dd-161">Mit Animation können Sie Steuerelemente und Elemente wachsen, bewegen, drehen sowie ein- und ausblenden lassen und z.B. interessante Seitenübergänge erzeugen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="cc7dd-162">Da Sie mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die meisten Eigenschaften animieren können, können Sie nicht nur die meisten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Objekte animieren, sondern Sie können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] auch verwenden, um benutzerdefinierte Objekte, die Sie erstellen, zu animieren.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-162">Because [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to animate most properties, not only can you animate most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] objects, you can also use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to animate custom objects that you create.</span></span>  
  
 <span data-ttu-id="cc7dd-163">![Bilder eines animierten Würfels](./media/wpfintrofigure7.png "WPFIntroFigure7")</span><span class="sxs-lookup"><span data-stu-id="cc7dd-163">![Images of an animated cube](./media/wpfintrofigure7.png "WPFIntroFigure7")</span></span>  
  
 <span data-ttu-id="cc7dd-164">Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="cc7dd-165">Ein einführendes Beispiel finden Sie unter [Beispielsammlung zu Animationen](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-165">For an introductory sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
<a name="media"></a>   
## <a name="media"></a><span data-ttu-id="cc7dd-166">Medien</span><span class="sxs-lookup"><span data-stu-id="cc7dd-166">Media</span></span>  
 <span data-ttu-id="cc7dd-167">Bilder, Videos und Audiodateien bieten eine umfangreiche Medienunterstützung, um Informationen zu vermitteln und für Benutzerfreundlichkeit zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>  
  
### <a name="images"></a><span data-ttu-id="cc7dd-168">Bilder</span><span class="sxs-lookup"><span data-stu-id="cc7dd-168">Images</span></span>  
 <span data-ttu-id="cc7dd-169">Bilder, z.B. Symbole, Hintergründe und sogar Teile von Animationen, sind ein wesentlicher Bestandteil der meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="cc7dd-170">Da Sie häufig Bilder verwenden müssen, bietet [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die Möglichkeit, sie auf vielfältige Weise einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-170">Because you frequently need to use images, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="cc7dd-171">In der folgenden Abbildung wird lediglich eine der Möglichkeiten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-171">The following illustration shows just one of those ways.</span></span>  
  
 <span data-ttu-id="cc7dd-172">![Bildschirmabbildung für Formatierungsbeispiel](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="cc7dd-172">![Styling sample screen shot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>  
  
 <span data-ttu-id="cc7dd-173">Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>  
  
### <a name="video-and-audio"></a><span data-ttu-id="cc7dd-174">Video und Audio</span><span class="sxs-lookup"><span data-stu-id="cc7dd-174">Video and Audio</span></span>  
 <span data-ttu-id="cc7dd-175">Ein Hauptfeature der Grafikfunktionen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] besteht in der nativen Unterstützung für die Arbeit mit Multimedia, z.B. Video und Audio.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-175">A core feature of the graphics capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="cc7dd-176">Im folgenden Beispiel wird veranschaulicht, wie einen MediaPlayer in eine Anwendung eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="cc7dd-176">The following example shows how to insert a media player into an application.</span></span>  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <span data-ttu-id="cc7dd-177"><xref:System.Windows.Controls.MediaElement> kann sowohl video als auch audio wiedergegeben, und ist erweiterbar genug, um die einfache Erstellung von benutzerdefinierten ermöglichen [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc7dd-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="cc7dd-178">Weitere Informationen finden Sie unter [Übersicht über Multimedia](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc7dd-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc7dd-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc7dd-179">See also</span></span>
- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="cc7dd-180">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="cc7dd-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="cc7dd-181">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="cc7dd-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="cc7dd-182">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="cc7dd-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="cc7dd-183">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="cc7dd-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="cc7dd-184">Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="cc7dd-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="cc7dd-185">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="cc7dd-185">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="cc7dd-186">Übersicht über Multimedia</span><span class="sxs-lookup"><span data-stu-id="cc7dd-186">Multimedia Overview</span></span>](multimedia-overview.md)
