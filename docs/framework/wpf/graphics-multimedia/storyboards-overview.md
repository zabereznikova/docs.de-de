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
ms.openlocfilehash: 5c058dbaf2ae209a198a8299790d4002447ac443
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559689"
---
# <a name="storyboards-overview"></a>Übersicht über Storyboards

In diesem Thema wird gezeigt, wie Sie mit <xref:System.Windows.Media.Animation.Storyboard>-Objekten Animationen organisieren und anwenden. Es wird beschrieben, wie <xref:System.Windows.Media.Animation.Storyboard> Objekten interaktiv bearbeitet und die indirekte Eigenschafts Ziel Syntax beschrieben wird.

## <a name="prerequisites"></a>Erforderliche Komponenten

Als Voraussetzung für dieses Thema sollten Sie mit den unterschiedlichen Animationstypen und ihren grundlegenden Funktionen vertraut sein. Eine Einführung zu Animationen finden Sie unter [Übersicht über Animationen](animation-overview.md). Sie sollten auch wissen, wie angefügte Eigenschaften verwendet werden. Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>Was ist ein Storyboard?

Animationen sind nicht der einzige nützliche Zeitachsentyp. Andere Zeitachsenklassen werden bereitgestellt,um Ihnen beim Organisieren von Sätzen von Zeitachsen zu helfen und Zeitachsen auf Eigenschaften anzuwenden. Containertimelines werden von der <xref:System.Windows.Media.Animation.TimelineGroup>-Klasse abgeleitet und enthalten <xref:System.Windows.Media.Animation.ParallelTimeline> und <xref:System.Windows.Media.Animation.Storyboard>.

Eine <xref:System.Windows.Media.Animation.Storyboard> ist eine Art von Container Zeitachse, die Ziel Informationen für die in ihr enthaltenen Zeitachsen bereitstellt. Ein Storyboard kann jede Art von <xref:System.Windows.Media.Animation.Timeline>enthalten, einschließlich anderer containertimelines und Animationen. <xref:System.Windows.Media.Animation.Storyboard> Objekte ermöglichen es Ihnen, Zeitachsen zu kombinieren, die eine Vielzahl von Objekten und Eigenschaften in einer einzelnen Zeitachsen Struktur beeinflussen, sodass Sie das komplexe Verhalten der zeitlichen Steuerung leicht organisieren und steuern können. Nehmen wir beispielsweise an, Sie wünschen eine Schaltfläche, die die folgenden drei Aktionen ausführt.

- Vergrößern und Ändern der Farbe, wenn der Benutzer die Schaltfläche auswählt.

- Verkleinern und dann wieder die ursprüngliche Größe annehmen, wenn auf sie geklickt wird.

- Verkleinern und zu 50 % Deckkraft ausgeblendet werden, wenn sie deaktiviert wird.

In diesem Fall sind mehrere Sätze von Animationen vorhanden, die auf das gleiche Objekt angewendet werden und die Sie abhängig vom Zustand der Schaltfläche zu unterschiedlichen Zeitpunkten wiedergeben möchten. mit <xref:System.Windows.Media.Animation.Storyboard>-Objekten können Sie Animationen organisieren und in Gruppen auf ein oder mehrere Objekte anwenden.

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>Wo können Sie ein Storyboard verwenden?

Eine <xref:System.Windows.Media.Animation.Storyboard> kann verwendet werden, um Abhängigkeits Eigenschaften von animier baren Klassen zu animieren (Weitere Informationen dazu, was eine Klasse animabel macht, finden Sie unter [Übersicht über Animationen](animation-overview.md)). Da das Storyboarding jedoch eine Funktion auf Frameworkebene ist, muss das Objekt zum <xref:System.Windows.NameScope> eines <xref:System.Windows.FrameworkElement> oder einer <xref:System.Windows.FrameworkContentElement>gehören.

