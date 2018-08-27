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
ms.openlocfilehash: a7f9539cd3ac571977a91cd4e7dce07d641af3b6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932320"
---
# <a name="storyboards-overview"></a>Übersicht über Storyboards
In diesem Thema wird gezeigt, wie Sie mit <xref:System.Windows.Media.Animation.Storyboard> Objekte zu organisieren und Anwenden von Animationen. Es wird beschrieben, wie interaktiv bearbeitet <xref:System.Windows.Media.Animation.Storyboard> Objekte und beschreibt die indirekte eigenschaftszielsyntax.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Als Voraussetzung für dieses Thema sollten Sie mit den unterschiedlichen Animationstypen und ihren grundlegenden Funktionen vertraut sein. Eine Einführung zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Sie sollten auch wissen, wie angefügte Eigenschaften verwendet werden. Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>Was ist ein Storyboard?  
 Animationen sind nicht der einzige nützliche Zeitachsentyp. Andere Zeitachsenklassen werden bereitgestellt,um Ihnen beim Organisieren von Sätzen von Zeitachsen zu helfen und Zeitachsen auf Eigenschaften anzuwenden. Containerzeitachsen leiten Sie von der <xref:System.Windows.Media.Animation.TimelineGroup> -Klasse und beinhalten <xref:System.Windows.Media.Animation.ParallelTimeline> und <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein Typ von Containerzeitachse, die Zielinformationen für die Zeitachsen bereitstellt, er enthält. Ein Storyboard kann jeden Datentyp enthalten <xref:System.Windows.Media.Animation.Timeline>, einschließlich anderer Containerzeitachsen und Animationen. <xref:System.Windows.Media.Animation.Storyboard> -Objekte ermöglichen Ihnen, Zeitachsen zu kombinieren, die Auswirkungen auf eine Vielzahl von Objekten und Eigenschaften in einer einzigen Zeitachsenstruktur, erleichtert das Organisieren und Steuerung komplexer Zeitsteuerungsverhalten vereinfachen. Nehmen wir beispielsweise an, Sie wünschen eine Schaltfläche, die die folgenden drei Aktionen ausführt.  
  
-   Vergrößern und Ändern der Farbe, wenn der Benutzer die Schaltfläche auswählt.  
  
-   Verkleinern und dann wieder die ursprüngliche Größe annehmen, wenn auf sie geklickt wird.  
  
-   Verkleinern und zu 50 % Deckkraft ausgeblendet werden, wenn sie deaktiviert wird.  
  
 In diesem Fall sind mehrere Sätze von Animationen vorhanden, die auf das gleiche Objekt angewendet werden und die Sie abhängig vom Zustand der Schaltfläche zu unterschiedlichen Zeitpunkten wiedergeben möchten. <xref:System.Windows.Media.Animation.Storyboard> -Objekte ermöglichen Ihnen, Animationen zu organisieren und sie in Gruppen auf ein oder mehrere Objekte anwenden.  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>Wo können Sie ein Storyboard verwenden?  
 Ein <xref:System.Windows.Media.Animation.Storyboard> können verwendet werden, um Abhängigkeitseigenschaften von animierbaren Klassen animieren (Weitere Informationen dazu, was eine Klasse animierbar macht, finden Sie unter den [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)). Da der Einsatz von Storyboards ein Feature auf Frameworkebene ist, das Objekt muss allerdings gehören zu den <xref:System.Windows.NameScope> von eine <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.FrameworkContentElement>.  
  
 Beispielsweise können Sie eine <xref:System.Windows.Media.Animation.Storyboard> die folgenden Schritte ausführen:  
  
-   Animieren einer <xref:System.Windows.Media.SolidColorBrush> (Element ohne Framework), der es sich um den Hintergrund einer Schaltfläche (eine Art von <xref:System.Windows.FrameworkElement>),  
  
