---
title: "Übersicht über Keyframe-Animationen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], key-frame
- key frames [WPF], about key-frame animations
- multiple animation target values [WPF]
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c4f4179087679ff891c705cf16693fc69c808d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="key-frame-animations-overview"></a>Übersicht über Keyframe-Animationen
Dieses Thema bietet eine Einführung in Keyframe-Animationen. Mit Keyframe-Animationen können Sie bei Animationen mehr als zwei Zielwerte animieren und die Interpolationsmethode einer Animation steuern.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für diese Übersicht sollten Sie mit Animationen und Zeitachsen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vertraut sein. Eine Einführung zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Kenntnisse in From/To/By-Animationen sind ebenfalls hilfreich. Weitere Informationen finden Sie unter „Übersicht über From/To/by-Animationen“.  
  
<a name="whatisakeyframeanimation"></a>   
## <a name="what-is-a-key-frame-animation"></a>Was ist eine Keyframe-Animation?  
 Wie eine From/To/By-Animation animiert eine Keyframe-Animation den Wert einer Zieleigenschaft. Erstellt einen Übergang zwischen den Zielwerten über seine <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Während eine From/To/By-Animation einen Übergang zwischen zwei Werten erstellt, kann eine einzelne Keyframe-Animation jedoch Übergänge zwischen einer beliebigen Anzahl von Zielwerten erstellen. Im Gegensatz zu einer From/To/By-Animation besitzt eine Keyframe-Animation keine From/To/by-Eigenschaften, mit denen die Zielwerte festgelegt werden könnten. Die Zielwerte einer Keyframe-Animation werden mithilfe von Keyframe-Objekten beschrieben (daher der Begriff „Keyframe-Animation“). Zum Angeben der Animation Zielwerten Keyframeobjekte erstellt und der Animation hinzugefügt <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> Auflistung. Wenn die Animation ausgeführt wird, erstellt sie Übergänge zwischen den Frames, die Sie angegeben haben.  
  
 Einige Keyframe-Methoden unterstützen nicht nur mehrere Zielwerte, sondern sogar mehrere Interpolationsmethoden. Die Interpolationsmethode einer Animation definiert, wie sie einen Übergang von einem Wert zum nächsten erstellt. Es gibt drei Arten von Interpolationen: diskret, linear und Spline.  
  
 Um Animationen mit einer Keyframe-Animation auszuführen, gehen Sie folgendermaßen vor.  
  
-   Deklarieren Sie die Animation, und geben Sie ihre <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, ebenso wie für eine Animation vom/auf/von.  
  
-   Für jeden Zielwert einen Keyframe des entsprechenden Typs zu erstellen, legen Sie dessen Wert und <xref:System.Windows.Media.Animation.KeyTime>, und fügen Sie es auf der Animation <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> Auflistung.  
  
-   Ordnen Sie der Animation eine Eigenschaft zu, genau so wie bei einer From/To/By-Animation. Weitere Informationen zum Anwenden einer Animation auf eine Eigenschaft mit einem Storyboard finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> zum Animieren einer <xref:System.Windows.Shapes.Rectangle> Element an vier verschiedene Positionen.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
 Wie eine From/To/By Animation, mithilfe eine Keyframe Animation auf eine Eigenschaft angewendet werden kann eine <xref:System.Windows.Media.Animation.Storyboard> in Markup und Code oder mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode im Code. Sie können auch eine Keyframe Animation zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und wendet ihn auf eine oder mehrere Eigenschaften. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="key-frame-animation-types"></a>Keyframe-Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Double> (z. B. ein Element <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft), verwenden Sie eine Animation, die erzeugt <xref:System.Double> Werte. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Windows.Point>, verwenden Sie eine Animation, die erzeugt <xref:System.Windows.Point> Werte und So weiter.  
  
 Die Keyframe-Animation-Klassen gehören zu den <xref:System.Windows.Media.Animation> Namespace und die folgende Benennungskonvention befolgen:  
  
 *\<Typ>* `AnimationUsingKeyFrames`  
  
 Wobei *\<Typ>* der Wertetyp ist, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet folgende Keyframe-Animationsklassen.  
  
