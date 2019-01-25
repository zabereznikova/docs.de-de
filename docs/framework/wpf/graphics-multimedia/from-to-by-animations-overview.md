---
title: Übersicht über aus / To / By-Animationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 39a3cd059c0fa9aad1ef2c1ae50fa37b95df52d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650443"
---
# <a name="fromtoby-animations-overview"></a>Übersicht über From/To/By-Animationen
Dieses Thema beschreibt, wie Sie From/To/By-Animationen verwenden, um Abhängigkeitseigenschaften zu animieren. Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Werten.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Um dieses Thema zu verstehen, sollten Sie mit vertraut sein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Animationsfunktionen. Eine Einführung in Animationsfunktionen, finden Sie unter den [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>Was ist eine From/To/By-Animation?  
 Eine From/To/By-Animation ist eine Art von <xref:System.Windows.Media.Animation.AnimationTimeline> , die einen Übergang zwischen einem Startwert und einen Endwert erstellt. Die Zeitdauer, der der Übergang dauert richtet sich nach der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation.  
  
 Sie können eine From/To/By anwenden Animation auf eine Eigenschaft mit einem <xref:System.Windows.Media.Animation.Storyboard> im Markup und Code oder mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode im Code. Sie können auch eine Animation to-verwenden, erstellen eine <xref:System.Windows.Media.Animation.AnimationClock> und auf eine oder mehrere Eigenschaften anwenden. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
 From/To/By-Animationen können nicht über mehr als zwei Zielwerte verfügen. Wenn Sie eine Animation benötigen, die über mehr als zwei Zielwerte verfügt, verwenden Sie eine Keyframe-Animation. Keyframe-Animationen werden unter der [Übersicht über Keyframe Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>From/To/By-Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen. Zum Animieren einer Eigenschaft, die akzeptiert eine <xref:System.Double>, z. B. die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eines Elements, verwenden Sie eine Animation, die erzeugt <xref:System.Double> Werte. Zum Animieren einer Eigenschaft, die akzeptiert eine <xref:System.Windows.Point>, verwenden Sie eine Animation, die erzeugt <xref:System.Windows.Point> Werte und So weiter.  
  
 From/To/By-Animationsklassen gehören zum die <xref:System.Windows.Media.Animation> Namespace und verwenden Sie die folgende Benennungskonvention verwendet:  
  
 *\<Typ>* `Animation`  
  
 Wobei *\<Typ>* der Wertetyp ist, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die folgenden From/To/By-Animationsklassen zur Verfügung.  
  
|Eigenschaftentyp|Entsprechende From/To/By-Animationsklassen|  
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
 Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Zielwerten. Es ist üblich, einen Startwert anzugeben (zum Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft) und einen Endwert (zum Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft). Sie können jedoch auch nur einen Startwert, einen Zielwert oder einen Offsetwert angeben. In diesen Fällen ruft die Animation den fehlenden Zielwert aus der Eigenschaft ab, die animiert wird. Die folgende Liste beschreibt die verschiedenen Methoden, um die Zielwerte einer Animation anzugeben.  
  
-   **Startwert**  
  
     Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, wenn Sie den Startwert einer Animation explizit angeben möchten. Sie können der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft allein oder zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> oder <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft. Wenn Sie nur angeben, die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft, die Animation ein Übergang von diesem Wert zu dem Basiswert der animierten Eigenschaft.  
  
-   **Endwert**  
  
     Um einen Endwert einer Animation anzugeben, verwenden die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft. Bei Verwendung der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft selbst, ruft die Animation ihren Startwert aus der Eigenschaft, die animiert wird, oder aus der Ausgabe einer anderen Animation, die auf dieselbe Eigenschaft angewendet wird. Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, um explizit anzugeben, Start- und Endwerte der Animation.  
  
-   **Offsetwert**  
  
     Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft können Sie einen Offset anstatt expliziter Start- oder Endwerte für die Animation angeben. Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft einer Animation gibt an, um wie viel ein Wert für die Dauer des ändert. Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft allein oder zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft. Wenn Sie nur angeben, die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft, die Animation fügt den Offsetwert zum Basiswert der Eigenschaft oder zur Ausgabe einer anderen Animation.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Verwenden von From/To/By-Werten  
 In den folgenden Abschnitten wird beschrieben, wie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften einzeln oder zusammen.  
  
 Die Beispiele in diesem Abschnitt wird jede mit einer <xref:System.Windows.Media.Animation.DoubleAnimation>, dies ist eine Art von From/To/By-Animation, um zu animieren der <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eine <xref:System.Windows.Shapes.Rectangle> , 10 geräteunabhängige Pixel hoch und 100 geräteunabhängige Pixel breit.  
  
 Obwohl jedes Beispiel verwendet eine <xref:System.Windows.Media.Animation.DoubleAnimation>, From, To und By Eigenschaften aller From/To/By Animationen Verhalten sich identisch. Obwohl jedes dieser Beispiele verwendet eine <xref:System.Windows.Media.Animation.Storyboard>, können Sie From/To/By-Animationen auf andere Weise. Weitere Informationen finden Sie unter [Eigenschaft Techniken-Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>Von/An  
 Beim Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Werte zusammen, um der Animation erfolgt ab der Wert, der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft verwenden, um den Wert, der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50 und die zugehörige <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> -Eigenschaft auf 300 festgelegt. Daher die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 50 zu 300 animiert.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>Beschreibung  
 Wenn Sie festlegen, nur der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> -Eigenschaft, verläuft die Animation vom Basiswert der animierten Eigenschaft oder aus der Ausgabe einer composing-Animation, die zuvor auf dieselbe Eigenschaft, auf den Wert angewendet wurde, die angegeben wird der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Diese Eigenschaft.  
  
 ("Composing-Animation" bezieht sich auf eine <xref:System.Windows.Media.Animation.ClockState.Active> oder <xref:System.Windows.Media.Animation.ClockState.Filling> Animation, die zuvor auf dieselbe Eigenschaft, die noch wirksam ist angewendet, wenn die aktuelle Animation angewendet wurde, mithilfe der <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> -Übergabeverhalten.)  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 300. Da kein Startwert angegeben wurde, die <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet den Basiswert (100), der die <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft als Startwert. Die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 100 zum Zielwert 300 der Animation animiert.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>um  
 Wenn Sie festlegen, nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft einer Animation, verläuft die Animation vom Basiswert der Eigenschaft, die animiert wird, oder klicken Sie in der Ausgabe einer composing-Animation auf die Summe dieses Werts und der Wert, der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Diese Eigenschaft.  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 300. Da das Beispiel einen Startwert, nicht angegeben ist die <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet den Basiswert von der <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft (100) als ihren Startwert. Der Endwert wird ermittelt, durch das Hinzufügen der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation (300) zu ihrem Startwert 100: 400. Daher die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 100 zu 400 animiert.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Beim Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften einer Animation, verläuft die Animation von dem Wert, der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft verwenden, um den Wert, der durch die Summe der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50 und die zugehörige <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft auf 300 festgelegt. Der Endwert wird ermittelt, durch das Hinzufügen der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation (300) zu ihrem Startwert 50: 350. Daher die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 50 zu 350 animiert.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>Von  
 Beim Angeben von nur die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Wert einer Animation, verläuft die Animation von dem Wert, der angegeben wird, und die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, die dem Basiswert der Eigenschaft, die animiert wird, oder der Ausgabe einer composing-Animation.  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50. Da kein Endwert angegeben wurde, die <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet den Basiswert von der <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft (100) als Endwert. Die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 50 zum Basiswert der animiert die <xref:System.Windows.FrameworkElement.Width%2A> 100-Eigenschaft.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Wenn Sie beide Optionen festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft einer Animation, die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft wird ignoriert.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Andere Animationstypen  
 From/To/By-Animationen sind nicht die einzige Art von Animationen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet: Es bietet auch Keyframe-Animationen und Path-Animationen.  
  
-   Eine Keyframe-Animation animiert entlang einer beliebigen Anzahl von Zielwerten, die mithilfe von Keyframes beschrieben. Weitere Informationen finden Sie unter den [Übersicht über Keyframe Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   Eine Pfadanimation generiert Ausgabewerte aus einem <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie unter den [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie außerdem Ihre eigenen benutzerdefinierten Animationstypen erstellen. Weitere Informationen finden Sie unter den [Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
- [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)
- [Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)
- [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](https://go.microsoft.com/fwlink/?LinkID=159988)