-   Animieren einer <xref:System.Windows.Media.SolidColorBrush> (Element ohne Framework), der es sich um die Füllung des eine <xref:System.Windows.Media.GeometryDrawing> (Element ohne Framework) angezeigt, mit einer <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).  
  
-   In Code Animieren einer <xref:System.Windows.Media.SolidColorBrush> deklarierten durch eine Klasse, die ebenfalls enthält eine <xref:System.Windows.FrameworkElement>, wenn die <xref:System.Windows.Media.SolidColorBrush> registriert, die den Namen <xref:System.Windows.FrameworkElement>.  
  
 Jedoch nicht verwendet werden konnte eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren einer <xref:System.Windows.Media.SolidColorBrush> , die nicht seinem Namen registriert hat eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, oder wurde nicht verwendet, um eine Eigenschaft eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>Anwenden von Animationen mit einem Storyboard  
 Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> zum Organisieren und Anwenden von Animationen, fügen Sie die Animationen als untergeordnete Zeitachsen dem <xref:System.Windows.Media.Animation.Storyboard>. Die <xref:System.Windows.Media.Animation.Storyboard> -Klasse stellt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> angefügten Eigenschaften. Sie können diese Eigenschaften für eine Animation einstellen, um deren Zielobjekt und Eigenschaft festzulegen.  
  
 Um Animationen auf ihre Ziele anzuwenden, starten Sie den <xref:System.Windows.Media.Animation.Storyboard> mit einer Triggeraktion oder einer Methode. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie verwenden eine <xref:System.Windows.Media.Animation.BeginStoryboard> Objekt mit einer <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>, oder <xref:System.Windows.DataTrigger>. Im Code können Sie auch die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode.  
  
 Die folgende Tabelle zeigt die unterschiedlichen Stellen, in dem jede <xref:System.Windows.Media.Animation.Storyboard> beginnen Technik wird unterstützt: pro Instanz, Stil, Steuerelementvorlage und Datenvorlage. „Pro Instanz“ bezieht sich auf das Verfahren, eine Animation oder ein Storyboard direkt auf Instanzen eines Objekts und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage anzuwenden.  
  
