---
title: Übersicht über Storyboards
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
ms.openlocfilehash: 36922dce795443a4c1136f6442eff1c297f3c641
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566898"
---
# <a name="storyboards-overview"></a>Übersicht über Storyboards
In diesem Thema zeigt, wie <xref:System.Windows.Media.Animation.Storyboard> Objekte zu organisieren und Animationen anzuwenden. Es wird beschrieben, wie interaktiv bearbeiten <xref:System.Windows.Media.Animation.Storyboard> Objekte und die indirekte Verwendung der Syntax von Eigenschaften beschrieben.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Als Voraussetzung für dieses Thema sollten Sie mit den unterschiedlichen Animationstypen und ihren grundlegenden Funktionen vertraut sein. Eine Einführung zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Sie sollten auch wissen, wie angefügte Eigenschaften verwendet werden. Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>Was ist ein Storyboard?  
 Animationen sind nicht der einzige nützliche Zeitachsentyp. Andere Zeitachsenklassen werden bereitgestellt,um Ihnen beim Organisieren von Sätzen von Zeitachsen zu helfen und Zeitachsen auf Eigenschaften anzuwenden. Containerzeitachsen Ableiten der <xref:System.Windows.Media.Animation.TimelineGroup> -Klasse und beinhalten <xref:System.Windows.Media.Animation.ParallelTimeline> und <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein Containerzeitachse, die Zielinformationen für die Zeitachsen bereitstellt, er enthält. Ein Storyboard kann jeden Datentyp enthalten <xref:System.Windows.Media.Animation.Timeline>, einschließlich andere Containerzeitachsen und Animationen. <xref:System.Windows.Media.Animation.Storyboard> Objekte können Sie Zeitachsen kombinieren, die eine Vielzahl von Objekten und Eigenschaften in einer einzelnen Zeitskala Struktur vereinfacht das Verwalten und Steuern von komplexen Zeitsteuerungsverhalten beeinflussen. Nehmen wir beispielsweise an, Sie wünschen eine Schaltfläche, die die folgenden drei Aktionen ausführt.  
  
-   Vergrößern und Ändern der Farbe, wenn der Benutzer die Schaltfläche auswählt.  
  
-   Verkleinern und dann wieder die ursprüngliche Größe annehmen, wenn auf sie geklickt wird.  
  
-   Verkleinern und zu 50 % Deckkraft ausgeblendet werden, wenn sie deaktiviert wird.  
  
 In diesem Fall sind mehrere Sätze von Animationen vorhanden, die auf das gleiche Objekt angewendet werden und die Sie abhängig vom Zustand der Schaltfläche zu unterschiedlichen Zeitpunkten wiedergeben möchten. <xref:System.Windows.Media.Animation.Storyboard> Objekte können Sie Animationen organisieren und sie in Gruppen auf ein oder mehrere Objekte anwenden.  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>Wo können Sie ein Storyboard verwenden?  
 Ein <xref:System.Windows.Media.Animation.Storyboard> zum Animieren von Abhängigkeitseigenschaften animierbaren Klassen verwendet werden kann (Weitere Informationen dazu, was eine Klasse animierbar wird, finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)). Da storyboarding eine Frameworkebene Funktion ist, das Objekt muss allerdings gehören zu den <xref:System.Windows.NameScope> von einer <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.FrameworkContentElement>.  
  
 Beispielsweise können Sie eine <xref:System.Windows.Media.Animation.Storyboard> die folgenden Schritte ausführen:  
  
-   Animieren einer <xref:System.Windows.Media.SolidColorBrush> (nicht-Framework-Element), zeichnet den Hintergrund einer Schaltfläche (ein <xref:System.Windows.FrameworkElement>),  
  
-   Animieren eine <xref:System.Windows.Media.SolidColorBrush> (nicht-Framework-Element), zeichnet die Füllung für eine <xref:System.Windows.Media.GeometryDrawing> (nicht-Framework-Element) angezeigt, mit einer <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).  
  
