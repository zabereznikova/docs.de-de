---
title: Definieren von XAML-Ressourcen
description: Erfahren Sie mehr über XAML-Ressourcen in WPF für .NET Core. Verstehen der XAML-Ressourcentypen und Erlernen der Definition von XAML-Ressourcen.
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: b278bb92afc308578d60e347871e0150b26a95db
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "81432569"
---
# <a name="overview-of-xaml-resources"></a>Überblick über XAML-Ressourcen

Eine Ressource ist ein Objekt, das an verschiedenen Stellen in Ihrer App wiederverwendet werden kann. Beispiele für Ressourcen sind Pinsel und Stile. In dieser Übersicht wird beschrieben, wie Ressourcen in XAML (Extensible Application Markup Language) verwendet werden. Sie können ressourcen auch mithilfe von Code erstellen und darauf zugreifen.

> [!NOTE]
> Die in diesem Artikel beschriebenen XAML-Ressourcen unterscheiden sich von *App-Ressourcen,* bei denen es sich im Allgemeinen um Dateien handelt, die einer App hinzugefügt werden, z. B. Inhalt, Daten oder eingebettete Dateien.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>Verwenden von Ressourcen in XAML

Im folgenden Beispiel <xref:System.Windows.Media.SolidColorBrush> wird eine als Ressource im Stammelement einer Seite definiert. Das Beispiel verweist dann auf die Ressource und verwendet sie, <xref:System.Windows.Controls.TextBlock>um Eigenschaften <xref:System.Windows.Controls.Button>mehrerer untergeordneter Elemente festzulegen, einschließlich a <xref:System.Windows.Shapes.Ellipse>, a und a .

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

Jedes Element auf<xref:System.Windows.FrameworkElement> Frameworkebene ( oder <xref:System.Windows.FrameworkContentElement>) verfügt über eine <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft, bei der es sich um einen <xref:System.Windows.ResourceDictionary> Typ handelt, der definierte Ressourcen enthält. Sie können Ressourcen für jedes Element <xref:System.Windows.Controls.Button>definieren, z. B. eine . Ressourcen werden jedoch am häufigsten für das <xref:System.Windows.Controls.Page> Stammelement definiert, das sich im Beispiel befindet.

Jeder Ressource in einem Ressourcenverzeichnis muss ein eindeutiger Schlüssel zugewiesen werden. Wenn Sie Ressourcen in Markup definieren, weisen Sie den eindeutigen Schlüssel über die [x:Key-Direktive](../xaml-services/xkey-directive.md)zu. In der Regel ist der Schlüssel eine Zeichenfolge. Sie können jedoch den Schlüssel auch als einen anderen Objekttyp definieren, indem Sie die entsprechenden Markuperweiterungen verwenden. Nicht-Zeichenfolgenschlüssel für Ressourcen werden von bestimmten Feature-Bereichen in WPF verwendet, insbesondere für Stile, Komponentenressourcen und Datenstyling.

Sie können eine definierte Ressource mit der Ressourcenmarkuperweiterungssyntax verwenden, die den Schlüsselnamen der Ressource angibt. Verwenden Sie die Ressource beispielsweise als Wert einer Eigenschaft für ein anderes Element.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

Wenn der XAML-Ladevorgang im vorherigen `{StaticResource MyBrush}` Beispiel <xref:System.Windows.Controls.Control.Background%2A> den <xref:System.Windows.Controls.Button>Wert für die Eigenschaft auf verarbeitet, <xref:System.Windows.Controls.Button> überprüft die Ressourcensuchlogik zuerst das Ressourcenwörterbuch für das Element. Wenn <xref:System.Windows.Controls.Button> keine Definition des Ressourcenschlüssels `MyBrush` vorliegt (in diesem Beispiel nicht; seine Ressourcensammlung ist leer), <xref:System.Windows.Controls.Button>wird bei <xref:System.Windows.Controls.Page>der Suche als Nächstes das übergeordnete Element von überprüft, das . Wenn Sie eine Ressource <xref:System.Windows.Controls.Page> für das Stammelement definieren, <xref:System.Windows.Controls.Page> können alle Elemente in der logischen Struktur des Elements darauf zugreifen. Außerdem können Sie dieselbe Ressource wiederverwenden, um den Wert jeder Eigenschaft festzulegen, die denselben Typ akzeptiert, den die Ressource darstellt. Im vorherigen Beispiel legt `MyBrush` dieselbe Ressource zwei <xref:System.Windows.Controls.Control.Background%2A> verschiedene <xref:System.Windows.Controls.Button>Eigenschaften fest: die von a und die <xref:System.Windows.Shapes.Shape.Fill%2A> einer <xref:System.Windows.Shapes.Rectangle>.

