---
title: Übersicht über from-to-by-Animationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 661c035f55ba1fb550726d75921cd01a72b2eecc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448999"
---
# <a name="fromtoby-animations-overview"></a>Übersicht über From/To/By-Animationen
Dieses Thema beschreibt, wie Sie From/To/By-Animationen verwenden, um Abhängigkeitseigenschaften zu animieren. Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Werten.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animations Features vertraut sein. Eine Einführung in Animations Funktionen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>Was ist eine From/To/By-Animation?  
 Eine from/to/by-Animation ist ein Typ von <xref:System.Windows.Media.Animation.AnimationTimeline>, der einen Übergang zwischen einem Startwert und einem Endwert erstellt. Die Zeitspanne, die der Übergang bis zum Abschluss dauert, wird durch den <xref:System.Windows.Media.Animation.Timeline.Duration%2A> dieser Animation bestimmt.  
  
 Sie können eine from/to/by-Animation auf eine Eigenschaft anwenden, indem Sie eine <xref:System.Windows.Media.Animation.Storyboard> in Markup und Code verwenden oder indem Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode im Code verwenden. Sie können auch eine from/to/by-Animation verwenden, um eine <xref:System.Windows.Media.Animation.AnimationClock> zu erstellen und Sie auf eine oder mehrere Eigenschaften anzuwenden. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md).  
  
 From/To/By-Animationen können nicht über mehr als zwei Zielwerte verfügen. Wenn Sie eine Animation benötigen, die über mehr als zwei Zielwerte verfügt, verwenden Sie eine Keyframe-Animation. Keyframe-Animationen werden in der [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)beschrieben.  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>From/To/By-Animationstypen  
 Da Animationen Eigenschaftswerte generieren, sind verschiedene Animationstypen für unterschiedliche Eigenschaftentypen vorhanden. Verwenden Sie zum Animieren einer Eigenschaft, die eine <xref:System.Double>annimmt, wie z. b. die <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft eines Elements, eine Animation, die <xref:System.Double> Werte erzeugt. Verwenden Sie zum Animieren einer Eigenschaft, die einen <xref:System.Windows.Point>annimmt, eine Animation, die <xref:System.Windows.Point> Werte erzeugt, usw.  
  
 From/to/by-Animations Klassen gehören zum <xref:System.Windows.Media.Animation>-Namespace und verwenden die folgende Benennungs Konvention:  
  
 *\<Typ >* `Animation`  
  
 Wobei *\<Typ>* der Wertetyp ist, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die folgenden From/To/By-Animationsklassen zur Verfügung.  
  
|Eigenschaftstyp|Entsprechende From/To/By-Animationsklassen|  
|-------------------|------------------------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>   
## <a name="target-values"></a>Zielwerte  
 Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Zielwerten. Es ist üblich, einen Startwert (mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft festzulegen) und einen Endwert (mit der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft festzulegen) anzugeben. Sie können jedoch auch nur einen Startwert, einen Zielwert oder einen Offsetwert angeben. In diesen Fällen ruft die Animation den fehlenden Zielwert aus der Eigenschaft ab, die animiert wird. Die folgende Liste beschreibt die verschiedenen Methoden, um die Zielwerte einer Animation anzugeben.  
  
- **Startwert**  
  
     Verwenden Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft, wenn Sie den Startwert einer Animation explizit angeben möchten. Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft eigenständig oder mit der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-oder <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft verwenden. Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft angeben, geht die Animation von diesem Wert zum Basiswert der animierten Eigenschaft über.  
  
- **Endwert**  
  
     Um einen Endwert einer Animation anzugeben, verwenden Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft. Wenn Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft eigenständig verwenden, ruft die Animation ihren Startwert aus der Eigenschaft ab, die animiert wird, oder von der Ausgabe einer anderen Animation, die auf dieselbe Eigenschaft angewendet wird. Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft in Verbindung mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft verwenden, um die Anfangs-und Endwerte für die Animation explizit anzugeben.  
  
