---
title: Übersicht über Pfadanimationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
ms.openlocfilehash: 0f795ad00823e7b1c37221f7417b09d3982c4c18
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43800205"
---
# <a name="path-animations-overview"></a>Übersicht über Pfadanimationen
<a name="introduction"></a> In diesem Thema werden Pfadanimationen beschrieben, die Ihnen ermöglichen, mithilfe eines geometrischen Pfads Ausgabewerte zu generieren. Pfadanimationen eignen sich zum Verschieben und Drehen von Objekten auf komplexen Pfaden.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit vertraut sein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Animationsfunktionen. Eine Einführung in Animationsfunktionen, finden Sie unter den [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Da Sie verwenden eine <xref:System.Windows.Media.PathGeometry> Objekt um eine Pfadanimation zu definieren. Sie sollten auch mit vertraut sein <xref:System.Windows.Media.PathGeometry> und die verschiedenen Typen von <xref:System.Windows.Media.PathSegment> Objekte. Weitere Informationen finden Sie unter den [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>Was ist eine Pfadanimation?  
 Eine Pfadanimation ist eine Art von <xref:System.Windows.Media.Animation.AnimationTimeline> , verwendet eine <xref:System.Windows.Media.PathGeometry> als Eingabe. Anstatt eine FROM-, to- oder By-Eigenschaft (wie bei einer From/To/By Animation) oder mithilfe von Keyframes (wie Sie für eine Keyframe Animation verwenden), Sie definieren einen geometrischen Pfad und die Verwendung zur Festlegung der `PathGeometry` -Eigenschaft der Pfadanimation. Die Pfadanimation liest im Verlauf die x-, y- und Winkelinformationen aus dem Pfad und generiert mithilfe dieser Informationen ihre Ausgabe.  
  
 Pfadanimationen sind sehr nützlich, um ein Objekt auf einem komplexen Pfad zu animieren. Eine Möglichkeit zum Verschieben ein Objekts entlang eines Pfads ist die Verwendung einer <xref:System.Windows.Media.MatrixTransform> und <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zum Transformieren eines Objekts entlang eines komplexen Pfads. Das folgende Beispiel veranschaulicht dieses Verfahren mithilfe der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>. Die <xref:System.Windows.Media.MatrixTransform> ist auf eine Schaltfläche angewendet und bewirkt, dass es entlang eines gekrümmten Pfads verschoben. Da die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> -Eigenschaftensatz auf `true`, dreht sich das Rechteck entlang der Tangente des Pfads.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Weitere Informationen zur Pfadsyntax, die verwendet wird die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel finden Sie unter der [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Übersicht. Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Sie können eine Pfadanimation auf eine Eigenschaft anwenden, mit einem <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und code oder mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode im Code. Sie können auch eine Pfadanimation zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und auf eine oder mehrere Eigenschaften anwenden. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie unter [Eigenschaft Techniken-Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Pfadanimationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen. Zum Animieren einer Eigenschaft, die akzeptiert eine <xref:System.Double> (z. B. die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft eine <xref:System.Windows.Media.TranslateTransform>), verwenden Sie eine Animation, die erzeugt <xref:System.Double> Werte. Zum Animieren einer Eigenschaft, die akzeptiert eine <xref:System.Windows.Point>, verwenden Sie eine Animation, die erzeugt <xref:System.Windows.Point> Werte und So weiter.  
  
 Pfadanimationsklassen gehören zu den <xref:System.Windows.Media.Animation> Namespace und verwenden Sie die folgende Benennungskonvention verwendet:  
  
 *\<Typ>* `AnimationUsingPath`  
  
 Wobei *\<Typ>* der Wertetyp ist, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet folgende Pfadanimationsklassen.  
  
|Eigenschaftentyp|Entsprechende Pfadanimationsklasse|Beispiel|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Verschieben eines Objekts auf einem Pfad (DoubleAnimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animieren eines Objekts auf einem Pfad (MatrixAnimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animieren eines Objekts entlang eines Pfads (Punktanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Ein <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> generiert <xref:System.Windows.Media.Matrix> Werte aus der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. Bei Verwendung mit einem <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> können ein Objekt entlang eines Pfads verschieben. Setzen Sie die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu `true`, es wird auch das Objekt auf den Kurven des Pfads.  
  
 Ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath> generiert <xref:System.Windows.Point> Werte aus den x- und y-Koordinaten von dessen <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. Mithilfe einer <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zum Animieren einer Eigenschaft, die akzeptiert <xref:System.Windows.Point> Werte, Sie können ein Objekt entlang eines Pfads verschieben. Ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath> kann Objekte nicht drehen.  
  
 Ein <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> generiert <xref:System.Double> Werte aus der <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Durch Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> -Eigenschaft, können Sie angeben, ob die <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> verwendet die X-Koordinate, y-Koordinate oder Winkel des Pfads als Ausgabe. Sie können eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> zum Drehen eines Objekts oder verschieben Sie sie auf der x-Achse oder y-Achse.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Pfadanimationseingabe  
 Jede Pfadanimation bietet eine <xref:System.Windows.Media.PathGeometry> Eigenschaft zum Angeben ihrer Eingabe. Die Pfadanimation verwendet die <xref:System.Windows.Media.PathGeometry> um ihre Ausgabewerte zu generieren. Die <xref:System.Windows.Media.PathGeometry> Klasse können Sie die Beschreibung mehrerer komplexer Figuren, die aus Bögen, Kurven und Linien zusammengesetzt sind.  
  
 Das Kernstück einer <xref:System.Windows.Media.PathGeometry> ist eine Sammlung von <xref:System.Windows.Media.PathFigure> Objekte, die diese Objekte werden so genannt, da jede Figur eine diskrete Form in beschreibt die <xref:System.Windows.Media.PathGeometry>. Jede <xref:System.Windows.Media.PathFigure> besteht aus einem oder mehreren <xref:System.Windows.Media.PathSegment> -Objekt, von denen jeder ein Segment der Figur beschreibt.  
  
 Es gibt viele Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bezier-Kurve zwischen zwei Punkten.|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubische Bezier-Kurven.|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe von quadratischen Bezier-Kurven.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bezierkurve.|  
  
 Die Segmente in einem <xref:System.Windows.Media.PathFigure> werden in einer einzelnen geometrischen Form, die den Endpunkt eines Segments als Startpunkt des nächsten Segments verwendet kombiniert. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft eine <xref:System.Windows.Media.PathFigure> gibt den Punkt, von dem das erste Segment gezeichnet wird. Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments. Z. B. eine vertikale Linie von `10,50` zu `10,150` definiert werden, indem Sie die Einstellung der <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft, um `10,50` und erstellen eine <xref:System.Windows.Media.LineSegment> mit eine <xref:System.Windows.Media.LineSegment.Point%2A> eigenschaftseinstellung `10,150`.  
  
 Weitere Informationen zu <xref:System.Windows.Media.PathGeometry> Objekten finden Sie die [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine besondere abgekürzte Syntax verwenden, Festlegen der <xref:System.Windows.Media.PathGeometry.Figures%2A> Eigenschaft eine <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie unter [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Übersicht.  
  
 Weitere Informationen zur Pfadsyntax, die verwendet wird die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel finden Sie unter der [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Übersicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028)  
 [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
