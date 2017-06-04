---
title: "&#220;bersicht &#252;ber From/To/By-Animationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation, From/To/By"
  - "From/To/By-Animation"
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber From/To/By-Animationen
In diesem Thema wird beschrieben, wie From\/To\/By\-Animationen verwendet werden, um [Abhängigkeitseigenschaften](GTMT) zu animieren.  Eine From\/To\/By\-Animation erstellt einen Übergang zwischen zwei Werten.  
  
 Dieses Thema enthält folgende Abschnitte.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prereq"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationsfeatures vertraut sein.  Eine Einführung in Animationsfeatures finden Sie unter der [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="whatisanimation"></a>   
## Was ist eine From\/To\/By\-Animation?  
 Eine From\/To\/By\-Animation ist ein Typ von <xref:System.Windows.Media.Animation.AnimationTimeline>, der einen Übergang zwischen einem Startwert und einem Endwert erstellt.  Die Zeitdauer, nach der der Übergang abgeschlossen ist, wird von <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Animation bestimmt.  
  
 Sie können eine From\/To\/By\-Animation in Markup und Code mithilfe eines <xref:System.Windows.Media.Animation.Storyboard> oder in Code mit der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode auf eine Eigenschaft anwenden.  Sie können mit einer From\/To\/By\-Animation auch eine <xref:System.Windows.Media.Animation.AnimationClock> erstellen und sie auf eine oder mehrere Eigenschaften anwenden.  Weitere Informationen zu den verschiedenen Anwendungsmethoden für Animationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
 From\/To\/By\-Animationen können über höchstens zwei Zielwerte verfügen.  Wenn Sie eine Animation mit mehr als zwei Zielwerten benötigen, müssen Sie eine Keyframe\-Animation verwenden.  Keyframe\-Animationen werden unter [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) beschrieben.  
  
<a name="animation_types"></a>   
## From\/To\/By\-Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es für die einzelnen Eigenschaftentypen unterschiedliche Animationstypen.  Zum Animieren einer Eigenschaft, die einen <xref:System.Double>\-Wert entgegennimmt \(wie zum Beispiel die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft eines Elements\), verwenden Sie eine Animation, die <xref:System.Double>\-Werte erzeugt.  Zum Animieren einer Eigenschaft, die einen <xref:System.Windows.Point>\-Wert entgegennimmt, verwenden Sie eine Animation, die <xref:System.Windows.Point>\-Werte erzeugt, usw.  
  
 From\/To\/By\-Animationsklassen gehören zum <xref:System.Windows.Media.Animation>\-Namespace und verwenden die folgende Benennungskonvention:  
  
 *\<Typ\>* `Animation`  
  
 Wobei *\<Typ\>* für den Wertetyp steht, den die Klasse animiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die folgenden From\/To\/By\-Animationsklassen zur Verfügung.  
  
|Eigenschaftentyp|Zugehörige From\/To\/By\-Animationsklasse|  
|----------------------|-----------------------------------------------|  
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
## Zielwerte  
 Eine From\/To\/By\-Animation erstellt einen Übergang zwischen zwei Zielwerten.  Üblicherweise wird ein Startwert \(in der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft\) und ein Endwert \(in der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft\) angegeben.  Sie können aber auch nur einen Startwert, einen Zielwert oder einen Offsetwert angeben.  In diesen Fällen ruft die Animation den fehlenden Zielwert aus der Eigenschaft ab, die animiert wird.  Die folgende Liste beschreibt die verschiedenen Möglichkeiten, die Zielwerte einer Animation anzugeben.  
  
-   ****Startwert****  
  
     Verwenden Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft, wenn Sie den Startwert einer Animation explizit angeben möchten.  Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft allein oder zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft oder der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft verwenden.  Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft angeben, erfolgt durch die Animation ein Übergang von diesem Wert zu dem Basiswert der animierten Eigenschaft.  
  
-   ****Endwert****  
  
     Verwenden Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft einer Animation, um einen Endwert anzugeben.  Wenn Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft allein verwenden, ruft die Animation ihren Startwert aus der Eigenschaft ab, die animiert wird, oder aus der Ausgabe einer anderen Animation, die auf dieselbe Eigenschaft angewendet wird.  Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft verwenden, um Start\- und Endwerte für die Animation explizit anzugeben.  
  
-   ****Offsetwert****  
  
     Mit der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft können Sie einen Offset anstatt expliziter Start\- oder Endwerte für die Animation angeben.  Die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft einer Animation gibt an, um wie viel ein Wert während einer Animation geändert wird.  Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft allein oder zusammen mit der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft verwenden.  Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft angeben, addiert die Animation den Offsetwert zum Basiswert der Eigenschaft oder zur Ausgabe einer anderen Animation.  
  
