---
title: Von-Zu-by-Animationen im Überblick
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 135f01823d374b30f8d4d41762d2267a254f98c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186464"
---
# <a name="fromtoby-animations-overview"></a>Übersicht über From/To/By-Animationen
Dieses Thema beschreibt, wie Sie From/To/By-Animationen verwenden, um Abhängigkeitseigenschaften zu animieren. Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Werten.  
  
<a name="prereq"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Um dieses Thema zu verstehen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sollten Sie mit Animationsfeatures vertraut sein. Eine Einführung in Animationsfeatures finden Sie in der [Animationsübersicht](animation-overview.md).  
  
<a name="whatisanimation"></a>
## <a name="what-is-a-fromtoby-animation"></a>Was ist eine From/To/By-Animation?  
 Eine Von/To/By-Animation ist <xref:System.Windows.Media.Animation.AnimationTimeline> ein Typ, der einen Übergang zwischen einem Startwert und einem Endwert erzeugt. Die Zeit, die der Übergang benötigt, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> wird durch die dieser Animation bestimmt.  
  
 Sie können eine Von/To/By-Animation auf <xref:System.Windows.Media.Animation.Storyboard> eine Eigenschaft anwenden, indem Sie <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> ein In-Markup und Code oder die Methode im Code verwenden. Sie können auch eine Von/To/By-Animation verwenden, um eine <xref:System.Windows.Media.Animation.AnimationClock> zu erstellen und auf eine oder mehrere Eigenschaften anzuwenden. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie in der [Übersicht über Eigenschaftenanimationstechniken](property-animation-techniques-overview.md).  
  
 From/To/By-Animationen können nicht über mehr als zwei Zielwerte verfügen. Wenn Sie eine Animation benötigen, die über mehr als zwei Zielwerte verfügt, verwenden Sie eine Keyframe-Animation. Keyframe-Animationen werden in der [Key-Frame-Animationsübersicht](key-frame-animations-overview.md)beschrieben.  
  
<a name="animation_types"></a>
## <a name="fromtoby-animation-types"></a>From/To/By-Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen. Um eine Eigenschaft zu <xref:System.Double>animieren, die eine annimmt, z. B. die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eines Elements, verwenden Sie eine Animation, die Werte erzeugt. <xref:System.Double> Um eine Eigenschaft zu <xref:System.Windows.Point>animieren, <xref:System.Windows.Point> die eine verwendet, verwenden Sie eine Animation, die Werte erzeugt usw.  
  
 Von/Bis/Durch-Animationsklassen gehören <xref:System.Windows.Media.Animation> zum Namespace und verwenden die folgende Namenskonvention:  
  
 * \<Typ>*`Animation`  
  
 Wobei * \<Typ>* ist der Werttyp, den die Klasse animiert.  
  
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
 Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Zielwerten. Es ist üblich, einen Startwert (satz <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> es mithilfe der Eigenschaft) und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> einen Endwert (set it by using the property) anzugeben. Sie können jedoch auch nur einen Startwert, einen Zielwert oder einen Offsetwert angeben. In diesen Fällen ruft die Animation den fehlenden Zielwert aus der Eigenschaft ab, die animiert wird. Die folgende Liste beschreibt die verschiedenen Methoden, um die Zielwerte einer Animation anzugeben.  
  
- **Startwert**  
  
     Verwenden <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Sie die Eigenschaft, wenn Sie den Startwert einer Animation explizit angeben möchten. Sie können <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> die Eigenschaft selbst oder <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> mit der oder der Eigenschaft nutzen. Wenn Sie nur <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> die Eigenschaft angeben, wechselt die Animation von diesem Wert zum Basiswert der animierten Eigenschaft.  
  
- **Endwert**  
  
     Um einen Endwert einer Animation <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> anzugeben, verwenden Sie deren Eigenschaft. Wenn Sie <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> die Eigenschaft selbst verwenden, ruft die Animation ihren Startwert von der Eigenschaft ab, die animiert wird, oder aus der Ausgabe einer anderen Animation, die auf dieselbe Eigenschaft angewendet wird. Sie können <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> die Eigenschaft <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> zusammen mit der Eigenschaft verwenden, um Start- und Endwerte für die Animation explizit anzugeben.  
  
- **Offsetwert**  
  
     Mit <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> der Eigenschaft können Sie einen Offset anstelle eines expliziten Start- oder Endwerts für die Animation angeben. Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft einer Animation gibt an, wie stark die Animation einen Wert über ihre Dauer ändert. Sie können <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> die Unterkunft selbst <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> oder mit der Unterkunft nutzen. Wenn Sie nur <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> die Eigenschaft angeben, fügt die Animation den Offsetwert zum Basiswert der Eigenschaft oder zur Ausgabe einer anderen Animation hinzu.  
  
