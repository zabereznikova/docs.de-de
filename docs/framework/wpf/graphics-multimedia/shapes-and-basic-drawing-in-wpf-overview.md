---
title: Shapes und grundlegende Zeichnungsübersicht
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
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141327"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="b9319-102">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="b9319-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="b9319-103">Dieses Thema gibt einen Überblick <xref:System.Windows.Shapes.Shape> über das Zeichnen mit Objekten.</span><span class="sxs-lookup"><span data-stu-id="b9319-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="b9319-104">A <xref:System.Windows.Shapes.Shape> ist eine <xref:System.Windows.UIElement> Art von, mit der Sie eine Form auf dem Bildschirm zeichnen können.</span><span class="sxs-lookup"><span data-stu-id="b9319-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="b9319-105">Da es sich <xref:System.Windows.Shapes.Shape> um UI-Elemente <xref:System.Windows.Controls.Panel> handelt, können Objekte innerhalb von Elementen und den meisten Steuerelementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9319-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="b9319-106">bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste.</span><span class="sxs-lookup"><span data-stu-id="b9319-106">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="b9319-107">Auf der obersten <xref:System.Windows.Shapes.Shape> Ebene sind Objekte einfach zu bedienen und bieten viele [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nützliche Funktionen, wie Layout und Teilnahme am Veranstaltungssystem.</span><span class="sxs-lookup"><span data-stu-id="b9319-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>
## <a name="shape-objects"></a><span data-ttu-id="b9319-108">Shape-Objekte</span><span class="sxs-lookup"><span data-stu-id="b9319-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="b9319-109">bietet eine Reihe gebrauchsfertiger <xref:System.Windows.Shapes.Shape> Objekte.</span><span class="sxs-lookup"><span data-stu-id="b9319-109">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="b9319-110">Alle Shape-Objekte erben <xref:System.Windows.Shapes.Shape> von der Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9319-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="b9319-111">Verfügbare Shape-Objekte <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>sind <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle>, , , und .</span><span class="sxs-lookup"><span data-stu-id="b9319-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="b9319-112"><xref:System.Windows.Shapes.Shape>Objekte teilen die folgenden gemeinsamen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b9319-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="b9319-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Beschreibt, wie der Umriss des Shapes gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="b9319-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="b9319-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Beschreibt die Dicke des Umrisses des Shapes.</span><span class="sxs-lookup"><span data-stu-id="b9319-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="b9319-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Beschreibt, wie das Innere der Form lackiert wird.</span><span class="sxs-lookup"><span data-stu-id="b9319-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="b9319-116">Dateneigenschaften zum Angeben von Koordinaten und Eckpunkten, gemessen in geräteunabhängigen Pixeln.</span><span class="sxs-lookup"><span data-stu-id="b9319-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="b9319-117">Da sie von <xref:System.Windows.UIElement>ableiten, können Shape-Objekte in Bedienfeldern und den meisten Steuerelementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9319-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="b9319-118">Das <xref:System.Windows.Controls.Canvas> Panel ist eine besonders gute Wahl für die Erstellung komplexer Zeichnungen, da es die absolute Positionierung seiner untergeordneten Objekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b9319-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="b9319-119">Mit <xref:System.Windows.Shapes.Line> der Klasse können Sie eine Linie zwischen zwei Punkten zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b9319-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="b9319-120">Das folgende Beispiel zeigt verschiedene Arten, wie Zeilenkoordinaten und Stricheigenschaften angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="b9319-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="b9319-121">Die folgende Abbildung zeigt <xref:System.Windows.Shapes.Line>die gerenderte .</span><span class="sxs-lookup"><span data-stu-id="b9319-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="b9319-122">![Liniendarstellung](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="b9319-122">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="b9319-123">Obwohl <xref:System.Windows.Shapes.Line> die Klasse <xref:System.Windows.Shapes.Shape.Fill%2A> eine Eigenschaft bietet, hat <xref:System.Windows.Shapes.Line> das Festlegen keine Auswirkungen, da ein Bereich nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b9319-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="b9319-124">Eine weitere gemeinsame <xref:System.Windows.Shapes.Ellipse>Form ist die .</span><span class="sxs-lookup"><span data-stu-id="b9319-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="b9319-125">Erstellen <xref:System.Windows.Shapes.Ellipse> Sie eine, indem <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> Sie die Eigenschaften und Eigenschaften des Shapes definieren.</span><span class="sxs-lookup"><span data-stu-id="b9319-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="b9319-126">Um einen Kreis zu <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.FrameworkElement.Width%2A> zeichnen, geben Sie einen an, dessen und <xref:System.Windows.FrameworkElement.Height%2A> die Werte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b9319-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="b9319-127">Die folgende Abbildung zeigt ein <xref:System.Windows.Shapes.Ellipse>Beispiel für eine gerenderte .</span><span class="sxs-lookup"><span data-stu-id="b9319-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="b9319-128">![Ellipsendarstellung](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="b9319-128">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a><span data-ttu-id="b9319-129">Verwenden von Pfaden und Geometrien</span><span class="sxs-lookup"><span data-stu-id="b9319-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="b9319-130">Mit <xref:System.Windows.Shapes.Path> der Klasse können Sie Kurven und komplexe Formen zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b9319-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="b9319-131">Diese Kurven und Formen <xref:System.Windows.Media.Geometry> werden mithilfe von Objekten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9319-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="b9319-132">Um eine <xref:System.Windows.Shapes.Path>zu verwenden, erstellen Sie <xref:System.Windows.Media.Geometry> <xref:System.Windows.Shapes.Path> eine und <xref:System.Windows.Shapes.Path.Data%2A> verwenden sie, um die Eigenschaft des Objekts festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b9319-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="b9319-133">Es gibt eine <xref:System.Windows.Media.Geometry> Vielzahl von Objekten zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="b9319-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="b9319-134">Die <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>, <xref:System.Windows.Media.EllipseGeometry> und Klassen beschreiben relativ einfache Formen.</span><span class="sxs-lookup"><span data-stu-id="b9319-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="b9319-135">Um komplexere Formen zu erstellen <xref:System.Windows.Media.PathGeometry>oder Kurven zu erstellen, verwenden Sie eine .</span><span class="sxs-lookup"><span data-stu-id="b9319-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="b9319-136">PathGeometry und PathSegments</span><span class="sxs-lookup"><span data-stu-id="b9319-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="b9319-137"><xref:System.Windows.Media.PathGeometry>Objekte bestehen aus einem <xref:System.Windows.Media.PathFigure> oder mehreren Objekten; jede <xref:System.Windows.Media.PathFigure> stellt eine andere "Figur" oder Form dar.</span><span class="sxs-lookup"><span data-stu-id="b9319-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="b9319-138">Jedes <xref:System.Windows.Media.PathFigure> besteht aus einem <xref:System.Windows.Media.PathSegment> oder mehreren Objekten, die jeweils einen verbundenen Teil der Figur oder Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="b9319-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="b9319-139">Segmenttypen umfassen die <xref:System.Windows.Media.LineSegment> <xref:System.Windows.Media.BezierSegment>folgenden: <xref:System.Windows.Media.ArcSegment>, und .</span><span class="sxs-lookup"><span data-stu-id="b9319-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="b9319-140">Im folgenden Beispiel <xref:System.Windows.Shapes.Path> wird a verwendet, um eine quadratische Bézierkurve zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b9319-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="b9319-141">Die folgende Abbildung zeigt die gerenderte Form.</span><span class="sxs-lookup"><span data-stu-id="b9319-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="b9319-142">![Pfaddarstellung](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="b9319-142">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="b9319-143">Weitere Informationen <xref:System.Windows.Media.PathGeometry> zu und <xref:System.Windows.Media.Geometry> zu den anderen Klassen finden Sie in der [Geometrieübersicht](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b9319-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="b9319-144">Abgekürzte Syntax in XAML</span><span class="sxs-lookup"><span data-stu-id="b9319-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="b9319-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie auch eine spezielle abgekürzte <xref:System.Windows.Shapes.Path>Syntax verwenden, um eine zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="b9319-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="b9319-146">Im folgenden Beispiel wird abgekürzte Syntax verwendet, um eine komplexe Form zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b9319-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="b9319-147">Die folgende Abbildung zeigt <xref:System.Windows.Shapes.Path>eine gerenderte .</span><span class="sxs-lookup"><span data-stu-id="b9319-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="b9319-148">![Pfaddarstellung](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="b9319-148">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="b9319-149">Die <xref:System.Windows.Shapes.Path.Data%2A> Attributzeichenfolge beginnt mit dem Befehl "moveto", der durch M angegeben wird und einen <xref:System.Windows.Controls.Canvas>Startpunkt für den Pfad im Koordinatensystem des festlegt.</span><span class="sxs-lookup"><span data-stu-id="b9319-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="b9319-150"><xref:System.Windows.Shapes.Path>Datenparameter werden die Groß-/Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="b9319-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="b9319-151">Die Hauptstadt M gibt eine absolute Position für den neuen aktuellen Punkt an.</span><span class="sxs-lookup"><span data-stu-id="b9319-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="b9319-152">Ein kleingeschriebenes m würde relative Koordinaten angeben.</span><span class="sxs-lookup"><span data-stu-id="b9319-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="b9319-153">Das erste Segment ist eine kubische Bézierkurve, die bei (100.200) beginnt und bei (400.175) endet, gezeichnet mit den beiden Kontrollpunkten (100,25) und (400,350).</span><span class="sxs-lookup"><span data-stu-id="b9319-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="b9319-154">Dieses Segment wird durch den <xref:System.Windows.Shapes.Path.Data%2A> Befehl C in der Attributzeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9319-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="b9319-155">Ein großes C gibt erneut einen absoluten Pfad an. Ein kleingeschriebenes c würde einen relativen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="b9319-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="b9319-156">Das zweite Segment beginnt mit einem absoluten horizontalen „Lineto“-Befehl H, der eine Linie vom vorherigen untergeordneten Endpunkt (400,175) zu einem neuen Endpunkt (280,175) zeichnet.</span><span class="sxs-lookup"><span data-stu-id="b9319-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="b9319-157">Da es sich um einen horizontalen "lineto"-Befehl handelt, ist der angegebene Wert eine x-Koordinate. *x*</span><span class="sxs-lookup"><span data-stu-id="b9319-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="b9319-158">Die vollständige Pfadsyntax finden <xref:System.Windows.Shapes.Path.Data%2A> Sie im Verweis und [Erstellen einer Form mithilfe einer PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="b9319-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a><span data-ttu-id="b9319-159">Zeichnen von Formen</span><span class="sxs-lookup"><span data-stu-id="b9319-159">Painting Shapes</span></span>  
 <span data-ttu-id="b9319-160"><xref:System.Windows.Media.Brush>Objekte werden verwendet, um <xref:System.Windows.Shapes.Shape.Stroke%2A> die <xref:System.Windows.Shapes.Shape.Fill%2A>Unden einer Form zu malen.</span><span class="sxs-lookup"><span data-stu-id="b9319-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="b9319-161">Im folgenden Beispiel werden strichund <xref:System.Windows.Shapes.Ellipse> füllen eines angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9319-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="b9319-162">Beachten Sie, dass Pinseleigenschaften entweder ein Schlüsselwort oder einen hexadezimalen Farbwert werden können.</span><span class="sxs-lookup"><span data-stu-id="b9319-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="b9319-163">Weitere Informationen zu verfügbaren Farbschlüsselwörtern <xref:System.Windows.Media.Colors> finden Sie <xref:System.Windows.Media> unter Eigenschaften der Klasse im Namespace.</span><span class="sxs-lookup"><span data-stu-id="b9319-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
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
  
 <span data-ttu-id="b9319-164">Die folgende Abbildung zeigt <xref:System.Windows.Shapes.Ellipse>die gerenderte .</span><span class="sxs-lookup"><span data-stu-id="b9319-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="b9319-165">![Eine Ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="b9319-165">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="b9319-166">Alternativ können Sie die Eigenschaftenelementsyntax verwenden, um explizit ein <xref:System.Windows.Media.SolidColorBrush> Objekt zu erstellen, um die Form mit einer Volltonfarbe zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b9319-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
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
  
 <span data-ttu-id="b9319-167">Die folgende Abbildung zeigt die gerenderte Form.</span><span class="sxs-lookup"><span data-stu-id="b9319-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="b9319-168">![SolidColorBrush-Darstellung](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="b9319-168">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="b9319-169">Sie können die Kontur oder Fläche einer Form auch mit Farbverläufen, Bildern, Mustern und mehr zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b9319-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="b9319-170">Weitere Informationen finden Sie unter [Die Übersicht über Das Gemälde mit Vollfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b9319-170">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a><span data-ttu-id="b9319-171">Gestreckte Formen</span><span class="sxs-lookup"><span data-stu-id="b9319-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="b9319-172">Die <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>Klassen <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle> , , <xref:System.Windows.Shapes.Shape.Stretch%2A> und Klassen verfügen alle über eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b9319-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="b9319-173">Diese Eigenschaft bestimmt, wie der Inhalt eines <xref:System.Windows.Shapes.Shape> Objekts (die zu <xref:System.Windows.Shapes.Shape> zeichnende Form) gestreckt wird, um den Layoutbereich des Objekts zu füllen.</span><span class="sxs-lookup"><span data-stu-id="b9319-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="b9319-174">Der <xref:System.Windows.Shapes.Shape> Layoutbereich eines Objekts ist <xref:System.Windows.Shapes.Shape> der Platz, der vom Layoutsystem <xref:System.Windows.FrameworkElement.Width%2A> zugewiesen <xref:System.Windows.FrameworkElement.Height%2A> wird, entweder <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> aufgrund einer expliziten Einstellung und aufgrund seiner und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b9319-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="b9319-175">Weitere Informationen zum Layout in Windows Presentation Foundation finden Sie unter [Layoutübersicht.](../advanced/layout.md)</span><span class="sxs-lookup"><span data-stu-id="b9319-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="b9319-176">Die Stretch-Eigenschaft nimmt einen der folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="b9319-176">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="b9319-177"><xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird nicht gestreckt.</span><span class="sxs-lookup"><span data-stu-id="b9319-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="b9319-178"><xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird gestreckt, um seinen Layoutbereich zu füllen.</span><span class="sxs-lookup"><span data-stu-id="b9319-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="b9319-179">Das Seitenverhältnis wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b9319-179">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="b9319-180"><xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird so weit wie möglich gestreckt, um seinen Layoutraum zu füllen und gleichzeitig das ursprüngliche Seitenverhältnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9319-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="b9319-181"><xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird gestreckt, um seinen Layoutbereich vollständig zu füllen und gleichzeitig das ursprüngliche Seitenverhältnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9319-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="b9319-182">Beachten Sie, <xref:System.Windows.Shapes.Shape> dass beim Dehnen des Inhalts <xref:System.Windows.Shapes.Shape> eines Objekts die Umrisslinie des Objekts nach der Dehnung gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="b9319-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="b9319-183">Im folgenden Beispiel <xref:System.Windows.Shapes.Polygon> wird a verwendet, um ein sehr kleines Dreieck von (0,0) bis (0,1) bis (1,1) zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b9319-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="b9319-184">Das <xref:System.Windows.Shapes.Polygon> Objekt <xref:System.Windows.FrameworkElement.Width%2A> ist <xref:System.Windows.FrameworkElement.Height%2A> und auf 100 festgelegt ist, und seine Stretch-Eigenschaft ist auf Füllen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9319-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="b9319-185">Daher wird der <xref:System.Windows.Shapes.Polygon> Inhalt des Objekts (das Dreieck) gestreckt, um den größeren Raum zu füllen.</span><span class="sxs-lookup"><span data-stu-id="b9319-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
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
## <a name="transforming-shapes"></a><span data-ttu-id="b9319-186">Transformieren von Formen</span><span class="sxs-lookup"><span data-stu-id="b9319-186">Transforming Shapes</span></span>  
 <span data-ttu-id="b9319-187">Die <xref:System.Windows.Media.Transform> Klasse bietet die Möglichkeit, Formen in einer zweidimensionalen Ebene zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="b9319-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="b9319-188">Zu den verschiedenen Transformationstypen<xref:System.Windows.Media.RotateTransform>gehören Rotation ( ), Skalierung (<xref:System.Windows.Media.ScaleTransform>), Schiefe (<xref:System.Windows.Media.SkewTransform>) und Übersetzung (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="b9319-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="b9319-189">Eine allgemeine Transformation einer Form ist die Drehung.</span><span class="sxs-lookup"><span data-stu-id="b9319-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="b9319-190">Um eine Form zu <xref:System.Windows.Media.RotateTransform> drehen, <xref:System.Windows.Media.RotateTransform.Angle%2A>erstellen Sie eine, und geben Sie ihre an.</span><span class="sxs-lookup"><span data-stu-id="b9319-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="b9319-191">Eine <xref:System.Windows.Media.RotateTransform.Angle%2A> von 45 dreht das Element um 45 Grad im Uhrzeigersinn; ein Winkel von 90 dreht das Element um 90 Grad im Uhrzeigersinn; Und so weiter.</span><span class="sxs-lookup"><span data-stu-id="b9319-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="b9319-192">Legen <xref:System.Windows.Media.RotateTransform.CenterX%2A> Sie <xref:System.Windows.Media.RotateTransform.CenterY%2A> die und Eigenschaften fest, wenn Sie den Punkt steuern möchten, um den das Element gedreht wird.</span><span class="sxs-lookup"><span data-stu-id="b9319-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="b9319-193">Diese Eigenschaftswerte werden im Koordinatenraum des transformierten Elements ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="b9319-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="b9319-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A>und <xref:System.Windows.Media.RotateTransform.CenterY%2A> haben Standardwerte von Null.</span><span class="sxs-lookup"><span data-stu-id="b9319-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="b9319-195">Wenden Sie <xref:System.Windows.Media.RotateTransform> schließlich die auf das Element an.</span><span class="sxs-lookup"><span data-stu-id="b9319-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="b9319-196">Wenn sie nicht möchten, dass sich die Transformation <xref:System.Windows.UIElement.RenderTransform%2A> auf das Layout auswirkt, legen Sie die Eigenschaft des Shapes fest.</span><span class="sxs-lookup"><span data-stu-id="b9319-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="b9319-197">Im folgenden Beispiel <xref:System.Windows.Media.RotateTransform> wird eine verwendet, um eine Form um 45 Grad um die obere linke Ecke des Shapes (0,0) zu drehen.</span><span class="sxs-lookup"><span data-stu-id="b9319-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="b9319-198">Im nächsten Beispiel eine andere Form um 45 Grad gedreht wird, aber dieses Mal wird sie über den Punkt (25,50) gedreht.</span><span class="sxs-lookup"><span data-stu-id="b9319-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="b9319-199">In der folgenden Abbildung werden die Ergebnisse der Anwendung der zwei Transformationen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9319-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="b9319-200">![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="b9319-200">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="b9319-201">In den vorherigen Beispielen wurde eine einzelne Transformation auf jedes Shape-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="b9319-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="b9319-202">Um mehrere Transformationen auf ein Shape (oder ein <xref:System.Windows.Media.TransformGroup>anderes UI-Element) anzuwenden, verwenden Sie eine .</span><span class="sxs-lookup"><span data-stu-id="b9319-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9319-203">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9319-203">See also</span></span>

- [<span data-ttu-id="b9319-204">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="b9319-204">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="b9319-205">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="b9319-205">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="b9319-206">Übersicht über die Geometrie</span><span class="sxs-lookup"><span data-stu-id="b9319-206">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="b9319-207">Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung</span><span class="sxs-lookup"><span data-stu-id="b9319-207">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="b9319-208">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="b9319-208">Animation Overview</span></span>](animation-overview.md)
