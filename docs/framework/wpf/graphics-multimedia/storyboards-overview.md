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
ms.openlocfilehash: 4d5a5ee3f1fcbd09fad9e25773d0e508209e1492
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855841"
---
# <a name="storyboards-overview"></a>Übersicht über Storyboards

In diesem Thema wird gezeigt, <xref:System.Windows.Media.Animation.Storyboard> wie-Objekte zum organisieren und Anwenden von Animationen verwendet werden. Es wird beschrieben, wie Sie <xref:System.Windows.Media.Animation.Storyboard> -Objekte interaktiv bearbeiten und die indirekte Eigenschafts Ziel Syntax beschreiben.

## <a name="prerequisites"></a>Erforderliche Komponenten

Als Voraussetzung für dieses Thema sollten Sie mit den unterschiedlichen Animationstypen und ihren grundlegenden Funktionen vertraut sein. Eine Einführung zu Animationen finden Sie unter [Übersicht über Animationen](animation-overview.md). Sie sollten auch wissen, wie angefügte Eigenschaften verwendet werden. Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>Was ist ein Storyboard?

Animationen sind nicht der einzige nützliche Zeitachsentyp. Andere Zeitachsenklassen werden bereitgestellt,um Ihnen beim Organisieren von Sätzen von Zeitachsen zu helfen und Zeitachsen auf Eigenschaften anzuwenden. Container Zeitachsen werden von der <xref:System.Windows.Media.Animation.TimelineGroup> -Klasse abgeleitet und enthalten <xref:System.Windows.Media.Animation.ParallelTimeline> und. <xref:System.Windows.Media.Animation.Storyboard>

Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein Typ von Container Zeitachse, der Ziel Informationen für die in ihm enthaltenen Zeitachsen bereitstellt. Ein Storyboard kann jeden beliebigen Typ <xref:System.Windows.Media.Animation.Timeline>enthalten, einschließlich anderer containertimelines und Animationen. <xref:System.Windows.Media.Animation.Storyboard>Objekte ermöglichen es Ihnen, Zeitachsen zu kombinieren, die eine Vielzahl von Objekten und Eigenschaften in einer einzelnen Zeitachsen Struktur beeinflussen, sodass Sie das komplexe Verhalten der zeitlichen Steuerung leicht organisieren und steuern können. Nehmen wir beispielsweise an, Sie wünschen eine Schaltfläche, die die folgenden drei Aktionen ausführt.

- Vergrößern und Ändern der Farbe, wenn der Benutzer die Schaltfläche auswählt.

- Verkleinern und dann wieder die ursprüngliche Größe annehmen, wenn auf sie geklickt wird.

- Verkleinern und zu 50 % Deckkraft ausgeblendet werden, wenn sie deaktiviert wird.

In diesem Fall sind mehrere Sätze von Animationen vorhanden, die auf das gleiche Objekt angewendet werden und die Sie abhängig vom Zustand der Schaltfläche zu unterschiedlichen Zeitpunkten wiedergeben möchten. <xref:System.Windows.Media.Animation.Storyboard>mit-Objekten können Sie Animationen organisieren und in Gruppen auf ein oder mehrere Objekte anwenden.

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>Wo können Sie ein Storyboard verwenden?

Ein <xref:System.Windows.Media.Animation.Storyboard> kann verwendet werden, um Abhängigkeits Eigenschaften von Animations baren Klassen zu animieren (Weitere Informationen dazu, was eine Klasse animabel macht, finden Sie unter [Übersicht über Animationen](animation-overview.md)). Da das Storyboarding jedoch eine Funktion auf Frameworkebene ist, muss das-Objekt <xref:System.Windows.NameScope> zu einem <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>einem gehören.

Beispielsweise können Sie eine <xref:System.Windows.Media.Animation.Storyboard> für folgende Aufgaben verwenden:

- Animieren eines <xref:System.Windows.Media.SolidColorBrush> (nicht-Framework-Elements), das den Hintergrund einer Schaltfläche zeichnet (ein <xref:System.Windows.FrameworkElement>Typ von),

- Animieren Sie <xref:System.Windows.Media.SolidColorBrush> ein (nicht-Framework-Element), das die Füllung <xref:System.Windows.Media.GeometryDrawing> eines (nicht-Framework- <xref:System.Windows.Controls.Image> Elements) zeichnet,<xref:System.Windows.FrameworkElement>das mithilfe von () angezeigt wird.

