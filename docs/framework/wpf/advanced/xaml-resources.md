---
title: XAML-Ressourcen
ms.date: 03/30/2017
helpviewer_keywords:
- reusing resources [WPF]
- resources [WPF], reusing
- reusing commonly defined objects [WPF]
- XAML [WPF], reusing resources
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
ms.openlocfilehash: 04d1a72d70d6fd0753677f2e9635a05a60d33fec
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748270"
---
# <a name="xaml-resources"></a>XAML-Ressourcen
Eine Ressource ist ein Objekt, das an unterschiedlichen Stellen in der Anwendung erneut verwendet werden kann. Beispiele für Ressourcen sind Pinsel und Stile. In dieser Übersicht wird beschrieben, wie Ressourcen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Sie können auch Zugriff auf Ressourcen mithilfe von Code oder abwechselnd zwischen Code und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Weitere Informationen finden Sie unter [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md).  
  
> [!NOTE]
>  Die in diesem Thema beschriebenen Ressourcendateien unterscheiden, als die Ressourcendateien im beschrieben [WPF-Anwendungsressource, Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md) und unterscheidet sich die eingebetteten oder verknüpften Ressourcen, die in beschriebenen [verwalten Ressourcen der Anwendung (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
  
<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>Verwendung von Ressourcen in XAML  
 Das folgende Beispiel definiert eine <xref:System.Windows.Media.SolidColorBrush> als Ressource für das Stammelement einer Seite. Anschließend verweist auf die Ressource und wird verwendet, um die Eigenschaften mehrerer untergeordneter Elemente, einschließlich einer <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Controls.TextBlock>, und ein <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FEResourceSH_snip#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 Jedes Element der Frameworkebene (<xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>) verfügt über eine <xref:System.Windows.FrameworkElement.Resources%2A> -Eigenschaft, die die Eigenschaft ist die Ressourcen enthält (als eine <xref:System.Windows.ResourceDictionary>), die eine Ressource definiert. Sie können Ressourcen für beliebige Elemente definieren. Ressourcen werden jedoch am häufigsten definiert, für das Stammelement, d.h. <xref:System.Windows.Controls.Page> im Beispiel.  
  
 Jeder Ressource in einem Ressourcenverzeichnis muss ein eindeutiger Schlüssel zugewiesen werden. Wenn Sie Ressourcen in Markup definieren, weisen Sie den eindeutigen Schlüssel durch die [X: Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md). In der Regel ist der Schlüssel eine Zeichenfolge. Sie können jedoch den Schlüssel auch als einen anderen Objekttyp definieren, indem Sie die entsprechenden Markuperweiterungen verwenden. Nichtzeichenfolgeschlüssel für Ressourcen werden verwendet, von bestimmten Funktionsbereichen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], insbesondere für Stile, Komponentenressourcen und datenformatierung.  
  
 Nachdem Sie eine Ressource definiert haben, können Sie einen Eigenschaftswert auf sie verweisen, indem Sie eine Markuperweiterungssyntax für Ressourcen verwenden, die den Schlüsselnamen angibt, zum Beispiel:  
  
 [!code-xaml[FEResourceSH_snip#KeyNameUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 Im vorherigen Beispiel wenn die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ladeprogramm verarbeitet den Wert `{StaticResource MyBrush}` für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft <xref:System.Windows.Controls.Button>, Suchlogik der Ressource überprüft zunächst das Ressourcenverzeichnis der <xref:System.Windows.Controls.Button> Element. Wenn <xref:System.Windows.Controls.Button> verfügt nicht über eine Definition des Ressourcenschlüssels `MyBrush` (nicht der Fall, die ressourcenauflistung ist leer), die Suche als Nächstes überprüft das übergeordnete Element des <xref:System.Windows.Controls.Button>, d.h. <xref:System.Windows.Controls.Page>. Daher beim Definieren einer Ressourcensatzes auf die <xref:System.Windows.Controls.Page> Stammelement, das alle Elemente in der logischen Struktur des der <xref:System.Windows.Controls.Page> darauf zugreifen können, und Sie können die gleiche Ressource wiederverwenden, für den Wert einer beliebigen Eigenschaft festlegen, akzeptiert die <xref:System.Type> , die die Ressource Stellt die dar. Im vorherigen Beispiel identisch `MyBrush` Ressourcensätze zwei unterschiedliche Eigenschaften: die <xref:System.Windows.Controls.Control.Background%2A> von einer <xref:System.Windows.Controls.Button>, und die <xref:System.Windows.Shapes.Shape.Fill%2A> von eine <xref:System.Windows.Shapes.Rectangle>.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>Statische und dynamische Ressourcen  
 Es kann entweder auf statische oder auf dynamische Ressourcen verwiesen werden. Dies erfolgt mithilfe der [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) oder [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Eine Markuperweiterung ist ein Feature von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , wobei Sie einen Objektverweis angeben können, indem die Markuperweiterung die Attributzeichenfolge verarbeitet und das Objekt, das Zurückgeben einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ladeprogramm. Weitere Informationen über das Markuperweiterungsverhalten finden Sie unter [Markuperweiterungen und WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Wenn Sie eine Markuperweiterung verwenden, geben Sie in der Regel einen oder mehrere Parameter im Zeichenfolgenformat an, die von dieser speziellen Markuperweiterung verarbeitet werden, und nicht im Kontext der festzulegenden Eigenschaft ausgewertet werden. Die [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) verarbeitet einen Schlüssel, indem Sie den Wert für diesen Schlüssel in allen verfügbaren Ressourcenverzeichnissen sucht. Dies geschieht beim Laden, d.h. zu dem Zeitpunkt, während der Ladeprozess dem statischen Ressourcenverweis einen Eigenschaftswert zuweisen muss. Die [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) stattdessen Prozesse ein Schlüssel durch Erstellen eines Ausdrucks und diesen Ausdruck nicht die Anwendung tatsächlich ausgeführt wird, bis zu diesem Zeitpunkt der Ausdruck wird ausgewertet, und gibt einen Wert an.  
  
 Wenn Sie auf eine Ressource verweisen, sind bei der Wahl zwischen einem statischen und einem dynamischen Ressourcenverweis folgende Aspekte zu beachten:  
  
-   Der allgemeine Entwurf, wie Sie die Ressourcen für Ihre Anwendung erstellen (pro Seite, in der Anwendung, in loser [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in einer reinen Ressourcenassembly).  
  
-   Die Funktionalität der Anwendung: ist das Aktualisieren von Ressourcen in Echtzeit ein Teil der Anforderungen an Ihre Anwendung?  
  
-   Das Suchverhalten des jeweiligen Ressourcenverweistyps.  
  
-   Jeweiliger Eigenschafts- oder Ressourcentyp sowie dessen natives Verhalten.  
  
### <a name="static-resources"></a>Statische Ressourcen  
 Statische Ressourcenverweise funktionieren optimal unter folgenden Bedingungen:  
  
-   Der Anwendungsentwurf behandelt die meisten Ressourcen auf der Seiten- oder Anwendungsebene. Statische Ressourcenverweise werden nicht basierend auf dem Laufzeitverhalten neu bewertet, z.B. beim Neuladen einer Seite. Daher kann durch die Verwendung statischer Ressourcenverweise ein Leistungsvorteil erzielt werden, da eine Vielzahl von dynamischen Verweisen vermieden wird, die nicht für Ihren Ressourcen- oder Anwendungsentwurf erforderlich sind.  
  
-   Legen Sie den Wert einer Eigenschaft, die nicht auf eine <xref:System.Windows.DependencyObject> oder <xref:System.Windows.Freezable>.  
  
-   Sie erstellen ein Ressourcenverzeichnis, das in eine DLL kompiliert und als ein Teil der Anwendung verpackt oder von mehreren Anwendungen gemeinsam genutzt wird.  
  
-   Sie erstellen ein Design für ein benutzerdefiniertes Steuerelement und definieren Ressourcen, die in den Designs verwendet werden. Für diesen Fall ist das Suchverhalten der dynamischen Verweise ungeeignet. Damit das Suchverhalten vorhersagbar und eigenständig für das Design gestaltet werden kann, sind statische Ressourcenverweise vorzuziehen. Dynamische Ressourcenverweise werden bis zur Laufzeit nicht ausgewertet. Es betrifft auch die Verweise innerhalb des Designs. Daher besteht die Möglichkeit, dass bei der Anwendung des Designs ein Schlüssel, auf den das Design zu verweisen versucht, von einem lokalen Element neu definiert wird, und das lokale Element statt des Designs bei der Suche gefunden wird. In diesem Fall wird Ihr Design sich nicht wie erwartet verhalten.  
  
-   Ressourcen werden verwendet, um die große Anzahl von Abhängigkeitseigenschaften festzulegen. Abhängigkeitseigenschaften können auf das effektive Zwischenspeichern von Werten des Eigenschaftensystems zugreifen. Wenn Sie einer Abhängigkeitseigenschaft einen Wert bereitstellen, der zur Ladezeit ausgewertet werden kann, ist keine Neuauswertung des Ausdrucks von der Abhängigkeitseigenschaft erforderlich. Sie kann den letzten effektiven Wert zurückgeben. Mit diesem Verfahren kann ein Leistungsvorteil erzielt werden.  
  
-   Die zugrunde liegende Ressource für alle Consumer ändern möchten, oder Sie separate Instanzen mit Schreibzugriff für jeden Consumer mit beibehalten möchten die [X: Shared-Attribut](../../../../docs/framework/xaml-services/x-shared-attribute.md).  
  
#### <a name="static-resource-lookup-behavior"></a>Suchverhalten von statischen Ressourcen  
  
1.  Der Suchprozess prüft den angeforderten Schlüssel im Ressourcenverzeichnis, das durch das Element definiert wird, das die Eigenschaft festlegt.  
  
2.  Der Suchprozess durchläuft anschließend die logische Struktur aufwärts, zum übergeordneten Element und seinem Ressourcenverzeichnis. Die Suche wird fortgesetzt, bis das Stammelement erreicht ist.  
  
3.  Als nächstes werden die Anwendungsressourcen geprüft. Anwendungsressourcen sind die Ressourcen im Ressourcenverzeichnis, das nach definiert ist die <xref:System.Windows.Application> Objekt für Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  
  
 Statische Ressourcenverweise innerhalb eines Ressourcenverzeichnisses müssen auf eine Ressource verweisen, die bereits vor dem Ressourcenverweis lexikalisch definiert worden ist. Vorwärtsverweise können von einem statischen Ressourcenverweis nicht aufgelöst werden. Wenn Sie statische Ressourcenverweise verwenden, müssen Sie daher die Struktur des Ressourcenverzeichnisses so entwerfen, dass Ressourcen, die durch andere Ressourcen verwendet werden können, zu Beginn der jeweiligen Ressourcenverweise definiert werden.  
  
 Statische Ressourcensuche kann auf Designs oder auf Systemressourcen zu erweitern, aber dies wird unterstützt, da die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ladeprogramm die Anforderung verzögert. Die Verzögerung ist zwecks einer ordnungsgemäßen Anwendung des Laufzeit-Designs zu dem Zeitpunkt, als die Seite geladen ist, erforderlich. Jedoch ist von statischen Ressourcenverweisen auf Schlüssel abzuraten, die nur in Designs oder als Systemressourcen vorkommen. Der Grund hierfür ist, dass solche Verweise nicht neu ausgewertet werden, falls ein Benutzer das Design in Echtzeit ändert. Dynamische Ressourcenverweise sind zuverlässiger, wenn Sie Designs oder Systemressourcen abfragen. Eine Ausnahme bilden Abfragen, bei denen ein Designelement selbst andere Ressourcen abfragt. Diese Verweise sind aus den oben genannten Gründen als statische Ressourcenverweise zu definieren.  
  
 Falls statistische Verweise nicht gefunden werden, sind verschiedene Ausnahmeverhaltensmuster möglich. Falls die Ressource verzögert wurde, tritt die Ausnahme zur Laufzeit ein. Falls die Ressource nicht verzögert wurde, tritt die Ausnahme zur Ladezeit ein.  
  
### <a name="dynamic-resources"></a>Dynamische Ressourcen  
 Dynamische Ressourcenverweise funktionieren optimal unter folgenden Bedingungen:  
  
-   Der Wert der Ressource hängt von Bedingungen ab, die bis zur Laufzeit unbekannt sind. Dies schließt Systemressourcen und Ressourcen ein, die andernfalls vom Benutzer festgelegt werden. Sie können z. B. Setter-Werte, die auf Systemeigenschaften verweisen erstellen, wie vom <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>, oder <xref:System.Windows.SystemParameters>. Diese Werte sind wirklich dynamisch, da sie letztlich von der Laufzeitumgebung des Benutzers und dem Betriebssystem stammen. Möglicherweise haben Sie außerdem Designs auf der Anwendungsebene, die sich ändern können, und deren Veränderungen auch vom Ressourcenzugriff auf der Seitenebene erfasst werden müssen.  
  
-   Sie erstellen Designstile für ein benutzerdefiniertes Steuerelement oder verweisen darauf.  
  
-   Sie beabsichtigen, passen Sie den Inhalt einer <xref:System.Windows.ResourceDictionary> während der Lebensdauer einer Anwendung.  
  
-   Sie haben eine komplizierte Ressourcenstruktur mit gegenseitigen Abhängigkeiten, die möglicherweise Vorwärtsverweise erfordert. Statische Ressourcenverweise Vorwärtsverweise, nicht unterstützt, aber dynamische Ressourcenverweise unterstützen, da die Ressource nicht bis zur Laufzeit ausgewertet werden muss, und Vorwärtsverweise sind daher kein relevantes Konzept.  
  
-   Sie verweisen auf eine Ressource, die aus der Perspektive eines kompilieren oder Arbeitssatzes besonders groß ist, und möglicherweise beim Laden der Seite nicht sofort verwendet wird. Statische Ressourcenverweise werden immer von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beim Laden der Seite, jedoch ein dynamischen Ressourcenverweis wird nicht geladen, bis er tatsächlich verwendet wird.  
  
-   Sie erstellen einen Stil, bei dem Setter-Werte von anderen Werten stammen könnten, die durch Designs oder andere Benutzereinstellungen beeinflusst werden.  
  
-   Sie ordnen Ressourcen Elementen zu, die in der logischen Struktur während der Lebensdauer der Anwendung neu zugeordnet werden können. Beim erneuten Zuordnen der Elemente wird möglicherweise auch der Ressourcensuchbereich neu definiert. Wenn Sie wollen, dass die Ressource für ein neu zugeordnetes Element entsprechend dem neuen Suchbereich neu ausgewertet wird, verwenden Sie immer einen dynamischen Ressourcenverweis.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>Suchverhalten von dynamischen Ressourcen  
 Suchverhalten von Ressourcen für einen dynamischen Ressourcenverweis entspricht dem Suchverhalten in Ihrem Code aus, wenn Sie aufrufen <xref:System.Windows.FrameworkElement.FindResource%2A> oder <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.  
  
1.  Der Suchprozess prüft den angeforderten Schlüssel im Ressourcenverzeichnis, das durch das Element definiert wird, das die Eigenschaft festlegt.  
  
    -   Wenn das Element definiert eine <xref:System.Windows.FrameworkElement.Style%2A> -Eigenschaft, die <xref:System.Windows.Style.Resources%2A> -Ressourcenverzeichnis innerhalb der <xref:System.Windows.Style> aktiviert ist.  
  
    -   Wenn das Element definiert eine <xref:System.Windows.Controls.Control.Template%2A> -Eigenschaft, die <xref:System.Windows.FrameworkTemplate.Resources%2A> -Ressourcenverzeichnis innerhalb der <xref:System.Windows.FrameworkTemplate> aktiviert ist.  
  
2.  Der Suchprozess durchläuft anschließend die logische Struktur aufwärts, zum übergeordneten Element und dessen Ressourcenverzeichnis. Die Suche wird fortgesetzt, bis das Stammelement erreicht ist.  
  
3.  Als nächstes werden die Anwendungsressourcen geprüft. Anwendungsressourcen sind die Ressourcen im Ressourcenverzeichnis, das nach definiert ist die <xref:System.Windows.Application> Objekt für Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  
  
4.  Das Ressourcenverzeichnis des Designs wird für das derzeit aktive Design überprüft. Falls das Design zur Laufzeit geändert wird, wird der Wert neu ausgewertet.  
  
5.  Systemressourcen werden geprüft.  
  
 Es sind verschiedene Ausnahmeverhaltensmuster möglich (sofern sie auftreten):  
  
-   Wenn eine Ressource, indem angefordert wurde eine <xref:System.Windows.FrameworkElement.FindResource%2A> aufrufen und nicht gefunden wurde, wird eine Ausnahme ausgelöst.  
  
-   Wenn eine Ressource, indem angefordert wurde eine <xref:System.Windows.FrameworkElement.TryFindResource%2A> aufrufen und nicht gefunden wurde, wird keine Ausnahme ausgelöst, aber der zurückgegebene Wert ist `null`. Wenn die festgelegte Eigenschaft wird nicht akzeptiert `null`, ist es weiterhin möglich, dass eine tiefere Ausnahme ausgelöst wird (Dies hängt von der jeweiligen Eigenschaft festgelegt wird).  
  
-   Wenn eine Ressource, von einem dynamischen Ressourcenverweis in angefordert wurde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und nicht gefunden wurde, und klicken Sie dann das Verhalten hängt vom allgemeinen Eigenschaftensystem, aber das übliche Verhalten ist, als ob keine eigenschafteneinstellung auf der Ebene vorgenommen, in dem die Ressource vorhanden ist. Wenn Sie z.B. versuchen, den Hintergrund eines einzelnen Schaltflächenelements mit einer Ressource festzulegen, die nicht ausgewertet werden konnte, wird als Ergebnis kein Wert festgelegt. Ein effektiver Wert kann aber dennoch von anderen Teilnehmern im Eigenschaftssystem und in der Wertrangfolge bereitgestellt werden. Beispielsweise kann der Wert für den Hintergrund von einem lokal definierten Schaltflächenstil oder vom Design-Stil zurückgegeben werden. Für Eigenschaften, die nicht von Design-Stilen definiert werden, kann nach einer fehlgeschlagenen Auswertung der Standardwert aus den Eigenschaftenmetadaten als effektiver Wert übernommen werden.  
  
#### <a name="restrictions"></a>Beschränkungen  
 Die Verwendung dynamischer Verweise ist mit einigen wichtigen Beschränkungen verbunden. Mindestens eine der folgenden Bedingungen muss erfüllt sein:  
  
-   Die festzulegende Eigenschaft muss eine Eigenschaft auf einen <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Dass die Eigenschaft gesichert werden muss, indem eine <xref:System.Windows.DependencyProperty>.  
  
-   Der Verweis bezieht sich auf einen Wert innerhalb einer <xref:System.Windows.Style> <xref:System.Windows.Setter>.  
  
-   Die festzulegende Eigenschaft muss eine Eigenschaft auf eine <xref:System.Windows.Freezable> , dient als Wert eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> -Eigenschaft oder ein <xref:System.Windows.Setter> Wert.  
  
 Da die festzulegende Eigenschaft sein, muss ein <xref:System.Windows.DependencyProperty> oder <xref:System.Windows.Freezable> -Eigenschaft, die meisten eigenschaftsänderungen können weitergegeben werden auf der Benutzeroberfläche, da die Änderung einer Eigenschaft (der Wert der geänderten dynamischen Ressourcen) vom Eigenschaftensystem bestätigt wird. Die meisten Steuerelemente enthalten Logik, die ein anderes Layout eines Steuerelements erzwungen wird, wenn eine <xref:System.Windows.DependencyProperty> ändert, und diese Eigenschaft die Layout beeinflussen kann. Allerdings nicht alle Eigenschaften, die haben einen [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) als ihren Wert ist garantiert, dass den Wert in einer Weise angeben, dass er in Echtzeit in der Benutzeroberfläche aktualisiert. Diese Funktionalität kann dennoch variieren, abhängig sowohl von der Eigenschaft als auch vom Typ, der die Eigenschaft besitzt oder sogar von der logischen Struktur Ihrer Anwendung.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>Stile, Datenvorlagen und implizite Schlüssel  
 Es wurde bereits angemerkt, dass alle Elemente in einem <xref:System.Windows.ResourceDictionary> muss einen Schlüssel haben. Aber dies bedeutet nicht, dass alle Ressourcen eine explizite müssen `x:Key`. Manche Objekttypen unterstützen einen impliziten Schlüssel, wenn sie als Ressourcen definiert sind, wobei der Schlüsselwert an den Wert einer anderen Eigenschaft gebunden ist. Dies wird als impliziter Schlüssel bezeichnet, während ein `x:Key` -Attribut ist ein expliziter Schlüssel. Sie können jegliche implizite Schlüssel durch die Angabe eines expliziten Schlüssels überschreiben.  
  
 Ein besonders wichtiges Szenario für Ressourcen ist beim Definieren einer <xref:System.Windows.Style>. In der Tat ein <xref:System.Windows.Style> ist fast immer als Eintrag in einem Ressourcenverzeichnis definiert, da Stile grundsätzlich zur Wiederverwendung vorgesehen sind. Weitere Informationen zu Stilen finden Sie unter [Stile und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Mit einem impliziten Schlüssel können Stile für Steuerelemente erstellt werden, und es kann damit auf sie verwiesen werden. Die Design-Stile, die die Standarddarstellung eines Steuerelements definieren, basieren auf diesen impliziten Schlüsseln. Ist der implizite Schlüssel aus der Sicht der Anforderung der <xref:System.Type> des Steuerelements selbst. Ist der implizite Schlüssel aus Sicht der Ressourcendefinition die <xref:System.Windows.Style.TargetType%2A> des Stils. Aus diesem Grund bei der Erstellung Designs für benutzerdefinierte Steuerelemente, Stile erstellen, die Interaktion mit vorhandenen Design-Stilen, Sie nicht müssen an einem [X: Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) , <xref:System.Windows.Style>. Und wenn Sie die Design-Stile verwenden möchten, müssen Sie gar keinen Stil angeben. Z. B. die folgenden Formatdefinition funktioniert, obwohl die <xref:System.Windows.Style> Ressource wird nicht angezeigt, um einen Schlüssel zu erhalten:  
  
 [!code-xaml[FEResourceSH_snip#ImplicitStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 Dieser Stil verfügt tatsächlich über einen Schlüssel: den impliziten Schlüssel `typeof(` <xref:System.Windows.Controls.Button> `)`. Im Markup können Sie angeben einer <xref:System.Windows.Style.TargetType%2A> direkt als Typ benannt (oder Sie können optional [{X: Type...}](../../../../docs/framework/xaml-services/x-type-markup-extension.md) Zurückgeben einer <xref:System.Type>.  
  
 Mithilfe der standardmäßigen Design Stil Mechanismen ein, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], dass der Stil angewendet wird, als der Stil für die Laufzeit von ein <xref:System.Windows.Controls.Button> auf der Seite, obwohl die <xref:System.Windows.Controls.Button> selbst wird nicht versucht, an die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft oder eine bestimmte Ressource Ein Verweis auf das Format. Die Formatvorlage definiert wird, auf der Seite befindet sich weiter oben in der Suchsequenz als Wörterbuch Designstil, mit dem gleichen Schlüssel, den dem Wörterbuch Designstil verfügt. Geben Sie einfach `<Button>Hello</Button>` an einer beliebigen Stelle in der Seite und den Stil, die Sie mit definiert <xref:System.Windows.Style.TargetType%2A> von `Button` würde auf diese Schaltfläche angewendet. Wenn Sie möchten, können Sie dennoch einen expliziten Schlüssel für den Stil mit demselben Typwert wie <xref:System.Windows.Style.TargetType%2A>für Klarheit in das Markup, aber dies optional ist.  
  
 Implizite Schlüssel für Stile werden nicht auf ein Steuerelement angewendet, wenn <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> ist `true` (Beachten Sie, dass <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> möglicherweise als Teil des nativen Verhaltens für die Control-Klasse, und nicht explizit in einer Instanz des Steuerelements festgelegt werden). Darüber hinaus um implizite Schlüssel für Szenarios mit abgeleiteten Klassen zu unterstützen, das Steuerelement muss außer Kraft setzen <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (alle existierenden Steuerelemente als Teil des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dazu). Weitere Informationen zu Stilen, Designs und Entwurf von Steuerelementen finden Sie unter [Richtlinien zum Entwerfen formatierbarer Steuerelemente](../../../../docs/framework/wpf/controls/guidelines-for-designing-stylable-controls.md).  
  
 <xref:System.Windows.DataTemplate> Außerdem verfügt über einen impliziten Schlüssel ein. Der implizite Schlüssel für eine <xref:System.Windows.DataTemplate> ist die <xref:System.Windows.DataTemplate.DataType%2A> -Eigenschaftswert. <xref:System.Windows.DataTemplate.DataType%2A> kann auch als Name des Typs angegeben werden, nicht explizit mit [{X: Type...} ](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Weitere Informationen finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.ResourceDictionary>
- [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)
- [Definieren einer Ressource und Verweisen auf eine Ressource](../../../../docs/framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md)
- [x:Type-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md)
- [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
- [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
