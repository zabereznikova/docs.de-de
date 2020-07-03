---
title: Übersicht über Formen und grundlegende Zeichnungen
description: Verbessern Sie Ihre Benutzeroberfläche mit sofort einsatzbereiten Formen und mehreren Ebenen der Renderingdienste in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 41d8f2b87232740c8945bd6a6099aa86dbe77bc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853688"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="2dfd1-103">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="2dfd1-103">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="2dfd1-104">Dieses Thema enthält eine Übersicht über das Zeichnen mit- <xref:System.Windows.Shapes.Shape> Objekten.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-104">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="2dfd1-105">Ein <xref:System.Windows.Shapes.Shape> ist ein Typ von <xref:System.Windows.UIElement> , mit dem Sie eine Form auf dem Bildschirm zeichnen können.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-105">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="2dfd1-106">Da es sich um Benutzeroberflächen Elemente handelt, <xref:System.Windows.Shapes.Shape> können-Objekte innerhalb von <xref:System.Windows.Controls.Panel> Elementen und den meisten Steuerelementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-106">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="2dfd1-107">bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-107">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="2dfd1-108">Auf der obersten Ebene <xref:System.Windows.Shapes.Shape> sind-Objekte einfach zu verwenden und bieten zahlreiche nützliche Features, wie z. b. das Layout und die Teilnahme am [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ereignis System.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-108">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>
## <a name="shape-objects"></a><span data-ttu-id="2dfd1-109">Shape-Objekte</span><span class="sxs-lookup"><span data-stu-id="2dfd1-109">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="2dfd1-110">stellt eine Reihe von gebrauchsfertigen <xref:System.Windows.Shapes.Shape> Objekten bereit.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-110">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="2dfd1-111">Alle Shape-Objekte erben von der- <xref:System.Windows.Shapes.Shape> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-111">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="2dfd1-112">Zu den verfügbaren Shape-Objekten zählen <xref:System.Windows.Shapes.Ellipse> , <xref:System.Windows.Shapes.Line> , <xref:System.Windows.Shapes.Path> , <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> und <xref:System.Windows.Shapes.Rectangle> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-112">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="2dfd1-113"><xref:System.Windows.Shapes.Shape>-Objekte haben die folgenden allgemeinen Eigenschaften gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-113"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="2dfd1-114"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Beschreibt, wie der Umriss der Form gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-114"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="2dfd1-115"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Beschreibt die Stärke der Kontur der Form.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-115"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="2dfd1-116"><xref:System.Windows.Shapes.Shape.Fill%2A>: Beschreibt, wie das Innere der Form gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-116"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="2dfd1-117">Dateneigenschaften zum Angeben von Koordinaten und Eckpunkten, gemessen in geräteunabhängigen Pixeln.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-117">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="2dfd1-118">Da Sie von abgeleitet <xref:System.Windows.UIElement> sind, können Shape-Objekte in Bereichen und den meisten Steuerelementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-118">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="2dfd1-119">Das <xref:System.Windows.Controls.Canvas> Panel ist eine besonders gute Wahl zum Erstellen komplexer Zeichnungen, da es die absolute Positionierung der untergeordneten Objekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-119">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="2dfd1-120">Mit der- <xref:System.Windows.Shapes.Line> Klasse können Sie eine Linie zwischen zwei Punkten zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-120">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="2dfd1-121">Das folgende Beispiel zeigt verschiedene Arten, wie Zeilenkoordinaten und Stricheigenschaften angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-121">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="2dfd1-122">Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Line> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-122">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="2dfd1-123">![Liniendarstellung](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="2dfd1-123">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="2dfd1-124">Obwohl die- <xref:System.Windows.Shapes.Line> Klasse eine-Eigenschaft bereitstellt, wirkt sich <xref:System.Windows.Shapes.Shape.Fill%2A> Diese Einstellung nicht aus, da ein <xref:System.Windows.Shapes.Line> keinen Bereich aufweist.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-124">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="2dfd1-125">Eine andere gängige Form ist die <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-125">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="2dfd1-126">Erstellen Sie ein, <xref:System.Windows.Shapes.Ellipse> indem Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften und der Form definieren <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-126">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="2dfd1-127">Zum Zeichnen eines Kreises geben Sie einen an, <xref:System.Windows.Shapes.Ellipse> dessen <xref:System.Windows.FrameworkElement.Width%2A> -Wert und- <xref:System.Windows.FrameworkElement.Height%2A> Wert gleich sind.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-127">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="2dfd1-128">Die folgende Abbildung zeigt ein Beispiel für eine gerenderte <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-128">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="2dfd1-129">![Ellipsendarstellung](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="2dfd1-129">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a><span data-ttu-id="2dfd1-130">Verwenden von Pfaden und Geometrien</span><span class="sxs-lookup"><span data-stu-id="2dfd1-130">Using Paths and Geometries</span></span>  
 <span data-ttu-id="2dfd1-131">Die <xref:System.Windows.Shapes.Path> -Klasse ermöglicht es Ihnen, Kurven und komplexe Formen zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-131">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="2dfd1-132">Diese Kurven und Formen werden mithilfe von <xref:System.Windows.Media.Geometry> Objekten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-132">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="2dfd1-133">Um einen zu verwenden <xref:System.Windows.Shapes.Path> , erstellen Sie eine <xref:System.Windows.Media.Geometry> und verwenden Sie, um die <xref:System.Windows.Shapes.Path> -Eigenschaft des-Objekts festzulegen <xref:System.Windows.Shapes.Path.Data%2A> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-133">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="2dfd1-134">Es gibt eine Vielzahl von <xref:System.Windows.Media.Geometry> Objekten, aus denen Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-134">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="2dfd1-135">Die <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry> Klassen, und <xref:System.Windows.Media.EllipseGeometry> beschreiben relativ einfache Formen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-135">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="2dfd1-136">Um komplexere Formen zu erstellen oder Kurven zu erstellen, verwenden Sie eine <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-136">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="2dfd1-137">PathGeometry und PathSegments</span><span class="sxs-lookup"><span data-stu-id="2dfd1-137">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="2dfd1-138"><xref:System.Windows.Media.PathGeometry>Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jede <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-138"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="2dfd1-139">Jede Komponente besteht aus <xref:System.Windows.Media.PathFigure> einem oder mehreren- <xref:System.Windows.Media.PathSegment> Objekten, die jeweils einen verbundenen Teil der Abbildung oder Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-139">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="2dfd1-140">Zu den Segment Typen zählen die folgenden: <xref:System.Windows.Media.LineSegment> , <xref:System.Windows.Media.BezierSegment> und <xref:System.Windows.Media.ArcSegment> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-140">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="2dfd1-141">Im folgenden Beispiel <xref:System.Windows.Shapes.Path> wird ein verwendet, um eine quadratische Bezier-Kurve zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-141">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="2dfd1-142">Die folgende Abbildung zeigt die gerenderte Form.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-142">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="2dfd1-143">![Pfaddarstellung](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="2dfd1-143">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="2dfd1-144">Weitere Informationen zu <xref:System.Windows.Media.PathGeometry> und den anderen <xref:System.Windows.Media.Geometry> Klassen finden Sie in der [Übersicht](geometry-overview.md)über die Geometrie.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-144">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="2dfd1-145">Abgekürzte Syntax in XAML</span><span class="sxs-lookup"><span data-stu-id="2dfd1-145">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="2dfd1-146">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie auch eine spezielle abgekürzte Syntax verwenden, um eine zu beschreiben <xref:System.Windows.Shapes.Path> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-146">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="2dfd1-147">Im folgenden Beispiel wird abgekürzte Syntax verwendet, um eine komplexe Form zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-147">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="2dfd1-148">Die folgende Abbildung zeigt ein gerendertes <xref:System.Windows.Shapes.Path> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-148">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="2dfd1-149">![Pfaddarstellung](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="2dfd1-149">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="2dfd1-150">Die <xref:System.Windows.Shapes.Path.Data%2A> Attribut Zeichenfolge beginnt mit dem Befehl "muveto", der durch M angegeben wird. Dadurch wird ein Startpunkt für den Pfad im Koordinatensystem von festgelegt <xref:System.Windows.Controls.Canvas> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-150">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="2dfd1-151"><xref:System.Windows.Shapes.Path>bei Daten Parametern wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-151"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="2dfd1-152">Das Kapital M gibt eine absolute Position für den neuen aktuellen Punkt an.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-152">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="2dfd1-153">Ein kleingeschriebenes m würde relative Koordinaten angeben.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-153">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="2dfd1-154">Das erste Segment ist eine kubische Bezier-Kurve, beginnend bei (100.200) und endet bei (400.175), gezeichnet mithilfe der beiden Kontrollpunkte (100, 25) und (400.350).</span><span class="sxs-lookup"><span data-stu-id="2dfd1-154">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="2dfd1-155">Dieses Segment wird durch den C-Befehl in der <xref:System.Windows.Shapes.Path.Data%2A> Attribut Zeichenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-155">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="2dfd1-156">Ein großes C gibt erneut einen absoluten Pfad an. Ein kleingeschriebenes c würde einen relativen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-156">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="2dfd1-157">Das zweite Segment beginnt mit einem absoluten horizontalen „Lineto“-Befehl H, der eine Linie vom vorherigen untergeordneten Endpunkt (400,175) zu einem neuen Endpunkt (280,175) zeichnet.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-157">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="2dfd1-158">Da es sich um einen horizontalen "LineTo"-Befehl handelt, ist der angegebene Wert eine *x*-Koordinate.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-158">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="2dfd1-159">Die gesamte Pfad Syntax finden Sie in der <xref:System.Windows.Shapes.Path.Data%2A> Referenz und unter [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="2dfd1-159">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a><span data-ttu-id="2dfd1-160">Zeichnen von Formen</span><span class="sxs-lookup"><span data-stu-id="2dfd1-160">Painting Shapes</span></span>  
 <span data-ttu-id="2dfd1-161"><xref:System.Windows.Media.Brush>-Objekte werden zum Zeichnen von und verwendet <xref:System.Windows.Shapes.Shape.Stroke%2A> <xref:System.Windows.Shapes.Shape.Fill%2A> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-161"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="2dfd1-162">Im folgenden Beispiel werden der Strich und die Füllung eines <xref:System.Windows.Shapes.Ellipse> angegeben.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-162">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="2dfd1-163">Beachten Sie, dass Pinseleigenschaften entweder ein Schlüsselwort oder einen hexadezimalen Farbwert werden können.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-163">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="2dfd1-164">Weitere Informationen zu verfügbaren Farb Schlüsselwörtern finden Sie unter Eigenschaften der- <xref:System.Windows.Media.Colors> Klasse im- <xref:System.Windows.Media> Namespace.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-164">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```xaml
<Canvas Background="LightGray">
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="2dfd1-165">Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-165">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="2dfd1-166">![Eine Ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="2dfd1-166">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="2dfd1-167">Alternativ können Sie die Eigenschafts Element Syntax verwenden, um explizit ein- <xref:System.Windows.Media.SolidColorBrush> Objekt zu erstellen, um die Form mit einer voll Tonfarbe zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-167">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="2dfd1-168">Die folgende Abbildung zeigt die gerenderte Form.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-168">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="2dfd1-169">![SolidColorBrush-Darstellung](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="2dfd1-169">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="2dfd1-170">Sie können die Kontur oder Fläche einer Form auch mit Farbverläufen, Bildern, Mustern und mehr zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-170">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="2dfd1-171">Weitere Informationen finden Sie unter [Übersicht über das Zeichnen mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2dfd1-171">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a><span data-ttu-id="2dfd1-172">Gestreckte Formen</span><span class="sxs-lookup"><span data-stu-id="2dfd1-172">Stretchable Shapes</span></span>  
 <span data-ttu-id="2dfd1-173">Die <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path> Klassen,, <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> und <xref:System.Windows.Shapes.Rectangle> verfügen alle über eine- <xref:System.Windows.Shapes.Shape.Stretch%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-173">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="2dfd1-174">Diese Eigenschaft bestimmt, wie der Inhalt eines- <xref:System.Windows.Shapes.Shape> Objekts (die Form, die gezeichnet werden soll) gestreckt wird, um den <xref:System.Windows.Shapes.Shape> Layoutbereich des Objekts zu füllen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-174">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="2dfd1-175">Der <xref:System.Windows.Shapes.Shape> Layoutbereich eines-Objekts ist die Menge des Speicherplatzes <xref:System.Windows.Shapes.Shape> , der vom Layoutsystem aufgrund einer expliziten <xref:System.Windows.FrameworkElement.Width%2A> und- <xref:System.Windows.FrameworkElement.Height%2A> Einstellung oder aufgrund der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -und- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Einstellungen zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-175">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="2dfd1-176">Weitere Informationen zum Layout in Windows Presentation Foundation finden Sie unter Übersicht über [das Layout.](../advanced/layout.md)</span><span class="sxs-lookup"><span data-stu-id="2dfd1-176">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="2dfd1-177">Die Stretch-Eigenschaft nimmt einen der folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="2dfd1-177">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="2dfd1-178"><xref:System.Windows.Media.Stretch.None>: Der <xref:System.Windows.Shapes.Shape> Inhalt des Objekts wird nicht gestreckt.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-178"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="2dfd1-179"><xref:System.Windows.Media.Stretch.Fill>: Der <xref:System.Windows.Shapes.Shape> Inhalt des Objekts wird gestreckt, um den Layoutbereich auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-179"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="2dfd1-180">Das Seitenverhältnis wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-180">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="2dfd1-181"><xref:System.Windows.Media.Stretch.Uniform>: Der <xref:System.Windows.Shapes.Shape> Inhalt des Objekts wird so weit wie möglich gestreckt, um den Layoutbereich auszufüllen, während das ursprüngliche Seitenverhältnis beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-181"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="2dfd1-182"><xref:System.Windows.Media.Stretch.UniformToFill>: Der <xref:System.Windows.Shapes.Shape> Inhalt des Objekts wird gestreckt, um seinen Layoutbereich vollständig auszufüllen, während das ursprüngliche Seitenverhältnis beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-182"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="2dfd1-183">Beachten Sie, dass <xref:System.Windows.Shapes.Shape> die <xref:System.Windows.Shapes.Shape> Kontur des Objekts nach der Streckung gezeichnet wird, wenn der Inhalt eines-Objekts gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-183">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="2dfd1-184">Im folgenden Beispiel <xref:System.Windows.Shapes.Polygon> wird eine zum Zeichnen eines sehr kleinen Dreiecks von (0,0) bis (0,0) bis (1, 1) verwendet.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-184">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="2dfd1-185">Der <xref:System.Windows.Shapes.Polygon> und die-Eigenschaft des-Objekts <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> werden auf 100 festgelegt, und die Stretch-Eigenschaft ist auf Fill festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-185">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="2dfd1-186">Folglich wird der Inhalt des <xref:System.Windows.Shapes.Polygon> Objekts (das Dreieck) gestreckt, um den größeren Bereich auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-186">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>
## <a name="transforming-shapes"></a><span data-ttu-id="2dfd1-187">Transformieren von Formen</span><span class="sxs-lookup"><span data-stu-id="2dfd1-187">Transforming Shapes</span></span>  
 <span data-ttu-id="2dfd1-188">Die- <xref:System.Windows.Media.Transform> Klasse stellt die Mittel zum Transformieren von Formen in einer zweidimensionalen Ebene bereit.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-188">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="2dfd1-189">Zu den verschiedenen Transformations Typen zählen Drehung ( <xref:System.Windows.Media.RotateTransform> ), Skalierung ( <xref:System.Windows.Media.ScaleTransform> ), Schiefe ( <xref:System.Windows.Media.SkewTransform> ) und Übersetzung ( <xref:System.Windows.Media.TranslateTransform> ).</span><span class="sxs-lookup"><span data-stu-id="2dfd1-189">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="2dfd1-190">Eine allgemeine Transformation einer Form ist die Drehung.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-190">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="2dfd1-191">Um eine Form zu drehen, erstellen Sie eine <xref:System.Windows.Media.RotateTransform> und geben deren an <xref:System.Windows.Media.RotateTransform.Angle%2A> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-191">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="2dfd1-192">Ein <xref:System.Windows.Media.RotateTransform.Angle%2A> von 45 dreht das Element um 45 Grad im Uhrzeigersinn, ein Winkel von 90 dreht das Element um 90 Grad im Uhrzeigersinn und so weiter.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-192">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="2dfd1-193">Legen Sie die-Eigenschaft und die-Eigenschaft fest <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> , wenn Sie den Punkt steuern möchten, an dem das Element gedreht wird.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-193">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="2dfd1-194">Diese Eigenschaftswerte werden im Koordinatenraum des transformierten Elements ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-194">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="2dfd1-195"><xref:System.Windows.Media.RotateTransform.CenterX%2A>und <xref:System.Windows.Media.RotateTransform.CenterY%2A> haben die Standardwerte 0 (null).</span><span class="sxs-lookup"><span data-stu-id="2dfd1-195"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="2dfd1-196">Wenden <xref:System.Windows.Media.RotateTransform> Sie schließlich auf das-Element an.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-196">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="2dfd1-197">Wenn Sie nicht möchten, dass sich die Transformation auf das Layout auswirkt, legen Sie die-Eigenschaft der Form fest <xref:System.Windows.UIElement.RenderTransform%2A> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-197">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="2dfd1-198">Im folgenden Beispiel wird ein-Wert <xref:System.Windows.Media.RotateTransform> verwendet, um eine Form 45 Grad um die linke obere Ecke (0,0) zu drehen.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-198">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="2dfd1-199">Im nächsten Beispiel eine andere Form um 45 Grad gedreht wird, aber dieses Mal wird sie über den Punkt (25,50) gedreht.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-199">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="2dfd1-200">In der folgenden Abbildung werden die Ergebnisse der Anwendung der zwei Transformationen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-200">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="2dfd1-201">![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="2dfd1-201">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="2dfd1-202">In den vorherigen Beispielen wurde eine einzelne Transformation auf jedes Shape-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="2dfd1-202">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="2dfd1-203">Verwenden Sie zum Anwenden mehrerer Transformationen auf eine Form (oder ein beliebiges anderes UI-Element) <xref:System.Windows.Media.TransformGroup> .</span><span class="sxs-lookup"><span data-stu-id="2dfd1-203">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfd1-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dfd1-204">See also</span></span>

- [<span data-ttu-id="2dfd1-205">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="2dfd1-205">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="2dfd1-206">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="2dfd1-206">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="2dfd1-207">Übersicht über die Geometrie</span><span class="sxs-lookup"><span data-stu-id="2dfd1-207">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="2dfd1-208">Exemplarische Vorgehensweise: Walkthrough: My first WPF desktop application (Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung)</span><span class="sxs-lookup"><span data-stu-id="2dfd1-208">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="2dfd1-209">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="2dfd1-209">Animation Overview</span></span>](animation-overview.md)