|Eigenschaftentyp|Entsprechende From/To/By-Animationsklassen|Unterstützte Interpolationsmethoden|  
|-------------------|------------------------------------------------|-------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|Diskret, linear, Spline|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|Diskret, linear, Spline|  
  
<a name="animation_target_values"></a>   
## <a name="target-values-key-frames-and-key-times"></a>Zielwerte (Keyframes) und Schlüsselzeiten  
 Ebenso wie es verschiedene Typen von Keyframe-Animationen zum Animieren verschiedener Eigenschaftentypen gibt, gibt es auch verschiedene Typen von Keyframe-Objekten: einen für jeden animierten Werttyp und jede unterstützte Interpolationsmethode. Keyframe-Typen entsprechen der folgenden Benennungskonvention:  
  
 *\<InterpolationMethod>\<Typ>* `KeyFrame`  
  
 Wobei *\<InterpolationMethod>* für die Interpolationsmethode steht, die der Keyframe verwendet, und *\<Typ>* für den Werttyp, den die Klasse animiert. Eine Keyframe-Animation, die alle drei Interpolationsmethoden unterstützt, besitzt drei Keyframe-Typen, die Sie verwenden können. Sie können z. B. drei Keyframe-Typen mit einem <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>: <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>, und <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>. (Interpolationsmethoden werden in einem späteren Abschnitt ausführlich beschrieben.)  
  
 Der Hauptzweck eines Keyframes ist die Angabe einer <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> und ein <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>. Jeder Keyframe-Typ stellt diese zwei Eigenschaften bereit.  
  
-   Die <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> Eigenschaft gibt den Zielwert für diesen Keyframe.  
  
-   Die <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> Eigenschaft gibt an, wann (innerhalb der Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A>) des Keyframes <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> erreicht ist.  
  
 Wenn eine Keyframe-Animation beginnt, durchläuft den Keyframes in der Reihenfolge von definiert ihre <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> Eigenschaften.  
  
-   Wenn kein Keyframe zum Zeitpunkt 0 vorhanden ist, erstellt die Animation einen Übergang zwischen dem aktuellen Wert der Zieleigenschaft und die <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> des ersten Keyframes; andernfalls die Animation Ausgabe des Wert wird der Wert des ersten Keyframes.  
  
-   Die Animation erstellt einen Übergang zwischen den <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> der ersten und zweiten Keyframes, die mit der durch den zweiten Keyframe angegebenen Interpolationsmethode. Der Übergang beginnt an der ersten Keyframes <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> und endet, wenn die zweite Keyframes <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> erreicht ist.  
  
-   Die Animation wird fortgesetzt und erstellt Übergänge zwischen jedem nachfolgenden Keyframe und dem vorangehenden Keyframe.  
  