Beispielsweise können Sie eine <xref:System.Windows.Media.Animation.Storyboard> für folgende Aufgaben verwenden:

- Animieren eines <xref:System.Windows.Media.SolidColorBrush> (Non-Framework-Element), das den Hintergrund einer Schaltfläche zeichnet (ein Typ <xref:System.Windows.FrameworkElement>),

- Animieren eines <xref:System.Windows.Media.SolidColorBrush> (Non-Framework-Element), das die Füllung eines <xref:System.Windows.Media.GeometryDrawing> (nicht-Framework-Element) zeichnet, das mithilfe eines <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>) angezeigt wird.

- Animieren Sie im Code eine <xref:System.Windows.Media.SolidColorBrush>, die von einer Klasse deklariert wurde, die auch einen <xref:System.Windows.FrameworkElement>enthält, wenn der <xref:System.Windows.Media.SolidColorBrush> seinen Namen bei diesem <xref:System.Windows.FrameworkElement>registriert hat.

Es ist jedoch nicht möglich, eine <xref:System.Windows.Media.Animation.Storyboard> zu animieren, um eine <xref:System.Windows.Media.SolidColorBrush> zu animieren, die ihren Namen nicht bei einem <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>registriert hat, oder Sie wurde nicht zum Festlegen einer Eigenschaft eines <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>verwendet.

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>Anwenden von Animationen mit einem Storyboard

Um eine <xref:System.Windows.Media.Animation.Storyboard> zum organisieren und Anwenden von Animationen zu verwenden, fügen Sie die Animationen als untergeordnete Zeitachsen der <xref:System.Windows.Media.Animation.Storyboard>hinzu. Die <xref:System.Windows.Media.Animation.Storyboard>-Klasse stellt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> und die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> angefügten Eigenschaften bereit. Sie können diese Eigenschaften für eine Animation einstellen, um deren Zielobjekt und Eigenschaft festzulegen.

Wenn Sie Animationen auf Ihre Ziele anwenden möchten, beginnen Sie mit der <xref:System.Windows.Media.Animation.Storyboard> mit einer Triggeraktion oder einer Methode. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]verwenden Sie ein <xref:System.Windows.Media.Animation.BeginStoryboard>-Objekt mit einer <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>oder <xref:System.Windows.DataTrigger>. Im Code können Sie auch die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode verwenden.

In der folgenden Tabelle werden die verschiedenen Orte angezeigt, an denen die einzelnen <xref:System.Windows.Media.Animation.Storyboard> BEGIN-Technik unterstützt werden: pro Instanz, Stil, Steuerelement Vorlage und Daten Vorlage. „Pro Instanz“ bezieht sich auf das Verfahren, eine Animation oder ein Storyboard direkt auf Instanzen eines Objekts und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage anzuwenden.

|Storyboard wird gestartet mit...|Pro Instanz|Art|Steuerelementvorlage|Datenvorlage|Beispiel|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard> und ein <xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard> und eine Eigenschaft <xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard> und eine <xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[Vorgehensweise: Auslösen einer Animation bei Änderung eines Eigenschaftswerts](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)|

Im folgenden Beispiel wird ein-<xref:System.Windows.Media.Animation.Storyboard> verwendet, um die <xref:System.Windows.FrameworkElement.Width%2A> eines <xref:System.Windows.Shapes.Rectangle>-Elements zu animieren, und die <xref:System.Windows.Media.SolidColorBrush.Color%2A> einer <xref:System.Windows.Media.SolidColorBrush>, die zum Zeichnen dieses <xref:System.Windows.Shapes.Rectangle>verwendet wird.

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

In den folgenden Abschnitten werden die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften ausführlicher beschrieben.

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Frameworkelemente, Frameworkinhaltselemente und Freezable-Objekte

