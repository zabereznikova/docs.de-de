---
title: Definieren von XAML-Ressourcen
description: Erfahren Sie mehr über XAML-Ressourcen in WPF für .NET Core. Informieren Sie sich über die Typen von XAML-Ressourcen und erfahren Sie, wie XAML-Ressourcen definiert werden.
author: adegeo
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: f8eaf3fd931aa6804b0b9a9c19c6bcc042678ebf
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325718"
---
# <a name="overview-of-xaml-resources"></a>Übersicht über XAML-Ressourcen

Eine Ressource ist ein Objekt, das an unterschiedlichen Stellen in Ihrer App wiederverwendet werden kann. Beispiele für Ressourcen sind Pinsel und Stile. In dieser Übersicht wird beschrieben, wie Ressourcen in XAML (Extensible Application Markup Language) verwendet werden. Sie können auch mithilfe von Code Ressourcen erstellen und auf diese zugreifen.

> [!NOTE]
> Die in diesem Artikel beschriebenen XAML-Ressourcen unterscheiden sich von *App-Ressourcen*, die in der Regel Dateien sind, die einer App hinzugefügt werden, z. B. Inhalte, Daten oder eingebettete Dateien.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>Verwenden von Ressourcen in XAML

Im folgenden Beispiel wird ein <xref:System.Windows.Media.SolidColorBrush>-Element als Ressource für das Stammelement einer Seite definiert. Anschließend verweist das Beispiel auf die Ressource und verwendet sie, um Eigenschaften mehrerer untergeordneter Elemente festzulegen, einschließlich eines <xref:System.Windows.Shapes.Ellipse>-, eines <xref:System.Windows.Controls.TextBlock>- und eines <xref:System.Windows.Controls.Button>-Elements.

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

Jedes Element auf Frameworkebene (<xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>) verfügt über eine <xref:System.Windows.FrameworkElement.Resources%2A>-Eigenschaft. Hierbei handelt es sich um einen <xref:System.Windows.ResourceDictionary>-Typ, der definierte Ressourcen enthält. Sie können Ressourcen für beliebige Elemente definieren, z. B.für ein <xref:System.Windows.Controls.Button>-Element. Ressourcen werden jedoch am häufigsten für das Stammelement definiert. In diesem Beispiel ist es eine <xref:System.Windows.Controls.Page>.

Jeder Ressource in einem Ressourcenverzeichnis muss ein eindeutiger Schlüssel zugewiesen werden. Wenn Sie Ressourcen in Markup definieren, weisen Sie den eindeutigen Schlüssel durch die [x:Key-Anweisung](../xaml-services/xkey-directive.md) zu. In der Regel ist der Schlüssel eine Zeichenfolge. Sie können jedoch den Schlüssel auch als einen anderen Objekttyp definieren, indem Sie die entsprechenden Markuperweiterungen verwenden. Nichtzeichenfolgeschlüssel für Ressourcen werden von bestimmten Funktionsbereichen in WPF verwendet, insbesondere für Stile, Komponentenressourcen und Datenformatierung.

Sie können eine definierte Ressource mit der Syntax der Ressourcenmarkuperweiterung verwenden, die den Schlüsselnamen der Ressource angibt. Verwenden Sie beispielsweise die Ressource als Wert einer Eigenschaft für ein anderes Element.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

Wenn im vorherigen Beispiel das XAML-Ladeprogramm den Wert `{StaticResource MyBrush}` für die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft für <xref:System.Windows.Controls.Button> verarbeitet, überprüft die Ressourcennachschlagelogik zuerst das Ressourcenverzeichnis auf das <xref:System.Windows.Controls.Button>-Element. Wenn <xref:System.Windows.Controls.Button> nicht über eine Definition des Ressourcenschlüssels `MyBrush` (in diesem Beispiel ist dies nicht der Fall, die Ressourcensammlung ist leer), überprüft die Nachschlagefunktion als nächstes das übergeordnete Element von <xref:System.Windows.Controls.Button>, das <xref:System.Windows.Controls.Page> ist. Wenn Sie eine Ressource für das <xref:System.Windows.Controls.Page>-Stammelement definieren, können alle Elemente in der logischen Struktur des <xref:System.Windows.Controls.Page>-Elements darauf zugreifen. Und Sie können dieselbe Ressource wiederverwenden, um den Wert einer beliebigen Eigenschaft festzulegen, die denselben Typ akzeptiert, den die Ressource darstellt. Im vorherigen Beispiel legt die gleiche `MyBrush`-Ressource zwei unterschiedliche Eigenschaften fest: den <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>-Elements und die <xref:System.Windows.Shapes.Shape.Fill%2A>-Eigenschaft eines <xref:System.Windows.Shapes.Rectangle>.

