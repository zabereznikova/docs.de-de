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
ms.openlocfilehash: 07628d26c8222c7c01f58826a36a15e13dc31ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181869"
---
# <a name="path-animations-overview"></a>Übersicht über Pfadanimationen
<a name="introduction"></a> In diesem Thema werden Pfadanimationen beschrieben, die Ihnen ermöglichen, mithilfe eines geometrischen Pfads Ausgabewerte zu generieren. Pfadanimationen eignen sich zum Verschieben und Drehen von Objekten auf komplexen Pfaden.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Um dieses Thema zu verstehen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sollten Sie mit Animationsfeatures vertraut sein. Eine Einführung in Animationsfeatures finden Sie in der [Animationsübersicht](animation-overview.md).  
  
 Da Sie <xref:System.Windows.Media.PathGeometry> ein Objekt zum Definieren einer Pfadanimation <xref:System.Windows.Media.PathGeometry> verwenden, sollten <xref:System.Windows.Media.PathSegment> Sie auch mit den verschiedenen Objekttypen vertraut sein. Weitere Informationen finden Sie in der [Geometrieübersicht](geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>
## <a name="what-is-a-path-animation"></a>Was ist eine Pfadanimation?  
 Eine Pfadanimation ist <xref:System.Windows.Media.Animation.AnimationTimeline> ein Typ <xref:System.Windows.Media.PathGeometry> von, der eine als Eingabe verwendet. Anstatt eine Von-, Bis- oder By-Eigenschaft festzulegen (wie Sie es bei einer Von/To/By-Animation tun) oder Keyframes zu verwenden `PathGeometry` (wie Sie es für eine Keyframe-Animation verwenden), definieren Sie einen geometrischen Pfad und verwenden ihn, um die Eigenschaft der Pfadanimation festzulegen. Die Pfadanimation liest im Verlauf die x-, y- und Winkelinformationen aus dem Pfad und generiert mithilfe dieser Informationen ihre Ausgabe.  
  
 Pfadanimationen sind sehr nützlich, um ein Objekt auf einem komplexen Pfad zu animieren. Eine Möglichkeit, ein Objekt entlang eines <xref:System.Windows.Media.MatrixTransform> Pfads <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu verschieben, besteht darin, ein Und ein zu verwenden, um ein Objekt entlang eines komplexen Pfads zu transformieren. Im folgenden Beispiel wird diese <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Technik veranschaulicht, indem das Objekt verwendet wird, um die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft einer <xref:System.Windows.Media.MatrixTransform>zu animieren. Der <xref:System.Windows.Media.MatrixTransform> wird auf eine Schaltfläche angewendet und bewirkt, dass er sich entlang eines gekrümmten Pfads bewegt. Da <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> die Eigenschaft `true`auf festgelegt ist, wird das Rechteck entlang der Tangente des Pfads gedreht.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Weitere Informationen zur Pfadsyntax, die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] im Beispiel verwendet wird, finden Sie in der Übersicht [Pfadmarkupsyntax.](path-markup-syntax.md) Das vollständige Beispiel finden Sie unter [Pfadanimationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 Sie können eine Pfadanimation auf eine <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Eigenschaft anwenden, indem <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Sie ein In und Code oder die Methode im Code verwenden. Sie können auch eine Pfadanimation <xref:System.Windows.Media.Animation.AnimationClock> verwenden, um eine zu erstellen und auf eine oder mehrere Eigenschaften anzuwenden. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie unter [Übersicht über Eigenschaftenanimationstechniken](property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>
## <a name="path-animation-types"></a>Pfadanimationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen. Um eine Eigenschaft zu <xref:System.Double> animieren, die eine (z. B. die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft a ) <xref:System.Windows.Media.TranslateTransform>annimmt, verwenden Sie eine Animation, die Werte erzeugt. <xref:System.Double> Um eine Eigenschaft zu <xref:System.Windows.Point>animieren, die <xref:System.Windows.Point> eine verwendet, verwenden Sie eine Animation, die Werte erzeugt usw.  
  
 Pfadanimationsklassen gehören <xref:System.Windows.Media.Animation> zum Namespace und verwenden die folgende Namenskonvention:  
  
 * \<Typ>*`AnimationUsingPath`  
  
 Wobei * \<Typ>* ist der Werttyp, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet folgende Pfadanimationsklassen.  
  
|Eigenschaftstyp|Entsprechende Pfadanimationsklasse|Beispiel|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Verschieben eines Objekts auf einem Pfad (DoubleAnimation)](how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animieren eines Objekts auf einem Pfad (MatrixAnimation)](how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animieren eines Objekts entlang eines Pfads (Punktanimation)](how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 A <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> <xref:System.Windows.Media.Matrix> generiert Werte <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>aus seiner . Bei Verwendung <xref:System.Windows.Media.MatrixTransform>mit <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> einem kann a ein Objekt entlang eines Pfads verschieben. Wenn Sie <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> die Eigenschaft <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> `true`des festlegen, wird das Objekt auch entlang der Kurven des Pfads gedreht.  
  
 A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> <xref:System.Windows.Point> generiert Werte aus den x- <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>und y-Koordinaten seiner . Wenn Sie <xref:System.Windows.Media.Animation.PointAnimationUsingPath> eine zum Animieren einer Eigenschaft verwenden, die Werte annimmt, <xref:System.Windows.Point> können Sie ein Objekt entlang eines Pfads verschieben. A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> kann Keine Objekte drehen.  
  
 A <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Double> generiert Werte <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>aus seiner . Durch Festlegen <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> der Eigenschaft können <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Sie angeben, ob die x-Koordinate, y-Koordinate oder den Winkel des Pfads als Ausgabe verwendet. Sie können <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> ein verwenden, um ein Objekt zu drehen oder entlang der x-Achse oder y-Achse zu verschieben.  
  
<a name="pathanimationinput"></a>
## <a name="path-animation-input"></a>Pfadanimationseingabe  
 Jede Pfadanimationsklasse <xref:System.Windows.Media.PathGeometry> stellt eine Eigenschaft zum Angeben ihrer Eingabe bereit. Die Pfadanimation <xref:System.Windows.Media.PathGeometry> verwendet die, um ihre Ausgabewerte zu generieren. Mit <xref:System.Windows.Media.PathGeometry> der Klasse können Sie mehrere komplexe Figuren beschreiben, die aus Bögen, Kurven und Linien bestehen.  
  
 Im Zentrum von <xref:System.Windows.Media.PathGeometry> a ist <xref:System.Windows.Media.PathFigure> eine Sammlung von Objekten; Diese Objekte sind so benannt, weil jede <xref:System.Windows.Media.PathGeometry>Abbildung eine diskrete Form im beschreibt. Jedes <xref:System.Windows.Media.PathFigure> besteht aus <xref:System.Windows.Media.PathSegment> einem oder mehreren Objekten, von denen jedes ein Segment der Figur beschreibt.  
  
 Es gibt viele Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bézierkurve zwischen zwei Punkten.|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubischen Bézierkurven.|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe quadratischer Bézierkurven.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bézierkurve.|  
  
 Die Segmente <xref:System.Windows.Media.PathFigure> in einem werden zu einer einzelnen geometrischen Form kombiniert, die den Endpunkt eines Segments als Startpunkt des nächsten Segments verwendet. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft <xref:System.Windows.Media.PathFigure> eines gibt den Punkt an, von dem das erste Segment gezeichnet wird. Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments. Beispielsweise kann eine vertikale `10,50` `10,150` Linie von zu <xref:System.Windows.Media.PathFigure.StartPoint%2A> definiert `10,50` werden, <xref:System.Windows.Media.LineSegment> indem <xref:System.Windows.Media.LineSegment.Point%2A> die Eigenschaft `10,150`auf und das Erstellen einer mit einer Eigenschaftseinstellung von festgelegt wird.  
  
 Weitere Informationen <xref:System.Windows.Media.PathGeometry> zu Objekten finden Sie in der [Geometrieübersicht](geometry-overview.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie auch eine spezielle abgekürzte <xref:System.Windows.Media.PathGeometry.Figures%2A> Syntax verwenden, um die Eigenschaft einer <xref:System.Windows.Media.PathGeometry>festzulegen. Weitere Informationen finden Sie unter [Pfadmarkupsyntaxübersicht.](path-markup-syntax.md)  
  
 Weitere Informationen zur Pfadsyntax, die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] im Beispiel verwendet wird, finden Sie in der Übersicht [Pfadmarkupsyntax.](path-markup-syntax.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Beispiel einer Pfadanimation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Pfadmarkupsyntax](path-markup-syntax.md)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