Im vorherigen Abschnitt wurde erwähnt, dass eine Animation den Namen des Ziels und die zu animierende Eigenschaft kennen muss, um ihr Ziel zu finden. Die Angabe der zu animierenden Eigenschaft erfolgt direkt: Legen Sie <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> einfach mit dem Namen der zu animierenden Eigenschaft fest.  Sie geben den Namen des Objekts an, dessen Eigenschaft Sie animieren möchten, indem Sie die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType>-Eigenschaft der Animation festlegen.

Damit die <xref:System.Windows.Setter.TargetName%2A>-Eigenschaft funktioniert, muss das Zielobjekt einen Namen aufweisen. Das Zuweisen eines Namens zu einem <xref:System.Windows.FrameworkElement> oder einer <xref:System.Windows.FrameworkContentElement> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterscheidet sich vom Zuweisen eines Namens zu einem <xref:System.Windows.Freezable> Objekt.

Frameworkelemente sind die Klassen, die von der <xref:System.Windows.FrameworkElement>-Klasse erben. Beispiele für Frameworkelemente sind <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>und <xref:System.Windows.Shapes.Rectangle>. Im Wesentlichen sind alle Fenster, Panels und Steuerelemente Elemente. Frameworkinhaltselemente sind die Klassen, die von der <xref:System.Windows.FrameworkContentElement>-Klasse erben. Beispiele für Frameworkinhaltselemente sind <xref:System.Windows.Documents.FlowDocument> und <xref:System.Windows.Documents.Paragraph>. Wenn Sie nicht sicher sind, ob ein Typ ein Frameworkelement oder ein Frameworkinhaltselement ist, überprüfen Sie, ob es über eine Name-Eigenschaft verfügt. Wenn dies der Fall ist, handelt es sich aller Wahrscheinlichkeit nach um ein Frameworkelement oder ein Frameworkinhaltselement. Um sicherzugehen, überprüfen Sie den Vererbungshierarchie-Abschnitt seiner Typ-Seite.

Um die Zielgruppen Steuerung für ein FrameworkElement oder ein Framework-Inhalts Element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]zu aktivieren, legen Sie dessen <xref:System.Windows.FrameworkElement.Name%2A>-Eigenschaft fest. Im Code müssen Sie auch die <xref:System.Windows.NameScope.RegisterName%2A>-Methode verwenden, um den Namen des Elements mit dem Element zu registrieren, für das Sie eine <xref:System.Windows.NameScope>erstellt haben.

Im folgenden Beispiel, das aus dem vorherigen Beispiel entnommen wurde, wird der Name `MyRectangle` ein <xref:System.Windows.Shapes.Rectangle>, ein <xref:System.Windows.FrameworkElement>Typ zugewiesen.

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

Wenn der Name vergeben wurde, können Sie eine Eigenschaft des Elements animieren.

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable> Typen sind die Klassen, die von der <xref:System.Windows.Freezable>-Klasse erben. Beispiele für <xref:System.Windows.Freezable> sind <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>und <xref:System.Windows.Media.GradientStop>.

Um die Zielvorgabe einer <xref:System.Windows.Freezable> durch eine Animation in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]zu aktivieren, verwenden Sie die [x:Name-Direktive](../../../desktop-wpf/xaml-services/xname-directive.md) , um ihr einen Namen zuzuweisen. Im Code verwenden Sie die <xref:System.Windows.NameScope.RegisterName%2A>-Methode, um den Namen mit dem Element zu registrieren, für das Sie eine <xref:System.Windows.NameScope>erstellt haben.

Im folgenden Beispiel wird einem <xref:System.Windows.Freezable>-Objekt ein Name zugewiesen.

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

Das Objekt kann dann animiert werden.

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard>-Objekte verwenden namens Bereiche zum Auflösen der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>-Eigenschaft. Weitere Informationen über WPF-Namescopes finden Sie unter [WPF-XAML-Namescopes](../advanced/wpf-xaml-namescopes.md). Wenn die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>-Eigenschaft ausgelassen wird, zielt die Animation auf das Element ab, für das Sie definiert ist, oder im Fall von Stilen das formatierte Element.