- **Offsetwert**  
  
     Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft ermöglicht es Ihnen, anstelle eines expliziten Start-oder Endwerts für die Animation einen Offset anzugeben. Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft einer Animation gibt an, wie viel die Animation einen Wert über die Dauer ändert. Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft eigenständig oder mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft verwenden. Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft angeben, fügt die Animation den Offset Wert dem Basiswert der Eigenschaft oder der Ausgabe einer anderen Animation hinzu.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Verwenden von From/To/By-Werten  
 In den folgenden Abschnitten wird beschrieben, wie die Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> in oder separat verwendet werden.  
  
 In den Beispielen in diesem Abschnitt wird jeweils eine <xref:System.Windows.Media.Animation.DoubleAnimation>verwendet, bei der es sich um eine Art von from/to/by-Animation handelt, um die <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft eines <xref:System.Windows.Shapes.Rectangle> zu animieren, das 10 geräteunabhängige Pixel hoch und 100 geräteunabhängige Pixel breit ist.  
  
 Obwohl jedes Beispiel eine <xref:System.Windows.Media.Animation.DoubleAnimation>verwendet, Verhalten sich die from-, to-und by-Eigenschaften aller from/to/by-Animationen identisch. Obwohl jedes dieser Beispiele eine <xref:System.Windows.Media.Animation.Storyboard>verwendet, können Sie from/to/by-Animationen auf andere Weise verwenden. Weitere Informationen finden Sie unter [Übersicht über die Animation von Eigenschaften](property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>Von/An  
 Wenn Sie die Werte für <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> in kombinieren, verläuft die Animation von dem Wert, der von der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft angegeben wird, mit dem Wert, der von der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft angegeben wird.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50 und dessen <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft auf 300 festgelegt. Folglich wird die <xref:System.Windows.FrameworkElement.Width%2A> der <xref:System.Windows.Shapes.Rectangle> von 50 zu 300 animiert.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>Zweck  
 Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft festlegen, verläuft die Animation vom Basiswert der animierten Eigenschaft oder von der Ausgabe einer Kompositions Animation, die zuvor auf dieselbe Eigenschaft angewendet wurde, auf den Wert, der in der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft angegeben ist.  
  
 ("Verfassen der Animation" bezieht sich auf eine <xref:System.Windows.Media.Animation.ClockState.Active> oder <xref:System.Windows.Media.Animation.ClockState.Filling> Animation, die zuvor auf dieselbe Eigenschaft angewendet wurde, die noch wirksam ist, wenn die aktuelle Animation mithilfe des <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> Übergabe Verhaltens angewendet wurde.)  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation> auf 300 festgelegt. Da kein Startwert angegeben wurde, verwendet der <xref:System.Windows.Media.Animation.DoubleAnimation> den Basiswert (100) der <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft als Startwert. Der <xref:System.Windows.FrameworkElement.Width%2A> des <xref:System.Windows.Shapes.Rectangle> wird von 100 zum Zielwert 300 der Animation animiert.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>nach  
 Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft einer Animation festlegen, wird die Animation vom Basiswert der zu animierenden Eigenschaft oder von der Ausgabe einer Kompositions Animation bis zur Summe dieses Werts und des Werts, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft angegeben wird, fortgesetzt.  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation> auf 300 festgelegt. Da im Beispiel kein Startwert angegeben ist, verwendet das <xref:System.Windows.Media.Animation.DoubleAnimation> den Basiswert der <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft, 100, als Startwert. Der Endwert wird bestimmt, indem der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation, 300, dem Startwert 100:400 hinzugefügt wird. Folglich wird die <xref:System.Windows.FrameworkElement.Width%2A> der <xref:System.Windows.Shapes.Rectangle> von 100 zu 400 animiert.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Wenn Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften einer Animation festlegen, verläuft die Animation von dem Wert, der von der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft angegeben wird, mit dem Wert, der durch die Summe der Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> angegeben wird.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50 und dessen <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft auf 300 festgelegt. Der Endwert wird bestimmt, indem der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation, 300, dem Startwert 50:350 hinzugefügt wird. Folglich wird die <xref:System.Windows.FrameworkElement.Width%2A> der <xref:System.Windows.Shapes.Rectangle> von 50 zu 350 animiert.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>Von  
 Wenn Sie nur den <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Wert einer Animation angeben, verläuft die Animation von dem Wert, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft angegeben wird, mit dem Basiswert der zu animierenden Eigenschaft oder der Ausgabe einer Kompositions Animation.  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50 festgelegt. Da kein Endwert angegeben wurde, verwendet der <xref:System.Windows.Media.Animation.DoubleAnimation> den Basiswert der <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft, 100, als Endwert. Der <xref:System.Windows.FrameworkElement.Width%2A> des <xref:System.Windows.Shapes.Rectangle> wird von 50 zum Basiswert der <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft, 100, animiert.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Wenn Sie die Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> der Animation festlegen, wird die Eigenschaft <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> ignoriert.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Andere Animationstypen  
 From/to/by-Animationen sind nicht die einzigen Typen von Animationen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitstellt: Sie stellen außerdem Keyframe-Animationen und Pfad Animationen bereit.  
  
- Eine Keyframe-Animation animiert entlang einer beliebigen Anzahl von Zielwerten, die mithilfe von Keyframes beschrieben. Weitere Informationen finden Sie unter [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md).  
  
- Eine Pfad Animation generiert Ausgabewerte aus einer <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie unter [Übersicht über Pfad Animationen](path-animations-overview.md).  
  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie außerdem Ihre eigenen benutzerdefinierten Animationstypen erstellen. Weitere Informationen finden Sie unter [Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Übersicht über Pfadanimationen](path-animations-overview.md)
- [Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md)
- [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