|Storyboard wird gestartet mit...|Pro Instanz|Stil|Steuerelementvorlage|Datenvorlage|Beispiel|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und ein <xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und eine Eigenschaft <xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und ein <xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[Vorgehensweise: Auslösen einer Animation bei Änderung eines Eigenschaftswerts](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren der <xref:System.Windows.FrameworkElement.Width%2A> von eine <xref:System.Windows.Shapes.Rectangle> Element und die <xref:System.Windows.Media.SolidColorBrush.Color%2A> von eine <xref:System.Windows.Media.SolidColorBrush> gezeichnet werden soll, die zum <xref:System.Windows.Shapes.Rectangle>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 Die folgenden Abschnitte beschreiben die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügten Eigenschaften ausführlicher.  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Frameworkelemente, Frameworkinhaltselemente und Freezable-Objekte  
 Im vorherigen Abschnitt wurde erwähnt, dass eine Animation den Namen des Ziels und die zu animierende Eigenschaft kennen muss, um ihr Ziel zu finden. Angeben der zu animierenden Eigenschaft ist leicht: Legen Sie einfach <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> durch den Namen des zu animierenden Eigenschaft.  Geben Sie den Namen des Objekts, dessen Eigenschaft, die Sie animieren, indem Sie festlegen möchten die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> Eigenschaft der Animation.  
  
 Für die <xref:System.Windows.Setter.TargetName%2A> -Eigenschaft funktioniert, das Zielobjekt muss einen Namen haben. Zuweisen eines Namens zu einer <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterscheidet sich vom Zuweisen eines Namens zu einer <xref:System.Windows.Freezable> Objekt.  
  
 Frameworkelemente sind die Klassen, die von erben die <xref:System.Windows.FrameworkElement> Klasse. Beispiele von Frameworkelementen sind <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>, und <xref:System.Windows.Shapes.Rectangle>. Im Wesentlichen sind alle Fenster, Panels und Steuerelemente Elemente. Frameworkinhaltselemente sind die Klassen, die von erben die <xref:System.Windows.FrameworkContentElement> Klasse. Beispiele von Frameworkinhaltselementen sind <xref:System.Windows.Documents.FlowDocument> und <xref:System.Windows.Documents.Paragraph>. Wenn Sie nicht sicher sind, ob ein Typ ein Frameworkelement oder ein Frameworkinhaltselement ist, überprüfen Sie, ob es über eine Name-Eigenschaft verfügt. Wenn dies der Fall ist, handelt es sich aller Wahrscheinlichkeit nach um ein Frameworkelement oder ein Frameworkinhaltselement. Um sicherzugehen, überprüfen Sie den Vererbungshierarchie-Abschnitt seiner Typ-Seite.  
  
 Zum Aktivieren des Ziels eines Frameworkelements oder Frameworkinhaltselements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], legen Sie dessen <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft. Im Code müssen Sie auch verwenden, die <xref:System.Windows.NameScope.RegisterName%2A> Methode, um den Namen des Elements mit dem Element registrieren für die Sie erstellt haben eine <xref:System.Windows.NameScope>.  
  
 Das folgende Beispiel stammt aus dem vorherigen Beispiel, weist den Namen `MyRectangle` eine <xref:System.Windows.Shapes.Rectangle>, einen Typ von <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 Wenn der Name vergeben wurde, können Sie eine Eigenschaft des Elements animieren.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable> Typen sind die Klassen, die von erben die <xref:System.Windows.Freezable> Klasse. Beispiele für <xref:System.Windows.Freezable> enthalten <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>, und <xref:System.Windows.Media.GradientStop>.  
  
 Zum Aktivieren des Ziels einer <xref:System.Windows.Freezable> eine Animation in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie die [X: Name Directive](../../../../docs/framework/xaml-services/x-name-directive.md) um ihm einen Namen zuzuweisen. Verwenden Sie im Code die <xref:System.Windows.NameScope.RegisterName%2A> Methode, um seinen Namen registrieren für die Sie erstellt haben, mit dem Element ein <xref:System.Windows.NameScope>.  
  
 Im folgenden Beispiel wird der Name einer <xref:System.Windows.Freezable> Objekt.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 Das Objekt kann dann animiert werden.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> -Objekte verwenden Namensbereiche, zum Auflösen der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Eigenschaft. Weitere Informationen über WPF-Namescopes finden Sie unter [WPF-XAML-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md). Wenn die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Eigenschaft ausgelassen wird, wird die Animation das Element aus, auf dem sie definiert ist, oder, im Fall von Stilen, das formatierte Element als Ziel.  
  
 In einigen Fällen ein Namen kann nicht zugewiesen werden eine <xref:System.Windows.Freezable> Objekt. Z. B. wenn ein <xref:System.Windows.Freezable> wird als Ressource deklariert oder verwendet, um einen Eigenschaftswert in einem Stil, es kann kein Name zugewiesen werden. Da es keinen Namen hat, kann es zwar kein direktes, aber ein indirektes Ziel sein. In den folgenden Abschnitten wird beschrieben, wie indirekte Ziele verwendet werden.  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>Indirektes Ziel  
 Es gibt Situationen eine <xref:System.Windows.Freezable> kann nicht angewendet werden, direkt für eine Animation, z. B. wenn die <xref:System.Windows.Freezable> wird als Ressource deklariert oder verwendet, um einen Eigenschaftswert in einem Stil. In diesen Fällen, obwohl Sie es als direktes Ziel können keine Sie können weiterhin Animieren der <xref:System.Windows.Freezable> Objekt. Statt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Eigenschaft mit dem Namen des der <xref:System.Windows.Freezable>, erhält sie den Namen des Elements, das <xref:System.Windows.Freezable> "gehört". Z. B. eine <xref:System.Windows.Media.SolidColorBrush> zum Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechtecks Element gehört, zu diesem Rechteck. Zum Animieren des Pinsels legen Sie die Animation <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> mit einer Kette von Eigenschaften, die an die Eigenschaft des Frameworkelements oder Frameworkinhaltselements beginnt die <xref:System.Windows.Freezable> wurde verwendet, um festzulegen, und endet mit dem <xref:System.Windows.Freezable> zu animierende Eigenschaft.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Beachten Sie, dass, wenn die <xref:System.Windows.Freezable> ist fixiert ist, wird ein Klon vorgenommen werden, und dieser Klon animiert wird. Wenn in diesem Fall des Originalobjekts <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> Eigenschaft weiterhin zurück `false`, da das Originalobjekt nicht animiert ist. Weitere Informationen zum Klonen finden Sie unter den [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Beachten Sie außerdem, dass nicht vorhandene Objekte Ziel sein können, wenn indirekte Eigenschaftenziele verwendet werden. Sie könnten beispielsweise annehmen, die die <xref:System.Windows.Controls.Control.Background%2A> einer bestimmten Schaltfläche mit festgelegt wurde eine <xref:System.Windows.Media.SolidColorBrush> und versuchen Sie es zum Animieren der Farbe, wenn tatsächlich eine <xref:System.Windows.Media.LinearGradientBrush> wurde verwendet, um den Hintergrund der Schaltfläche festlegen. In diesen Fällen wird keine Ausnahme ausgelöst. die Animation hat keinen sichtbaren Effekt haben, da <xref:System.Windows.Media.LinearGradientBrush> reagiert nicht auf Änderungen an der <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft.  
  
 In den folgenden Abschnitten wird die Syntax für indirekte Eigenschaftenziele ausführlicher erklärt.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Verwenden einer Eigenschaft eines Freezable-Objekts in XAML als indirektes Ziel  
 Eine Eigenschaft eines Freezable-Objekts im Ziel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie die folgende Syntax.  
  
| |  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* ist die Eigenschaft der <xref:System.Windows.FrameworkElement> die der <xref:System.Windows.Freezable> wird verwendet, um festzulegen, und  
  
-   *FreezablePropertyName* ist die Eigenschaft der <xref:System.Windows.Freezable> zu animieren.  
  
 Der folgende Code zeigt, wie Sie animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einer <xref:System.Windows.Media.SolidColorBrush> zum Festlegen der  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> ein Rectangle-Elements.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden.  
  
 Um ein in einer Auflistung enthaltenes Freezable-Objekt als Ziel zu verwenden, geben Sie die folgende Pfadsyntax an.  
  
| |  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Wo *CollectionIndex* ist der Index des Objekts im Array oder in der Auflistung.  
  
 Nehmen wir beispielsweise an, dass ein Rechteck ist ein <xref:System.Windows.Media.TransformGroup> Ressource angewendet werden, um die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, und Sie möchten eine der Transformationen animieren sie enthält.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 Der folgende Code zeigt, wie Sie animieren der <xref:System.Windows.Media.RotateTransform.Angle%2A> Eigenschaft der <xref:System.Windows.Media.RotateTransform> im vorherigen Beispiel gezeigt.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Verwenden einer Eigenschaft eines Freezable-Objekts im Code als indirektes Ziel  
 Erstellen Sie im Code eine <xref:System.Windows.PropertyPath> Objekt. Bei der Erstellung der <xref:System.Windows.PropertyPath>, Sie geben eine <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 Erstellung <xref:System.Windows.PropertyPath.PathParameters%2A>, erstellen Sie ein Array vom Typ <xref:System.Windows.DependencyProperty> , die eine Liste von Abhängigkeitseigenschaften-Bezeichnerfeldern enthält. Das erste Bezeichnerfeld ist für die Eigenschaft der <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> , die die <xref:System.Windows.Freezable> dient zum festlegen. Das nächste Bezeichnerfeld stellt die Eigenschaft dar. die <xref:System.Windows.Freezable> Ziel. Betrachten Sie sie als eine Kette von Eigenschaften, die verbindet die <xref:System.Windows.Freezable> auf die <xref:System.Windows.FrameworkElement> Objekt.  
  
 Folgendes ist ein Beispiel für eine Eigenschaft Abhängigkeitskette, dessen Ziel die <xref:System.Windows.Media.SolidColorBrush.Color%2A> von eine <xref:System.Windows.Media.SolidColorBrush> zum Festlegen der der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteckelements.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 Sie müssen auch angeben einer <xref:System.Windows.PropertyPath.Path%2A>. Ein <xref:System.Windows.PropertyPath.Path%2A> ist eine <xref:System.String> , informiert die <xref:System.Windows.PropertyPath.Path%2A> Interpretation dessen <xref:System.Windows.PropertyPath.PathParameters%2A>. Die folgende Syntax wird verwendet.  
  
| |  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* ist der Index des der <xref:System.Windows.DependencyProperty> Array, das den Bezeichner der enthält die <xref:System.Windows.FrameworkElement> -Eigenschaft des Objekts, das <xref:System.Windows.Freezable> wird verwendet, um festzulegen, und  
  
-   *FreezablePropertyArrayIndex* ist der Schnittstellenindex der <xref:System.Windows.DependencyProperty> Array, das den Bezeichner der Zieleigenschaft enthält.  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.PropertyPath.Path%2A> , das wäre begleiten die <xref:System.Windows.PropertyPath.PathParameters%2A> im vorherigen Beispiel definiert.
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 Das folgende Beispiel kombiniert den Code in den vorherigen Beispielen zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von eine <xref:System.Windows.Media.SolidColorBrush> zum Festlegen der der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteckelements.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden. Nehmen wir beispielsweise an, dass ein Rechteck ist ein <xref:System.Windows.Media.TransformGroup> Ressource angewendet werden, um die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, und Sie möchten eine der Transformationen animieren sie enthält.  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Soll ein <xref:System.Windows.Freezable> in einer Auflistung enthalten, verwenden Sie die folgende Pfadsyntax.  
  
| |  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 Wo *CollectionIndex* ist der Index des Objekts im Array oder in der Auflistung.  
  
 Ziel der <xref:System.Windows.Media.RotateTransform.Angle%2A> Eigenschaft der <xref:System.Windows.Media.RotateTransform>, der zweiten Transformation in der <xref:System.Windows.Media.TransformGroup>, verwenden Sie die folgende <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 Das folgende Beispiel zeigt den vollständigen Code zum Animieren der <xref:System.Windows.Media.RotateTransform.Angle%2A> von einer <xref:System.Windows.Media.RotateTransform> enthaltenen eine <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Indirektes Ziel mit einem Freezable-Objekt als Ausgangspunkt  
 Die vorherigen Abschnitten beschrieben, wie Sie indirektes Ziel eine <xref:System.Windows.Freezable> von ab eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> und eine Eigenschaftenkette zu einer <xref:System.Windows.Freezable> Untereigenschaft. Sie können auch eine <xref:System.Windows.Freezable> als Ausgangspunkt und indirekt eine der seine <xref:System.Windows.Freezable> untergeordnete Eigenschaften. Eine zusätzliche Einschränkung gilt bei Verwendung einer <xref:System.Windows.Freezable> als Ausgangspunkt für das indirekte Ziel: das Starten <xref:System.Windows.Freezable> und jede <xref:System.Windows.Freezable> zwischen diesem und den indirektes Ziel verwendeten Untereigenschaft dürfen nicht fixiert sein.  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Interaktives Steuern eines Storyboards in XAML  
 Zum Starten eines Storyboards [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie verwenden eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion auslösen. <xref:System.Windows.Media.Animation.BeginStoryboard> verteilt die Animationen an die Objekte und Eigenschaften, die sie animieren möchten, die und startet das Storyboard an. (Weitere Informationen zu diesem Prozess finden Sie unter den [Animation und zeitliche Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).) Sie erteilen die <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen durch Angabe der <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> -Eigenschaft, Sie machen es ein steuerbares Storyboard. Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde. Die folgende Liste enthält Aktionen des steuerbaren Storyboards, die Sie mit Ereignistriggern zum Steuern eines Storyboards verwenden.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Es setzt ein angehaltenes Storyboard fort.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Geschwindigkeit des Storyboards.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Verschiebt ein Storyboard an das Ende seines Füllbereichs, sofern vorhanden.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Hält das Storyboard an.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard an.  
  
 Im folgenden Beispiel werden Aktionen des steuerbaren Storyboards zum interaktiven Steuern eines Storyboards verwendet.  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Interaktives Steuern eines Storyboards mithilfe von Code  
 In den vorherigen Beispielen wurde gezeigt, wie mithilfe von Triggeraktionen animiert wird. Im Code können Sie auch steuern ein Storyboards mithilfe von interaktiven Methoden der der <xref:System.Windows.Media.Animation.Storyboard> Klasse. Für eine <xref:System.Windows.Media.Animation.Storyboard> interaktiv in Code ausgeführt werden, müssen Sie die geeignete Überladung der Storyboard verwenden <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, und geben Sie `true` damit sie steuerbar wird. Finden Sie unter den <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> Seite erhalten Sie weitere Informationen.  
  
 Die folgende Liste enthält die Methoden, die verwendet werden können, zum Bearbeiten einer <xref:System.Windows.Media.Animation.Storyboard> nachdem es gestartet wurde:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 Der Vorteil bei der Verwendung dieser Methoden ist, dass Sie nicht erstellen müssen <xref:System.Windows.Trigger> oder <xref:System.Windows.TriggerAction> Objekte; Sie lediglich einen Verweis auf die steuerbar <xref:System.Windows.Media.Animation.Storyboard> Sie bearbeiten möchten.  
  
 **Hinweis:** alle interaktiven Aktionen auf, eine <xref:System.Windows.Media.Animation.Clock>, und daher auch auf eine <xref:System.Windows.Media.Animation.Storyboard> treten auf dem nächsten Teilstrich der zeitsteuerungs-Engine kurz vor dem nächsten Rendering erfolgt. Angenommen, Sie verwenden die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode springen zu einem anderen Punkt in einer Animation, die den Wert der Eigenschaft nicht sofort geändert, sondern der Wert ändert, beim nächsten Teilstrich der zeitsteuerungs-Engine.  
  
 Das folgende Beispiel zeigt, wie angewendet und Steuern von Animationen mit interaktiven Methoden der der <xref:System.Windows.Media.Animation.Storyboard> Klasse.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>Animieren in einem Stil  
 Sie können <xref:System.Windows.Media.Animation.Storyboard> Objekte, um Animationen im Definieren einer <xref:System.Windows.Style>. Animieren mit einem <xref:System.Windows.Media.Animation.Storyboard> in eine <xref:System.Windows.Style> funktioniert ähnlich wie eine <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle mit den folgenden drei Ausnahmen:  
  
-   Keine Angabe einer <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; die <xref:System.Windows.Media.Animation.Storyboard> immer das Element, die <xref:System.Windows.Style> angewendet wird. Ziel <xref:System.Windows.Freezable> Objekte aufweist, müssen Sie indirektes Ziel verwenden. Weitere Informationen über indirekte Ziele finden Sie unter den [indirektes Ziel](#pathsyntaxforchangeable) Abschnitt.  
  
-   Sie nicht angeben, ein <xref:System.Windows.EventTrigger.SourceName%2A> für eine <xref:System.Windows.EventTrigger> oder <xref:System.Windows.Trigger>.  
  
-   Sie können keine dynamische ressourcenreferenzen oder Datenbindungsausdrücke festgelegt <xref:System.Windows.Media.Animation.Storyboard> oder animationseigenschaftenwert. Der Grund dafür ist alles, was in einem <xref:System.Windows.Style> muss threadsicher sein und das Zeitsteuerungssystem muss <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> Objekte, um sie threadsicher zu machen. Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht fixiert werden, wenn es oder seine untergeordneten Zeitachsen dynamische ressourcenreferenzen oder Datenbindungsausdrücke enthalten. Weitere Informationen über das Fixieren und andere <xref:System.Windows.Freezable> Features finden Sie die [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können keine Ereignishandler für deklarieren <xref:System.Windows.Media.Animation.Storyboard> oder Animationsereignisse.  
  
 Ein Beispiel zeigt, wie ein Storyboard in einem Stil definiert wird, finden Sie die [Animieren in einem Stil](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) Beispiel.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>Animieren in einer ControlTemplate  
 Sie können <xref:System.Windows.Media.Animation.Storyboard> Objekte, um Animationen im Definieren einer <xref:System.Windows.Controls.ControlTemplate>. Animieren mit einem <xref:System.Windows.Media.Animation.Storyboard> in eine <xref:System.Windows.Controls.ControlTemplate> funktioniert ähnlich wie eine <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle mit den folgenden zwei Ausnahmen:  
  
-   Die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> kann nur auf untergeordnete Objekte verweisen, die <xref:System.Windows.Controls.ControlTemplate>. Wenn <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> nicht angegeben ist, wird die Animation das Element, der als Ziel der <xref:System.Windows.Controls.ControlTemplate> angewendet wird.  
  
-   Die <xref:System.Windows.EventTrigger.SourceName%2A> für eine <xref:System.Windows.EventTrigger> oder <xref:System.Windows.Trigger> kann nur auf untergeordnete Objekte verweisen, die <xref:System.Windows.Controls.ControlTemplate>.  
  
-   Sie können keine dynamische ressourcenreferenzen oder Datenbindungsausdrücke festgelegt <xref:System.Windows.Media.Animation.Storyboard> oder animationseigenschaftenwert. Der Grund dafür ist alles, was in einem <xref:System.Windows.Controls.ControlTemplate> muss threadsicher sein und das Zeitsteuerungssystem muss <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> Objekte, um sie threadsicher zu machen. Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht fixiert werden, wenn es oder seine untergeordneten Zeitachsen dynamische ressourcenreferenzen oder Datenbindungsausdrücke enthalten. Weitere Informationen über das Fixieren und andere <xref:System.Windows.Freezable> Features finden Sie die [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können keine Ereignishandler für deklarieren <xref:System.Windows.Media.Animation.Storyboard> oder Animationsereignisse.  
  
 Ein Beispiel für ein Storyboard im Definieren einer <xref:System.Windows.Controls.ControlTemplate>, finden Sie unter der [Animieren in einer ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) Beispiel.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>Animieren, wenn sich ein Eigenschaftswert ändert  
 In Stilen und Steuerelementvorlagen können Sie mit Triggerobjekten ein Storyboard starten, wenn sich eine Eigenschaft ändert. Beispiele finden Sie in [Auslösen einer Animation bei der eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) und [Animieren in einer ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Eigenschaft angewendete Animationen <xref:System.Windows.Trigger> Objekte verhalten sich komplexer als <xref:System.Windows.EventTrigger> Animationen oder Animationen Einstieg <xref:System.Windows.Media.Animation.Storyboard> Methoden.  Sie "übergeben" mit Animationen definiert, die von anderen <xref:System.Windows.Trigger> Objekte, aber verfassen mit <xref:System.Windows.EventTrigger> und Methoden ausgelösten Animationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