<a name="examples"></a>   
## Verwenden von From\/To\/By\-Werten  
 In den folgenden Abschnitten wird beschrieben, wie die Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> einzeln oder zusammen verwendet werden.  
  
 In jedem Beispiel in diesem Abschnitt wird der From\/To\/By\-Animationstyp <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet, um die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft eines <xref:System.Windows.Shapes.Rectangle>\-Objekts zu animieren, das 10 [geräteunabhängige Pixel](GTMT) hoch und 100 [geräteunabhängige Pixel](GTMT) breit ist.  
  
 Auch wenn in jedem Beispiel eine <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet wird, verhalten sich die From\-, To\- und By\-Eigenschaften aller From\/To\/By\-Animationen identisch.  Auch wenn in jedem Beispiel ein <xref:System.Windows.Media.Animation.Storyboard> verwendet wird, können Sie From\/To\/By\-Animationen auch auf andere Weisen verwenden.  Weitere Informationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### From\/To  
 Wenn Sie die Werte <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> zusammen festlegen, verläuft die Animation von dem in der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft festgelegten Wert zu dem in der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft festgelegten Wert.  
  
 Im folgenden Beispiel wird für die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation>\-Elements der Wert 50 festgelegt, und für ihre <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft der Wert 300.  Als Ergebnis wird die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft des <xref:System.Windows.Shapes.Rectangle>\-Elements von 50 zu 300 animiert.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### To  
 Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft festlegen, verläuft die Animation vom Basiswert der animierten Eigenschaft bzw. von der Ausgabe einer Composing\-Animation, die zuvor auf dieselbe Eigenschaft angewendet wurde, zu dem von der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft angegebenen Wert.  
  
 \("Composing\-Animation" bezieht sich auf eine zuvor auf dieselbe Eigenschaft angewendete <xref:System.Windows.Media.Animation.ClockState>\- oder <xref:System.Windows.Media.Animation.ClockState>\-Animation, die noch wirksam ist, wenn die aktuelle Animation mittels des <xref:System.Windows.Media.Animation.HandoffBehavior>\-Übergabeverhaltens angewendet wird.\)  
  
 Im folgenden Beispiel wird nur für die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation>\-Elements der Wert 300 festgelegt  Da kein Startwert angegeben wurde, verwendet das <xref:System.Windows.Media.Animation.DoubleAnimation>\-Element den Basiswert \(100\) der <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft als Startwert.  Die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft von <xref:System.Windows.Shapes.Rectangle> wird von 100 zum Zielwert 300 der Animation animiert.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### Von  
 Wenn Sie nur die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft einer Animation festlegen, verläuft die Animation vom Basiswert der Eigenschaft, die animiert wird, bzw. von der Ausgabe einer Composing\-Animation, zu der Summe aus diesem Wert und dem durch die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft angegebenen Wert.  
  
 Im folgenden Beispiel wird nur für die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation>\-Elements der Wert 300 festgelegt  Da in dem Beispiel kein Startwert angegeben wird, verwendet das <xref:System.Windows.Media.Animation.DoubleAnimation>\-Element den Basiswert der <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft \(100\) als ihren Startwert.  Der Endwert wird ermittelt, indem der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Wert der Animation \(300\) zu ihrem Startwert \(100\) addiert wird: 400.  Als Ergebnis wird die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft des <xref:System.Windows.Shapes.Rectangle>\-Elements von 100 zu 400 animiert.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### From\/By  
 Wenn Sie die Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> einer Animation festlegen, verläuft die Animation von dem durch die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft angegebenen Wert bis zu dem von der Summe der Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> angegebenen Wert.  
  
 Im folgenden Beispiel wird für die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation>\-Elements der Wert 50 festgelegt, und für ihre <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft der Wert 300.  Der Endwert wird ermittelt, indem der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Wert der Animation \(300\) zu ihrem Startwert \(50\) addiert wird: 350.  Als Ergebnis wird die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft des <xref:System.Windows.Shapes.Rectangle>\-Elements von 50 zu 350 animiert.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### Von  
 Wenn Sie nur den <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Wert einer Animation festlegen, verläuft die Animation von dem von der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft angegebenen Wert bis zu dem Basiswert der Eigenschaft, die animiert wird, bzw. zu der Ausgabe einer Composing\-Animation.  
  
 Im folgenden Beispiel wird nur für die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\-Eigenschaft des <xref:System.Windows.Media.Animation.DoubleAnimation>\-Elements der Wert 50 festgelegt  Da kein Endwert angegeben wurde, verwendet das <xref:System.Windows.Media.Animation.DoubleAnimation>\-Element den Basiswert der <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft \(100\) als Endwert.  Die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft von <xref:System.Windows.Shapes.Rectangle> wird von 50 bis zu dem Basiswert der <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft \(100\) animiert.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### To\/By  
 Wenn Sie sowohl die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft als auch die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft einer Animation festlegen, wird die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>\-Eigenschaft ignoriert.  
  
<a name="otheranimationtypes"></a>   
## Andere Animationstypen  
 Außer From\/To\/By\-Animationen stellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] noch weitere Animationstypen zur Verfügung: Keyframe\-Animationen und Path\-Animationen.  
  
-   Eine Keyframe\-Animation animiert entlang einer beliebigen Anzahl von Zielwerten, die mithilfe von Keyframes beschrieben werden.  Weitere Informationen finden Sie unter [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   Eine Path\-Animation generiert Ausgabewerte von einem <xref:System.Windows.Media.PathGeometry>.  Weitere Informationen finden Sie unter [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie auch eigene benutzerdefinierte Animationstypen erstellen.  Weitere Informationen finden Sie unter [Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)   
 [Beispiel für From, To, and By\-Animationszielwerte](http://go.microsoft.com/fwlink/?LinkID=159988)