Manchmal kann ein Name nicht einem <xref:System.Windows.Freezable> Objekt zugewiesen werden. Wenn beispielsweise eine <xref:System.Windows.Freezable> als Ressource deklariert oder zum Festlegen eines Eigenschafts Werts in einem Stil verwendet wird, kann Ihr kein Name zugewiesen werden. Da es keinen Namen hat, kann es zwar kein direktes, aber ein indirektes Ziel sein. In den folgenden Abschnitten wird beschrieben, wie indirekte Ziele verwendet werden.

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>Indirektes Ziel

Es gibt vorkommen, dass ein <xref:System.Windows.Freezable> nicht direkt durch eine Animation als Ziel festgelegt werden kann, z. b. wenn die <xref:System.Windows.Freezable> als Ressource deklariert oder zum Festlegen eines Eigenschafts Werts in einem Stil verwendet wird. In diesen Fällen können Sie das <xref:System.Windows.Freezable> Objekt animieren, obwohl Sie es nicht direkt ausrichten können. Anstatt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>-Eigenschaft mit dem Namen des <xref:System.Windows.Freezable>festzulegen, benennen Sie den Namen des Elements, zu dem der <xref:System.Windows.Freezable> "gehört. Beispielsweise ist eine <xref:System.Windows.Media.SolidColorBrush>, die verwendet wird, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteck Elements festzulegen, zu diesem Rechteck gehört. Um den Pinsel zu animieren, müssen Sie die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> der Animation mit einer Kette von Eigenschaften festlegen, die bei der-Eigenschaft des Framework-Elements oder Frameworkinhaltselements beginnt, das <xref:System.Windows.Freezable> verwendet wurde, um die <xref:System.Windows.Freezable>-Eigenschaft festzulegen und zu animieren.

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

Beachten Sie Folgendes: Wenn die <xref:System.Windows.Freezable> eingefroren ist, wird ein Klon erstellt, und der Klon wird animiert. In diesem Fall gibt die <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A>-Eigenschaft des ursprünglichen Objekts weiterhin `false`zurück, da das ursprüngliche Objekt nicht tatsächlich animiert ist. Weitere Informationen zum Klonen finden Sie unter Übersicht über frei wählbare [Objekte](../advanced/freezable-objects-overview.md).

Beachten Sie außerdem, dass nicht vorhandene Objekte Ziel sein können, wenn indirekte Eigenschaftenziele verwendet werden. Beispielsweise können Sie davon ausgehen, dass der <xref:System.Windows.Controls.Control.Background%2A> einer bestimmten Schaltfläche mit einem <xref:System.Windows.Media.SolidColorBrush> festgelegt wurde, und versuchen, seine Farbe zu animieren, wenn tatsächlich ein <xref:System.Windows.Media.LinearGradientBrush> zum Festlegen des Hintergrunds der Schaltfläche verwendet wurde. In diesen Fällen wird keine Ausnahme ausgelöst. die Animation kann nicht sichtbar sein, da <xref:System.Windows.Media.LinearGradientBrush> nicht auf Änderungen der <xref:System.Windows.Media.SolidColorBrush.Color%2A>-Eigenschaft reagiert.

In den folgenden Abschnitten wird die Syntax für indirekte Eigenschaftenziele ausführlicher erklärt.

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Verwenden einer Eigenschaft eines Freezable-Objekts in XAML als indirektes Ziel

Verwenden Sie die folgende Syntax, um eine Eigenschaft eines frei wählbaren in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]als Ziel zu verwenden.

| |
|-|
|*ElementPropertyName* `.` *frezablepropertyname*|

Where

- *ElementPropertyName* ist die Eigenschaft des <xref:System.Windows.FrameworkElement> der mithilfe des <xref:System.Windows.Freezable> festgelegt werden kann.