## <a name="static-and-dynamic-resources"></a>Statische und dynamische Ressourcen

Auf eine Ressource kann als statische oder dynamische Ressource verwiesen werden. Verweise werden über die [StaticResource-Markuperweiterung](../../framework/wpf/advanced/staticresource-markup-extension.md) oder die [DynamicResource-Markuperweiterung](../../framework/wpf/advanced/dynamicresource-markup-extension.md) erstellt. Eine Markuperweiterung ist eine XAML-Funktion, mit der Sie einen Objektverweis angeben können, indem die Markuperweiterung die Attributzeichenfolge verarbeitet und das Objekt an das XAML-Ladeprogramm zurückgibt. Weitere Inforationen zum Verhalten von Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF-XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

Wenn Sie eine Markuperweiterung verwenden, geben Sie in der Regel einen oder mehrere Parameter im Zeichenfolgenformat an, die von dieser speziellen Markuperweiterung verarbeitet werden. Die [StaticResource-Markuperweiterung](../../framework/wpf/advanced/staticresource-markup-extension.md) verarbeitet einen Schlüssel, indem sie nach dem Wert für diesen Schlüssel in allen verfügbaren Ressourcenverzeichnissen sucht. Die Verarbeitung erfolgt beim Laden, d. h., wenn der Ladeprozess den Eigenschaftswert zuweisen muss. Die [DynamicResource-Markuperweiterung](../../framework/wpf/advanced/dynamicresource-markup-extension.md) verarbeitet stattdessen einen Schlüssel, indem sie einen Ausdruck erstellt. Dieser Ausdruck wird nicht ausgewertet, bis die App ausgeführt wird. Zu diesem Zeitpunkt wird der Ausdruck ausgewertet und ergibt einen Wert.

Wenn Sie auf eine Ressource verweisen, sind bei der Wahl zwischen einem statischen und einem dynamischen Ressourcenverweis folgende Aspekte zu beachten:

- Wenn Sie den allgemeinen Entwurf festlegen, wie Sie die Ressourcen für Ihre Anwendung erstellen (pro Seite, in der App, in „losem“ XAML oder in einer reinen Ressourcenassembly), sollten Sie Folgendes berücksichtigen:

- Die Funktionalität der App. Ist die Aktualisierung von Ressourcen in Echtzeit Bestandteil Ihrer Anwendungsanforderungen?
- Das Suchverhalten des jeweiligen Ressourcenverweistyps.
- Jeweiliger Eigenschafts- oder Ressourcentyp sowie dessen natives Verhalten.

## <a name="static-resources"></a>Statische Ressourcen

Statische Ressourcenverweise funktionieren optimal unter folgenden Bedingungen:

- Der App-Entwurf konzentriert die meisten seiner Ressourcen in Ressourcenverzeichnissen auf Seiten- oder Anwendungsebene. Statische Ressourcenverweise werden nicht basierend auf Laufzeitverhalten wie dem erneuten Laden einer Seite erneut ausgewertet. Es kann also ein gewisser Leistungsvorteil entstehen, wenn Sie eine große Anzahl dynamischer Ressourcenverweise vermeiden, wenn diese aufgrund Ihres Ressourcen- und App-Entwurfs nicht erforderlich sind.

- Sie legen den Wert einer Eigenschaft fest, die nicht für einen <xref:System.Windows.DependencyObject> oder ein <xref:System.Windows.Freezable>-Element ist.

- Sie erstellen ein Ressourcenverzeichnis, das in eine DLL kompiliert und als ein Teil der App verpackt oder von mehreren Apps gemeinsam genutzt wird.

- Sie erstellen ein Design für ein benutzerdefiniertes Steuerelement und definieren Ressourcen, die in den Designs verwendet werden. Für diesen Fall ist das Suchverhalten der dynamischen Verweise ungeeignet. Damit das Suchverhalten vorhersagbar und eigenständig für das Design gestaltet werden kann, sind statische Ressourcenverweise vorzuziehen. Bei einem dynamischen Ressourcenverweis wird sogar ein Verweis innerhalb eines Designs erst zur Laufzeit ausgewertet. Daher besteht die Möglichkeit, dass bei der Anwendung des Designs ein Schlüssel, auf den das Design zu verweisen versucht, von einem lokalen Element neu definiert wird, und das lokale Element statt des Designs bei der Suche gefunden wird. In diesem Fall wird Ihr Design sich nicht wie erwartet verhalten.