- Animieren Sie in Code einen <xref:System.Windows.Media.SolidColorBrush> , der von einer Klasse deklariert wird, <xref:System.Windows.FrameworkElement>die auch einen <xref:System.Windows.Media.SolidColorBrush> enthält, wenn der seinen <xref:System.Windows.FrameworkElement>Namen mit dem registriert hat.

Sie können jedoch <xref:System.Windows.Media.Animation.Storyboard> keinen verwenden, um einen <xref:System.Windows.Media.SolidColorBrush> zu animieren, der seinen Namen nicht mit <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>registriert hat oder nicht zum Festlegen einer Eigenschaft von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>verwendet wurde.

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>Anwenden von Animationen mit einem Storyboard

Um einen <xref:System.Windows.Media.Animation.Storyboard> zum organisieren und anwenden <xref:System.Windows.Media.Animation.Storyboard>von Animationen zu verwenden, fügen Sie die Animationen als untergeordnete Zeitachsen von hinzu. Die <xref:System.Windows.Media.Animation.Storyboard> -Klasse stellt <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> angefügten Eigenschaften und bereit. Sie können diese Eigenschaften für eine Animation einstellen, um deren Zielobjekt und Eigenschaft festzulegen.

Wenn Sie Animationen auf Ihre Ziele anwenden möchten, beginnen <xref:System.Windows.Media.Animation.Storyboard> Sie mit der Verwendung einer Triggeraktion oder einer Methode. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]verwenden Sie ein <xref:System.Windows.Media.Animation.BeginStoryboard> -Objekt mit <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>oder <xref:System.Windows.DataTrigger>. Im Code können Sie auch die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode verwenden.

In der folgenden Tabelle werden die verschiedenen Orte angezeigt <xref:System.Windows.Media.Animation.Storyboard> , an denen die einzelnen BEGIN-Techniken unterstützt werden: pro Instanz, Stil, Steuerelement Vorlage und Daten Vorlage. „Pro Instanz“ bezieht sich auf das Verfahren, eine Animation oder ein Storyboard direkt auf Instanzen eines Objekts und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage anzuwenden.

|Storyboard wird gestartet mit...|Pro Instanz|Stil|Steuerelementvorlage|Datenvorlage|Beispiel|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard>und ein<xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>und eine Eigenschaft<xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>und a<xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[Vorgehensweise: Beim Ändern von Daten eine Animation auslöst](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)|

Im <xref:System.Windows.Media.Animation.Storyboard> folgenden Beispiel <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Media.SolidColorBrush> wird ein <xref:System.Windows.Media.SolidColorBrush.Color%2A> -Elementverwendet,umdieeines-Elementszuanimieren,unddas-Elementeines-Elements,daszumZeichnen<xref:System.Windows.Shapes.Rectangle>

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

In den folgenden Abschnitten werden <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften und ausführlicher beschrieben.

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Frameworkelemente, Frameworkinhaltselemente und Freezable-Objekte

Im vorherigen Abschnitt wurde erwähnt, dass eine Animation den Namen des Ziels und die zu animierende Eigenschaft kennen muss, um ihr Ziel zu finden. Die Angabe der zu animierenden Eigenschaft erfolgt direkt: <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> legen Sie einfach den Namen der zu animierenden Eigenschaft fest.  Sie geben den Namen des Objekts an, dessen Eigenschaft Sie animieren möchten, indem Sie <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> die-Eigenschaft für die Animation festlegen.

Damit die <xref:System.Windows.Setter.TargetName%2A> -Eigenschaft funktioniert, muss das Zielobjekt einen Namen haben. Das Zuweisen eines Namens zu <xref:System.Windows.FrameworkElement> einem oder <xref:System.Windows.FrameworkContentElement> einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in unterscheidet sich vom Zuweisen eines namens <xref:System.Windows.Freezable> zu einem-Objekt.