- " *Freizablepropertyname* " ist die Eigenschaft des zu animierenden <xref:System.Windows.Freezable>.

Der folgende Code zeigt, wie die <xref:System.Windows.Media.SolidColorBrush.Color%2A> eines <xref:System.Windows.Media.SolidColorBrush> animiert wird, das verwendet wird, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteck Elements festzulegen.

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden.

Um ein in einer Auflistung enthaltenes Freezable-Objekt als Ziel zu verwenden, geben Sie die folgende Pfadsyntax an.

| |
|-|
|*ElementPropertyName* `.Children[` *collectionindex* `].` *freizablepropertyname*|

Dabei ist *collectionindex* der Index des Objekts in dessen Array oder Auflistung.

Nehmen wir beispielsweise an, dass ein Rechteck eine <xref:System.Windows.Media.TransformGroup> Ressource hat, die auf seine <xref:System.Windows.UIElement.RenderTransform%2A>-Eigenschaft angewendet wird, und Sie möchten eine der in ihr enthaltenen Transformationen animieren.

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

Der folgende Code zeigt, wie Sie die <xref:System.Windows.Media.RotateTransform.Angle%2A>-Eigenschaft des im vorherigen Beispiel gezeigten <xref:System.Windows.Media.RotateTransform> animieren.

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Verwenden einer Eigenschaft eines Freezable-Objekts im Code als indirektes Ziel

Im Code erstellen Sie ein <xref:System.Windows.PropertyPath>-Objekt. Wenn Sie die <xref:System.Windows.PropertyPath>erstellen, geben Sie eine <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A>an.

Um <xref:System.Windows.PropertyPath.PathParameters%2A>zu erstellen, erstellen Sie ein Array vom Typ <xref:System.Windows.DependencyProperty>, das eine Liste von Bezeichnerfeldern für die Abhängigkeits Eigenschaft enthält. Das erste Bezeichnerfeld ist für die-Eigenschaft des <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, das mit dem <xref:System.Windows.Freezable> festgelegt wird. Das nächste Bezeichnerfeld stellt die-Eigenschaft des <xref:System.Windows.Freezable> dar, das als Ziel für das Ziel Stellen Sie sich dies als eine Kette von Eigenschaften vor, die die <xref:System.Windows.Freezable> mit dem <xref:System.Windows.FrameworkElement> Objekt verbindet.

Im folgenden finden Sie ein Beispiel für eine Abhängigkeits Eigenschaften Kette, die auf die <xref:System.Windows.Media.SolidColorBrush.Color%2A> eines-<xref:System.Windows.Media.SolidColorBrush> abzielt, das verwendet wird, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteck Elements festzulegen.

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

Außerdem müssen Sie einen <xref:System.Windows.PropertyPath.Path%2A>angeben. Eine <xref:System.Windows.PropertyPath.Path%2A> ist eine <xref:System.String>, die dem <xref:System.Windows.PropertyPath.Path%2A> mitteilt, wie seine <xref:System.Windows.PropertyPath.PathParameters%2A>interpretiert werden soll. Die folgende Syntax wird verwendet.

| |
|-|
|`(` " *besitzpropertyarrayindex* " `).(` " *freiprozablepropertyarrayindex* " `)`|

Where

- " *Besitzpropertyarrayindex* " ist der Index des <xref:System.Windows.DependencyProperty> Arrays, das den Bezeichner der Eigenschaft des <xref:System.Windows.FrameworkElement> Objekts enthält, für die der <xref:System.Windows.Freezable> verwendet wird, und

- " *Freizablepropertyarrayindex* " ist der Index des <xref:System.Windows.DependencyProperty> Arrays, das den Bezeichner der zu zielenden Eigenschaft enthält.

Das folgende Beispiel zeigt die <xref:System.Windows.PropertyPath.Path%2A>, die die im vorherigen Beispiel definierten <xref:System.Windows.PropertyPath.PathParameters%2A> begleitet.

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

