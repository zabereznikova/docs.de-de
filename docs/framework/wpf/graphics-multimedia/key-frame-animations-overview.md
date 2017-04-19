---
title: "&#220;bersicht &#252;ber Keyframe-Animationen | Microsoft Docs"
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
  - "Animation, Keyframes"
  - "Keyframes [WPF], Informationen über Keyframe-Animationen"
  - "Mehrere Animationszielwerte"
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# &#220;bersicht &#252;ber Keyframe-Animationen
Dieses Thema enthält eine Einführung in Keyframe\-Animationen.  Mit Keyframe\-Animationen können Sie bei Animationen mehr als zwei Zielwerte verwenden und die Interpolationsmethode einer Animation steuern.  
  
 Dieses Thema enthält folgende Abschnitte.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Vorbereitungsmaßnahmen](#prerequisites)  
  
-   [Verwenden von Keyframe\-Animationen](#keyframeanimations)  
  
-   [Verwandte Themen](#seeAlsoToggle)  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 Für diese Übersicht sollten Sie mit Animationen und Zeitachsen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vertraut sein.  Eine Einführung in Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Kenntnisse in From\/To\/By\-Animationen sind ebenfalls hilfreich.  Weitere Informationen finden Sie unter [Übersicht über From\/To\/By\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md).  
  
<a name="whatisakeyframeanimation"></a>   
## Was ist eine Keyframe\-Animation?  
 Wie eine From\/To\/By\-Animation animiert eine Keyframe\-Animation den Wert einer Zieleigenschaft.  Sie erstellt während der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einen Übergang zwischen den Zielwerten.  Während eine From\/To\/By\-Animation einen Übergang zwischen zwei Werten erstellt, kann eine einzelne Keyframe\-Animation jedoch Übergänge zwischen einer beliebigen Anzahl von Zielwerten erstellen.  Im Gegensatz zu einer From\/To\/By\-Animation besitzt eine Keyframe\-Animation keine From\-, To\- oder By\-Eigenschaft, mit der die Zielwerte festgelegt werden könnten.  Die Zielwerte einer Keyframe\-Animation werden mit Keyframe\-Objekten \(daher der Begriff "Keyframe\-Animation"\) beschrieben.  Um die Zielwerte einer Animation anzugeben, werden Keyframe\-Objekte erstellt und der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A>\-Auflistung der Animation hinzugefügt.  Wenn die Animation ausgeführt wird, erstellt sie Übergänge zwischen den angegebenen Frames.  
  
 Einige Keyframe\-Methoden unterstützen nicht nur mehrere Zielwerte, sondern sogar mehrere Interpolationsmethoden.  Die Interpolationsmethode einer Animation definiert, wie sie einen Übergang von einem Wert zum nächsten erstellt.  Es gibt drei Interpolationstypen: [diskret](GTMT), [linear](GTMT) und [Spline](GTMT).  
  
 Um Animationen mit einer Keyframe\-Animation auszuführen, gehen Sie folgendermaßen vor.  
  
-   Deklarieren Sie die Animation, und geben Sie die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> an, genau so wie bei einer From\/To\/By\-Animation.  
  
-   Erstellen Sie für jeden Zielwert einen Keyframe des entsprechenden Typs, legen Sie seinen Wert und <xref:System.Windows.Media.Animation.KeyTime> fest, und fügen Sie ihn der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A>\-Auflistung der Animation hinzu.  
  
-   Ordnen Sie der Animation eine Eigenschaft zu, genau so wie bei einer From\/To\/By\-Animation.  Weitere Informationen über das Anwenden einer Animation auf eine Eigenschaft mit einem Storyboard finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> verwendet, um ein <xref:System.Windows.Shapes.Rectangle>\-Element an vier verschiedenen Orten zu animieren.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->  
  
 Wie eine From\/To\/By\-Animation kann eine Keyframe\-Animation mithilfe von <xref:System.Windows.Media.Animation.Storyboard> in Markup und Code oder mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode in Code auf eine Eigenschaft angewendet werden.  Sie können mit einer Keyframe\-Animation auch eine <xref:System.Windows.Media.Animation.AnimationClock> erstellen und sie auf eine oder mehrere Eigenschaften anwenden.  Weitere Informationen zu den verschiedenen Anwendungsmethoden für Animationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## Keyframe\-Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen.  Um eine Eigenschaft zu animieren, die einen <xref:System.Double>\-Wert akzeptiert \(wie zum Beispiel die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft eines Elements\), verwenden Sie eine Animation, die <xref:System.Double>\-Werte erzeugt.  Zum Animieren einer Eigenschaft, die einen <xref:System.Windows.Point>\-Wert entgegennimmt, verwenden Sie eine Animation, die <xref:System.Windows.Point>\-Werte erzeugt usw.  
  
 Die Keyframe\-Animationsklassen gehören zum <xref:System.Windows.Media.Animation>\-Namespace und entsprechen der folgenden Benennungskonvention:  
  
 *\<Typ\>* `AnimationUsingKeyFrames`  
  
 Wobei *\<Typ\>* für den Wertetyp steht, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die folgenden Keyframe\-Animationsklassen bereit.  
  
|Eigenschaftentyp|Zugehörige From\/To\/By\-Animationsklasse|Unterstützte Interpolationsmethoden|  
|----------------------|-----------------------------------------------|-----------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Diskret|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|Diskret, Linear, Spline|  
  
<a name="animation_target_values"></a>   
## Zielwerte \(Keyframes\) und Schlüsselzeiten  
 Ebenso wie es verschiedene Typen von Keyframe\-Animationen zum Animieren verschiedener Eigenschaftentypen gibt, gibt es auch verschiedene Typen von Keyframe\-Objekten: einen für jeden animierten Werttyp und jede unterstützte Interpolationsmethode.  Keyframe\-Typen entsprechen der folgenden Benennungskonvention:  
  
 *\<InterpolationMethod\>\<Typ\>* `KeyFrame`  
  
 Wobei *\<InterpolationMethod\>* für die Interpolationsmethode steht, die der Keyframe verwendet, und *\<Typ\>* für den Werttyp, den die Klasse animiert.  Eine Keyframe\-Animation, die alle drei Interpolationsmethoden unterstützt, besitzt drei Keyframe\-Typen, die verwendet werden können.  Sie können z. B. drei Keyframe\-Typen mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> verwenden: <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> und <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>.  \(Interpolationsmethoden werden in einem späteren Abschnitt ausführlich beschrieben.\)  
  
 Die Hauptaufgabe eines Keyframes besteht darin, eine <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> und einen <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> anzugeben.  Jeder Keyframe\-Typ stellt diese zwei Eigenschaften bereit.  
  
-   Die <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>\-Eigenschaft gibt den Zielwert für diesen Keyframe an.  
  
-   Die <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>\-Eigenschaft gibt an, wann \(innerhalb der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation\) der <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> eines Keyframes erreicht wird.  
  
 Wenn eine Keyframe\-Animation beginnt, durchläuft sie die zugehörigen Keyframes in der durch deren <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>\-Eigenschaften definierten Reihenfolge.  
  
-   Wenn zur Zeit 0 \(null\) kein Keyframe vorhanden ist, erstellt die Animation einen Übergang zwischen dem aktuellen Wert der Zieleigenschaft und dem <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> des ersten Keyframes. Andernfalls wird der Ausgabewert der Animation zum Wert des ersten Keyframes.  
  
-   Die Animation erstellt mit der vom zweiten Keyframe angegebenen Interpolationsmethode einen Übergang zwischen dem <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> des ersten und zweiten Keyframes.  Der Übergang beginnt an der <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> des ersten Keyframes und endet, wenn die <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> des zweiten Keyframes erreicht ist.  
  
-   Die Animation wird fortgesetzt und erstellt Übergänge zwischen jedem nachfolgenden Keyframe und dem vorangehenden Keyframe.  
  
-   Schließlich wechselt die Animation zum Wert des Keyframes mit der größten Schlüsselzeit, die maximal so groß ist wie die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation.  
  
 Wenn die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation <xref:System.Windows.Duration.Automatic%2A> ist oder deren <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeit des letzten Keyframes entspricht, endet die Animation.  Im anderen Fall, wenn die <xref:System.Windows.Duration> der Animation größer ist als die Schlüsselzeit des letzten Keyframes, behält die Animation den Keyframe\-Wert bei, bis sie das Ende der <xref:System.Windows.Duration> erreicht.  Wie alle Animationen bestimmt eine Keyframe\-Animation mit der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft, ob sie den Endwert am Ende des Aktivitätszeitraums beibehält.  Weitere Informationen finden Sie unter [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
 Im folgenden Beispiel wird mit dem im vorherigen Beispiel definierten <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>\-Objekt veranschaulicht, wie die <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>\-Eigenschaft und die <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>\-Eigenschaft funktionieren.  
  
-   Der erste Keyframe legt sofort den Ausgabewert der Animation auf 0 \(null\) fest.  
  
-   Der zweite Keyframe führt eine Animation von 0 bis 350 aus.  Er wird nach dem Ende des ersten Keyframes \(zur Zeit \= 0 Sekunden\) gestartet, 2 Sekunden lang abgespielt und endet zur Zeit \= 0:0:2.  
  
-   Der dritte Keyframe führt eine Animation von 350 bis 50 aus.  Er wird am Ende des zweiten Keyframes \(zur Zeit \= 2 Sekunden\) gestartet, 5 Sekunden lang abgespielt und endet zur Zeit \= 0:0:7.  
  
-   Der vierte Keyframe führt eine Animation von 50 bis 200 aus.  Er wird am Ende des dritten Keyframes \(zur Zeit \= 7 Sekunden\) gestartet, 1 Sekunde lang abgespielt und endet zur Zeit \= 0:0:8.  
  
-   Da die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>\-Eigenschaft der Animation auf 10 Sekunden festgelegt war, behält die Animation den Endwert zwei Sekunden lang bei, bevor sie zur Zeit \= 0:0:10 endet.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->  
  
<a name="interpolationmethods"></a>   
## Interpolationsmethoden  
 In den vorangehenden Abschnitten wurde erwähnt, dass einige Keyframe\-Animationen mehrere Interpolationsmethoden unterstützen.  Die Interpolation einer Animation beschreibt, wie eine Animation während ihrer Dauer einen Übergang zwischen Werten erstellt.  Durch die Auswahl, welcher Keyframe\-Typ für die Animation verwendet wird, kann die Interpolationsmethode für dieses Keyframe\-Segment definiert werden.  Es gibt drei verschiedene Typen von Interpolationsmethoden: linear und diskret und Spline.  
  
### Lineare Interpolation  
 Bei der [linearen Interpolation](GTMT) wird die Animation mit konstanter Geschwindigkeit der Segmentdauer durchlaufen.  Wenn z. B. ein Keyframe\-Segment während einer Dauer von 5 Sekunden von 0 \(null\) auf 10 wechselt, gibt die Animation zu den angegebenen Zeiten die folgenden Werte aus:  
  
|Uhrzeit|Ausgabewert|  
|-------------|-----------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### Diskrete Interpolation  
 Bei der [diskreten Interpolation](GTMT) springt die Animationsfunktion ohne Interpolation von einem Wert zum nächsten.  Wenn ein Keyframe\-Segment während einer Dauer von 5 Sekunden von 0 \(null\) auf 10 wechselt, gibt die Animation zu den angegebenen Zeiten die folgenden Werte aus:  
  
|Uhrzeit|Ausgabewert|  
|-------------|-----------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 Beachten Sie, dass die Animation ihren Ausgabewert erst ganz am Ende der Segmentdauer ändert.  
  
 Die [Spline\-Interpolation](GTMT) ist komplexer.  Sie wird im nächsten Abschnitt beschrieben.  
  
<a name="anim_spline"></a>   
### Spline\-Interpolation  
 Mit der Spline\-Interpolation lassen sich realistischere Effekte zur Zeitsteuerung erreichen.  Da Animationen sehr oft dazu eingesetzt werden, Effekte aus der realen Welt zu imitieren, benötigen Entwickler möglicherweise eine Feinsteuerung bei der Beschleunigung und der Verzögerung von Objekten und eine exakte Bearbeitungsmöglichkeit für die Zeitsteuerung von Segmenten.  Sie können Spline\-Keyframes einsetzen, um Animationen mit der Spline\-Interpolation ausführen.  Bei anderen Keyframes geben Sie einen <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> und eine <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> an.  Bei einem Spline\-Keyframe geben Sie auch einen <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> an.  Im folgenden Beispiel wird ein einzelner Spline\-Keyframe für eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> dargestellt.  Beachten Sie die <xref:System.Windows.Media.Animation.KeySpline>\-Eigenschaft. Erst dadurch unterscheidet sich ein Spline\-Keyframe von den anderen Keyframe\-Typen.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->  
  
 Eine [kubische Bézierkurve](GTMT) wird durch einen Anfangspunkt, einen Endpunkt und zwei Kontrollpunkte definiert.  Die <xref:System.Windows.Media.Animation.KeySpline>\-Eigenschaft eines Spline\-Keyframes definiert die zwei Kontrollpunkte einer Bézierkurve, die von \(0,0\) bis \(1,1\) reicht.  Der erste Kontrollpunkt kontrolliert den Kurvenfaktor der ersten Hälfte der Bézierkurve, und der zweite Kontrollpunkt kontrolliert den Kurvenfaktor der zweiten Hälfte des Béziersegments.  Die resultierende Kurve beschreibt die Änderungsrate für diesen Spline\-Keyframe.  Je steiler die Kurve, desto schneller ändert der Keyframe seine Werte.  Wenn die Kurve flacher wird, ändert der Keyframe seine Werte langsamer.  
  
 Sie können mit <xref:System.Windows.Media.Animation.KeySpline> auch physische Bewegungen wie bei herabstürzendem Wasser oder springenden Bällen simulieren oder andere "Ease\-In"\- und "Ease\-Out"\-Effekte auf die Animation von Bewegungen anwenden.  Um Effekte für die Benutzerinteraktion wie Hintergrundausblendungen oder zurückfedernde Steuerelementschaltflächen zu erzielen, können Sie mit der Spline\-Interpolation die Änderungsgeschwindigkeit einer Animation auf besondere Weise beschleunigen oder verzögern.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.KeySpline> von 0,1 1,0 angegeben, der die folgende Bézierkurve erstellt.  
  
 ![Eine Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm\_keyspline\_0\_1\_1\_0")  
Ein Spline für Keyframes mit den Kontrollpunkten \(0,0, 1,0\) und \(1,0, 0,0\)  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->  
  
 Dieser Keyframe führt die Animation am Anfang schnell aus, wird langsamer und dann wieder schneller, bevor er endet.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.KeySpline> von 0,5,0,25 0,75,1,0 angegeben, der die folgende Bézierkurve erstellt.  
  
 ![Eine Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm\_keyspline\_025\_050\_075\_10")  
Ein Spline für Keyframes mit den Kontrollpunkten \(0,25, 0,5\) und \(0,75, 1,0\)  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  -->  
  
 Da sich die Krümmung der Bézierkurve nur wenig ändert, führt dieser Keyframe die Animation mit fast konstanter Geschwindigkeit aus und wird gegen Ende etwas langsamer.  
  
 Im folgenden Beispiel wird mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> die Position eines Rechtecks animiert.  Da <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>\-Objekte verwendet, wird für den Übergang zwischen jedem Keyframe\-Wert die Spline\-Interpolation eingesetzt.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  -->  
  
 Es ist möglicherweise schwierig, die Spline\-Interpolation zu verstehen. Es kann daher hilfreich sein, mit verschiedenen Einstellungen zu experimentieren.  Mit dem [Beispiel für die Animation von Splines für Keyframes](http://go.microsoft.com/fwlink/?LinkID=160011) können Sie Splinewerte für Keyframes ändern und die Auswirkungen auf eine Animation anzeigen.  
  
<a name="combininginterpolationmethods"></a>   
### Kombinieren von Interpolationsmethoden  
 Sie können Keyframes mit verschiedenen Interpolationstypen in einer einzelnen Keyframe\-Animation verwenden.  Wenn zwei Keyframe\-Animationen mit verschiedenen Interpolationen aufeinanderfolgen, wird mit der Interpolationsmethode des zweiten Keyframes der Übergang vom ersten zum zweiten Wert erstellt.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> erstellt, die lineare Interpolation, Spline\-Interpolation und diskrete Interpolation verwendet.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#combointerpolationexample)]  -->  
  
<a name="keytimes"></a>   
## Weitere Informationen zu Zeitdauer und Schlüsselzeiten  
 Wie andere Animationen, verfügen auch Keyframe\-Animationen über eine <xref:System.Windows.Duration>\-Eigenschaft.  Zusätzlich zur Angabe der <xref:System.Windows.Duration> der Animation muss auch angegeben werden, welchen Zeitanteil daran jeder einzelne Keyframe erhalten soll.  Dies wird erreicht, indem für jeden Keyframe der Animation eine <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> beschrieben wird.  Die <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> jedes Keyframes gibt den Zeitpunkt an, zu dem der Keyframe endet.  
  
 Die <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>\-Eigenschaft gibt nicht die Wiedergabedauer der Schlüsselzeit an.  Die Wiedergabedauer eines Keyframes hängt von der Dauer der Animation, dem Zeitpunkt, an dem der Keyframe endet, und vom Zeitpunkt, an dem der vorherige Keyframe geendet hat, ab.  Schlüsselzeiten können als Zeitwert, Prozentwert oder als die speziellen Werte <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> bzw. <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> angegeben werden.  
  
 In der folgenden Liste werden die verschiedenen Möglichkeiten beschrieben, Schlüsselzeiten anzugeben.  
  
### TimeSpan\-Werte  
 Sie können mit <xref:System.TimeSpan>\-Werten eine <xref:System.Windows.Media.Animation.KeyTime> angeben.  Der Wert sollte mindestens 0 \(null\) betragen und maximal so groß sein wie die Dauer der Animation.  Im folgenden Beispiel werden eine Animation mit einer Dauer von 10 Sekunden und vier Keyframes gezeigt, deren Schlüsselzeiten als Zeitwerte angegeben sind.  
  
-   Der erste Keyframe führt die Animation vom Basiswert bis 100 in den ersten 3 Sekunden aus und endet zur Zeit 0:0:03.  
  
-   Der zweite Keyframe führt eine Animation von 100 bis 200 aus.  Er wird nach dem Ende des ersten Keyframes \(zur Zeit \= 3 Sekunden\) gestartet, 5 Sekunden lang abgespielt und endet zur Zeit \= 0:0:8.  
  
-   Der dritte Keyframe führt eine Animation von 200 bis 500 aus.  Er wird am Ende des zweiten Keyframes \(zur Zeit \= 8 Sekunden\) gestartet, 1 Sekunde lang abgespielt und endet zur Zeit \= 0:0:9.  
  
-   Der vierte Keyframe führt eine Animation von 500 bis 600 aus.  Er wird am Ende des dritten Keyframes \(zur Zeit \= 9 Sekunden\) gestartet, 1 Sekunde lang abgespielt und endet zur Zeit \= 0:0:10.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#timespankeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#timespankeytimeexample)]  -->  
  
### Prozentwerte  
 Ein Prozentwert gibt an, dass der Keyframe bei einem bestimmten Prozentsatz der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation endet.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird der Prozentsatz als Zahl angeben, gefolgt vom `%`\-Zeichen.  Im Code verwenden Sie die <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A>\-Methode und übergeben ihr einen <xref:System.Double>\-Wert, der den Prozentsatz angibt.  Der Wert muss mindestens 0 \(null\) und darf maximal 100 Prozent betragen.  Im folgenden Beispiel werden eine Animation mit einer Dauer von 10 Sekunden und vier Keyframes gezeigt, deren Schlüsselzeiten als Prozentsätze angegeben sind.  
  
-   Der erste Keyframe führt die Animation vom Basiswert bis 100 in den ersten 3 Sekunden aus und endet zur Zeit 0:0:3.  
  
-   Der zweite Keyframe führt eine Animation von 100 bis 200 aus.  Er wird nach dem Ende des ersten Keyframes \(zur Zeit \= 3 Sekunden\) gestartet, 5 Sekunden lang abgespielt und endet zur Zeit \= 0:0:8 \(0,8 x 10 \= 8\).  
  
-   Der dritte Keyframe führt eine Animation von 200 bis 500 aus.  Er wird am Ende des zweiten Keyframes \(zur Zeit \= 8 Sekunden\) gestartet, 1 Sekunde lang abgespielt und endet zur Zeit \= 0:0:9 \(0,9 x 10 \= 9\).  
  
-   Der vierte Keyframe führt eine Animation von 500 bis 600 aus.  Er wird am Ende des dritten Keyframes \(zur Zeit \= 9 Sekunden\) gestartet, 1 Sekunde lang abgespielt und endet zur Zeit \= 0:0:10 \(1 x 10 \= 10\).  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#percentagekeytimeexample)]  -->  
  
### Spezieller Wert "Uniform"  
 Verwenden Sie die <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>\-Zeitsteuerung, wenn Sie möchten, dass jeder Keyframe die gleiche Zeitdauer erhält.  
  
 Eine <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>\-Schlüsselzeit teilt die verfügbare Zeit gleichmäßig durch die Anzahl der Keyframes, um die Endzeit jedes Keyframes zu bestimmen.  Im folgenden Beispiel werden eine Animation mit einer Dauer von 10 Sekunden und vier Keyframes gezeigt, deren Schlüsselzeiten als <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> angegeben sind.  
  
-   Der erste Keyframe führt die Animation vom Basiswert bis 100 in den ersten 2,5 Sekunden aus und endet zur Zeit 0:0:2,5.  
  
-   Der zweite Keyframe führt eine Animation von 100 bis 200 aus.  Er wird nach dem Ende des ersten Keyframes \(zur Zeit \= 2,5 Sekunden\) gestartet, ungefähr 2,5 Sekunden lang abgespielt und endet zur Zeit \= 0:0:5.  
  
-   Der dritte Keyframe führt eine Animation von 200 bis 500 aus.  Er wird am Ende des zweiten Keyframes \(zur Zeit \= 5 Sekunden\) gestartet, 2,5 Sekunden lang abgespielt und endet zur Zeit \= 0:0:7,5.  
  
-   Der vierte Keyframe führt eine Animation von 500 bis 600 aus.  Er wird am Ende des zweiten Keyframes \(zur Zeit \= 7,5 Sekunden\) gestartet, 2,5 Sekunden lang abgespielt und endet zur Zeit \= 0:0:1.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#uniformkeytimeexample)]  -->  
  
### Spezieller Wert "Paced"  
 Verwenden Sie die <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>\-Zeitsteuerung, wenn Sie die Animation mit konstanter Geschwindigkeit ausführen möchten.  
  
 Eine <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>\-Schlüsselzeit weist die verfügbare Zeit entsprechend der Länge der einzelnen Keyframes zu, um die Dauer jedes Frames zu bestimmen.  Auf diese Weise kann sichergestellt werden, dass die Geschwindigkeit der Animation konstant bleibt.  Im folgenden Beispiel werden eine Animation mit einer Dauer von 10 Sekunden und drei Keyframes gezeigt, deren Schlüsselzeiten als <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> angegeben sind.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#pacedkeytimeexample)]  -->  
  
 Beachten Sie, dass die aufgelöste Schlüsselzeit auf 100 Prozent festgelegt wird, wenn die Schlüsselzeit des letzten Keyframes <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ist.  Wenn der erste Keyframe in einer Multiframe\-Animation einen Paced\-Wert besitzt, wird die aufgelöste Schlüsselzeit auf 0 \(null\) festgelegt.  \(Wenn die Keyframe\-Auflistung nur einen einzelnen Keyframe enthält und es sich dabei um einen Keyframe mit einem Paced\-Wert handelt, wird die aufgelöste Schlüsselzeit auf 100 Prozent festgelegt.\)  
  
 Verschiedene Keyframes innerhalb einer einzelnen Keyframe\-Animation können verschiedene Schlüsselzeittypen verwenden.  
  
<a name="combiningkeytimes"></a>   
## Kombinieren von Schlüsselzeiten, Keyframes in falscher Reihenfolge  
 Sie können Keyframes mit verschiedenen <xref:System.Windows.Media.Animation.KeyTime>\-Werttypen in derselben Animation verwenden.  Und obwohl empfohlen wird, Keyframes in der Reihenfolge hinzuzufügen, in der sie abgespielt werden sollen, ist das nicht notwendig.  Das Animations\- und Zeitsteuerungssystem kann Keyframes in falscher Reihenfolge auflösen.  Keyframes mit ungültigen Schlüsselzeiten werden ignoriert.  
  
 In der folgenden Liste wird die Vorgehensweise beschrieben, mit der Schlüsselzeiten für Keyframes einer Keyframe\-Animation aufgelöst werden.  
  
1.  Lösen Sie <xref:System.TimeSpan>\-<xref:System.Windows.Media.Animation.KeyTime>\-Werte auf.  
  
2.  Bestimmen Sie die *gesamte Interpolationszeit* der Animation, die Gesamtzeit, die die Keyframe\-Animation für eine vollständige Vorwärtsiteration benötigt.  
  
    1.  Wenn die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation nicht <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A> ist, ist die gesamte Interpolationszeit der Wert der <xref:System.Windows.Media.Animation.Timeline.Duration%2A>\-Eigenschaft der Animation.  
  
    2.  Andernfalls ist die gesamte Interpolationszeit der größte <xref:System.TimeSpan>\-<xref:System.Windows.Media.Animation.KeyTime>\-Wert, der unter den Keyframes, sofern vorhanden, angegeben ist.  
  
    3.  Andernfalls beträgt die gesamte Interpolationszeit 1 Sekunde.  
  
3.  Verwenden Sie den Wert für die gesamte Interpolationszeit, um <xref:System.Windows.Media.Animation.KeyTimeType>\-<xref:System.Windows.Media.Animation.KeyTime>\-Werte aufzulösen.  
  
4.  Lösen Sie den letzten Keyframe auf, wenn er nicht bereits in den vorherigen Schritten aufgelöst wurde.  Wenn die <xref:System.Windows.Media.Animation.KeyTime> des letzten Keyframes <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ist, entspricht die aufgelöste Zeit der gesamten Interpolationszeit.  
  
     Wenn die <xref:System.Windows.Media.Animation.KeyTime> des ersten Keyframes <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ist und diese Animation über mehr als einen Keyframe verfügt, lösen Sie den <xref:System.Windows.Media.Animation.KeyTime>\-Wert auf null auf. Wenn nur ein Keyframe vorhanden ist und dessen <xref:System.Windows.Media.Animation.KeyTime>\-Wert <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ist, wird er auf die gesamte Interpolationszeit aufgelöst, wie im vorherigen Schritt beschrieben.  
  
5.  Lösen Sie verbleibenden <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>\-<xref:System.Windows.Media.Animation.KeyTime>\-Werte auf: Sie erhalten jeweils einen gleichen Anteil der verfügbaren Zeit.  Während dieses Vorgangs werden nicht aufgelöste <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>\-<xref:System.Windows.Media.Animation.KeyTime>\-Werte vorübergehend als <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>\-<xref:System.Windows.Media.Animation.KeyTime>\-Werte behandelt und erhalten eine vorübergehend aufgelöste Zeit.  
  
6.  Lösen Sie die <xref:System.Windows.Media.Animation.KeyTime>\-Werte von Keyframes mit nicht angegebenen Schlüsselzeiten auf, indem Sie die in unmittelbarer Nähe dazu deklarierten Keyframes mit aufgelösten <xref:System.Windows.Media.Animation.KeyTime>\-Werten verwenden.  
  
7.  Lösen Sie verbleibende <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>\-<xref:System.Windows.Media.Animation.KeyTime>\-Werte auf.  <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> verwenden die <xref:System.Windows.Media.Animation.KeyTime>\-Werte der benachbarten Keyframes, um ihre aufgelöste Zeit zu bestimmen.  Das Ziel ist es, sicherzustellen, dass die Geschwindigkeit der Animation um die aufgelöste Zeit dieses Keyframes herum konstant ist.  
  
8.  Sortieren Sie die Keyframes in der Reihenfolge der aufgelösten Zeit \(Primärschlüssel\) und in der Reihenfolge der Deklaration \(Sekundärschlüssel\), d. h., verwenden Sie eine stabile Sortierung, die auf den aufgelösten Keyframe <xref:System.Windows.Media.Animation.KeyTime>\-Werten basiert.  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.KeyTime>   
 <xref:System.Windows.Media.Animation.KeySpline>   
 <xref:System.Windows.Media.Animation.Timeline>   
 [Beispiel für die Animation von Splines für Keyframes](http://go.microsoft.com/fwlink/?LinkID=160011)   
 [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)