Frameworkelemente sind die Klassen, die von <xref:System.Windows.FrameworkElement> der-Klasse erben. Beispiele für Frameworkelemente <xref:System.Windows.Window>sind <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>, und <xref:System.Windows.Shapes.Rectangle>. Im Wesentlichen sind alle Fenster, Panels und Steuerelemente Elemente. Frameworkinhaltselemente sind die Klassen, die <xref:System.Windows.FrameworkContentElement> von der-Klasse erben. Beispiele für Frameworkinhaltselemente <xref:System.Windows.Documents.Paragraph>sind <xref:System.Windows.Documents.FlowDocument> und. Wenn Sie nicht sicher sind, ob ein Typ ein Frameworkelement oder ein Frameworkinhaltselement ist, überprüfen Sie, ob es über eine Name-Eigenschaft verfügt. Wenn dies der Fall ist, handelt es sich aller Wahrscheinlichkeit nach um ein Frameworkelement oder ein Frameworkinhaltselement. Um sicherzugehen, überprüfen Sie den Vererbungshierarchie-Abschnitt seiner Typ-Seite.

Um die Zielgruppen Steuerung für ein FrameworkElement oder ein Framework- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Inhalts Element in zu <xref:System.Windows.FrameworkElement.Name%2A> aktivieren, legen Sie dessen-Eigenschaft fest. Im Code müssen Sie auch die <xref:System.Windows.NameScope.RegisterName%2A> -Methode verwenden, um den Namen des Elements mit dem Element zu registrieren, für das Sie eine <xref:System.Windows.NameScope>erstellt haben.

Im folgenden Beispiel, das aus dem vorherigen Beispiel entnommen wurde, wird `MyRectangle` der <xref:System.Windows.Shapes.Rectangle>Name a, dem <xref:System.Windows.FrameworkElement>Typ, zugewiesen.

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

Wenn der Name vergeben wurde, können Sie eine Eigenschaft des Elements animieren.

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable>Typen sind die Klassen, die von der <xref:System.Windows.Freezable> -Klasse erben. Beispiele für <xref:System.Windows.Freezable> sind <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>und .<xref:System.Windows.Media.GradientStop>

Um die Zielvorgabe <xref:System.Windows.Freezable> eines durch eine Animation in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]zu aktivieren, verwenden Sie die [x:Name-Direktive](../../xaml-services/x-name-directive.md) , um ihm einen Namen zuzuweisen. Im Code verwenden Sie die <xref:System.Windows.NameScope.RegisterName%2A> -Methode, um den Namen mit dem Element zu registrieren, für das Sie eine <xref:System.Windows.NameScope>erstellt haben.

Im folgenden Beispiel wird einem- <xref:System.Windows.Freezable> Objekt ein Name zugewiesen.

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

Das Objekt kann dann animiert werden.

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard>-Objekte verwenden namens Bereiche zum Auflösen <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> der-Eigenschaft. Weitere Informationen über WPF-Namescopes finden Sie unter [WPF-XAML-Namescopes](../advanced/wpf-xaml-namescopes.md). Wenn die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> -Eigenschaft ausgelassen wird, zielt die Animation auf das Element ab, für das Sie definiert ist, oder im Fall von Stilen das formatierte Element.

Manchmal kann ein Name keinem- <xref:System.Windows.Freezable> Objekt zugewiesen werden. Wenn beispielsweise eine <xref:System.Windows.Freezable> als Ressource deklariert oder verwendet wird, um einen Eigenschafts Wert in einem Stil festzulegen, kann Ihr kein Name zugewiesen werden. Da es keinen Namen hat, kann es zwar kein direktes, aber ein indirektes Ziel sein. In den folgenden Abschnitten wird beschrieben, wie indirekte Ziele verwendet werden.

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>Indirektes Ziel

Es kann vorkommen, <xref:System.Windows.Freezable> dass ein nicht direkt auf eine Animation ausgerichtet werden kann, z <xref:System.Windows.Freezable> . b. wenn der als Ressource deklariert wird oder zum Festlegen eines Eigenschafts Werts in einem Stil verwendet wird. In diesen Fällen können Sie das <xref:System.Windows.Freezable> Objekt trotzdem animieren, obwohl Sie es nicht direkt ausrichten können. Anstatt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> -Eigenschaft mit dem Namen <xref:System.Windows.Freezable>des festzulegen, benennen Sie Sie mit dem Namen des Elements, zu dem <xref:System.Windows.Freezable> das-Element gehört. Zum Beispiel gehört ein <xref:System.Windows.Media.SolidColorBrush> , mit dem der <xref:System.Windows.Shapes.Shape.Fill%2A> eines Rechteck Elements festgelegt wird, zu diesem Rechteck. Wenn Sie den Pinsel animieren möchten, legen Sie die- <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> Animation mit einer Kette von Eigenschaften fest, die bei der-Eigenschaft des Framework-Elements oder des <xref:System.Windows.Freezable> Framework-Inhalts Elements beginnt, das verwendet <xref:System.Windows.Freezable> wurde, um die zu animierende Eigenschaft festzulegen und zu beenden.

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