<a name="examples"></a>
## <a name="using-fromtoby-values"></a>Verwenden von From/To/By-Werten  
 In den folgenden Abschnitten <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>wird <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>beschrieben, wie die , und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften zusammen oder getrennt verwendet werden.  
  
 Die Beispiele in diesem <xref:System.Windows.Media.Animation.DoubleAnimation>Abschnitt verwenden jeweils eine , die eine Art <xref:System.Windows.FrameworkElement.Width%2A> von Von/To/By-Animation ist, um die Eigenschaft eines <xref:System.Windows.Shapes.Rectangle> geräts unabhängigen Pixels hoch und 100 geräteunabhängige Pixel breit zu animieren.  
  
 Obwohl jedes Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation>eine verwendet, verhalten sich die Eigenschaften Von, An und By aller Von/To/By-Animationen identisch. Obwohl jedes dieser Beispiele <xref:System.Windows.Media.Animation.Storyboard>eine verwendet, können Sie Von/To/By-Animationen auf andere Weise verwenden. Weitere Informationen finden Sie unter [Übersicht über Eigenschaftenanimationstechniken](property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>Von/An  
 Wenn Sie <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> und die Werte zusammen festlegen, wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Animation von dem von der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft angegebenen Wert zu dem von der Eigenschaft angegebenen Wert fort.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> wird <xref:System.Windows.Media.Animation.DoubleAnimation> die Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Auf 50 und ihre Eigenschaft auf 300 festgelegt. Als Ergebnis <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> wird der von 50 bis 300 animiert.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>To  
 Wenn Sie nur <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> die Eigenschaft festlegen, wird die Animation vom Basiswert der animierten Eigenschaft oder von der Ausgabe einer kompositorierenden Animation, die zuvor auf dieselbe Eigenschaft angewendet wurde, zu dem Wert, der von der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft angegeben wird, fort.  
  
 ("Komponierende Animation" <xref:System.Windows.Media.Animation.ClockState.Active> bezieht <xref:System.Windows.Media.Animation.ClockState.Filling> sich auf eine oder eine Animation, die zuvor auf dieselbe <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> Eigenschaft angewendet wurde, die noch in Kraft ist, als die aktuelle Animation mithilfe des Übergabeverhaltens angewendet wurde.)  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> wird nur <xref:System.Windows.Media.Animation.DoubleAnimation> die Eigenschaft des auf 300 festgelegt. Da kein Startwert angegeben <xref:System.Windows.Media.Animation.DoubleAnimation> wurde, verwendet der den Basiswert (100) der <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft als Startwert. Der <xref:System.Windows.FrameworkElement.Width%2A> der <xref:System.Windows.Shapes.Rectangle> wird von 100 bis zum Zielwert der Animation von 300 animiert.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>nach  
 Wenn Sie nur <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> die Eigenschaft einer Animation festlegen, wird die Animation vom Basiswert der Eigenschaft, die animiert wird, oder von der Ausgabe <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> einer kompositorierenden Animation zur Summe dieses Werts und des von der Eigenschaft angegebenen Werts fort.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> wird nur <xref:System.Windows.Media.Animation.DoubleAnimation> die Eigenschaft des auf 300 festgelegt. Da im Beispiel kein Startwert <xref:System.Windows.Media.Animation.DoubleAnimation> angegeben ist, verwendet <xref:System.Windows.FrameworkElement.Width%2A> der den Basiswert der Eigenschaft 100 als Startwert. Der Endwert wird bestimmt, indem der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation, 300, zu ihrem Startwert 100: 400 addiert wird. Als Ergebnis <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> wird der von 100 bis 400 animiert.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Wenn Sie <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> und die Eigenschaften einer Animation festlegen, wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Animation von dem von der Eigenschaft angegebenen <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert zu dem Wert, der durch die Summe der und-Eigenschaften angegeben wird, fort.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> wird <xref:System.Windows.Media.Animation.DoubleAnimation> die Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Auf 50 und ihre Eigenschaft auf 300 festgelegt. Der Endwert wird bestimmt, indem der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation, 300, zu ihrem Startwert 50: 350 hinzugefügt wird. Als Ergebnis <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> wird der von 50 bis 350 animiert.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>From  
 Wenn Sie nur <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> den Wert einer Animation angeben, wird die Animation <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> von dem von der Eigenschaft angegebenen Wert zum Basiswert der Eigenschaft, die animiert wird, oder zur Ausgabe einer kompositorierenden Animation fort.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> wird nur <xref:System.Windows.Media.Animation.DoubleAnimation> die Eigenschaft der auf 50 festgelegt. Da kein Endwert angegeben <xref:System.Windows.Media.Animation.DoubleAnimation> wurde, verwendet <xref:System.Windows.FrameworkElement.Width%2A> der den Basiswert der Eigenschaft 100 als Endwert. Der <xref:System.Windows.FrameworkElement.Width%2A> der <xref:System.Windows.Shapes.Rectangle> wird von 50 zum Basiswert der <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft 100 animiert.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Wenn Sie sowohl <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften als auch <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> die Eigenschaften einer Animation festlegen, wird die Eigenschaft ignoriert.  
  
<a name="otheranimationtypes"></a>
## <a name="other-animation-types"></a>Andere Animationstypen  
 Von/To/By-Animationen sind nicht die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einzigen Arten von Animationen, die bietet: es bietet auch Key-Frame-Animationen und Pfadanimationen.  
  
- Eine Keyframe-Animation animiert entlang einer beliebigen Anzahl von Zielwerten, die mithilfe von Keyframes beschrieben. Weitere Informationen finden Sie in der [Key-Frame-Animationsübersicht](key-frame-animations-overview.md).  
  
- Eine Pfadanimation generiert Ausgabewerte aus einer <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie in der [Pfadanimationsübersicht](path-animations-overview.md).  
  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie außerdem Ihre eigenen benutzerdefinierten Animationstypen erstellen. Weitere Informationen finden Sie in der [Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Übersicht über Pfadanimationen](path-animations-overview.md)
- [Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md)
- [Beispiel für From-, To- und By-Animationszielwerte](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
