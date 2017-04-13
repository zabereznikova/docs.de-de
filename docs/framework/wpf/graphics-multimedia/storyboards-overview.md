---
title: "&#220;bersicht &#252;ber Storyboards | Microsoft Docs"
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
  - "Storyboard-Syntax"
  - "Syntax, Storyboard"
  - "Zeitachsen"
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# &#220;bersicht &#252;ber Storyboards
In diesem Thema wird gezeigt, wie mit <xref:System.Windows.Media.Animation.Storyboard>\-Objekten Animationen organisiert und angewendet werden.  Es wird beschrieben, wie <xref:System.Windows.Media.Animation.Storyboard>\-Objekte interaktiv bearbeitet werden. Außerdem wird die Syntax für die indirekte Verwendung von Eigenschaften beschrieben.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit den verschiedenen Animationstypen und ihren grundlegenden Features vertraut sein.  Eine Einführung in Animationsfeatures finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Sie sollten auch wissen, wie angefügte Eigenschaften verwendet werden.  Weitere Informationen über angefügte Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## Was ist ein Storyboard?  
 Animationen sind nicht der einzige nützliche Zeitachsentyp.  Es stehen andere Zeitachsenklassen zur Verfügung, um bei der Organisation von Zeitachsengruppen zu helfen und Zeitachsen auf Eigenschaften anzuwenden.  Containerzeitachsen sind von der <xref:System.Windows.Media.Animation.TimelineGroup>\-Klasse abgeleitet und enthalten <xref:System.Windows.Media.Animation.ParallelTimeline> und <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein Typ von Containerzeitachse, der Zielinformationen für die Zeitachsen zur Verfügung stellt, die sie enthält.  Ein Storyboard kann jeden Typ von <xref:System.Windows.Media.Animation.Timeline> enthalten, auch andere Containerzeitachsen und \-animationen.  Mit <xref:System.Windows.Media.Animation.Storyboard>\-Objekten können Sie Zeitachsen kombinieren, die eine Vielzahl von Objekten und Eigenschaften in einer einzelnen Zeitachsenstruktur beeinflussen können, wodurch komplexes Zeitverhalten einfach organisiert und gesteuert werden kann.  Angenommen, eine Schaltfläche soll Folgendes ausführen.  
  
-   Größer werden und die Farbe ändern, wenn der Benutzer die Schaltfläche auswählt.  
  
-   Kleiner werden und dann wieder auf die ursprüngliche Größe wachsen, wenn auf die Schaltfläche geklickt wird.  
  
-   Kleiner und zu 50 Prozent durchlässig werden, wenn die Schaltfläche deaktiviert dargestellt wird.  
  
 In diesem Fall stehen mehrere Sätze von Animationen zur Verfügung, die auf dasselbe Objekt angewendet werden und die Sie je nach Zustand der Schaltfläche zu unterschiedlichen Zeiten wiedergeben möchten.  Mit <xref:System.Windows.Media.Animation.Storyboard>\-Objekten können Sie Animationen organisieren und sie in Gruppen auf ein oder mehrere Objekte anwenden.  
  
<a name="wherecanyouuseastoryboard"></a>   
## Wo können Sie ein Storyboard verwenden?  
 Mit einem <xref:System.Windows.Media.Animation.Storyboard> können Sie [Abhängigkeitseigenschaften](GTMT) von animierbaren Klassen animieren \(weitere Informationen darüber, wodurch eine Klasse animierbar wird, finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)\).  Da der Einsatz von Storyboards ein Feature auf Frameworkebene ist, muss das Objekt allerdings zum <xref:System.Windows.NameScope> eines <xref:System.Windows.FrameworkElement> oder eines <xref:System.Windows.FrameworkContentElement> gehören.  
  
 Mit einem <xref:System.Windows.Media.Animation.Storyboard> können Sie zum Beispiel:  
  