Beachten Sie Folgendes: Wenn <xref:System.Windows.Freezable> der eingefroren ist, wird ein Klon erstellt, und der Klon wird animiert. Wenn dies geschieht, wird die-Eigenschaft <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> des ursprünglichen-Objekts `false`weiterhin zurückgegeben, da das ursprüngliche-Objekt nicht tatsächlich animiert ist. Weitere Informationen zum Klonen finden Sie unter Übersicht über frei wählbare [Objekte](../advanced/freezable-objects-overview.md).

Beachten Sie außerdem, dass nicht vorhandene Objekte Ziel sein können, wenn indirekte Eigenschaftenziele verwendet werden. Beispielsweise können Sie davon ausgehen, dass <xref:System.Windows.Controls.Control.Background%2A> der einer bestimmten Schaltfläche mit einem <xref:System.Windows.Media.SolidColorBrush> festgelegt wurde, und versuchen, seine Farbe zu animieren, <xref:System.Windows.Media.LinearGradientBrush> wenn tatsächlich ein verwendet wurde, um den Hintergrund der Schaltfläche festzulegen. In diesen Fällen wird keine Ausnahme ausgelöst. die Animation kann nicht sichtbar sein, da <xref:System.Windows.Media.LinearGradientBrush> nicht auf Änderungen an der <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft reagiert.

In den folgenden Abschnitten wird die Syntax für indirekte Eigenschaftenziele ausführlicher erklärt.

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Verwenden einer Eigenschaft eines Freezable-Objekts in XAML als indirektes Ziel

Verwenden Sie die folgende Syntax, um eine Eigenschaft [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]eines frei wählbaren in als Ziel zu verwenden.

| |
|-|
|*ElementPropertyName* `.` *FreezablePropertyName*|

Where

- *ElementPropertyName* ist die Eigenschaft des <xref:System.Windows.FrameworkElement> <xref:System.Windows.Freezable> -Objekts, das verwendet wird, um festzulegen.

- " *Freizablepropertyname* " ist die- <xref:System.Windows.Freezable> Eigenschaft des zu animierenden-Objekts.

Der folgende Code zeigt, wie Sie den <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush> eines animieren, der verwendet wird <xref:System.Windows.Shapes.Shape.Fill%2A> , um den eines Rechteck Elements festzulegen.

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden.

Um ein in einer Auflistung enthaltenes Freezable-Objekt als Ziel zu verwenden, geben Sie die folgende Pfadsyntax an.

| |
|-|
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|

Dabei ist *collectionindex* der Index des Objekts in dessen Array oder Auflistung.

Angenommen, ein Rechteck hat eine <xref:System.Windows.Media.TransformGroup> Ressource, die auf seine <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft angewendet wird, und Sie möchten eine der darin enthaltenen Transformationen animieren.

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

Der folgende Code zeigt, wie Sie die <xref:System.Windows.Media.RotateTransform.Angle%2A> -Eigenschaft <xref:System.Windows.Media.RotateTransform> der im vorherigen Beispiel animieren.

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Verwenden einer Eigenschaft eines Freezable-Objekts im Code als indirektes Ziel

Im Code erstellen Sie ein <xref:System.Windows.PropertyPath> -Objekt. Wenn Sie das <xref:System.Windows.PropertyPath>erstellen, geben Sie einen <xref:System.Windows.PropertyPath.Path%2A> und <xref:System.Windows.PropertyPath.PathParameters%2A>einen an.

Zum Erstellen <xref:System.Windows.PropertyPath.PathParameters%2A>von erstellen Sie ein Array vom Typ <xref:System.Windows.DependencyProperty> , das eine Liste von Bezeichnerfeldern für die Abhängigkeits Eigenschaft enthält. Das erste Bezeichnerfeld ist für die-Eigenschaft <xref:System.Windows.FrameworkElement> des <xref:System.Windows.FrameworkContentElement> oder, <xref:System.Windows.Freezable> das verwendet wird, um festzulegen. Das nächste Bezeichnerfeld stellt die-Eigenschaft <xref:System.Windows.Freezable> der als Ziel dar. Stellen Sie sich dies als eine Kette von Eigenschaften vor, <xref:System.Windows.Freezable> die den <xref:System.Windows.FrameworkElement> mit dem-Objekt verbindet.

