---
title: "Übersicht über die FROM-zu-By-Animationen"
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
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c4c2c3b9cabb630b5762fdc49f6cb62eef28f71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="fromtoby-animations-overview"></a>Übersicht über From/To/By-Animationen
Dieses Thema beschreibt, wie Sie From/To/By-Animationen verwenden, um Abhängigkeitseigenschaften zu animieren. Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Werten.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit vertraut sein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animationen Funktionen. Eine Einführung zu Funktionen finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>Was ist eine From/To/By-Animation?  
 Eine From/zu/von Animation ist eine Art von <xref:System.Windows.Media.Animation.AnimationTimeline> , der einen Übergang zwischen einem Startwert und einen Endwert erstellt. Die Zeitspanne, die zum Abschließen der Übergangs richtet sich nach der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation.  
  
 Sie können eine From/zu/von anwenden Animation auf eine Eigenschaft mit einer <xref:System.Windows.Media.Animation.Storyboard> in Markup und Code oder mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode im Code. Sie können auch eine Animation From/To/By zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und wendet ihn auf eine oder mehrere Eigenschaften. Weitere Informationen zu den verschiedenen Methoden zum Anwenden von Animationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
 From/To/By-Animationen können nicht über mehr als zwei Zielwerte verfügen. Wenn Sie eine Animation benötigen, die über mehr als zwei Zielwerte verfügt, verwenden Sie eine Keyframe-Animation. Keyframe-Animationen in beschrieben werden die [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>From/To/By-Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Double>, wie z. B. die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eines Elements, verwenden Sie eine Animation, erzeugt <xref:System.Double> Werte. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Windows.Point>, verwenden Sie eine Animation, erzeugt <xref:System.Windows.Point> Werte und So weiter.  
  
 Von/zu/von Animationsklassen gehören zu den <xref:System.Windows.Media.Animation> Namespace und die folgende Benennungskonvention:  
  
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
 Eine From/To/By-Animation erstellt einen Übergang zwischen zwei Zielwerten. Es ist üblich, einen Anfangswert angeben (Legen Sie sie mithilfe der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft) und einen Endwert (Legen Sie sie mithilfe der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft). Sie können jedoch auch nur einen Startwert, einen Zielwert oder einen Offsetwert angeben. In diesen Fällen ruft die Animation den fehlenden Zielwert aus der Eigenschaft ab, die animiert wird. Die folgende Liste beschreibt die verschiedenen Methoden, um die Zielwerte einer Animation anzugeben.  
  
-   **Startwert**  
  
     Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, wenn Sie den Anfangswert der Animation explizit angeben möchten. Können Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft alleine oder zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> oder <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft. Wenn Sie nur angeben, dass die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft, die die Animation Übergänge von diesem Wert dem Basiswert der animierten Eigenschaft.  
  
-   **Endwert**  
  
     Verwenden Sie zum Angeben eines Endwert der Animation seine <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft. Bei Verwendung der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft selbst, ruft die Animation ihren Startwert aus der Eigenschaft, die animiert wird, oder aus der Ausgabe einer anderen Animation, die auf die gleiche Eigenschaft angewendet wird. Sie können der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, um explizit anzugeben, Start- und Endwert der Animation.  
  
-   **Offsetwert**  
  
     Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft ermöglicht Ihnen das Festlegen ein Offsets anstelle einer expliziten Anfangs- oder Endwert der Animation. Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft einer Animation gibt an, um wie viel die Animation einen Wert über seine Dauer ändert. Können Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft alleine oder zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft. Wenn Sie nur angeben, dass die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> -Eigenschaft, die Animation dem Basiswert der Eigenschaft oder die Ausgabe einer anderen Animation den Offsetwert hinzufügt.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Verwenden von From/To/By-Werten  
 In den folgenden Abschnitten wird beschrieben, wie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften einzeln oder zusammen.  
  
 In den Beispielen in diesem Abschnitt jedes eine <xref:System.Windows.Media.Animation.DoubleAnimation>, d. h. einen Typ von aus/zu/von Animationen zum Animieren der <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eine <xref:System.Windows.Shapes.Rectangle> also 10 geräteunabhängige Pixel hoch und 100 geräteunabhängige Pixel breit.  
  
 Obwohl in jedem Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation>, die aus, um nach den Eigenschaften der alle von/zu/von Animationen Verhalten und identisch. Obwohl jedes dieser Beispiele verwendet eine <xref:System.Windows.Media.Animation.Storyboard>, können Sie auf andere Weise von/zu/von Animationen. Weitere Informationen finden Sie unter [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>Von/An  
 Beim Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Werte zusammen, die im Verlauf des Animation aus dem Wert, der durch angegeben ist die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft, um den Wert, der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft von der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50 und dessen <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft auf 300. Daher die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 50 und 300 animiert.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>Beschreibung  
 Beim gerade Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> -Eigenschaft, die im Verlauf des Animation aus dem Basiswert der animierten Eigenschaft oder aus der Ausgabe einer zusammengesetzten Animation, die zuvor auf die gleiche Eigenschaft, auf den Wert angewendet wurde, die von angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Diese Eigenschaft.  
  
 ("Verfassen Animation" bezieht sich auf eine <xref:System.Windows.Media.Animation.ClockState.Active> oder <xref:System.Windows.Media.Animation.ClockState.Filling> Animation an, die zuvor auf die gleiche Eigenschaft angewendet werden, die weiterhin aktiv ist, wenn die aktuelle Animation angewendet wurde, mithilfe der <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> -Übergabeverhalten.)  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft von der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 300. Da kein Startwert angegeben wurde, die <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet den Basiswert (100), der die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft als Startwert. Die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 100 auf 300 Zielwert der Animation animiert.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>um  
 Wenn Sie festlegen, nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft einer Animation, verläuft die Animation aus dem Basiswert der Eigenschaft, die animiert wird, oder aus der Ausgabe einer zusammengesetzten Animation auf die Summe dieses Werts und der Wert, der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Diese Eigenschaft.  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft von der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 300. Da das Beispiel einen Startwert, nicht angegeben ist die <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet den Basiswert der <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft (100) als Startwert. Der Endwert wird bestimmt durch Hinzufügen der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation, 300, um ihren Startwert 100:400. Daher die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 100 bis 400 animiert.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Beim Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften einer Animation, verläuft die Animation von der Wert, der angegeben wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, um den Wert, der durch die Summe der angegebenen der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft von der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50 und dessen <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft auf 300. Der Endwert wird bestimmt durch Hinzufügen der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Wert der Animation, 300, um ihren Startwert 50:350. Daher die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> wird von 50 bis 350 animiert.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>Von  
 Beim Angeben von nur die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> im Verlauf des Animation aus dem Wert, der angegeben wird, den Wert einer Animation die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, die dem Basiswert der Eigenschaft, die animiert wird, oder der Ausgabe einer zusammengesetzten Animation.  
  
 Im folgenden Beispiel wird nur die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft von der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 50. Da kein Endwert angegeben wurde, die <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet den Basiswert der <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft (100) als Endwert. Die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Shapes.Rectangle> von 50 dem Basiswert der animierten ist die <xref:System.Windows.FrameworkElement.Width%2A> 100-Eigenschaft.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Wenn Sie beide Optionen festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften einer Animation die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft wird ignoriert.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Andere Animationstypen  
 Von/zu/von Animationen werden nicht der einzige Typ von Animationen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet: er enthält zudem Keyframe-Animationen und Path-Animationen.  
  
-   Eine Keyframe-Animation animiert entlang einer beliebigen Anzahl von Zielwerten, die mithilfe von Keyframes beschrieben. Weitere Informationen finden Sie unter der [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   Eine Path-Animation generiert Ausgabewerte von einem <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie unter der [Path Animationen Overview](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie außerdem Ihre eigenen benutzerdefinierten Animationstypen erstellen. Weitere Informationen finden Sie unter der [Animationen-Übersicht über benutzerdefinierte](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)  
 [Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)  
 [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](http://go.microsoft.com/fwlink/?LinkID=159988)
