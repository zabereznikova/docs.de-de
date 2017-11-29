---
title: "Übersicht über Pfadanimationen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 237dbe83fa52bb967d2f2429fb2beb021c084f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="path-animations-overview"></a>Übersicht über Pfadanimationen
<a name="introduction"></a> In diesem Thema werden Pfadanimationen beschrieben, die Ihnen ermöglichen, mithilfe eines geometrischen Pfads Ausgabewerte zu generieren. Pfadanimationen eignen sich zum Verschieben und Drehen von Objekten auf komplexen Pfaden.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit vertraut sein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animationen Funktionen. Eine Einführung zu Funktionen finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Da Sie verwenden eine <xref:System.Windows.Media.PathGeometry> Objekt, das eine Pfadanimation definieren Sie sollte auch mit vertraut sein <xref:System.Windows.Media.PathGeometry> und die verschiedenen Typen von <xref:System.Windows.Media.PathSegment> Objekte. Weitere Informationen finden Sie unter der [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>Was ist eine Pfadanimation?  
 Eine Path-Animation ist eine Art von <xref:System.Windows.Media.Animation.AnimationTimeline> , verwendet eine <xref:System.Windows.Media.PathGeometry> als Eingabe. Statt eine From zu festzulegen oder Eigenschaft (wie bei einem From/zu/von Animation) oder Keyframes wie (Sie für einen Keyframe-Animation verwenden), einen geometrischen Pfad zu definieren und verwenden, um festzulegen der `PathGeometry` -Eigenschaft der Pfadanimation. Die Pfadanimation liest im Verlauf die x-, y- und Winkelinformationen aus dem Pfad und generiert mithilfe dieser Informationen ihre Ausgabe.  
  
 Pfadanimationen sind sehr nützlich, um ein Objekt auf einem komplexen Pfad zu animieren. Eine Möglichkeit zum Verschieben, ein Objekt entlang eines Pfads ist die Verwendung einer <xref:System.Windows.Media.MatrixTransform> und ein <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zum Transformieren eines Objekts einem komplexen Pfad. Das folgende Beispiel veranschaulicht dieses Verfahren mithilfe der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>. Die <xref:System.Windows.Media.MatrixTransform> wird auf eine Schaltfläche angewendet und bewirkt, dass es entlang eines Kurvenpfads zu verschieben. Da die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> -Eigenschaftensatz auf `true`, das Rechteck entlang der Tangente des Pfads gedreht wird.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Weitere Informationen über die Pfadsyntax in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beispielsweise finden Sie unter der [Markup Pfadsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) (Übersicht). Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Sie können eine Path-Animation auf eine Eigenschaft anwenden, mit einem <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und code oder mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode im Code. Sie können auch eine Path-Animation zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und wendet ihn auf eine oder mehrere Eigenschaften. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen, finden Sie unter [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Pfadanimationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Double> (z. B. die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft eine <xref:System.Windows.Media.TranslateTransform>), verwenden Sie eine Animation, die erzeugt <xref:System.Double> Werte. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Windows.Point>, verwenden Sie eine Animation, die erzeugt <xref:System.Windows.Point> Werte und So weiter.  
  
 Pfad Animationsklassen gehören zu den <xref:System.Windows.Media.Animation> Namespace und die folgende Benennungskonvention:  
  
 *\<Typ>* `AnimationUsingPath`  
  
 Wobei *\<Typ>* der Wertetyp ist, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet folgende Pfadanimationsklassen.  
  
|Eigenschaftentyp|Entsprechende Pfadanimationsklasse|Beispiel|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Verschieben eines Objekts auf einem Pfad (DoubleAnimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animieren eines Objekts auf einem Pfad (MatrixAnimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animieren eines Objekts entlang eines Pfads (Punktanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Ein <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> generiert <xref:System.Windows.Media.Matrix> Werte aus der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. Bei Verwendung mit einem <xref:System.Windows.Media.MatrixTransform>, eine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> kann ein Objekt entlang eines Pfads zu verschieben. Wenn Sie festlegen, die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> auf `true`, es auch wird das Objekt entlang der Kurve des Pfads gedreht.  
  
 Ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath> generiert <xref:System.Windows.Point> Werte aus den x- und y-Koordinaten von seiner <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. Mithilfe einer <xref:System.Windows.Media.Animation.PointAnimationUsingPath> eine Eigenschaft animieren, akzeptiert <xref:System.Windows.Point> Werte, können Sie ein Objekt entlang eines Pfads verschieben. Ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath> Objekte können nicht gedreht werden kann.  
  
 Ein <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> generiert <xref:System.Double> Werte aus der <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Durch Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> -Eigenschaft, können Sie angeben, ob die <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> die X-Koordinate, die y-Koordinate oder den Winkel des Pfads als Ausgabe verwendet. Sie können eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> zum Drehen eines Objekts oder verschieben Sie sie auf der x-Achse oder y-Achse.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Pfadanimationseingabe  
 Jeder Pfad Animation-Klasse wird eine <xref:System.Windows.Media.PathGeometry> Eigenschaft zur Angabe der Eingabe. Die Pfadanimation verwendet, die <xref:System.Windows.Media.PathGeometry> Generieren der Ausgabewerte. Die <xref:System.Windows.Media.PathGeometry> Klasse können Sie mehrere komplexe Zahlen zu beschreiben, die aus Bögen, Kurven und Linien bestehen.  
  
 Der Kern von einem <xref:System.Windows.Media.PathGeometry> ist eine Sammlung von <xref:System.Windows.Media.PathFigure> Objekten; diese Objekte werden so genannt, da jeder Zahl in eine diskrete Form beschreibt die <xref:System.Windows.Media.PathGeometry>. Jede <xref:System.Windows.Media.PathFigure> besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jede ein Segment der Abbildung beschreibt.  
  
 Es gibt viele Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bézierkurve zwischen zwei Punkten.|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubischen Bézierkurven.|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe von quadratischen Bézierkurven.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bézierkurve.|  
  
 Die Segmente in einem <xref:System.Windows.Media.PathFigure> eine einzelne geometrische Form, das den Ausgangspunkt des nächsten Segments am Ende eines Segments verwendet zusammengefasst werden. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft von einem <xref:System.Windows.Media.PathFigure> gibt den Punkt, von dem das erste Segment gezeichnet wird. Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments. Z. B. eine vertikale Linie von `10,50` auf `10,150` können definiert werden, indem die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft, um `10,50` und erstellen eine <xref:System.Windows.Media.LineSegment> mit einer <xref:System.Windows.Media.LineSegment.Point%2A> eigenschaftseinstellung `10,150`.  
  
 Weitere Informationen zu <xref:System.Windows.Media.PathGeometry> anzuzeigen, die [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine besondere abgekürzte Syntax zum Festlegen der <xref:System.Windows.Media.PathGeometry.Figures%2A> Eigenschaft eine <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie unter [Markup Pfadsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) (Übersicht).  
  
 Weitere Informationen über die Pfadsyntax in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beispielsweise finden Sie unter der [Markup Pfadsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) (Übersicht).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel zu Textanimation](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