-   Einen <xref:System.Windows.Media.SolidColorBrush> \(kein Frameworkelement\) animieren, der den Hintergrund einer Schaltfläche \(ein Typ von <xref:System.Windows.FrameworkElement>\) zeichnet.  
  
-   Einen <xref:System.Windows.Media.SolidColorBrush> \(kein Frameworkelement\) animieren, der die Füllung einer <xref:System.Windows.Media.GeometryDrawing> \(kein Frameworkelement\) zeichnet, die mit einem <xref:System.Windows.Controls.Image> \(<xref:System.Windows.FrameworkElement>\) angezeigt wird.  
  
-   Einen <xref:System.Windows.Media.SolidColorBrush> in Code animieren, der von einer Klasse deklariert wird, die auch ein <xref:System.Windows.FrameworkElement> enthält, wenn der <xref:System.Windows.Media.SolidColorBrush> seinen Namen bei diesem <xref:System.Windows.FrameworkElement> registriert hat.  
  
 Sie können aber mit einem <xref:System.Windows.Media.Animation.Storyboard> keinen <xref:System.Windows.Media.SolidColorBrush> animieren, der seinen Namen nicht bei einem <xref:System.Windows.FrameworkElement> oder einem <xref:System.Windows.FrameworkContentElement> registriert hat oder der nicht verwendet wurde, um eine Eigenschaft von einem <xref:System.Windows.FrameworkElement> oder einem <xref:System.Windows.FrameworkContentElement> festzulegen.  
  
<a name="applyanimationswithastoryboard"></a>   
## Anwenden von Animationen mit einem Storyboard  
 Um mit einem <xref:System.Windows.Media.Animation.Storyboard> Animationen zu organisieren und anzuwenden, fügen Sie die Animationen als untergeordnete Zeitachsen von <xref:System.Windows.Media.Animation.Storyboard> hinzu.  Die <xref:System.Windows.Media.Animation.Storyboard>\-Klasse stellt die angefügten Eigenschaften <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName> zur Verfügung.  Diese Eigenschaften werden für eine Animation festgelegt, um deren Zielobjekt und Eigenschaft anzugeben.  
  
 Um Animationen auf ihre Ziele anzuwenden, starten Sie das <xref:System.Windows.Media.Animation.Storyboard> mit einer Triggeraktion oder einer Methode.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden Sie ein <xref:System.Windows.Media.Animation.BeginStoryboard>\-Objekt mit einem <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger> oder <xref:System.Windows.DataTrigger>.  In Code können Sie auch die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode verwenden.  
  
 Die folgende Tabelle zeigt die unterschiedlichen Stellen, an denen die einzelnen Verfahren zum Starten von <xref:System.Windows.Media.Animation.Storyboard> unterstützt werden: Pro Instanz, Stil, Steuerelementvorlage und Datenvorlage. "  Pro Instanz" bezieht sich auf das Verfahren, wonach eine Animation oder ein Storyboard auf die Objektinstanzen direkt angewendet wird, und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage.  
  
|Storyboard wird gestartet mit…|Pro Instanz|Format|Steuerelementvorlage|Datenvorlage|Beispiel|  
|------------------------------------|-----------------|------------|--------------------------|------------------|--------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und einem <xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und einem Eigenschaften\-<xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und einem <xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/de-de/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Im folgenden Beispiel werden mit einem <xref:System.Windows.Media.Animation.Storyboard> die <xref:System.Windows.FrameworkElement.Width%2A> eines <xref:System.Windows.Shapes.Rectangle>\-Elements und die <xref:System.Windows.Media.SolidColorBrush.Color%2A> eines <xref:System.Windows.Media.SolidColorBrush>\-Elements, mit dem das <xref:System.Windows.Shapes.Rectangle> gezeichnet wurde, animiert.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 In den folgenden Abschnitten werden die angefügten Eigenschaften <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> ausführlicher beschrieben.  
  