- Ressourcen werden verwendet, um die große Anzahl von Abhängigkeitseigenschaften festzulegen. Abhängigkeitseigenschaften können auf das effektive Zwischenspeichern von Werten des Eigenschaftensystems zugreifen. Wenn Sie einer Abhängigkeitseigenschaft einen Wert bereitstellen, der zur Ladezeit ausgewertet werden kann, ist keine Neuauswertung des Ausdrucks von der Abhängigkeitseigenschaft erforderlich. Sie kann den letzten effektiven Wert zurückgeben. Mit diesem Verfahren kann ein Leistungsvorteil erzielt werden.

- Sie möchten die zugrunde liegende Ressource für alle Consumer ändern oder für jeden einzelnen Consumer separate Instanzen mit Schreibzugriff unter Verwendung der [x: Shared-Attribute](../xaml-services/xshared-attribute.md) verwalten.

### <a name="static-resource-lookup-behavior"></a>Suchverhalten von statischen Ressourcen

Im Folgenden wird der Suchvorgang beschrieben, der automatisch erfolgt, wenn von einer Eigenschaft oder einem Element auf eine statische Ressource verwiesen wird:

01. Der Suchprozess prüft den angeforderten Schlüssel im Ressourcenverzeichnis, das durch das Element definiert wird, das die Eigenschaft festlegt.

01. Der Suchprozess durchläuft anschließend die logische Struktur aufwärts zum übergeordneten Element und dessen Ressourcenverzeichnis. Dieser Vorgang wird fortgesetzt, bis das Stammelement erreicht wird.

01. App-Ressourcen werden überprüft. App-Ressourcen sind die Ressourcen im Ressourcenverzeichnis, die vom <xref:System.Windows.Application>-Objekt für Ihre WPF-Anwendung definiert werden.

Statische Ressourcenverweise innerhalb eines Ressourcenverzeichnisses müssen auf eine Ressource verweisen, die bereits vor dem Ressourcenverweis lexikalisch definiert worden ist. Vorwärtsverweise können von einem statischen Ressourcenverweis nicht aufgelöst werden. Gestalten Sie daher Ihre Ressourcenverzeichnisstruktur so, dass die Ressourcen am oder nahe dem Anfang des jeweiligen Ressourcenverzeichnisses definiert werden.

Statische Ressourcensuche kann auf Designs oder auf Systemressourcen ausgeweitet werden. Diese Suche wird aber nur aus dem Grund unterstützt, dass das XAML-Ladeprogramm die Anforderung verzögert. Die Verzögerung ist erforderlich, damit das Laufzeitdesign zum Zeitpunkt des Ladens der Seite ordnungsgemäß auf die App angewendet wird. Statische Ressourcenverweise auf Schlüssel, von denen bekannt ist, dass sie nur in Designs oder als Systemressourcen vorhanden sind, sind jedoch nicht zu empfehlen, da solche Verweise nicht erneut ausgewertet werden, wenn das Design vom Benutzer in Echtzeit geändert wird. Dynamische Ressourcenverweise sind zuverlässiger, wenn Sie Designs oder Systemressourcen abfragen. Eine Ausnahme bilden Abfragen, bei denen ein Designelement selbst andere Ressourcen abfragt. Diese Verweise sind aus den oben genannten Gründen als statische Ressourcenverweise zu definieren.

Falls statistische Verweise nicht gefunden werden, sind verschiedene Ausnahmeverhaltensmuster möglich. Falls die Ressource verzögert wurde, tritt die Ausnahme zur Laufzeit ein. Falls die Ressource nicht verzögert wurde, tritt die Ausnahme zur Ladezeit ein.

## <a name="dynamic-resources"></a>Dynamische Ressourcen

Dynamische Ressourcen funktionieren am besten, wenn Folgendes gilt:

- Der Wert der Ressource, einschließlich der Systemressourcen oder Ressourcen, die anderweitig vom Benutzer festgelegt werden können, hängt von Bedingungen ab, die erst zur Laufzeit bekannt sind. Beispielsweise können Sie Setterwerte erstellen, die sich auf Systemeigenschaften beziehen, wie sie durch <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts> oder <xref:System.Windows.SystemParameters> offengelegt werden. Diese Werte sind wirklich dynamisch, da sie letztlich von der Laufzeitumgebung des Benutzers und dem Betriebssystem stammen. Möglicherweise haben Sie außerdem Designs auf der Anwendungsebene, die sich ändern können, und deren Veränderungen auch vom Ressourcenzugriff auf der Seitenebene erfasst werden müssen.

- Sie erstellen Designstile für ein benutzerdefiniertes Steuerelement oder verweisen darauf.

- Sie beabsichtigen, den Inhalt eines <xref:System.Windows.ResourceDictionary>-Elements während der Lebensdauer einer App anzupassen.

- Sie haben eine komplizierte Ressourcenstruktur mit gegenseitigen Abhängigkeiten, die möglicherweise Vorwärtsverweise erfordert. Im Gegensatz zu statischen Ressourcenverweisen, unterstützen dynamische Ressourcenverweise Vorwärtsverweise, da die Ressource erst zur Laufzeit ausgewertet werden muss, und Vorwärtsverweise daher kein relevantes Konzept sind.

- Sie verweisen auf eine Ressource, die aus der Perspektive eines kompilieren oder Arbeitssatzes groß ist, und möglicherweise beim Laden der Seite nicht sofort verwendet wird. Statische Ressourcenverweise werden immer aus XAML geladen, wenn die Seite geladen wird. Ein dynamischer Ressourcenverweis wird jedoch erst geladen, wenn er verwendet wird.

- Sie erstellen einen Stil, bei dem Setterwerte von anderen Werten stammen könnten, die durch Designs oder andere Benutzereinstellungen beeinflusst werden.

- Sie ordnen Ressourcen Elementen zu, die in der logischen Struktur während der Lebensdauer der App neu zugeordnet werden können. Beim erneuten Zuordnen der Elemente wird möglicherweise auch der Ressourcensuchbereich neu definiert. Wenn Sie wollen, dass die Ressource für ein neu zugeordnetes Element entsprechend dem neuen Suchbereich neu ausgewertet wird, verwenden Sie immer einen dynamischen Ressourcenverweis.

### <a name="dynamic-resource-lookup-behavior"></a>Suchverhalten von dynamischen Ressourcen

Das Verhalten der Ressourcensuche für einen dynamischen Ressourcenverweis weist Parallelen zum Nachschlageverhalten in Ihrem Code auf, wenn Sie <xref:System.Windows.FrameworkElement.FindResource%2A> oder <xref:System.Windows.FrameworkElement.SetResourceReference%2A> aufrufen:

01. Die Suche prüft den angeforderten Schlüssel im Ressourcenverzeichnis, das durch das Element definiert wird, das die Eigenschaft festlegt:

    - Wenn das Element eine <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft definiert, wird <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName> des Elements auf sein Verzeichnis <xref:System.Windows.Style.Resources> geprüft.

    - Wenn das Element eine <xref:System.Windows.Controls.Control.Template%2A>-Eigenschaft definiert, wird das Verzeichnis <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> des Elements überprüft.

01. Die Suche durchläuft die logische Struktur aufwärts bis zum übergeordneten Element und dessen Ressourcenverzeichnis. Dieser Vorgang wird fortgesetzt, bis das Stammelement erreicht wird.

01. App-Ressourcen werden überprüft. App-Ressourcen sind die Ressourcen im Ressourcenverzeichnis, die vom <xref:System.Windows.Application>-Objekt für Ihre WPF-Anwendung definiert werden.

01. Das Ressourcenverzeichnis des Designs wird für das derzeit aktive Design überprüft. Falls das Design zur Laufzeit geändert wird, wird der Wert neu ausgewertet.

01. Systemressourcen werden geprüft.

Es sind verschiedene Ausnahmeverhaltensmuster möglich (sofern sie auftreten):

- Wenn eine Ressource von einem <xref:System.Windows.FrameworkElement.FindResource%2A>-Aufruf angefordert und nicht gefunden wurde, wird eine Ausnahme ausgelöst.

- Wenn eine Ressource von einem <xref:System.Windows.FrameworkElement.TryFindResource%2A>-Aufruf angefordert und nicht gefunden wurde, wird keine Ausnahme ausgelöst, und der zurückgegebene Wert ist `null`. Wenn die festzulegende Eigenschaft `null` nicht akzeptiert, ist es dennoch möglich, dass eine tiefere Ausnahme ausgelöst wird. Dies hängt von der jeweiligen Eigenschaft ab, die festgelegt wird.