-   In Code Animieren einer <xref:System.Windows.Media.SolidColorBrush> deklarierten durch eine Klasse, die ebenfalls enthält eine <xref:System.Windows.FrameworkElement>, wenn die <xref:System.Windows.Media.SolidColorBrush> seinen Namen, die registriert <xref:System.Windows.FrameworkElement>.  
  
 Jedoch können Sie nicht verwenden eine <xref:System.Windows.Media.Animation.Storyboard> zu animierende eine <xref:System.Windows.Media.SolidColorBrush> , die nicht seinen Namen mit registriert hat eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, oder nicht verwendet, um eine Eigenschaft festgelegt eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>Anwenden von Animationen mit einem Storyboard  
 Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> zum Organisieren und Animationen anzuwenden, fügen Sie die Animationen als untergeordnete Zeitachsen von der <xref:System.Windows.Media.Animation.Storyboard>. Die <xref:System.Windows.Media.Animation.Storyboard> -Klasse stellt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> angefügte Eigenschaften. Sie können diese Eigenschaften für eine Animation einstellen, um deren Zielobjekt und Eigenschaft festzulegen.  
  
 Um Animationen auf ihre Ziele anzuwenden, starten Sie den <xref:System.Windows.Media.Animation.Storyboard> über eine Triggeraktion oder eine Methode. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie verwenden eine <xref:System.Windows.Media.Animation.BeginStoryboard> -Objekt mit einem <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>, oder <xref:System.Windows.DataTrigger>. Im Code können Sie auch die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode.  
  
 Die folgende Tabelle zeigt die verschiedenen Positionen, in dem jede <xref:System.Windows.Media.Animation.Storyboard> beginnen Technik wird unterstützt: pro Instanz, Stil, Steuerelementvorlage und Datenvorlage. „Pro Instanz“ bezieht sich auf das Verfahren, eine Animation oder ein Storyboard direkt auf Instanzen eines Objekts und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage anzuwenden.  
  
