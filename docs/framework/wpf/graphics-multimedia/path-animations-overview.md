---
title: "&#220;bersicht &#252;ber Pfadanimationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation Pfade"
  - "Pfadanimationen"
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber Pfadanimationen
<a name="introduction"></a>In diesem Thema werden Pfadanimationen beschrieben, die Ihnen ermöglichen, mithilfe eines geometrischen Pfads Ausgabewerte zu generieren. Pfadanimationen eignen sich zum Verschieben und Drehen von Objekten auf komplexen Pfaden.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit vertraut sein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animationen Funktionen. Eine Einführung in Animationsfeatures finden Sie in der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Da Sie verwenden ein <xref:System.Windows.Media.PathGeometry> Objekts, um eine Pfadanimation definieren Sie sollten auch mit vertraut sein <xref:System.Windows.Media.PathGeometry> und die verschiedenen Typen von <xref:System.Windows.Media.PathSegment> Objekte. Weitere Informationen finden Sie unter der [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>Was ist eine Pfadanimation?  
 Eine Pfadanimation ist ein Typ von <xref:System.Windows.Media.Animation.AnimationTimeline> , verwendet eine <xref:System.Windows.Media.PathGeometry> als Eingabe. Anstelle eine FROM-, to- oder By-Eigenschaft (wie für eine From/To/By Animation) oder mithilfe von Keyframes (wie bei einer Keyframe-Animation verwenden), definieren ein geometrisches Pfads und Verwendung zur Festlegung der `PathGeometry` -Eigenschaft der Pfadanimation. Als Durchlaufen der Pfadanimation liest die X, y und Informationen aus dem Pfad und verwendet diese Informationen, um die Ausgabe zu generieren.  
  
 Pfadanimationen sind sehr nützlich zum Animieren eines Objekts entlang eines Pfads komplexer. Eine Möglichkeit zum Verschieben ein Objekts entlang eines Pfads ist die Verwendung einer <xref:System.Windows.Media.MatrixTransform> und <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> auf einem komplexen Pfad zu transformieren. Im folgende Beispiel wird diese Technik veranschaulicht, mit der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft ein <xref:System.Windows.Media.MatrixTransform>. Die <xref:System.Windows.Media.MatrixTransform> wird auf eine Schaltfläche angewendet und bewirkt, dass sie einem gekrümmten Pfad verschoben. Da die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> -Eigenschaft wird festgelegt, um `true`, das Rechteck an der Tangente des Pfads gedreht wird.  
  
 [!code-xml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Weitere Informationen zu der Syntax, die in verwendet wird die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel finden Sie unter der [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) (Übersicht). Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Sie können eine Pfadanimation auf eine Eigenschaft anwenden, mit einem <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und code oder mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> -Methode im Code. Sie können auch eine Pfadanimation zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und auf eine oder mehrere Eigenschaften anwenden. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie unter [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Pfad Animationstypen  
 Da Animationen Eigenschaftswerte generieren, sind gibt es für verschiedene Eigenschaftentypen unterschiedliche Animationstypen. Zum Animieren einer Eigenschaft, die akzeptiert ein <xref:System.Double> (wie z. B. die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft ein <xref:System.Windows.Media.TranslateTransform>), verwenden Sie eine Animation, die erstellt <xref:System.Double> Werte. Eine Eigenschaft animieren, akzeptiert ein <xref:System.Windows.Point>, verwenden Sie eine Animation, die erzeugt <xref:System.Windows.Point> Werte usw..  
  
 Pfad-Animationsklassen gehören zu den <xref:System.Windows.Media.Animation> Namespace und verwenden die folgende Benennungskonvention:  
  
 *<>\>*`AnimationUsingPath`  
  
 Wobei * <> \> * ist der Typ des Werts, der die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Stellt die folgenden Animationsklassen bereit.  
  
|Eigenschaftentyp|Entsprechende Path Animation-Klasse|Beispiel|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Animieren eines Objekts auf einem Pfad (DoubleAnimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animieren eines Objekts entlang eines Pfads (Matrixanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animieren eines Objekts entlang eines Pfads (Punktanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Ein <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> generiert <xref:System.Windows.Media.Matrix> Werte aus den <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. Bei Verwendung mit einer <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> können ein Objekt auf einem Pfad verschieben. Wenn Sie festlegen der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> , `true`, auch das Objekt entlang der Kurve des Pfads drehen.  
  
 Ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath> generiert <xref:System.Windows.Point> Werte aus den x- und y-Koordinaten von seiner <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. Mithilfe einer <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zum Animieren einer Eigenschaft, die akzeptiert <xref:System.Windows.Point> Werte, Sie können ein Objekt auf einem Pfad verschieben. Ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath> kann Objekte nicht drehen.  
  
 Ein <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> generiert <xref:System.Double> Werte aus den <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Durch Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> -Eigenschaft können Sie angeben, ob die <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> der X-Koordinate, die y-Koordinate oder den Winkel des Pfads als Ausgabe verwendet. Sie können eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Drehen eines Objekts oder auf der x-Achse oder y-Achse verschieben.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Eingabe für Path-Animation  
 Jeder Pfad Animation-Klasse stellt einen <xref:System.Windows.Media.PathGeometry> Eigenschaft zum Angeben der Eingabe. Der Pfadanimation werden mithilfe der <xref:System.Windows.Media.PathGeometry> die Ausgabewerte zu generieren. Die <xref:System.Windows.Media.PathGeometry> -Klasse können Sie mehrere komplexe Figuren beschreiben, die aus Bögen, Kurven und Linien zusammengesetzt sind.  
  
 Im Wesentlichen eine <xref:System.Windows.Media.PathGeometry> ist eine Sammlung von <xref:System.Windows.Media.PathFigure> Objekte, die diese Objekte werden so genannt, da jede Figur eine eigenständige Form in beschreibt die <xref:System.Windows.Media.PathGeometry>. Jede <xref:System.Windows.Media.PathFigure> besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jede ein Segment der Abbildung beschreibt.  
  
 Es gibt viele Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bézier-Kurve zwischen zwei Punkten.|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubische Bezier-Kurven.|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe von quadratische Bézier-Kurven.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bézier-Kurve.|  
  
 Die Segmente in einem <xref:System.Windows.Media.PathFigure> zu einer einzelnen geometrischen Form, die den Endpunkt eines Segments als Startpunkt des nächsten Segments verwendet kombiniert. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft ein <xref:System.Windows.Media.PathFigure> gibt den Punkt, von dem das erste Segment gezeichnet wird. Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments. Z. B. eine vertikale Linie von `10,50` auf `10,150` können definiert werden, indem die <xref:System.Windows.Media.PathFigure.StartPoint%2A> -Eigenschaft auf `10,50` und erstellen eine <xref:System.Windows.Media.LineSegment> mit einer <xref:System.Windows.Media.LineSegment.Point%2A> Einstellung der Eigenschaft der `10,150`.  
  
 Weitere Informationen zu <xref:System.Windows.Media.PathGeometry> von Objekten finden Sie die [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine besondere abgekürzte Syntax verwenden, um festzulegen der <xref:System.Windows.Media.PathGeometry.Figures%2A> Eigenschaft ein <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie unter [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) (Übersicht).  
  
 Weitere Informationen zu der Syntax, die in verwendet wird die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel finden Sie unter der [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) (Übersicht).  
  
## <a name="see-also"></a>Siehe auch  
 [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)   
 [Pfad-Themen zur Pfadanimation](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)   
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)