- Wenn eine Ressource von einem dynamischen Ressourcenverweis in XAML angefordert und nicht gefunden wurde, hängt das Verhalten vom allgemeinen Eigenschaftensystem ab. Das allgemeine Verhalten ist so, als ob auf der Ebene, auf der die Ressource vorhanden ist, kein Vorgang zum Festlegen von Eigenschaften stattfindet. Wenn Sie z. B. versuchen, den Hintergrund eines einzelnen Schaltflächenelements mit einer Ressource festzulegen, die nicht ausgewertet werden konnte, wird als Ergebnis kein Wert festgelegt. Ein effektiver Wert kann aber dennoch von anderen Teilnehmern im Eigenschaftssystem und in der Wertrangfolge bereitgestellt werden. Beispielsweise kann der Wert für den Hintergrund von einem lokal definierten Schaltflächenstil oder vom Designstil zurückgegeben werden. Für Eigenschaften, die nicht von Designstilen definiert werden, kann nach einer fehlgeschlagenen Auswertung der Standardwert aus den Eigenschaftenmetadaten als effektiver Wert übernommen werden.

### <a name="restrictions"></a>Beschränkungen

Die Verwendung dynamischer Verweise ist mit einigen wichtigen Beschränkungen verbunden. Mindestens eine der folgenden Bedingungen muss erfüllt sein:

- Die Eigenschaft, die festgelegt wird, muss eine Eigenschaft für ein <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> sein. Diese Eigenschaft muss durch eine <xref:System.Windows.DependencyProperty> unterstützt werden.

- Der Verweis bezieht sich auf einen Wert in einem `StyleSetter`.

- Die Eigenschaft, die festgelegt wird, muss eine Eigenschaft für ein <xref:System.Windows.Freezable>-Element sein, das entweder als Wert einer <xref:System.Windows.FrameworkElement>- oder <xref:System.Windows.FrameworkContentElement>-Eigenschaft oder als <xref:System.Windows.Setter>-Wert bereitgestellt wird.

Da die festzulegende Eigenschaft eine <xref:System.Windows.DependencyProperty>- oder eine <xref:System.Windows.Freezable>-Eigenschaft sein muss, können die meisten Eigenschaftsänderungen an die Benutzeroberfläche weitergeleitet werden, da Eigenschaftsänderungen (die Werte der geänderten dynamischen Ressourcen) vom Eigenschaftensystem anerkannt werden. Die meisten Steuerelemente enthalten eine Logik, die ein anderes Layout eines Steuerelements erzwingt, wenn eine <xref:System.Windows.DependencyProperty> geändert wird, und diese Eigenschaft sich auf das Layout auswirken könnte. Allerdings ist nicht für alle Eigenschaften, die eine [DynamicResource-Markuperweiterung](../../framework/wpf/advanced/dynamicresource-markup-extension.md) als Wert aufweisen, garantiert, dass sie Echtzeitaktualisierungen in der Benutzeroberfläche bereitstellen. Diese Funktionalität kann dennoch variieren, abhängig sowohl von der Eigenschaft als auch vom Typ, der die Eigenschaft besitzt oder sogar von der logischen Struktur Ihrer App.

## <a name="styles-datatemplates-and-implicit-keys"></a>Stile, DataTemplates und implizite Schlüssel

Obwohl alle Elemente in einem <xref:System.Windows.ResourceDictionary>-Element über einen Schlüssel verfügen müssen, bedeutet das nicht, dass alle Ressourcen über einen expliziten `x:Key`verfügen müssen. Manche Objekttypen unterstützen einen impliziten Schlüssel, wenn sie als Ressourcen definiert sind, wobei der Schlüsselwert an den Wert einer anderen Eigenschaft gebunden ist. Dieser Schlüsseltyp wird als impliziter Schlüssel bezeichnet, während ein `x:Key`-Attribut ein expliziter Schlüssel ist. Sie können jegliche implizite Schlüssel durch die Angabe eines expliziten Schlüssels überschreiben.

Ein besonders wichtiges Szenario für Ressourcen ist das Definieren eines <xref:System.Windows.Style>. Tatsächlich ist ein <xref:System.Windows.Style> fast immer als ein Eintrag in einem Ressourcenverzeichnis definiert, da Stile grundsätzlich zur Wiederverwendung vorgesehen sind. Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](styles-templates-overview.md).