## <a name="static-and-dynamic-resources"></a>Statische und dynamische Ressourcen

Eine Ressource kann als statisch oder dynamisch referenziert werden. Referenzen werden entweder mit der [StaticResource Markup Extension](../../framework/wpf/advanced/staticresource-markup-extension.md) oder der [DynamicResource Markup Extension](../../framework/wpf/advanced/dynamicresource-markup-extension.md)erstellt. Eine Markuperweiterung ist ein XAML-Feature, mit dem Sie einen Objektverweis angeben können, indem Sie die Markuperweiterung die Attributzeichenfolge verarbeiten und das Objekt an einen XAML-Lader zurückgeben. Weitere Informationen zum Verhalten der Markuperweiterung finden Sie unter [Markuperweiterungen und WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

Wenn Sie eine Markuperweiterung verwenden, stellen Sie in der Regel einen oder mehrere Parameter in Zeichenfolgenform bereit, die von dieser bestimmten Markuperweiterung verarbeitet werden. [Die StaticResource Markup Extension](../../framework/wpf/advanced/staticresource-markup-extension.md) verarbeitet einen Schlüssel, indem der Wert für diesen Schlüssel in allen verfügbaren Ressourcenwörterbüchern gesucht wird. Die Verarbeitung erfolgt während des Ladens, d. h., wenn der Ladevorgang den Eigenschaftswert zuweisen muss. Die [DynamicResource Markup-Erweiterung](../../framework/wpf/advanced/dynamicresource-markup-extension.md) verarbeitet stattdessen einen Schlüssel, indem ein Ausdruck erstellt wird, und dieser Ausdruck bleibt nicht ausgewertet, bis die App ausgeführt wird, zu dem Zeitpunkt, zu dem der Ausdruck ausgewertet wird und einen Wert bereitstellt.

Wenn Sie auf eine Ressource verweisen, sind bei der Wahl zwischen einem statischen und einem dynamischen Ressourcenverweis folgende Aspekte zu beachten:

- Berücksichtigen Sie beim Bestimmen des Gesamtentwurfs, wie Sie die Ressourcen für Ihre App erstellen (pro Seite, in der App, in losem XAML oder in einer reinen Ressourcenassembly), Folgendes:

- Die Funktionalität der App. Sind die Aktualisierungsressourcen in Echtzeit Teil Ihrer App-Anforderungen?
- Das Suchverhalten des jeweiligen Ressourcenverweistyps.
- Jeweiliger Eigenschafts- oder Ressourcentyp sowie dessen natives Verhalten.

## <a name="static-resources"></a>Statische Ressourcen

Statische Ressourcenverweise funktionieren optimal unter folgenden Bedingungen:

- Ihr App-Entwurf konzentriert die meisten Ressourcen in Ressourcenwörterbüchern auf Seiten- oder Anwendungsebene. Statische Ressourcenverweise werden nicht basierend auf Laufzeitverhalten neu bewertet, z. B. beim erneuten Laden einer Seite. Es kann also ein gewisser Leistungsvorteil sein, wenn eine große Anzahl dynamischer Ressourcenverweise vermieden wird, wenn sie aufgrund Ihres Ressourcen- und App-Designs nicht erforderlich sind.

- Sie legen den Wert einer Eigenschaft fest, die <xref:System.Windows.DependencyObject> sich <xref:System.Windows.Freezable>nicht auf einer oder einer befindet.

- Sie erstellen ein Ressourcenwörterbuch, das in eine DLL kompiliert und als Teil der App verpackt oder zwischen Apps freigegeben wird.

- Sie erstellen ein Design für ein benutzerdefiniertes Steuerelement und definieren Ressourcen, die in den Designs verwendet werden. In diesem Fall möchten Sie in der Regel nicht das dynamische Suchverhalten für Ressourcenreferenzen. Stattdessen soll das statische Ressourcenreferenzverhalten angezeigt werden, damit die Suche vorhersagbar und für das Design in sich geschlossen ist. Bei einem dynamischen Ressourcenverweis wird sogar ein Verweis innerhalb eines Themas bis zur Laufzeit nicht ausgewertet. und es besteht die Möglichkeit, dass beim Anwenden des Themas ein lokales Element einen Schlüssel neu definiert, auf den das Design zu verweisen versucht, und das lokale Element vor dem Thema selbst in der Suche fällt. In diesem Fall verhält sich Ihr Thema nicht wie erwartet.

- Sie verwenden Ressourcen, um eine große Anzahl von Abhängigkeitseigenschaften festzulegen. Abhängigkeitseigenschaften verfügen über effektiveWertzwischenspeicherung, wie vom Eigenschaftensystem aktiviert, wenn Sie also einen Wert für eine Abhängigkeitseigenschaft angeben, die zum Zeitpunkt des Ladens ausgewertet werden kann, muss die Abhängigkeitseigenschaft nicht nach einem neu ausgewerteten Ausdruck suchen und kann den letzten effektiven Wert zurückgeben. Mit diesem Verfahren kann ein Leistungsvorteil erzielt werden.

- Sie möchten die zugrunde liegende Ressource für alle Consumer ändern oder separate beschreibbare Instanzen für jeden Consumer verwalten, indem Sie das [x:Shared-Attribut](../xaml-services/xshared-attribute.md)verwenden.

### <a name="static-resource-lookup-behavior"></a>Suchverhalten von statischen Ressourcen

Im Folgenden wird der Suchvorgang beschrieben, der automatisch auftritt, wenn eine statische Ressource von einer Eigenschaft oder einem Element referenziert wird:

01. Der Suchprozess prüft den angeforderten Schlüssel im Ressourcenverzeichnis, das durch das Element definiert wird, das die Eigenschaft festlegt.

01. Der Suchprozess durchläuft dann die logische Struktur nach oben zum übergeordneten Element und seinem Ressourcenwörterbuch. Dieser Prozess wird fortgesetzt, bis das Stammelement erreicht ist.

01. App-Ressourcen werden überprüft. App-Ressourcen sind die Ressourcen innerhalb des <xref:System.Windows.Application> Ressourcenwörterbuchs, die vom Objekt für Ihre WPF-App definiert werden.

Statische Ressourcenverweise innerhalb eines Ressourcenverzeichnisses müssen auf eine Ressource verweisen, die bereits vor dem Ressourcenverweis lexikalisch definiert worden ist. Vorwärtsverweise können von einem statischen Ressourcenverweis nicht aufgelöst werden. Entwerfen Sie aus diesem Grund die Ressourcenwörterbuchstruktur so, dass Ressourcen am oder in der Nähe des Anfangs jedes jeweiligen Ressourcenwörterbuchs definiert werden.

Die statische Ressourcensuche kann sich in Designs oder in Systemressourcen erstrecken, aber diese Suche wird nur unterstützt, da der XAML-Ladevorgang die Anforderung verzögert. Der Aufschub ist erforderlich, damit das Laufzeitdesign zum Zeitpunkt des Ladens der Seite ordnungsgemäß auf die App angewendet wird. Statische Ressourcenverweise auf Schlüssel, von denen bekannt ist, dass sie nur in Designs oder als Systemressourcen vorhanden sind, werden jedoch nicht empfohlen, da solche Verweise nicht neu ausgewertet werden, wenn das Design vom Benutzer in Echtzeit geändert wird. Dynamische Ressourcenverweise sind zuverlässiger, wenn Sie Designs oder Systemressourcen abfragen. Eine Ausnahme bilden Abfragen, bei denen ein Designelement selbst andere Ressourcen abfragt. Diese Verweise sind aus den oben genannten Gründen als statische Ressourcenverweise zu definieren.

Das Ausnahmeverhalten, wenn kein statischer Ressourcenverweis gefunden wird, variiert. Falls die Ressource verzögert wurde, tritt die Ausnahme zur Laufzeit ein. Falls die Ressource nicht verzögert wurde, tritt die Ausnahme zur Ladezeit ein.

## <a name="dynamic-resources"></a>Dynamische Ressourcen

Dynamische Ressourcen funktionieren am besten, wenn:

- Der Wert der Ressource, einschließlich Systemressourcen oder Ressourcen, die andernfalls vom Benutzer festgelegt werden können, hängt von Bedingungen ab, die bis zur Laufzeit nicht bekannt sind. Sie können z. B. Setterwerte erstellen, <xref:System.Windows.SystemColors>die <xref:System.Windows.SystemFonts>auf <xref:System.Windows.SystemParameters>Systemeigenschaften verweisen, die von verfügbar gemacht werden, oder . Diese Werte sind wirklich dynamisch, da sie letztlich von der Laufzeitumgebung des Benutzers und dem Betriebssystem stammen. Möglicherweise haben Sie außerdem Designs auf der Anwendungsebene, die sich ändern können, und deren Veränderungen auch vom Ressourcenzugriff auf der Seitenebene erfasst werden müssen.

- Sie erstellen oder verweisen auf Designstile für ein benutzerdefiniertes Steuerelement.

- Sie beabsichtigen, den Inhalt <xref:System.Windows.ResourceDictionary> einer App während einer App-Lebensdauer anzupassen.

- Sie haben eine komplizierte Ressourcenstruktur mit gegenseitigen Abhängigkeiten, die möglicherweise Vorwärtsverweise erfordert. Statische Ressourcenverweise unterstützen keine Vorwärtsverweise, aber dynamische Ressourcenverweise unterstützen sie, da die Ressource erst zur Laufzeit ausgewertet werden muss und Weiterleitungsverweise daher kein relevantes Konzept sind.

- Sie verweisen auf eine Ressource, die aus der Perspektive eines Kompilierungs- oder Arbeitssatzes groß ist, und die Ressource wird möglicherweise nicht sofort verwendet, wenn die Seite geladen wird. Statische Ressourcenverweise werden immer aus XAML geladen, wenn die Seite geladen wird. Ein dynamischer Ressourcenverweis wird jedoch erst geladen, wenn er verwendet wird.

- Sie erstellen einen Stil, in dem Setterwerte aus anderen Werten stammen können, die von Designs oder anderen Benutzereinstellungen beeinflusst werden.

- Sie wenden Ressourcen auf Elemente an, die während der App-Lebensdauer in der logischen Struktur neu erwidert werden können. Beim erneuten Zuordnen der Elemente wird möglicherweise auch der Ressourcensuchbereich neu definiert. Wenn Sie wollen, dass die Ressource für ein neu zugeordnetes Element entsprechend dem neuen Suchbereich neu ausgewertet wird, verwenden Sie immer einen dynamischen Ressourcenverweis.

### <a name="dynamic-resource-lookup-behavior"></a>Suchverhalten von dynamischen Ressourcen

Das Ressourcensuchverhalten für einen dynamischen Ressourcenverweis parallelt das Suchverhalten im Code, wenn Sie aufrufen <xref:System.Windows.FrameworkElement.FindResource%2A> oder: <xref:System.Windows.FrameworkElement.SetResourceReference%2A>

01. Die Suche nach dem angeforderten Schlüssel innerhalb des Ressourcenwörterbuchs, das durch das Element definiert wird, das die Eigenschaft festlegt, wird überprüft:

    - Wenn das Element <xref:System.Windows.FrameworkElement.Style%2A> eine Eigenschaft <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName> definiert, hat <xref:System.Windows.Style.Resources> das des Elements sein Wörterbuch aktiviert.

    - Wenn das Element <xref:System.Windows.Controls.Control.Template%2A> eine Eigenschaft <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> definiert, wird das Wörterbuch des Elements aktiviert.

01. Bei der Suche wird die logische Struktur nach oben zum übergeordneten Element und seinem Ressourcenwörterbuch durchläuft. Dieser Prozess wird fortgesetzt, bis das Stammelement erreicht ist.

01. App-Ressourcen werden überprüft. App-Ressourcen sind die Ressourcen im Ressourcenwörterbuch, die <xref:System.Windows.Application> vom Objekt für Ihre WPF-App definiert werden.

01. Das Designressourcenwörterbuch wird auf das aktuell aktive Design überprüft. Falls das Design zur Laufzeit geändert wird, wird der Wert neu ausgewertet.

01. Systemressourcen werden geprüft.

Es sind verschiedene Ausnahmeverhaltensmuster möglich (sofern sie auftreten):

- Wenn eine Ressource von <xref:System.Windows.FrameworkElement.FindResource%2A> einem Aufruf angefordert und nicht gefunden wurde, wird eine Ausnahme ausgelöst.

- Wenn eine Ressource von <xref:System.Windows.FrameworkElement.TryFindResource%2A> einem Aufruf angefordert und nicht gefunden wurde, `null`wird keine Ausnahme ausgelöst, und der zurückgegebene Wert ist . Wenn die festgelegte Eigenschaft `null`nicht akzeptiert, ist es immer noch möglich, dass eine tiefere Ausnahme ausgelöst wird, abhängig von der einzelnen Eigenschaft, die festgelegt wird.

- Wenn eine Ressource von einem dynamischen Ressourcenverweis in XAML angefordert und nicht gefunden wurde, hängt das Verhalten vom allgemeinen Eigenschaftensystem ab. Das allgemeine Verhalten ist so, als ob kein Eigenschafteneinstellungsvorgang auf der Ebene aufgetreten wäre, auf der die Ressource vorhanden ist. Wenn Sie z. B. versuchen, den Hintergrund für ein einzelnes Schaltflächenelement mithilfe einer Ressource festzulegen, die nicht ausgewertet werden konnte, werden keine Werte satzergebnisse, aber der effektive Wert kann weiterhin von anderen Teilnehmern im Eigenschaftensystem und der Wertpriorität stammen. Der Hintergrundwert kann z. B. immer noch aus einem lokal definierten Schaltflächenstil oder aus dem Designstil stammen. Bei Eigenschaften, die nicht durch Designstile definiert sind, kann der effektive Wert nach einer fehlgeschlagenen Ressourcenauswertung vom Standardwert in den Eigenschaftenmetadaten stammen.

### <a name="restrictions"></a>Beschränkungen

Die Verwendung dynamischer Verweise ist mit einigen wichtigen Beschränkungen verbunden. Mindestens eine der folgenden Bedingungen muss erfüllt sein:

- Die festgelegte Eigenschaft muss eine <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>Eigenschaft für eine oder sein. Diese Eigenschaft muss durch <xref:System.Windows.DependencyProperty>eine unterstützt werden.

- Der Verweis bezieht sich `StyleSetter`auf einen Wert innerhalb einer .

- Die festgelegte Eigenschaft muss eine <xref:System.Windows.Freezable> Eigenschaft auf einer sein, <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> die als <xref:System.Windows.Setter> Wert von a oder eigenschaft oder als Wert bereitgestellt wird.

Da die festgelegte Eigenschaft <xref:System.Windows.DependencyProperty> <xref:System.Windows.Freezable> eine oder eine Eigenschaft sein muss, können die meisten Eigenschaftenänderungen an die Benutzeroberfläche weitergegeben werden, da eine Eigenschaftsänderung (der geänderte dynamische Ressourcenwert) vom Eigenschaftensystem bestätigt wird. Die meisten Steuerelemente enthalten Logik, die <xref:System.Windows.DependencyProperty> ein anderes Layout eines Steuerelements erzwingt, wenn eine Änderung und diese Eigenschaft das Layout beeinflussen könnte. Allerdings werden nicht alle Eigenschaften, deren Wert eine [DynamicResource Markup-Erweiterung](../../framework/wpf/advanced/dynamicresource-markup-extension.md) als Wert hat, in Echtzeit aktualisierungen in der Benutzeroberfläche bereitstellen. Diese Funktionalität kann je nach Eigenschaft und je nach Typ, der die Eigenschaft besitzt, oder sogar von der logischen Struktur Ihrer App variieren.

## <a name="styles-datatemplates-and-implicit-keys"></a>Stile, DataTemplates und implizite Schlüssel

Obwohl alle Elemente <xref:System.Windows.ResourceDictionary> in einem einen Schlüssel haben müssen, bedeutet dies nicht, dass alle Ressourcen eine explizite `x:Key`haben müssen. Manche Objekttypen unterstützen einen impliziten Schlüssel, wenn sie als Ressourcen definiert sind, wobei der Schlüsselwert an den Wert einer anderen Eigenschaft gebunden ist. Dieser Schlüsseltyp wird als impliziter Schlüssel `x:Key` bezeichnet, während ein Attribut ein expliziter Schlüssel ist. Sie können jegliche implizite Schlüssel durch die Angabe eines expliziten Schlüssels überschreiben.

Ein wichtiges Szenario für Ressourcen <xref:System.Windows.Style>ist das Definieren einer . Tatsächlich wird <xref:System.Windows.Style> a fast immer als Eintrag in einem Ressourcenwörterbuch definiert, da Stile von Natur aus für die Wiederverwendung vorgesehen sind. Weitere Informationen zu Stilen finden Sie unter [Styling und Templating](styles-templates-overview.md).

Mit einem impliziten Schlüssel können Stile für Steuerelemente erstellt werden, und es kann damit auf sie verwiesen werden. Die Design-Stile, die die Standarddarstellung eines Steuerelements definieren, basieren auf diesen impliziten Schlüsseln. Vom Standpunkt der Anforderung ist der implizite Schlüssel der <xref:System.Type> des Steuerelements selbst. Vom Standpunkt der Definition der Ressourcen ist <xref:System.Windows.Style.TargetType%2A> der implizite Schlüssel der des Stils. Wenn Sie daher Designs für benutzerdefinierte Steuerelemente oder Formatvorlagen erstellen, die mit vorhandenen Designstilen interagieren, müssen Sie dafür keine [x:Key-Direktive](../xaml-services/xkey-directive.md) <xref:System.Windows.Style>angeben. Und wenn Sie die Design-Stile verwenden möchten, müssen Sie gar keinen Stil angeben. Beispielsweise funktioniert die folgende Stildefinition, <xref:System.Windows.Style> auch wenn die Ressource keinen Schlüssel zu haben scheint:

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

Dieser Stil hat wirklich einen Schlüssel: den impliziten Schlüssel `typeof(System.Windows.Controls.Button)`. In Markup können Sie <xref:System.Windows.Style.TargetType%2A> direkt einen als Typnamen angeben (oder Sie können optional [die Option "x:Type..."](../xaml-services/xtype-markup-extension.md) verwenden. , um <xref:System.Type>eine zurückzugeben.

Durch die von WPF verwendeten Standarddesignstilmechanismen wird dieser Stil als <xref:System.Windows.Controls.Button> Laufzeitstil einer auf <xref:System.Windows.Controls.Button> der Seite angewendet, <xref:System.Windows.FrameworkElement.Style%2A> auch wenn der selbst nicht versucht, seine Eigenschaft oder einen bestimmten Ressourcenverweis auf den Stil anzugeben. Der in der Seite definierte Stil wird früher in der Suchsequenz gefunden als der Designwörterbuchstil, mit demselben Schlüssel, den der Designwörterbuchstil hat. Sie können `<Button>Hello</Button>` einfach eine beliebige Stelle auf der <xref:System.Windows.Style.TargetType%2A> `Button` Seite angeben, und der Stil, den Sie mit definiert haben, würde auf diese Schaltfläche angewendet. Wenn Sie möchten, können Sie den Stil weiterhin <xref:System.Windows.Style.TargetType%2A> explizit mit dem gleichen Typwert wie aus Gründen der Übersichtlichkeit in Ihrem Markup verwenden, aber das ist optional.

Implizite Schlüssel für Stile gelten <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> nicht `true`für ein Steuerelement, wenn dies der Fall ist. (Beachten Sie <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> auch, dass dies möglicherweise als Teil des systemeigenen Verhaltens für die Steuerelementklasse festgelegt wird und nicht explizit für eine Instanz des Steuerelements.) Um implizite Schlüssel für abgeleitete Klassenszenarien zu unterstützen, muss das Steuerelement außerdem überschreiben <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (alle vorhandenen Steuerelemente, die als Teil von WPF bereitgestellt werden, enthalten diese Außerkraftsetzung). Weitere Informationen zu Stilen, Designs und Steuerelementdesign finden Sie unter [Richtlinien zum Entwerfen von stylierbaren Steuerelementen](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md).

<xref:System.Windows.DataTemplate>hat auch einen impliziten Schlüssel. Der implizite <xref:System.Windows.DataTemplate> Schlüssel <xref:System.Windows.DataTemplate.DataType%2A> für a ist der Eigenschaftswert. <xref:System.Windows.DataTemplate.DataType%2A>kann auch als Name des Typs angegeben werden, anstatt explizit [mit .x:Type..."](../xaml-services/xtype-markup-extension.md). Weitere Informationen finden Sie unter Übersicht über [Die Datenbeversuchsübersicht](../../framework/wpf/data/data-templating-overview.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.ResourceDictionary>
- [Anwendungsressourcen](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Ressourcen und Code](../../framework/wpf/advanced/resources-and-code.md)
- [Definieren und Verweisen auf eine Ressource](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [Übersicht über das Anwendungsmanagement](../../framework/wpf/app-development/application-management-overview.md)
- [x:Markuperweiterung typisiert](../xaml-services/xtype-markup-extension.md)
- [StaticResource-Markuperweiterung](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [DynamicResource-Markuperweiterung](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