|Storyboard wird gestartet mit...|Pro Instanz|Stil|Steuerelementvorlage|Datenvorlage|Beispiel|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und ein <xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und einer Eigenschaft <xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und ein <xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[Vorgehensweise: Auslösen einer Animation bei Änderung eines Eigenschaftswerts](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.Storyboard> zu animierende der <xref:System.Windows.FrameworkElement.Width%2A> des eine <xref:System.Windows.Shapes.Rectangle> Element und die <xref:System.Windows.Media.SolidColorBrush.Color%2A> des eine <xref:System.Windows.Media.SolidColorBrush> verwendet, die gezeichnet <xref:System.Windows.Shapes.Rectangle>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 Die folgenden Abschnitte beschreiben die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaften im Detail.  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Frameworkelemente, Frameworkinhaltselemente und Freezable-Objekte  
 Im vorherigen Abschnitt wurde erwähnt, dass eine Animation den Namen des Ziels und die zu animierende Eigenschaft kennen muss, um ihr Ziel zu finden. Unkompliziert ist die zu animierende Eigenschaft angeben: Legen Sie einfach <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> durch den Namen der zu animierenden Eigenschaft.  Geben Sie den Namen des Objekts, dessen Eigenschaft animieren, indem Sie festlegen möchten die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> Eigenschaft für die Animation.  
  
 Für die <xref:System.Windows.Setter.TargetName%2A> -Eigenschaft funktioniert, das Zielobjekt muss einen Namen aufweisen. Ein Name zugewiesen eine <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.FrameworkContentElement> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterscheidet sich ein Name zugewiesen ein <xref:System.Windows.Freezable> Objekt.  
  
 Frameworkelemente sind die Klassen, die von erben die <xref:System.Windows.FrameworkElement> Klasse. Beispiele für Frameworkelemente <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>, und <xref:System.Windows.Shapes.Rectangle>. Im Wesentlichen sind alle Fenster, Panels und Steuerelemente Elemente. Framework-Inhaltselemente sind die Klassen, die von erben die <xref:System.Windows.FrameworkContentElement> Klasse. Beispiele für Frameworkinhaltselemente <xref:System.Windows.Documents.FlowDocument> und <xref:System.Windows.Documents.Paragraph>. Wenn Sie nicht sicher sind, ob ein Typ ein Frameworkelement oder ein Frameworkinhaltselement ist, überprüfen Sie, ob es über eine Name-Eigenschaft verfügt. Wenn dies der Fall ist, handelt es sich aller Wahrscheinlichkeit nach um ein Frameworkelement oder ein Frameworkinhaltselement. Um sicherzugehen, überprüfen Sie den Vererbungshierarchie-Abschnitt seiner Typ-Seite.  
  
 So aktivieren Sie die Zielgruppenadressierung von Framework-Element oder ein Framework Inhaltselement im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], legen Sie dessen <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft. Im Code müssen Sie auch mithilfe der <xref:System.Windows.NameScope.RegisterName%2A> Methode, um den Namen des Elements mit dem Element registrieren für die Sie erstellt haben eine <xref:System.Windows.NameScope>.  
  
 Im folgende Beispiel, stammt aus dem vorherigen Beispiel weist den Namen `MyRectangle` eine <xref:System.Windows.Shapes.Rectangle>, einen Typ von <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 Wenn der Name vergeben wurde, können Sie eine Eigenschaft des Elements animieren.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable> Typen sind die Klassen, die von erben die <xref:System.Windows.Freezable> Klasse. Beispiele für <xref:System.Windows.Freezable> enthalten <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>, und <xref:System.Windows.Media.GradientStop>.  
  
 So aktivieren Sie die Zielgruppenadressierung von einer <xref:System.Windows.Freezable> eine Animation in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie die [X: Name-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md) einen Namen zuweisen. Verwenden Sie im Code die <xref:System.Windows.NameScope.RegisterName%2A> Methode, um seinen Namen registrieren für die Sie erstellt haben, mit dem Element ein <xref:System.Windows.NameScope>.  
  
 Im folgenden Beispiel wird der Name einer <xref:System.Windows.Freezable> Objekt.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 Das Objekt kann dann animiert werden.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> Objekte mithilfe von Namensbereichen zum Auflösen der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Eigenschaft. Weitere Informationen über WPF-Namescopes finden Sie unter [WPF-XAML-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md). Wenn die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> -Eigenschaft weggelassen wird, die die Animation ausgerichtet ist, das Element aus, die er definiert ist, oder, im Falle von Formatvorlagen, das formatierte Element.  
  
 In einigen Fällen kann kein Name zugewiesen werden, auf eine <xref:System.Windows.Freezable> Objekt. Z. B. wenn ein <xref:System.Windows.Freezable> deklarierte als eine Ressource oder einen Eigenschaftswert in einem Format festgelegt kann kein Name gegeben. Da es keinen Namen hat, kann es zwar kein direktes, aber ein indirektes Ziel sein. In den folgenden Abschnitten wird beschrieben, wie indirekte Ziele verwendet werden.  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>Indirektes Ziel  
 Es gibt Situationen ein <xref:System.Windows.Freezable> kann nicht direkt durch eine Animation, z. B. wenn angesprochen werden die <xref:System.Windows.Freezable> als Ressource deklariert oder verwendet, um einen Eigenschaftswert in einem Format festgelegt wird. In diesen Fällen, obwohl Sie es direkt Ziel verwenden können Sie können weiterhin Animieren der <xref:System.Windows.Freezable> Objekt. Anstatt durch die Einstellung der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> durch den Namen der Eigenschaft der <xref:System.Windows.Freezable>, erhält sie den Namen des Elements, der die <xref:System.Windows.Freezable> "gehört." Z. B. eine <xref:System.Windows.Media.SolidColorBrush> zum Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechtecks, das Element gehört, um das Rechteck. Um den Pinsel zu animieren, legen Sie der Animation <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> mit einer Kette von Eigenschaften, die an die Eigenschaft der Framework-Element oder Framework Inhaltselement beginnt die <xref:System.Windows.Freezable> wurde verwendet, um festzulegen, und endet mit dem <xref:System.Windows.Freezable> zu animierende Eigenschaft.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Beachten Sie, dass die <xref:System.Windows.Freezable> ist fixiert ist, wird ein Klon vorgenommen werden, und dieser Klon animiert wird. Wenn in diesem Fall des ursprünglichen Objekts <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> Eigenschaft zurückgeben weiterhin `false`, da das ursprüngliche Objekt eigentlich nicht animiert wird. Weitere Informationen zum Klonen finden Sie unter der [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Beachten Sie außerdem, dass nicht vorhandene Objekte Ziel sein können, wenn indirekte Eigenschaftenziele verwendet werden. Angenommen, Sie können davon ausgehen, dass die <xref:System.Windows.Controls.Control.Background%2A> einer bestimmten Schaltfläche wurde festgelegt mit eine <xref:System.Windows.Media.SolidColorBrush> und versuchen Sie es, dessen Farbe, wenn tatsächlich animieren eine <xref:System.Windows.Media.LinearGradientBrush> wurde verwendet, um den Hintergrund der Schaltfläche festzulegen. In diesen Fällen wird keine Ausnahme ausgelöst. eine sichtbare Auswirkung haben, da die Animation nicht <xref:System.Windows.Media.LinearGradientBrush> nicht als Reaktion auf Änderungen an der <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft.  
  
 In den folgenden Abschnitten wird die Syntax für indirekte Eigenschaftenziele ausführlicher erklärt.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Verwenden einer Eigenschaft eines Freezable-Objekts in XAML als indirektes Ziel  
 Um eine Eigenschaft eines freezable in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie die folgende Syntax.  
  
||  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* ist die Eigenschaft von der <xref:System.Windows.FrameworkElement> die der <xref:System.Windows.Freezable> wird verwendet, um festzulegen, und  
  
-   *FreezablePropertyName* ist die Eigenschaft von der <xref:System.Windows.Freezable> animiert.  
  
 Der folgende Code zeigt, wie zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einer <xref:System.Windows.Media.SolidColorBrush> verwendet, um festzulegen der  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> ein Rechteck-Elements.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden.  
  
 Um ein in einer Auflistung enthaltenes Freezable-Objekt als Ziel zu verwenden, geben Sie die folgende Pfadsyntax an.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Wobei *CollectionIndex* ist der Index des Objekts in seine Arrays oder einer Auflistung.  
  
 Nehmen wir beispielsweise an, dass ein Rechteck ist ein <xref:System.Windows.Media.TransformGroup> Ressource angewendet wird, um seine <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, und Sie möchten eine der Transformationen animieren sie enthält.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 Der folgende Code zeigt, wie zum Animieren der <xref:System.Windows.Media.RotateTransform.Angle%2A> Eigenschaft von der <xref:System.Windows.Media.RotateTransform> im vorherigen Beispiel gezeigt.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Verwenden einer Eigenschaft eines Freezable-Objekts im Code als indirektes Ziel  
 In Code, erstellen Sie eine <xref:System.Windows.PropertyPath> Objekt. Beim Erstellen der <xref:System.Windows.PropertyPath>, Sie geben eine <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 Zum Erstellen <xref:System.Windows.PropertyPath.PathParameters%2A>, erstellen Sie ein Array des Typs <xref:System.Windows.DependencyProperty> , enthält eine Liste der Abhängigkeit Bezeichner Eigenschaftenfelder. Das erste Bezeichnerfeld für die Eigenschaft ist die <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> , die die <xref:System.Windows.Freezable> festgelegt. Das nächste Bezeichnerfeld stellt die Eigenschaft der <xref:System.Windows.Freezable> zum Ziel. Betrachten Sie es als eine Kette von Eigenschaften, die verbindet die <xref:System.Windows.Freezable> auf die <xref:System.Windows.FrameworkElement> Objekt.  
  
 Folgender Ausdruck ist ein Beispiel für eine Abhängigkeitskette für die Eigenschaft, die als Ziel verwendet die <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einem <xref:System.Windows.Media.SolidColorBrush> verwendet, um festzulegen der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteckelements.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 Sie müssen auch angeben einer <xref:System.Windows.PropertyPath.Path%2A>. Ein <xref:System.Windows.PropertyPath.Path%2A> ist ein <xref:System.String> , informiert der <xref:System.Windows.PropertyPath.Path%2A> Interpretieren von seiner <xref:System.Windows.PropertyPath.PathParameters%2A>. Die folgende Syntax wird verwendet.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* ist der Index des der <xref:System.Windows.DependencyProperty> Array, das den Bezeichner der enthält die <xref:System.Windows.FrameworkElement> -Eigenschaft des Objekts, das <xref:System.Windows.Freezable> wird verwendet, um festzulegen, und  
  
-   *FreezablePropertyArrayIndex* der Index der <xref:System.Windows.DependencyProperty> Array, das den Bezeichner der Eigenschaft zum Ziel enthält.  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.PropertyPath.Path%2A> , die auftreten würde die <xref:System.Windows.PropertyPath.PathParameters%2A> im vorherigen Beispiel definiert.
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 Das folgende Beispiel kombiniert den Code in den vorherigen Beispielen zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einer <xref:System.Windows.Media.SolidColorBrush> verwendet, um festzulegen der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteckelements.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden. Nehmen wir beispielsweise an, dass ein Rechteck ist ein <xref:System.Windows.Media.TransformGroup> Ressource angewendet wird, um seine <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, und Sie möchten eine der Transformationen animieren sie enthält.  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Ziel eine <xref:System.Windows.Freezable> in einer Auflistung enthalten sind, verwenden Sie die folgende Pfadsyntax.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 Wobei *CollectionIndex* ist der Index des Objekts in seine Arrays oder einer Auflistung.  
  
 Ziel der <xref:System.Windows.Media.RotateTransform.Angle%2A> Eigenschaft von der <xref:System.Windows.Media.RotateTransform>, die zweite Transformation in der <xref:System.Windows.Media.TransformGroup>, nutzen Sie Folgendes <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 Das folgende Beispiel zeigt den vollständigen Code für die Animation die <xref:System.Windows.Media.RotateTransform.Angle%2A> von einem <xref:System.Windows.Media.RotateTransform> enthaltenen eine <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Indirektes Ziel mit einem Freezable-Objekt als Ausgangspunkt  
 In den vorherigen Abschnitten beschrieben, wie indirekt eine <xref:System.Windows.Freezable> mit eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> und erstellen eine Kette zu einer <xref:System.Windows.Freezable> untergeordnete Eigenschaft. Sie können auch eine <xref:System.Windows.Freezable> als Ausgangspunkt und indirekt eines seine <xref:System.Windows.Freezable> untergeordnete Eigenschaften. Eine zusätzliche Einschränkung gilt bei Verwendung einer <xref:System.Windows.Freezable> als Ausgangspunkt für die indirekte Verwendung: das Starten <xref:System.Windows.Freezable> und alle <xref:System.Windows.Freezable> zwischen ihm und indirekt untergeordnete Zieleigenschaft muss nicht fixiert werden.  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Interaktives Steuern eines Storyboards in XAML  
 So starten Sie ein Storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie verwenden eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion auslösen. <xref:System.Windows.Media.Animation.BeginStoryboard> verteilt die Animationen an die Objekte und Eigenschaften, die sie dem animiert werden soll, die und das Storyboard gestartet wird. (Einzelheiten zu diesem Prozess finden Sie unter der [Animationen und zeitlichen Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).) Wenn verfügt die <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen durch Angabe seiner <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> -Eigenschaft, ist er ein Storyboard steuerbares. Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde. Die folgende Liste enthält Aktionen des steuerbaren Storyboards, die Sie mit Ereignistriggern zum Steuern eines Storyboards verwenden.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Nimmt eine angehaltene Storyboards.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Geschwindigkeit des Storyboards.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Setzt ein Storyboard bis zum Ende des Füllzeitraums, falls vorhanden.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Das Storyboard beendet.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard.  
  
 Im folgenden Beispiel werden Aktionen des steuerbaren Storyboards zum interaktiven Steuern eines Storyboards verwendet.  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Interaktives Steuern eines Storyboards mithilfe von Code  
 In den vorherigen Beispielen wurde gezeigt, wie mithilfe von Triggeraktionen animiert wird. Im Code können Sie auch ein Storyboard mit interaktiven Methoden der steuern die <xref:System.Windows.Media.Animation.Storyboard> Klasse. Für eine <xref:System.Windows.Media.Animation.Storyboard> um interaktive im Code vorgenommen werden, müssen Sie die entsprechende Überladung der Drehbuchs verwenden <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, und geben Sie `true` steuerbar machen. Finden Sie unter der <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> um weitere Informationen zu erhalten.  
  
 Die folgende Liste enthält die Methoden, die verwendet werden können, zum Bearbeiten einer <xref:System.Windows.Media.Animation.Storyboard> nachdem dieser gestartet wurde:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 Der Vorteil der Verwendung dieser Methoden ist, müssen Sie nicht erstellen, <xref:System.Windows.Trigger> oder <xref:System.Windows.TriggerAction> Objekte; Sie benötigen nur einen Verweis auf die steuerbar <xref:System.Windows.Media.Animation.Storyboard> bearbeitet werden soll.  
  
 **Hinweis:** interaktive Aktionen auf einer <xref:System.Windows.Media.Animation.Clock>, und daher auch auf eine <xref:System.Windows.Media.Animation.Storyboard> treten auf das nächste Ticken des Datenbankmoduls ein Timeout der kurz vor dem nächsten Rendern ausgeführt wird. Angenommen, Sie verwenden die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode springen zu einer anderen Stelle in einer Animation, den Wert der Eigenschaft wird nicht sofort geändert, ändert sich das nächste Ticken der zeitlichen Steuerung-Engine.  
  
 Das folgende Beispiel zeigt, wie Sie mithilfe der interaktiven Methoden von Animationen anwenden und Steuern der <xref:System.Windows.Media.Animation.Storyboard> Klasse.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>Animieren in einem Stil  
 Sie können <xref:System.Windows.Media.Animation.Storyboard> Objekte, um Animationen in definieren eine <xref:System.Windows.Style>. Animieren mit einer <xref:System.Windows.Media.Animation.Storyboard> in einer <xref:System.Windows.Style> gleicht dem Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle, mit den folgenden drei Ausnahmen:  
  
-   Geben Sie Sie keine <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; das <xref:System.Windows.Media.Animation.Storyboard> immer das Element, der <xref:System.Windows.Style> angewendet wird. Ziel <xref:System.Windows.Freezable> Objekte aufweist, müssen Sie indirekte verwenden. Weitere Informationen über die indirekte Verwendung finden Sie unter der [indirekte](#pathsyntaxforchangeable) Abschnitt.  
  
-   Kann nicht angegeben werden eine <xref:System.Windows.EventTrigger.SourceName%2A> für eine <xref:System.Windows.EventTrigger> oder ein <xref:System.Windows.Trigger>.  
  
-   Sie können keine dynamische Ressourcen Verweise oder Datenbindungsausdrücke festgelegt <xref:System.Windows.Media.Animation.Storyboard> oder Eigenschaftswerten Animation. Liegt darin, dass alle darin enthaltenen Elemente eine <xref:System.Windows.Style> muss threadsicher sein und muss die Zeitsteuerungssystems <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> Objekte, damit sie threadsichere. Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht fixiert werden, wenn er oder seine untergeordneten Zeitachsen dynamische Ressourcen Verweise oder Datenbindungsausdrücke enthalten. Weitere Informationen über das Fixieren und andere <xref:System.Windows.Freezable> Features, finden Sie unter der [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], kann nicht deklariert werden Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard> oder Animationsereignisse.  
  
 Ein Beispiel, das zeigt, wie ein Storyboard in einem Stil zu definieren, finden Sie die [Animieren eines Formats](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) Beispiel.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>Animieren in einer ControlTemplate  
 Sie können <xref:System.Windows.Media.Animation.Storyboard> Objekte, um Animationen in definieren eine <xref:System.Windows.Controls.ControlTemplate>. Animieren mit einer <xref:System.Windows.Media.Animation.Storyboard> in einer <xref:System.Windows.Controls.ControlTemplate> gleicht dem Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle, mit den folgenden zwei Ausnahmen:  
  
-   Die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> dürfen nur auf untergeordnete Objekte verweisen die <xref:System.Windows.Controls.ControlTemplate>. Wenn <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> nicht angegeben ist, wird die Animation ausgerichtet ist, das Element, das <xref:System.Windows.Controls.ControlTemplate> angewendet wird.  
  
-   Die <xref:System.Windows.EventTrigger.SourceName%2A> für eine <xref:System.Windows.EventTrigger> oder ein <xref:System.Windows.Trigger> dürfen nur auf untergeordnete Objekte verweisen die <xref:System.Windows.Controls.ControlTemplate>.  
  
-   Sie können keine dynamische Ressourcen Verweise oder Datenbindungsausdrücke festgelegt <xref:System.Windows.Media.Animation.Storyboard> oder Eigenschaftswerten Animation. Liegt darin, dass alle darin enthaltenen Elemente eine <xref:System.Windows.Controls.ControlTemplate> muss threadsicher sein und muss die Zeitsteuerungssystems <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> Objekte, damit sie threadsichere. Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht fixiert werden, wenn er oder seine untergeordneten Zeitachsen dynamische Ressourcen Verweise oder Datenbindungsausdrücke enthalten. Weitere Informationen über das Fixieren und andere <xref:System.Windows.Freezable> Features, finden Sie unter der [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], kann nicht deklariert werden Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard> oder Animationsereignisse.  
  
 Ein Beispiel zur Vorgehensweise definieren Sie ein Storyboard in einem <xref:System.Windows.Controls.ControlTemplate>, finden Sie unter der [Animieren in einer ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) Beispiel.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>Animieren, wenn sich ein Eigenschaftswert ändert  
 In Stilen und Steuerelementvorlagen können Sie mit Triggerobjekten ein Storyboard starten, wenn sich eine Eigenschaft ändert. Beispiele finden Sie unter [Auslösen einer Animation Wenn ein Eigenschaftswert ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) und [Animieren in einer ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Animationen, die von der Eigenschaft angewendet <xref:System.Windows.Trigger> Objekte verhalten sich in einer komplexeren Weise als <xref:System.Windows.EventTrigger> Animationen oder Animationen Schritte mit <xref:System.Windows.Media.Animation.Storyboard> Methoden.  Diese "Übergabe" mit Animationen definiert, die von anderen <xref:System.Windows.Trigger> Objekte, bilden jedoch mit <xref:System.Windows.EventTrigger> und Animationen Methode ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