Im folgenden Beispiel wird der Code in den vorherigen Beispielen kombiniert, um die <xref:System.Windows.Media.SolidColorBrush.Color%2A> eines <xref:System.Windows.Media.SolidColorBrush> zu animieren, der zum Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteck Elements verwendet wird.

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden. Nehmen wir beispielsweise an, dass ein Rechteck eine <xref:System.Windows.Media.TransformGroup> Ressource hat, die auf seine <xref:System.Windows.UIElement.RenderTransform%2A>-Eigenschaft angewendet wird, und Sie möchten eine der in ihr enthaltenen Transformationen animieren.

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

Verwenden Sie die folgende Pfad Syntax, um eine <xref:System.Windows.Freezable> zu verwenden, die in einer Auflistung enthalten ist.

| |
|-|
|`(` *besitzpropertyarrayindex* `).(` *collectionchildren enpropertyarrayindex* `)` `[` *collectionindex* `].(` *freizablepropertyarrayindex* `)`|

Dabei ist *collectionindex* der Index des Objekts in dessen Array oder Auflistung.

Wenn Sie die <xref:System.Windows.Media.RotateTransform.Angle%2A>-Eigenschaft der <xref:System.Windows.Media.RotateTransform>als Ziel verwenden möchten, verwenden Sie die zweite Transformation in der <xref:System.Windows.Media.TransformGroup>, indem Sie die folgenden <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A>verwenden.

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

Das folgende Beispiel zeigt den gesamten Code zum Animieren der <xref:System.Windows.Media.RotateTransform.Angle%2A> einer <xref:System.Windows.Media.RotateTransform>, die in einem <xref:System.Windows.Media.TransformGroup>enthalten ist.

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Indirektes Ziel mit einem Freezable-Objekt als Ausgangspunkt

In den vorherigen Abschnitten wurde beschrieben, wie eine <xref:System.Windows.Freezable> indirekt auf eine abzielen, indem mit einem <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> begonnen und eine Eigenschaften Kette zu einer <xref:System.Windows.Freezable> untergeordneten Eigenschaft erstellt wird. Sie können auch eine <xref:System.Windows.Freezable> als Ausgangspunkt verwenden und indirekt eine ihrer <xref:System.Windows.Freezable> untergeordneten Eigenschaften als Ziel verwenden. Eine zusätzliche Einschränkung gilt, wenn ein <xref:System.Windows.Freezable> als Ausgangspunkt für die indirekte Zielgruppe verwendet wird: die Start <xref:System.Windows.Freezable> und alle <xref:System.Windows.Freezable> dazwischen und die indirekt Ziel Eigenschaft dürfen nicht eingefroren werden.

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Interaktives Steuern eines Storyboards in XAML

Wenn Sie ein Storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]starten möchten, verwenden Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard> Triggeraktion. <xref:System.Windows.Media.Animation.BeginStoryboard> verteilt die Animationen an die Objekte und Eigenschaften, die Sie animieren, und startet das Storyboard. (Ausführliche Informationen zu diesem Prozess finden Sie unter [Übersicht über das Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).) Wenn Sie dem <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen geben, indem Sie dessen <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>-Eigenschaft angeben, legen Sie ihn als steuerbares Storyboard fest. Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde. Die folgende Liste enthält Aktionen des steuerbaren Storyboards, die Sie mit Ereignistriggern zum Steuern eines Storyboards verwenden.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: hält das Storyboard an.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: nimmt ein angehaltene Storyboard wieder auf.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: ändert die Geschwindigkeit des Storyboards.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: verschiebt ein Storyboard auf das Ende seines Füllzeitraums, wenn es über eines verfügt.

- <xref:System.Windows.Media.Animation.StopStoryboard>: hält das Storyboard an.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: entfernt das Storyboard.