-   Schließlich wechselt die Animation auf den Wert des Keyframes mit der größten Schlüsselzeit also gleich oder kleiner als der Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 Wenn der Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ist <xref:System.Windows.Duration.Automatic%2A> oder den zugehörigen <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ist identisch mit der Zeit der der letzte Keyframe, der die Animation enden. Andernfalls gilt: Wenn der Animation <xref:System.Windows.Duration> ist größer als die Schlüsselzeit der der letzte Keyframe Animation enthält, die der Wert des Keyframes, bis es das Ende erreicht seiner <xref:System.Windows.Duration>. Wie alle Animationen eine Keyframe Animation verwendet seine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft, um zu bestimmen, ob es Endwert erreicht das Ende seines Aktivitätszeitraums fest. Weitere Informationen finden Sie unter [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Objekt definiert, die im vorherigen Beispiel zur Veranschaulichung der Funktion wie die <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> und <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> Eigenschaften.  
  
-   Der erste Keyframe legt sofort den Ausgabewert der Animation auf 0 fest.  
  
-   Der zweite Keyframe führt eine Animation von 0 bis 350 aus. Sie beginnt nach dem Ende des ersten Keyframes (zur Zeit = 0 Sekunden), wird 2 Sekunden lang abgespielt und endet zur Zeit = 0:0:2.  
  
-   Der dritte Keyframe führt eine Animation von 350 bis 50 aus. Sie beginnt nach dem Ende des zweiten Keyframes (zur Zeit = 2 Sekunden), wird 5 Sekunden lang abgespielt und endet zur Zeit = 0:0:7.  
  
-   Der vierte Keyframe führt eine Animation von 50 bis 200 aus. Sie beginnt nach dem Ende des dritten Keyframes (zur Zeit = 7 Sekunden), wird 1 Sekunde lang abgespielt und endet zur Zeit = 0:0:8.  
  
-   Da die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> -Eigenschaft der Animation auf 10 Sekunden festgelegt wurde, behält die Animation zwei Sekunden vor dem Beenden den endgültigen Wert zur Zeit = 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
<a name="interpolationmethods"></a>   
## <a name="interpolation-methods"></a>Interpolationsmethoden  
 In den vorherigen Abschnitten wurde erwähnt, dass einige Keyframe-Animationen mehrere Interpolationsmethoden unterstützen. Die Interpolation einer Animation beschreibt, wie eine Animation während ihrer Dauer einen Übergang zwischen Werten erstellt. Durch die Auswahl, welcher Keyframe-Typ für die Animation verwendet wird, kann die Interpolationsmethode für dieses Keyframe-Segment definiert werden. Es gibt drei verschiedene Typen von Interpolationsmethoden: linear, diskret und Spline.  
  
### <a name="linear-interpolation"></a>Lineare Interpolation  
 Bei der linearen Interpolation verläuft die Animation mit konstanter Geschwindigkeit der Segmentdauer. Wenn z.B. ein Keyframe-Segment während einer Dauer von 5 Sekunden von 0 auf 10 wechselt, gibt die Animation zu den angegebenen Zeiten die folgenden Werte aus:  
  
|zeit|Ausgabewert|  
|----------|------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### <a name="discrete-interpolation"></a>Diskrete Interpolation  
 Bei der diskreten Interpolation springt die Animationsfunktion ohne Interpolation von einem Wert zum nächsten. Wenn ein Keyframe-Segment während einer Dauer von 5 Sekunden von 0 auf 10 wechselt, gibt die Animation zu den angegebenen Zeiten die folgenden Werte aus:  
  
|zeit|Ausgabewert|  
|----------|------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 Beachten Sie, dass die Animation ihren Ausgabewert erst ganz am Ende der Segmentdauer ändert.  
  
 Die Spline-Interpolation ist komplexer. Sie wird im nächsten Abschnitt beschrieben.  
  
<a name="anim_spline"></a>   
### <a name="splined-interpolation"></a>Spline-Interpolation  
 Die Spline-Interpolation kann verwendet werden, um realistischere Effekte zur Zeitsteuerung zu erreichen. Da Animationen sehr oft verwendet werden, um Effekte aus der realen Welt zu imitieren, benötigen Entwickler möglicherweise eine Feinsteuerung bei der Beschleunigung und Verlangsamung der Objekte und eine exakte Bearbeitungsmöglichkeit für die Zeitsteuerung von Segmenten. Sie können Spline-Keyframes verwenden, um Animationen mit der Spline-Interpolation auszuführen. Bei anderen Keyframes geben Sie einen <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> und <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>. Bei einem Spline-Keyframe Geben Sie auch eine <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>. Das folgende Beispiel zeigt einen einzelnes Spline-Keyframe für eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Beachten Sie, dass die <xref:System.Windows.Media.Animation.KeySpline> Eigenschaft; die einen Spline-Keyframe sich von anderen Typen von Keyframes ermöglicht.  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Eine kubische Bézierkurve wird durch einen Anfangspunkt, einen Endpunkt und zwei Kontrollpunkte definiert. Die <xref:System.Windows.Media.Animation.KeySpline> Eigenschaft von einem Spline-Keyframe definiert, den zwei Kontrollpunkt eine Bézier-Kurve, die von (0,0) bis (1,1) reicht. Der erste Kontrollpunkt kontrolliert den Kurvenfaktor der ersten Hälfte der Bézierkurve, und der zweite Kontrollpunkt kontrolliert den Kurvenfaktor der zweiten Hälfte des Béziersegments. Die resultierende Kurve beschreibt die Änderungsrate für diesen Spline-Keyframe. Je steiler die Kurve, desto schneller ändert der Keyframe seine Werte. Wenn die Kurve flacher wird, ändert der Keyframe seine Werte langsamer.  
  
 Sie können <xref:System.Windows.Media.Animation.KeySpline> physischen Leitkurven wie fallen Wasser oder springenden Balls simulieren, oder andere "Beschleunigung" und "Abbremsen" Auswirkungen auf Animationen anwenden. Um Effekte für die Benutzerinteraktion wie Hintergrundausblendungen oder zurückfedernde Steuerelementschaltflächen zu erzielen, können Sie mit der Spline-Interpolation die Änderungsgeschwindigkeit einer Animation auf besondere Weise beschleunigen oder verzögern.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.KeySpline> von 0,1 1,0, die die folgenden Bézier-Kurve wird erstellt.  
  
 ![Eine Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm_keyspline_0_1_1_0")  
Ein KeySpline mit Kontrollpunkten (0,0, 1,0) und (1,0, 0,0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Diese Keyframe führt die Animation am Anfang schnell aus, wird langsamer und dann wieder schneller, bevor er endet.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.KeySpline> von 0,5,0,25 0,75,1,0 angegeben, die die folgenden Bézier-Kurve wird erstellt.  
  
 ![Eine Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm_keyspline_025_050_075_10")  
Ein Spline für Keyframes mit den Kontrollpunkten (0,25, 0,5) und (0,75, 1,0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  
  
 Da sich die Krümmung der Bézierkurve nur wenig ändert, animiert der Keyframe mit fast konstanter Geschwindigkeit. Sie wird ganz am Ende etwas verlangsamt.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> die Position des Rechtecks animiert. Da die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> verwendet <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> Objekte aufweist, der Übergang zwischen jedem Wert des Keyframes verwendet Spline-Interpolation.  
  
 [!code-xaml[keyframes_ovw_snippet#SplinedInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  
  
 Die Spline-Interpolation kann schwer verständlich sein. Es kann daher hilfreich sein, mit verschiedenen Einstellungen zu experimentieren. Mit dem [Beispiel für die Animation von Splines für Keyframe](http://go.microsoft.com/fwlink/?LinkID=160011) können Sie die Splinewerte für Keyframes ändern und die Auswirkungen auf eine Animation anzeigen.  
  
<a name="combininginterpolationmethods"></a>   
### <a name="combining-interpolation-methods"></a>Kombinieren von Interpolationsmethoden  
 Sie können Keyframes mit verschiedenen Interpolationstypen in einer einzelnen Keyframe-Animation verwenden. Wenn zwei Keyframe-Animationen mit verschiedenen Interpolationen aufeinanderfolgen, wird mit der Interpolationsmethode des zweiten Keyframes der Übergang vom ersten zum zweiten Wert erstellt.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> wird erstellt, verwendet linear, Spline und diskrete Interpolation.  
  
 [!code-xaml[keyframes_ovw_snippet#ComboInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  
  
<a name="keytimes"></a>   
## <a name="more-about-duration-and-key-times"></a>Weitere Informationen zu Zeitdauer und Schlüsselzeiten  
 Wie andere Animationen Keyframe-Animationen haben eine <xref:System.Windows.Duration> Eigenschaft. Zusätzlich zum Angeben der Animation <xref:System.Windows.Duration>, müssen Sie angeben, welcher Teil dieser Dauer auf jedem Keyframe gewährt wird. Beschreiben Sie dazu eine <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> für jeden von Keyframes für die Animation. Jedem Keyframe <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> gibt an, wann diese Keyframes endet.  
  
 Die <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> -Eigenschaft wird nicht angegeben, wie lange die Schlüsselzeit spielt. Die Wiedergabedauer eines Keyframes hängt von der Animationsdauer, dem Zeitpunkt, an dem der Keyframe endet, und vom Zeitpunkt, an dem der vorherige Keyframe geendet hat, ab. Wichtige Zeiten können angegeben werden, als Time-Wert, einen Prozentsatz oder als die speziellen Werte <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 In der folgenden Liste werden die verschiedenen Methoden zur Angabe von Schlüsselzeiten beschrieben.  
  
### <a name="timespan-values"></a>TimeSpan-Werte  
 Sie können <xref:System.TimeSpan> Werte fest, um eine <xref:System.Windows.Media.Animation.KeyTime>. Der Wert muss größer als oder gleich 0 und kleiner als oder gleich der Dauer der Animation sein. Das folgende Beispiel zeigt eine Animation mit einer Dauer von 10 Sekunden und vier Keyframes, deren Schlüsselzeiten als Zeitwerte angegeben sind.  
  
-   Der erste Keyframe führt die Animation vom Basiswert bis 100 in den ersten 3 Sekunden aus und endet zur Zeit = 0:0:03.  
  
-   Der zweite Keyframe führt eine Animation von 100 bis 200 aus. Sie beginnt nach dem Ende des ersten Keyframes (zur Zeit = 3 Sekunden), wird 5 Sekunden lang abgespielt und endet zur Zeit = 0:0:8.  
  
-   Der dritte Keyframe führt eine Animation von 200 bis 500 aus. Sie beginnt nach dem Ende des zweiten Keyframes (zur Zeit = 8 Sekunden), wird 1 Sekunden lang abgespielt und endet zur Zeit = 0:0:9.  
  
-   Der vierte Keyframe führt eine Animation von 500 bis 600 aus. Sie beginnt nach dem Ende des dritten Keyframes (zur Zeit = 9 Sekunden), wird 1 Sekunde lang abgespielt und endet zur Zeit = 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#TimeSpanKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#timespankeytimeexample)]  
  
### <a name="percentage-values"></a>Prozentwerte  
 Ein Prozentwert gibt an, dass das Ende des Keyframes bei einem bestimmten Prozentsatz der Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird der Prozentsatz als Zahl angegeben, gefolgt vom `%`-Symbol. Verwenden Sie im Code die <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> Methode und übergibt ihn dann ein <xref:System.Double> , der angibt, der des Prozentsatzes. Der Wert muss größer als oder gleich 0 und kleiner als oder gleich 100 Prozent sein. Das folgende Beispiel zeigt eine Animation mit einer Dauer von 10 Sekunden und vier Keyframes, deren Schlüsselzeiten als Prozentsätze angegeben sind.  
  
-   Der erste Keyframe führt die Animation vom Basiswert bis 100 in den ersten 3 Sekunden aus und endet zur Zeit = 0:0:3.  
  
-   Der zweite Keyframe führt eine Animation von 100 bis 200 aus. Sie beginnt nach dem Ende des ersten Keyframes (zur Zeit = 3 Sekunden), wird 5 Sekunden lang abgespielt und endet zur Zeit = 0:0:8 (0.8 * 10 = 8).  
  
-   Der dritte Keyframe führt eine Animation von 200 bis 500 aus. Sie beginnt nach dem Ende des zweiten Keyframes (zur Zeit = 8 Sekunden), wird 1 Sekunden lang abgespielt und endet zur Zeit = 0:0:9 (0.9 * 10 = 9).  
  
-   Der vierte Keyframe führt eine Animation von 500 bis 600 aus. Sie beginnt nach dem Ende des dritten Keyframes (zur Zeit = 9 Sekunden), wird 1 Sekunde lang abgespielt und endet zur Zeit = 0:0:10 (1 * 10 = 10).  
  
 [!code-xaml[keyframes_ovw_snippet#PercentageKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  
  
### <a name="special-value-uniform"></a>Spezieller Wert „Uniform“  
 Verwendung <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ein Timeout bei jedem Keyframe auf die gleiche Menge an Zeit dauern soll.  
  
 Ein <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> Schlüsselzeit teilt die verfügbare Zeit gleichmäßig durch die Anzahl von Keyframes für die Endzeit der einzelnen Keyframes zu bestimmen. Das folgende Beispiel zeigt eine Animation mit einer Dauer von 10 Sekunden und vier Keyframes, dessen Schlüssel erreicht als <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
-   Der erste Keyframe führt die Animation vom Basiswert bis 100 in den ersten 2,5 Sekunden aus und endet zur Zeit = 0:0:2.5.  
  
-   Der zweite Keyframe führt eine Animation von 100 bis 200 aus. Sie beginnt nach dem Ende des ersten Keyframes (zur Zeit = 2,5 Sekunden), wird ungefähr 2,5 Sekunden lang abgespielt und endet zur Zeit = 0:0:5.  
  
-   Der dritte Keyframe führt eine Animation von 200 bis 500 aus. Sie beginnt nach dem Ende des zweiten Keyframes (zur Zeit = 5 Sekunden), wird 2,5 Sekunden lang abgespielt und endet zur Zeit = 0:0:7.5.  
  
-   Der vierte Keyframe führt eine Animation von 500 bis 600 aus. Sie beginnt nach dem Ende des zweiten Keyframes (zur Zeit = 7,5 Sekunden), wird 2,5 Sekunden lang abgespielt und endet zur Zeit = 0:0:1.  
  
 [!code-xaml[keyframes_ovw_snippet#UniformKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  
  
### <a name="special-value-paced"></a>Spezieller Wert „Paced“  
 Verwendung <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> Zeitpunkt mit konstanter Geschwindigkeit animiert werden soll.  
  
 Ein <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> Schlüsselzeit weist die verfügbare Zeit entsprechend der Länge der einzelnen Keyframes zur Bestimmung der Dauer der einzelnen Frames.  Auf diese Weise kann sichergestellt werden, dass die Geschwindigkeit der Animation konstant bleibt.  Das folgende Beispiel zeigt eine Animation mit einer Dauer von 10 Sekunden und drei Keyframes, dessen Schlüssel erreicht als <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 [!code-xaml[keyframes_ovw_snippet#PacedKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  
  
 Beachten Sie Folgendes: Wenn der letzte Keyframe Schlüsselzeit ist <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>, die aufgelöste Schlüsselzeit auf 100 Prozent festgelegt. Wenn der erste Keyframe in einer Multiframe-Animation einen Paced-Wert besitzt, wird die aufgelöste Schlüsselzeit auf 0 festgelegt. (Wenn die Keyframe-Auflistung nur einen einzelnen Keyframe enthält und es sich dabei um einen Keyframe mit einem Paced-Wert handelt, wird die aufgelöste Schlüsselzeit auf 100 Prozent festgelegt.)  
  
 Verschiedene Keyframes innerhalb einer einzelnen Keyframe-Animation können verschiedene Schlüsselzeittypen verwenden.  
  
<a name="combiningkeytimes"></a>   
## <a name="combining-key-times-out-of-order-key-frames"></a>Kombinieren von Schlüsselzeiten, Keyframes in falscher Reihenfolge  
 Können Sie mit anderen Keyframes <xref:System.Windows.Media.Animation.KeyTime> Werttypen in der gleichen Animation. Und obwohl empfohlen wird, Keyframes in der Reihenfolge hinzuzufügen, in der sie abgespielt werden sollen, ist das nicht notwendig. Das Animations- und Zeitsteuerungssystem kann Keyframes in falscher Reihenfolge auflösen. Keyframes mit ungültigen Schlüsselzeiten werden ignoriert.  
  
 Die folgende Liste beschreibt das Verfahren, mit dem Schlüsselzeiten für Keyframes einer Keyframe-Animation aufgelöst werden.  
  
1.  Beheben Sie <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> Werte.  
  
2.  Bestimmen Sie die *gesamte Interpolationszeit* der Animation, die Gesamtzeit, die die Keyframe-Animation für eine vollständige Vorwärtsiteration benötigt.  
  
    1.  Wenn der Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A> nicht <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A>, die gesamte Zeit ist der Wert der Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.  
  
    2.  Die gesamte Zeit ist, andernfalls das größte <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> Wert zwischen den Keyframes angegeben wird, falls vorhanden.  
  
    3.  Andernfalls beträgt die gesamte Interpolationszeit Zeit 1 Sekunde.  
  
3.  Verwenden Sie die gesamte Time-Werten zum Auflösen <xref:System.Windows.Media.Animation.KeyTimeType.Percent> <xref:System.Windows.Media.Animation.KeyTime> Werte.  
  
4.  Lösen Sie den letzten Keyframe auf, wenn er nicht bereits in den vorherigen Schritten aufgelöst wurde. Wenn die <xref:System.Windows.Media.Animation.KeyTime> des letzten Keyframes ist <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, die aufgelöste Zeit wird die gesamte Zeit gleich sein.  
  
     Wenn die <xref:System.Windows.Media.Animation.KeyTime> des ersten Keyframes ist <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> und beheben Sie diese Animation hat mehr als auf Keyframes, seine <xref:System.Windows.Media.Animation.KeyTime> Wert auf 0 (null); Wenn nur ein Keyframe vorhanden ist und die zugehörige <xref:System.Windows.Media.Animation.KeyTime> Wert <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, wird er mit dem gesamten aufgelöst Interpolationszeit, wie im vorherigen Schritt beschrieben.  
  
5.  Beheben Sie die verbleibenden <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> Werte: sie erhalten jeweils einen gleichen Anteil der verfügbaren Zeit.  Während dieses Vorgangs nicht aufgelöste <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> Werte werden als vorübergehend behandelt <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> Werte und erhalten eine vorübergehend aufgelöste Zeit.  
  
6.  Beheben Sie die <xref:System.Windows.Media.Animation.KeyTime> Werte von Keyframes mit nicht Key Zeiten angegeben, mit der Keyframes am nächsten liegt, sie deklariert, die behoben wurden <xref:System.Windows.Media.Animation.KeyTime> Werte.  
  
7.  Beheben Sie die verbleibenden <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> Werte. <xref:System.Windows.Media.Animation.KeyTime.Paced%2A><xref:System.Windows.Media.Animation.KeyTime> verwenden die <xref:System.Windows.Media.Animation.KeyTime> Werte der benachbarten Keyframes, um ihre aufgelöste Zeit zu bestimmen.  Das Ziel ist es, sicherzustellen, dass die Geschwindigkeit der Animation um die aufgelöste Zeit dieses Keyframes herum konstant ist.  
  
8.  Sortieren Sie Keyframes in der Reihenfolge der aufgelösten Zeit (Primärschlüssel), und die Reihenfolge der Deklaration (Sekundärschlüssel), d. h., verwenden Sie eine stabile Sortierung basierend auf den aufgelösten Keyframe <xref:System.Windows.Media.Animation.KeyTime> Werte.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.KeyTime>  
 <xref:System.Windows.Media.Animation.KeySpline>  
 <xref:System.Windows.Media.Animation.Timeline>  
 [Spline für Keyframes-Animation-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160011)  
 [KeyFrame-Animation-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160012)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