<a name="targetingelementsandfreezables"></a>   
## Verwenden von Frameworkelementen, Frameworkinhaltselementen und Freezable\-Objekten  
 Im vorhergehenden Abschnitt wurde erwähnt, dass einer Animation, der Zielname und die zu animierende Eigenschaft bekannt sein müssen, damit sie ihr Ziel findet.  Das Angeben der zu animierenden Eigenschaft ist leicht: Legen Sie für <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName> einfach den Namen der zu animierenden Eigenschaft fest.  Sie geben den Namen des Objekts, dessen Eigenschaft animiert werden soll, an, indem Sie die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName>\-Eigenschaft für die Animation festlegen.  
  
 Damit die <xref:System.Windows.Setter.TargetName%2A>\-Eigenschaft eingesetzt werden kann, muss das Zielobjekt einen Namen besitzen.  Einem <xref:System.Windows.FrameworkElement> oder einem <xref:System.Windows.FrameworkContentElement> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einen Namen zuzuweisen, unterscheidet sich davon, einem <xref:System.Windows.Freezable>\-Objekt einen Namen zuzuweisen.  
  
 Frameworkelemente sind die Klassen, die von der <xref:System.Windows.FrameworkElement>\-Klasse erben.  Zu den Frameworkelementen zählen <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button> und <xref:System.Windows.Shapes.Rectangle>.  Im Prinzip sind alle Fenster, Bereiche und Steuerelemente Elemente.  Frameworkinhaltselemente sind die Klassen, die von der <xref:System.Windows.FrameworkContentElement>\-Klasse erben.  Zu den Frameworkinhaltselementen zählen <xref:System.Windows.Documents.FlowDocument> und <xref:System.Windows.Documents.Paragraph>.  Wenn Sie nicht sicher sind, ob es sich bei einem Typ um ein Frameworkelement oder ein Frameworkinhaltselelement handelt, überprüfen Sie, ob es eine Name\-Eigenschaft besitzt.  Trifft dies zu, handelt es sich wahrscheinlich um ein Frameworkelement oder ein Frameworkinhaltselement.  Um sicherzugehen, überprüfen Sie den Abschnitt Vererbungshierarchie  der Typseite.  
  
 Um die Verwendung eines Frameworkelements oder eines Frameworkinhaltselements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zu aktivieren, legen Sie dessen <xref:System.Windows.FrameworkElement.Name%2A>\-Eigenschaft fest.  Im Code müssen Sie außerdem mit der <xref:System.Windows.NameScope.RegisterName%2A>\-Methode den Elementnamen für das Element registrieren, für das Sie einen <xref:System.Windows.NameScope> erstellt haben.  
  
 Im folgenden Beispiel, das aus dem vorherigen Beispiel stammt, wird einem <xref:System.Windows.Shapes.Rectangle>, einem Typ von <xref:System.Windows.FrameworkElement>, der Name `MyRectangle` zugewiesen.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 Wenn es einen Namen besitzt, können Sie eine Eigenschaft dieses Elements animieren.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable>\-Typen sind die Klassen, die von der <xref:System.Windows.Freezable>\-Klasse erben.  Zu <xref:System.Windows.Freezable> zählen <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform> und <xref:System.Windows.Media.GradientStop>.  
  
 Damit ein <xref:System.Windows.Freezable>\-Objekt für eine Animation in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet werden kann, weisen Sie ihm mit dem [x:Name\-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md) einen Namen zu.  Im Code registrieren Sie mit der <xref:System.Windows.NameScope.RegisterName%2A>\-Methode den Namen für das Element, für das Sie einen <xref:System.Windows.NameScope> erstellt haben.  
  
 Im folgenden Beispiel wird einem <xref:System.Windows.Freezable>\-Objekt ein Name zugewiesen.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 Das Objekt kann dann für eine Animation verwendet werden.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard>\-Objekte lösen die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>\-Eigenschaft mithilfe von Namensbereichen auf.  Weitere Informationen über WPF\-Namensbereiche finden Sie unter [WPF\-XAML\-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  Wenn die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>\-Eigenschaft weggelassen wird, verwendet die Animation das Element, für das sie definiert ist. Im Fall von Stilen ist dies das formatierte Element.  
  
 Manchmal kann einem <xref:System.Windows.Freezable>\-Objekt ein Name nicht zugewiesen werden.  Wenn z. B. ein <xref:System.Windows.Freezable>\-Objekt als Ressource deklariert ist oder verwendet wird, um einen Eigenschaftswert in einem Stil festzulegen, kann ihm kein Name zugewiesen werden.  Ohne Namen kann es nicht direkt verwendet werden, wohl aber indirekt.  In den folgenden Abschnitten wird beschrieben, wie die indirekte Verwendung eingesetzt wird.  
  
<a name="pathsyntaxforchangeable"></a>   
## Indirekte Verwendung  
 Manchmal kann ein <xref:System.Windows.Freezable>\-Objekt nicht direkt für eine Animation verwendet werden, z. B. wenn das <xref:System.Windows.Freezable>\-Objekt als Ressource deklariert ist oder verwendet wird, um einen Eigenschaftswert in einem Stil festzulegen.  In diesen Fällen kann das <xref:System.Windows.Freezable>\-Objekt dennoch animiert werden, obwohl es sich nicht direkt verwenden lässt.  Anstatt für die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>\-Eigenschaft den Namen des <xref:System.Windows.Freezable>\-Objekts festzulegen, erhält sie den Namen des Elements, zu dem das <xref:System.Windows.Freezable>\-Objekt "gehört". Zum Beispiel gehört ein <xref:System.Windows.Media.SolidColorBrush>, mit dem die <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteckelements festgelegt wird, zu diesem Rechteck.  Um den Pinsel zu animieren, legen Sie die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> der Animation mit einer Kette von Eigenschaften fest, die bei der Eigenschaft des Frameworkelements bzw. Frameworkinhaltselements beginnt, die mit dem <xref:System.Windows.Freezable>\-Objekt festgelegt wurde, und mit der zu animierenden <xref:System.Windows.Freezable>\-Eigenschaft endet.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Beachten Sie, dass ein Klon erstellt und dieser Klon animiert wird, wenn das <xref:System.Windows.Freezable>\-Objekt fixiert ist.  Wenn dieser Fall eintritt, gibt die <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A>\-Eigenschaft des ursprünglichen Objekts weiterhin `false` zurück, da das ursprüngliche Objekt eigentlich nicht animiert wird.  Weitere Informationen über das Klonen finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Beachten Sie beim Einsatz der indirekten Verwendung von Eigenschaften auch, dass es möglich ist, Objekte zu verwenden, die nicht vorhanden sind.  Angenommen, der <xref:System.Windows.Controls.Control.Background%2A> einer bestimmten Schaltfläche wurde mit einem <xref:System.Windows.Media.SolidColorBrush> festgelegt, und Sie versuchen, dessen Farbe zu animieren, wenn der Hintergrund der Schaltfläche tatsächlich aber mit einem <xref:System.Windows.Media.LinearGradientBrush> festgelegt wurde.  In diesen Fällen wird keine Ausnahme ausgelöst. Die Animation hat keinen sichtbaren Effekt, da <xref:System.Windows.Media.LinearGradientBrush> nicht auf Änderungen an der <xref:System.Windows.Media.SolidColorBrush.Color%2A>\-Eigenschaft reagiert.  
  
 In den folgenden Abschnitten wird die Syntax für die indirekte Verwendung von Eigenschaften ausführlicher erklärt.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### Indirekte Verwendung einer Eigenschaft eines Freezable\-Objekts in XAML  
 Um eine Eigenschaft eines Freezable\-Objekts in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zu verwenden, verwenden Sie die folgende Syntax.  
  
||  
|-|  
|*ElementPropertyName*`.`*FreezablePropertyName*|  
  
 Speicherort  
  
-   *ElementPropertyName* ist die Eigenschaft von <xref:System.Windows.FrameworkElement>, die mit dem <xref:System.Windows.Freezable>\-Objekt festgelegt wird, und  
  
-   *FreezablePropertyName* ist die zu animierende Eigenschaft des <xref:System.Windows.Freezable>\-Objekts.  
  
 Der folgende Code zeigt, wie die <xref:System.Windows.Media.SolidColorBrush.Color%2A> für einen <xref:System.Windows.Media.SolidColorBrush> animiert wird, mit dem die  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rectangle\-Elements festgelegt wird.  
  
  
  
 Manchmal müssen Sie ein Freezable\-Objekt verwenden, das in einer Auflistung oder einem Array enthalten ist.  
  
 Um ein in einer Auflistung enthaltenes Freezable\-Objekt zu verwenden, verwenden Sie die folgende Pfadsyntax.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Wobei *CollectionIndex* der Index des Objekts im Array oder in der Auflistung ist.  
  
 Angenommen, bei einem Rechteck wird eine <xref:System.Windows.Media.TransformGroup>\-Ressource auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft angewendet, und Sie möchten eine der Transformationen animieren, die sie enthält.  
  
  
  
 Im folgenden Code wird veranschaulicht, wie die <xref:System.Windows.Media.RotateTransform.Angle%2A>\-Eigenschaft der <xref:System.Windows.Media.RotateTransform> aus dem vorhergehenden Beispiel animiert wird.  
  
  
  
<a name="targetingpropertyofchangeableincode"></a>   
### Indirekte Verwendung einer Eigenschaft eines Freezable\-Objekts in Code  
 In Code erstellen Sie ein <xref:System.Windows.PropertyPath>\-Objekt.  Wenn Sie den <xref:System.Windows.PropertyPath> erstellen, geben Sie einen <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A> an.  
  
 Um <xref:System.Windows.PropertyPath.PathParameters%2A> zu erstellen, erstellen Sie ein Array vom Typ <xref:System.Windows.DependencyProperty>, das eine Liste mit Bezeichnerfeldern der Abhängigkeitseigenschaft enthält.  Das erste Bezeichnerfeld ist für die Eigenschaft von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, die mit dem <xref:System.Windows.Freezable>\-Objekt festgelegt wird.  Das nächste Bezeichnerfeld stellt die Eigenschaft des zu verwendenden <xref:System.Windows.Freezable>Elements dar.  Sie können sich dies als eine Kette von Eigenschaften vorstellen, die das <xref:System.Windows.Freezable>\-Objekt mit dem <xref:System.Windows.FrameworkElement>\-Objekt verbindet.  
  
 Im folgenden Beispiel wird eine Kette von Abhängigkeitseigenschaften gezeigt, die die <xref:System.Windows.Media.SolidColorBrush.Color%2A> für einen <xref:System.Windows.Media.SolidColorBrush> verwenden, mit dem die <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rectangle\-Elements festgelegt wird.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 Sie müssen auch einen <xref:System.Windows.PropertyPath.Path%2A> angeben.  Ein <xref:System.Windows.PropertyPath.Path%2A> ist eine <xref:System.String>, mit der dem <xref:System.Windows.PropertyPath.Path%2A> mitgeteilt wird, wie die <xref:System.Windows.PropertyPath.PathParameters%2A> interpretiert werden.  Folgende Syntax wird verwendet.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(`*FreezablePropertyArrayIndex*`)`|  
  
 Speicherort  
  
-   *OwnerPropertyArrayIndex* ist der Index des <xref:System.Windows.DependencyProperty>\-Arrays, das den Bezeichner der Eigenschaft des <xref:System.Windows.FrameworkElement>\-Objekts enthält, die mit dem <xref:System.Windows.Freezable>\-Objekt festgelegt wird, und  
  
-   *FreezablePropertyArrayIndex* ist der Index des <xref:System.Windows.DependencyProperty>\-Arrays, das den Bezeichner der zu verwendenden Eigenschaft enthält.  
  
 Im folgenden Beispiel wird der <xref:System.Windows.PropertyPath.Path%2A> für die im vorhergehenden Beispiel definierten <xref:System.Windows.PropertyPath.PathParameters%2A> dargestellt.  
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 Im folgenden Beispiel wird eine Kombinationen von Code aus den vorhergehenden Beispielen verwenden, um die <xref:System.Windows.Media.SolidColorBrush.Color%2A> für einen <xref:System.Windows.Media.SolidColorBrush> zu animieren, mit dem die <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rectangle\-Elements festgelegt wurde.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 Manchmal müssen Sie ein Freezable\-Objekt verwenden, das in einer Auflistung oder einem Array enthalten ist.  Angenommen, bei einem Rechteck wird eine <xref:System.Windows.Media.TransformGroup>\-Ressource auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft angewendet, und Sie möchten eine der Transformationen animieren, die sie enthält.  
  
 [!code-xml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Um ein in einer Auflistung enthaltenes <xref:System.Windows.Freezable>\-Objekt zu verwenden, verwenden Sie die folgende Pfadsyntax.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(` *CollectionChildrenPropertyArrayIndex*`)` `[`*CollectionIndex* `].(`*FreezablePropertyArrayIndex*`)`|  
  
 Wobei *CollectionIndex* der Index des Objekts im Array oder in der Auflistung ist.  
  
 Um die <xref:System.Windows.Media.RotateTransform.Angle%2A>\-Eigenschaft der <xref:System.Windows.Media.RotateTransform>, der zweiten Transformation in der <xref:System.Windows.Media.TransformGroup>, zu verwenden, werden der folgende <xref:System.Windows.PropertyPath.Path%2A> und die folgenden <xref:System.Windows.PropertyPath.PathParameters%2A> verwendet.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 Das folgende Beispiel enthält den vollständigen Code, um den <xref:System.Windows.Media.RotateTransform.Angle%2A> einer <xref:System.Windows.Media.RotateTransform> zu animieren, die in einer <xref:System.Windows.Media.TransformGroup> enthalten ist.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### Indirekte Verwendung mit einem Freezable\-Objekt als Ausgangspunkt  
 In den vorhergehenden Abschnitten wurde beschreiben, wie ein <xref:System.Windows.Freezable>\-Objekt indirekt verwendet wird, indem mit einem <xref:System.Windows.FrameworkElement> oder einem <xref:System.Windows.FrameworkContentElement> begonnen und eine Eigenschaftenkette zu einer <xref:System.Windows.Freezable>\-Untereigenschaft erstellt wird.  Sie können als Ausgangspunkt auch ein <xref:System.Windows.Freezable>\-Objekt verwenden und indirekt eine der <xref:System.Windows.Freezable>\-Untereigenschaften verwenden.  Es gilt eine zusätzliche Einschränkung, wenn ein <xref:System.Windows.Freezable>\-Objekt als Ausgangspunkt für die indirekte Verwendung verwendet wird: das erste <xref:System.Windows.Freezable>\-Objekt und jedes <xref:System.Windows.Freezable>\-Objekt, das sich zwischen diesem und der indirekt verwendeten Untereigenschaft befindet, darf nicht fixiert sein.  
  
<a name="controllable_storyboards"></a>   
## Interaktives Steuern eines Storyboards in XAML  
 Verwenden Sie zum Starten eines Storyboards in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] eine <xref:System.Windows.Media.Animation.BeginStoryboard>\-Triggeraktion.  <xref:System.Windows.Media.Animation.BeginStoryboard> verteilt die Animationen an die zu animierenden Objekte und Eigenschaften und startet anschließend das Storyboard.  \(Ausführliche Informationen über diesen Vorgang finden Sie unter [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).\) Wenn Sie <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen geben, indem Sie die entsprechende <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>\-Eigenschaft festlegen, wird dieses Storyboard steuerbar.  Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde.  In der folgenden Liste werden steuerbare Storyboard\-Aktionen aufgeführt, die zusammen mit Ereignistriggern zur Steuerung eines Storyboards verwendet werden.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltenes Storyboard fort.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Storyboard\-Geschwindigkeit.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Setzt ein Storyboard an das Ende seines Füllzeitraums, sofern vorhanden.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Beendet das Storyboard.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard.  
  
 Im folgenden Beispiel werden steuerbare Storyboard\-Aktionen zur interaktiven Steuerung eines Storyboards verwendet.  
  
 [!code-xml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## Interaktive Steuerung eines Storyboards mithilfe von Code  
 In den vorhergehenden Beispielen wurde gezeigt, wie mithilfe von Triggeraktionen Animationen ausgeführt werden.  In Code können Sie ebenfalls ein Storyboard mithilfe interaktiver Methoden der <xref:System.Windows.Media.Animation.Storyboard>\-Klasse steuern.  Um ein <xref:System.Windows.Media.Animation.Storyboard> in Code als interaktiv festzulegen, müssen Sie die entsprechende Überladung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode des Storyboards verwenden und `true` angeben, damit es sich steuern lässt.  Weitere Informationen finden Sie auf der Seite <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>.  
  
 In der folgenden Liste sind die Methoden aufgeführt, mit denen ein <xref:System.Windows.Media.Animation.Storyboard> nach seinem Start bearbeitet werden kann:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 Der Vorteil dieser Methoden liegt darin, dass Sie weder ein <xref:System.Windows.Trigger>\-Objekt noch ein <xref:System.Windows.TriggerAction>\-Objekt erstellen müssen. Sie benötigen lediglich einen Verweis auf das steuerbare <xref:System.Windows.Media.Animation.Storyboard>, das Sie bearbeiten möchten.  
  
 **Hinweis:** Alle interaktiven Aktionen, die für eine <xref:System.Windows.Media.Animation.Clock> und somit auch für ein <xref:System.Windows.Media.Animation.Storyboard> ausgeführt werden, erfolgen beim nächsten Teilstrich des Zeitgebermoduls, d. h. kurz vor dem nächsten Rendern.  Wenn Sie z. B. mit der <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>\-Methode an eine andere Stelle in einer Animation springen, ändert sich der Eigenschaftswert nicht unmittelbar. Der Wert ändert sich erst beim nächsten Teilstrich des Zeitgebermoduls.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie mithilfe der interaktiven Methoden der <xref:System.Windows.Media.Animation.Storyboard>\-Klasse Animationen anwenden und steuern können.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## Animieren in einem Stil  
 Sie können mit <xref:System.Windows.Media.Animation.Storyboard>\-Objekten Animationen in einem <xref:System.Windows.Style> definieren.  Das Ausführen von Animationen mit einem <xref:System.Windows.Media.Animation.Storyboard> in einem <xref:System.Windows.Style> ähnelt der Verwendung eines <xref:System.Windows.Media.Animation.Storyboard>\-Elements an anderer Stelle, mit den folgenden drei Ausnahmen:  
  
-   Sie geben keinen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> an. Das <xref:System.Windows.Media.Animation.Storyboard> verwendet immer das Element, auf das der <xref:System.Windows.Style> angewendet wird.  Um <xref:System.Windows.Freezable>\-Objekte zu verwenden, müssen Sie die indirekte Verwendung benutzen.  Weitere Informationen über die indirekte Verwendung finden Sie im Abschnitt [Indirekte Verwendung](#pathsyntaxforchangeable).  
  
-   Sie können keinen <xref:System.Windows.EventTrigger.SourceName%2A> für einen <xref:System.Windows.EventTrigger> oder einen <xref:System.Windows.Trigger> angeben.  
  
-   Sie können keine dynamischen Ressourcenverweise oder Datenbindungsausdrücke verwenden, um <xref:System.Windows.Media.Animation.Storyboard> oder Eigenschaftswerte für Animationen festzulegen.  Der Grund liegt darin, dass alles in einem <xref:System.Windows.Style> threadsicher sein muss, und das Zeitsteuerungssystem muss <xref:System.Windows.Media.Animation.Storyboard>\-Objekte mit <xref:System.Windows.Freezable.Freeze%2A> fixieren, um sie threadsicher zu machen.  Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht fixiert werden, wenn es selbst oder seine untergeordneten Zeitachsen dynamische Ressourcenverweise oder Datenbindungsausdrücke enthalten.  Weitere Informationen über das Fixieren und andere <xref:System.Windows.Freezable>\-Features finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie keine Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard> oder Animationsereignisse deklarieren.  
  
 Ein Beispiel, in dem gezeigt wird, wie ein Storyboard in einem Stil definiert wird, finden Sie unter [Animieren in einem Stil](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md).  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## Animieren in einer ControlTemplate  
 Sie können mit <xref:System.Windows.Media.Animation.Storyboard>\-Objekten Animationen in einem <xref:System.Windows.Controls.ControlTemplate> definieren.  Das Ausführen von Animationen mit einem <xref:System.Windows.Media.Animation.Storyboard> in einem <xref:System.Windows.Controls.ControlTemplate> ähnelt der Verwendung eines <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle, mit den folgenden zwei Ausnahmen:  
  
-   Der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> darf nur auf untergeordnete Objekte der <xref:System.Windows.Controls.ControlTemplate> verweisen.  Wenn <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> nicht angegeben wird, verwendet die Animation das Element, auf das die <xref:System.Windows.Controls.ControlTemplate> angewendet wird.  
  
-   Der <xref:System.Windows.EventTrigger.SourceName%2A> für einen <xref:System.Windows.EventTrigger> oder einen <xref:System.Windows.Trigger> darf nur auf untergeordnete Objekte der <xref:System.Windows.Controls.ControlTemplate> verweisen.  
  
-   Sie können keine dynamischen Ressourcenverweise oder Datenbindungsausdrücke verwenden, um <xref:System.Windows.Media.Animation.Storyboard> oder Eigenschaftswerte für Animationen festzulegen.  Der Grund liegt darin, dass alles in einem <xref:System.Windows.Controls.ControlTemplate> threadsicher sein muss, und das Zeitsteuerungssystem muss <xref:System.Windows.Media.Animation.Storyboard>\-Objekte mit <xref:System.Windows.Freezable.Freeze%2A> fixieren, um sie threadsicher zu machen.  Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht fixiert werden, wenn es selbst oder seine untergeordneten Zeitachsen dynamische Ressourcenverweise oder Datenbindungsausdrücke enthalten.  Weitere Informationen über das Fixieren und andere <xref:System.Windows.Freezable>\-Features finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie keine Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard> oder Animationsereignisse deklarieren.  
  
 Ein Beispiel, in dem gezeigt wird, wie ein Storyboard in einer <xref:System.Windows.Controls.ControlTemplate> definiert wird, finden Sie unter [Animieren in einer ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## Animieren bei Änderung eines Eigenschaftswerts  
 In Stilen und Steuerelementvorlagen können Sie mit Triggerobjekten ein Storyboard starten, wenn sich eine Eigenschaft ändert.  Beispiele zu diesem Thema finden Sie unter [Auslösen einer Animation, wenn sich eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) und [Animieren in einer ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Von <xref:System.Windows.Trigger>\-Eigenschaftenobjekten angewendete Animationen verhalten sich komplexer als <xref:System.Windows.EventTrigger>\-Animationen oder Animationen, die mithilfe von <xref:System.Windows.Media.Animation.Storyboard>\-Methoden gestartet wurden.  Sie werden mit Animationen "übergeben", die von anderen <xref:System.Windows.Trigger>\-Objekten definiert wurden, setzen sich aber aus <xref:System.Windows.EventTrigger> und durch Methoden ausgelösten Animationen zusammen.  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)