Im folgenden Beispiel werden Aktionen des steuerbaren Storyboards zum interaktiven Steuern eines Storyboards verwendet.

[!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]

<a name="controllable_storyboards_procedural"></a>

## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Interaktives Steuern eines Storyboards mithilfe von Code

In den vorherigen Beispielen wurde gezeigt, wie mithilfe von Triggeraktionen animiert wird. Im Code können Sie auch ein Storyboard mithilfe interaktiver Methoden der <xref:System.Windows.Media.Animation.Storyboard>-Klasse steuern. Damit eine <xref:System.Windows.Media.Animation.Storyboard> interaktiv im Code erstellt werden kann, müssen Sie die entsprechende Überladung der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode des Storyboards verwenden und `true` angeben, um Sie steuerbar zu machen. Weitere Informationen finden Sie unter <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>.

Die folgende Liste zeigt die Methoden, die verwendet werden können, um eine <xref:System.Windows.Media.Animation.Storyboard> zu bearbeiten, nachdem Sie gestartet wurde:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

Der Vorteil der Verwendung dieser Methoden besteht darin, dass Sie keine <xref:System.Windows.Trigger>-oder <xref:System.Windows.TriggerAction> Objekte erstellen müssen. Sie benötigen lediglich einen Verweis auf das steuerbare <xref:System.Windows.Media.Animation.Storyboard>, das Sie bearbeiten möchten.

> [!NOTE]
> Alle interaktiven Aktionen, die für eine <xref:System.Windows.Media.Animation.Clock>ausgeführt werden, und damit auch auf einem <xref:System.Windows.Media.Animation.Storyboard> erfolgen, werden beim nächsten Tick der Zeit Steuerungs-Engine ausgeführt, die kurz vor dem nächsten Rendervorgang erfolgt. Wenn Sie z. b. die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>-Methode verwenden, um zu einem anderen Punkt in einer Animation zu springen, ändert sich der Eigenschafts Wert nicht sofort, stattdessen ändert sich der Wert beim nächsten Tick der Zeit Steuerungs-Engine.

Im folgenden Beispiel wird gezeigt, wie Animationen mithilfe der interaktiven Methoden der <xref:System.Windows.Media.Animation.Storyboard>-Klasse angewendet und gesteuert werden.

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>Animieren in einem Stil

Sie können <xref:System.Windows.Media.Animation.Storyboard>-Objekte verwenden, um Animationen in einer <xref:System.Windows.Style>zu definieren. Die Animation mit einem <xref:System.Windows.Media.Animation.Storyboard> in einem <xref:System.Windows.Style> ähnelt der Verwendung einer <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle, mit den folgenden drei Ausnahmen:

- Sie geben keine <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>an. der <xref:System.Windows.Media.Animation.Storyboard> ist für das Element, auf das die <xref:System.Windows.Style> angewendet wird, immer als Ziel. Wenn Sie <xref:System.Windows.Freezable> Objekte als Ziel verwenden möchten, müssen Sie indirekte Zielgruppen verwenden. Weitere Informationen zur indirekten Ziel Ausrichtung finden Sie im Abschnitt [indirekte Zielvorgabe](#pathsyntaxforchangeable) .

- Sie können keine <xref:System.Windows.EventTrigger.SourceName%2A> für eine <xref:System.Windows.EventTrigger> oder eine <xref:System.Windows.Trigger>angeben.

- Sie können keine dynamischen Ressourcen Verweise oder Daten Bindungs Ausdrücke verwenden, um <xref:System.Windows.Media.Animation.Storyboard>-oder Animations Eigenschaftswerte festzulegen. Das liegt daran, dass alles innerhalb einer <xref:System.Windows.Style> Thread sicher sein muss, und das Zeit Steuerungssystem muss <xref:System.Windows.Media.Animation.Storyboard> Objekte <xref:System.Windows.Freezable.Freeze%2A>, um Sie Thread sicher zu machen. Eine <xref:System.Windows.Media.Animation.Storyboard> kann nicht eingefroren werden, wenn Sie oder ihre untergeordneten Zeitachsen dynamische Ressourcen Verweise oder Daten Bindungs Ausdrücke enthalten. Weitere Informationen zum Einfrieren und anderen <xref:System.Windows.Freezable>-Features finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie keine Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard>-oder Animations Ereignisse deklarieren.

Ein Beispiel, das zeigt, wie ein Storyboard in einem Stil definiert wird, finden Sie unter [Animieren in einem Stil](how-to-animate-in-a-style.md) Beispiel.

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>Animieren in einer ControlTemplate

Sie können <xref:System.Windows.Media.Animation.Storyboard>-Objekte verwenden, um Animationen in einer <xref:System.Windows.Controls.ControlTemplate>zu definieren. Die Animation mit einem <xref:System.Windows.Media.Animation.Storyboard> in einem <xref:System.Windows.Controls.ControlTemplate> ähnelt der Verwendung einer <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle, mit den folgenden zwei Ausnahmen:

- Der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> darf nur auf untergeordnete Objekte des <xref:System.Windows.Controls.ControlTemplate>verweisen. Wenn <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> nicht angegeben ist, zielt die Animation auf das Element ab, auf das die <xref:System.Windows.Controls.ControlTemplate> angewendet wird.

- Der <xref:System.Windows.EventTrigger.SourceName%2A> für eine <xref:System.Windows.EventTrigger> oder eine <xref:System.Windows.Trigger> darf nur auf untergeordnete Objekte der <xref:System.Windows.Controls.ControlTemplate>verweisen.

- Sie können keine dynamischen Ressourcen Verweise oder Daten Bindungs Ausdrücke verwenden, um <xref:System.Windows.Media.Animation.Storyboard>-oder Animations Eigenschaftswerte festzulegen. Das liegt daran, dass alles innerhalb einer <xref:System.Windows.Controls.ControlTemplate> Thread sicher sein muss, und das Zeit Steuerungssystem muss <xref:System.Windows.Media.Animation.Storyboard> Objekte <xref:System.Windows.Freezable.Freeze%2A>, um Sie Thread sicher zu machen. Eine <xref:System.Windows.Media.Animation.Storyboard> kann nicht eingefroren werden, wenn Sie oder ihre untergeordneten Zeitachsen dynamische Ressourcen Verweise oder Daten Bindungs Ausdrücke enthalten. Weitere Informationen zum Einfrieren und anderen <xref:System.Windows.Freezable>-Features finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie keine Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard>-oder Animations Ereignisse deklarieren.

Ein Beispiel, das zeigt, wie Sie ein Storyboard in einem <xref:System.Windows.Controls.ControlTemplate>definieren, finden Sie im Beispiel [Animieren in einer ControlTemplate](how-to-animate-in-a-controltemplate.md) .

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>Animieren, wenn sich ein Eigenschaftswert ändert

In Stilen und Steuerelementvorlagen können Sie mit Triggerobjekten ein Storyboard starten, wenn sich eine Eigenschaft ändert. Beispiele hierzu finden Sie unter Auslösung einer [Animation, wenn sich ein Eigenschafts Wert ändert](how-to-trigger-an-animation-when-a-property-value-changes.md) und [in einer ControlTemplate animiert](how-to-animate-in-a-controltemplate.md)wird.

Von Eigenschaften <xref:System.Windows.Trigger> Objekten angewendete Animationen verhalten sich komplexer als <xref:System.Windows.EventTrigger> Animationen oder Animationen, die mit <xref:System.Windows.Media.Animation.Storyboard> Methoden gestartet wurden.  Sie "Handoff" mit Animationen, die von anderen <xref:System.Windows.Trigger> Objekten definiert werden, verfassen aber mit <xref:System.Windows.EventTrigger> und Methoden ausgelösten Animationen.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