Im folgenden finden Sie ein Beispiel für eine Abhängigkeits Eigenschaften Kette, <xref:System.Windows.Media.SolidColorBrush.Color%2A> die auf <xref:System.Windows.Media.SolidColorBrush> den eines-Objekts <xref:System.Windows.Shapes.Shape.Fill%2A> abzielt, das verwendet wird, um den eines Rechteck Elements festzulegen.

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

Sie müssen auch ein <xref:System.Windows.PropertyPath.Path%2A>angeben. Eine <xref:System.Windows.PropertyPath.Path%2A> ist eine <xref:System.String> , die <xref:System.Windows.PropertyPath.Path%2A> angibt, wie Ihre <xref:System.Windows.PropertyPath.PathParameters%2A>interpretiert werden soll. Die folgende Syntax wird verwendet.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|

Where

- "Besitzer *propertyarrayindex* " ist der Index <xref:System.Windows.DependencyProperty> des Arrays, das <xref:System.Windows.FrameworkElement> den Bezeichner der Eigenschaft des Objekts enthält <xref:System.Windows.Freezable> , mit dem der festgelegt wird, und

- " *Freizablepropertyarrayindex* " ist der Index <xref:System.Windows.DependencyProperty> des Arrays, das den Bezeichner der Eigenschaft enthält, die Ziel ist.

Im folgenden Beispiel wird das <xref:System.Windows.PropertyPath.Path%2A> -Beispiel gezeigt, <xref:System.Windows.PropertyPath.PathParameters%2A> das die enthält, die im vorherigen Beispiel definiert ist.

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

Im folgenden Beispiel <xref:System.Windows.Media.SolidColorBrush> wird der Code in den vorherigen Beispielen kombiniert, um <xref:System.Windows.Media.SolidColorBrush.Color%2A> die eines-Elements zu animieren <xref:System.Windows.Shapes.Shape.Fill%2A> , mit dem der eines Rechteck Elements festgelegt wird.

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

Manchmal müssen Sie ein in einer Auflistung oder einem Array enthaltenes Freezable-Objekt als Ziel verwenden. Angenommen, ein Rechteck hat eine <xref:System.Windows.Media.TransformGroup> Ressource, die auf seine <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft angewendet wird, und Sie möchten eine der darin enthaltenen Transformationen animieren.

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

Verwenden Sie die <xref:System.Windows.Freezable> folgende Pfad Syntax, um ein Ziel in einer Auflistung als Ziel zu verwenden.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|

Dabei ist *collectionindex* der Index des Objekts in dessen Array oder Auflistung.

Wenn Sie die <xref:System.Windows.Media.RotateTransform.Angle%2A> -Eigenschaft <xref:System.Windows.Media.RotateTransform>des-Objekts, <xref:System.Windows.Media.TransformGroup>die zweite Transformation in, als Ziel verwenden möchten <xref:System.Windows.PropertyPath.Path%2A> , <xref:System.Windows.PropertyPath.PathParameters%2A>verwenden Sie Folgendes und.

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

Das folgende Beispiel zeigt den gesamten Code für die Animation <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform> eines in einer <xref:System.Windows.Media.TransformGroup>.

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Indirektes Ziel mit einem Freezable-Objekt als Ausgangspunkt

In <xref:System.Windows.Freezable> den vorherigen Abschnitten wurde beschrieben, wie Sie indirekt auf abzielen, indem Sie <xref:System.Windows.FrameworkElement> mit oder <xref:System.Windows.FrameworkContentElement> beginnen und eine Eigenschaften <xref:System.Windows.Freezable> Kette zu einer untergeordneten Eigenschaft erstellen. Sie können auch eine <xref:System.Windows.Freezable> als Ausgangspunkt verwenden und indirekt eine Ihrer <xref:System.Windows.Freezable> untergeordneten Eigenschaften als Ziel verwenden. Eine zusätzliche Einschränkung gilt, wenn ein <xref:System.Windows.Freezable> als Ausgangspunkt für die indirekte Zielgruppe verwendet wird <xref:System.Windows.Freezable> : der <xref:System.Windows.Freezable> Start und jede zwischen dem und der indirekt ausgerichteten untergeordneten Eigenschaft dürfen nicht eingefroren werden.

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Interaktives Steuern eines Storyboards in XAML