Mit einem impliziten Schlüssel können Stile für Steuerelemente erstellt werden, und es kann damit auf sie verwiesen werden. Die Design-Stile, die die Standarddarstellung eines Steuerelements definieren, basieren auf diesen impliziten Schlüsseln. Aus Sicht der Anforderung ist der implizite Schlüssel der <xref:System.Type> des Steuerelements selbst. Unter dem Gesichtspunkt der Definition der Ressourcen ist der implizite Schlüssel der <xref:System.Windows.Style.TargetType%2A> des Stils. Wenn Sie daher Designs für benutzerdefinierte Steuerelemente oder Stile erstellen, die mit vorhandenen Design-Stilen interagieren, müssen Sie keine [x:Key-Anweisung](../xaml-services/xkey-directive.md) für diesen <xref:System.Windows.Style> angeben. Und wenn Sie die Design-Stile verwenden möchten, müssen Sie gar keinen Stil angeben. Beispielsweise funktioniert die folgende Definition eines Stils, obwohl die <xref:System.Windows.Style>-Ressource nicht über einen Schlüssel zu verfügen scheint:

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

Dieser Stil besitzt aber tatsächlich einen Schlüssel: den impliziten Schlüssel `typeof(System.Windows.Controls.Button)`. Im Markup können Sie einen <xref:System.Windows.Style.TargetType%2A> direkt als den Typnamen angeben (optional können Sie [{x:Type...}](../xaml-services/xtype-markup-extension.md) verwenden, damit ein <xref:System.Type> zurückgegeben wird.

Durch die von WPF verwendeten Standardmechanismen für Designstile wird dieser Stil als Laufzeitstil eines <xref:System.Windows.Controls.Button>-Elements auf der Seite angewendet, auch wenn das <xref:System.Windows.Controls.Button>-Element selbst nicht versucht, seine <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft oder einen spezifischen Ressourcenverweis auf den Stil anzugeben. Ihr auf dieser Seite definierter Stil wird unter der Verwendung des selben Schlüssels in der Suchsequenz früher als der Stil des Designverzeichnisses gefunden. Sie könnten `<Button>Hello</Button>` an einer beliebigen Stelle auf der Seite anlegen, und der mit <xref:System.Windows.Style.TargetType%2A> von `Button` definierte Stil würde auf diese Schaltfläche angewendet werden. Wenn Sie möchten, können Sie für den Stil dennoch aus Gründen der Übersichtlichkeit den Schlüssel mit demselben Typwert wie <xref:System.Windows.Style.TargetType%2A> angeben. Das ist allerdings nur eine Option.

Implizite Schlüssel für Stile gelten nicht für ein Steuerelement, wenn <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> `true` ist. (Beachten Sie auch, dass <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> als Teil des nativen Verhaltens für die Steuerelementklasse und nicht explizit für eine Instanz des Steuerelements festgelegt werden kann.) Um implizite Schlüssel für Szenarien mit abgeleiteten Klassen zu unterstützen, muss das Steuerelement <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> außer Kraft setzen (alle vorhandenen Steuerelemente, die mit WPF bereitgestellt werden, enthalten diese Außerkraftsetzung). Weitere Informationen zu Stilen, Designs und dem Steuerelemententwurf finden Sie unter [Richtlinien zum Entwerfen formatierbarer Steuerelemente](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md).

<xref:System.Windows.DataTemplate> verfügt auch über einen impliziten Schlüssel. Der implizite Schlüssel für eine <xref:System.Windows.DataTemplate> ist der <xref:System.Windows.DataTemplate.DataType%2A>-Eigenschaftswert. <xref:System.Windows.DataTemplate.DataType%2A> kann auch als der Name des Typs angegeben werden, anstatt [{x:Type...}](../xaml-services/xtype-markup-extension.md) explizit zu verwenden. Weitere Informationen finden Sie unter [Übersicht über Datenvorlagen](../../framework/wpf/data/data-templating-overview.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ResourceDictionary>
- [Anwendungsressourcen](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Ressourcen und Code](../../framework/wpf/advanced/resources-and-code.md)
- [Definieren einer Ressource und Verweisen auf eine Ressource](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [Übersicht über die Anwendungsverwaltung](../../framework/wpf/app-development/application-management-overview.md)
- [x:Type-Markuperweiterung](../xaml-services/xtype-markup-extension.md)
- [StaticResource-Markuperweiterung](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [DynamicResource-Markuperweiterung](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