Zum Starten eines Storyboards in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]verwenden Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard> Triggeraktion. <xref:System.Windows.Media.Animation.BeginStoryboard>verteilt die Animationen an die Objekte und Eigenschaften, die Sie animieren, und startet das Storyboard. (Ausführliche Informationen zu diesem Prozess finden Sie unter [Übersicht über das Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).) Wenn Sie einen Namen <xref:System.Windows.Media.Animation.BeginStoryboard> angeben, indem Sie die <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> zugehörige-Eigenschaft angeben, legen Sie ihn als steuerbares Storyboard fest. Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde. Die folgende Liste enthält Aktionen des steuerbaren Storyboards, die Sie mit Ereignistriggern zum Steuern eines Storyboards verwenden.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltene Storyboard fort.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Geschwindigkeit des Storyboards.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Verschiebt ein Storyboard auf das Ende seines Füllzeitraums, wenn es über eines verfügt.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Beendet das Storyboard.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard.

Im folgenden Beispiel werden Aktionen des steuerbaren Storyboards zum interaktiven Steuern eines Storyboards verwendet.

[!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]

<a name="controllable_storyboards_procedural"></a>

## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Interaktives Steuern eines Storyboards mithilfe von Code

In den vorherigen Beispielen wurde gezeigt, wie mithilfe von Triggeraktionen animiert wird. Im Code können Sie auch ein Storyboard mithilfe interaktiver Methoden der <xref:System.Windows.Media.Animation.Storyboard> -Klasse steuern. Damit eine <xref:System.Windows.Media.Animation.Storyboard> interaktiv im Code erstellt werden kann, müssen Sie die entsprechende Überladung der- <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode des Storyboards verwenden und `true` angeben, um Sie steuerbar zu machen. Weitere Informationen <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> finden Sie auf der Seite.

Die folgende Liste zeigt die Methoden, die verwendet werden können, um <xref:System.Windows.Media.Animation.Storyboard> eine nach dem Start zu bearbeiten:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

Der Vorteil der Verwendung dieser Methoden besteht darin, dass Sie keine- <xref:System.Windows.Trigger> oder <xref:System.Windows.TriggerAction> -Objekte erstellen müssen. Sie benötigen lediglich einen Verweis <xref:System.Windows.Media.Animation.Storyboard> auf die steuerbare, die Sie bearbeiten möchten.

> [!NOTE]
> Alle interaktiven Aktionen, die auf <xref:System.Windows.Media.Animation.Clock>einem ausgeführt werden, und daher <xref:System.Windows.Media.Animation.Storyboard> auch auf einem werden auf dem nächsten Tick der zeitlichen Steuerung durchgeführt, der kurz vor dem nächsten Rendervorgang auftritt. Wenn Sie z. b. die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> -Methode verwenden, um zu einem anderen Punkt in einer Animation zu springen, ändert sich der Eigenschafts Wert nicht sofort. stattdessen ändert sich der Wert beim nächsten Tick der zeitlichen Steuerung.

Im folgenden Beispiel wird gezeigt, wie Animationen mithilfe der interaktiven Methoden der <xref:System.Windows.Media.Animation.Storyboard> -Klasse angewendet und gesteuert werden.

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>Animieren in einem Stil

Sie können- <xref:System.Windows.Media.Animation.Storyboard> Objekte verwenden, um Animationen in <xref:System.Windows.Style>einem zu definieren. Die Animation mit einem <xref:System.Windows.Media.Animation.Storyboard> in einem <xref:System.Windows.Style> ähnelt der Verwendung eines <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle, mit den folgenden drei Ausnahmen:

- Sie geben <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>keinen an. der <xref:System.Windows.Media.Animation.Storyboard> verwendet immer das Element, auf das <xref:System.Windows.Style> das angewendet wird. Zum Ziel <xref:System.Windows.Freezable> von Objekten müssen Sie indirekte Zielgruppen verwenden. Weitere Informationen zur indirekten Ziel Ausrichtung finden Sie im Abschnitt [indirekte Zielvorgabe](#pathsyntaxforchangeable) .

- Sie können keine <xref:System.Windows.EventTrigger.SourceName%2A> für einen <xref:System.Windows.EventTrigger> oder einen <xref:System.Windows.Trigger>angeben.

- Sie können keine dynamischen Ressourcen Verweise oder Daten Bindungs Ausdrücke verwenden, <xref:System.Windows.Media.Animation.Storyboard> um Eigenschaftswerte festzulegen oder zu Animation. Das liegt daran, dass alles <xref:System.Windows.Style> in einem Thread sicher sein muss, und das Zeit Steuerungs <xref:System.Windows.Freezable.Freeze%2A> System muss <xref:System.Windows.Media.Animation.Storyboard> Objekte aufweisen, um Sie Thread sicher zu machen. Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht eingefroren werden, wenn es oder seine untergeordneten Zeitachsen dynamische Ressourcen Verweise oder Daten Bindungs Ausdrücke enthalten. Weitere Informationen zum Einfrieren und anderen <xref:System.Windows.Freezable> Features finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie keine Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard> -oder-Animations Ereignisse deklarieren.

Ein Beispiel, das zeigt, wie ein Storyboard in einem Stil definiert wird, finden Sie unter [Animieren in einem Stil](how-to-animate-in-a-style.md) Beispiel.

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>Animieren in einer ControlTemplate

Sie können- <xref:System.Windows.Media.Animation.Storyboard> Objekte verwenden, um Animationen in <xref:System.Windows.Controls.ControlTemplate>einem zu definieren. Die Animation mit einem <xref:System.Windows.Media.Animation.Storyboard> in einem <xref:System.Windows.Controls.ControlTemplate> ähnelt der Verwendung eines <xref:System.Windows.Media.Animation.Storyboard> an anderer Stelle, mit den folgenden zwei Ausnahmen:

- Der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> darf nur auf untergeordnete Objekte <xref:System.Windows.Controls.ControlTemplate>von verweisen. Wenn <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> nicht angegeben wird, ist die Animation das Element, auf das <xref:System.Windows.Controls.ControlTemplate> die angewendet wird.

- Der <xref:System.Windows.EventTrigger.SourceName%2A> für einen <xref:System.Windows.EventTrigger> oder eine <xref:System.Windows.Trigger> darfnuraufuntergeordnete<xref:System.Windows.Controls.ControlTemplate>Objekte von verweisen.

- Sie können keine dynamischen Ressourcen Verweise oder Daten Bindungs Ausdrücke verwenden, <xref:System.Windows.Media.Animation.Storyboard> um Eigenschaftswerte festzulegen oder zu Animation. Das liegt daran, dass alles <xref:System.Windows.Controls.ControlTemplate> in einem Thread sicher sein muss, und das Zeit Steuerungs <xref:System.Windows.Freezable.Freeze%2A> System muss <xref:System.Windows.Media.Animation.Storyboard> Objekte aufweisen, um Sie Thread sicher zu machen. Ein <xref:System.Windows.Media.Animation.Storyboard> kann nicht eingefroren werden, wenn es oder seine untergeordneten Zeitachsen dynamische Ressourcen Verweise oder Daten Bindungs Ausdrücke enthalten. Weitere Informationen zum Einfrieren und anderen <xref:System.Windows.Freezable> Features finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie keine Ereignishandler für <xref:System.Windows.Media.Animation.Storyboard> -oder-Animations Ereignisse deklarieren.

Ein Beispiel für die Definition eines Storyboards in einem <xref:System.Windows.Controls.ControlTemplate>finden Sie im Beispiel [Animieren in einer ControlTemplate](how-to-animate-in-a-controltemplate.md) .

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>Animieren, wenn sich ein Eigenschaftswert ändert

In Stilen und Steuerelementvorlagen können Sie mit Triggerobjekten ein Storyboard starten, wenn sich eine Eigenschaft ändert. Beispiele hierzu finden Sie unter Auslösung einer [Animation, wenn sich ein Eigenschafts Wert ändert](how-to-trigger-an-animation-when-a-property-value-changes.md) und [in einer ControlTemplate animiert](how-to-animate-in-a-controltemplate.md)wird.

Durch Eigenschafts <xref:System.Windows.Trigger> Objekte angewendete Animationen verhalten sich komplexer als <xref:System.Windows.EventTrigger> Animationen oder Animationen, die <xref:System.Windows.Media.Animation.Storyboard> mithilfe von Methoden gestartet wurden.  Sie "Handoff" mit Animationen, die von <xref:System.Windows.Trigger> anderen Objekten definiert werden, <xref:System.Windows.EventTrigger> verfassen jedoch mit und durch Methoden ausgelöste Animationen.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
