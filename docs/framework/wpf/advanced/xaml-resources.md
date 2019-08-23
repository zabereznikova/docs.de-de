---
title: XAML-Ressourcen
ms.date: 03/30/2017
helpviewer_keywords:
- reusing resources [WPF]
- resources [WPF], reusing
- reusing commonly defined objects [WPF]
- XAML [WPF], reusing resources
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
ms.openlocfilehash: 738a4f397b1677b867126c7bb439b027f951baa0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958818"
---
# <a name="xaml-resources"></a>XAML-Ressourcen
Eine Ressource ist ein Objekt, das an unterschiedlichen Stellen in der Anwendung erneut verwendet werden kann. Beispiele für Ressourcen sind Pinsel und Stile. In dieser Übersicht wird beschrieben, wie Ressourcen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]in verwendet werden. Sie können auch Ressourcen erstellen und auf diese zugreifen, indem Sie Code verwenden oder zwischen Code und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]austauschen. Weitere Informationen finden Sie unter [Ressourcen und Code](resources-and-code.md).  
  
> [!NOTE]
> Die in diesem Thema beschriebenen Ressourcen Dateien unterscheiden sich von den Ressourcen Dateien, die in [WPF-Anwendungs Ressource, Inhalts-und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md) beschrieben werden, und unterscheiden sich von den in [Verwalten von Anwendungs Ressourcen (.net) beschriebenen eingebetteten oder verknüpften Ressourcen. ](/visualstudio/ide/managing-application-resources-dotnet).  

<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>Verwendung von Ressourcen in XAML  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.SolidColorBrush> als Ressource für das Stamm Element einer Seite definiert. Im Beispiel wird dann auf die Ressource verwiesen und zum Festlegen von Eigenschaften mehrerer untergeordneter Elemente verwendet, <xref:System.Windows.Shapes.Ellipse>einschließlich <xref:System.Windows.Controls.TextBlock>,, und <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 Jedes Element auf Frameworkebene <xref:System.Windows.FrameworkContentElement>(<xref:System.Windows.FrameworkElement> oder) <xref:System.Windows.FrameworkElement.Resources%2A> verfügt über eine-Eigenschaft, die die- <xref:System.Windows.ResourceDictionary>Eigenschaft enthält, die die von einer Ressource definierten Ressourcen (als) enthält. Sie können Ressourcen für beliebige Elemente definieren. Allerdings werden Ressourcen am häufigsten für das root-Element definiert, das <xref:System.Windows.Controls.Page> im Beispiel ist.  
  
 Jeder Ressource in einem Ressourcenverzeichnis muss ein eindeutiger Schlüssel zugewiesen werden. Wenn Sie Ressourcen im Markup definieren, weisen Sie den eindeutigen Schlüssel über die [x:Key-Direktive](../../xaml-services/x-key-directive.md)zu. In der Regel ist der Schlüssel eine Zeichenfolge. Sie können jedoch den Schlüssel auch als einen anderen Objekttyp definieren, indem Sie die entsprechenden Markuperweiterungen verwenden. Nicht-Zeichen folgen Schlüssel für Ressourcen werden von bestimmten Featurebereichen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verwendet, insbesondere bei Stilen, Komponenten Ressourcen und Datenformaten.  
  
 Nachdem Sie eine Ressource definiert haben, können Sie einen Eigenschaftswert auf sie verweisen, indem Sie eine Markuperweiterungssyntax für Ressourcen verwenden, die den Schlüsselnamen angibt, zum Beispiel:  
  
 [!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 Wenn [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] im vorherigen Beispiel das Lade Programm den Wert `{StaticResource MyBrush}` für die <xref:System.Windows.Controls.Control.Background%2A> -Eigenschaft auf <xref:System.Windows.Controls.Button>verarbeitet, überprüft die Ressourcen Suchlogik zuerst das Ressourcen Wörterbuch auf <xref:System.Windows.Controls.Button> das-Element. Wenn <xref:System.Windows.Controls.Button> nicht über eine Definition des Ressourcen Schlüssels `MyBrush` verfügt (Dies ist nicht der Fall, die Ressourcensammlung ist leer), überprüft die Suche als nächstes das übergeordnete <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Page>Element von, d. h. Wenn Sie also eine Ressource für das <xref:System.Windows.Controls.Page> Stamm Element definieren, <xref:System.Windows.Controls.Page> können alle Elemente in der logischen Struktur von darauf zugreifen, und Sie können dieselbe Ressource wieder verwenden, um den Wert einer beliebigen Eigenschaft festzulegen, die das <xref:System.Type> -Objekt akzeptiert, das die Ressource ist. Im vorherigen `MyBrush` Beispiel legt die gleiche Ressource zwei unterschiedliche Eigenschaften fest: die <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>und die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle>.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>Statische und dynamische Ressourcen  
 Es kann entweder auf statische oder auf dynamische Ressourcen verwiesen werden. Dies erfolgt mithilfe der [statikresource-Markup Erweiterung](staticresource-markup-extension.md) oder der [dynamikresource-Markup Erweiterung](dynamicresource-markup-extension.md). Eine Markup Erweiterung ist eine Funktion von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , mit der Sie einen Objekt Verweis angeben können, indem die Markup Erweiterung die Attribut Zeichenfolge verarbeitet und das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Objekt an ein Lade Modul zurückgibt. Weitere Informationen zum Markup Erweiterungs Verhalten finden Sie unter [Markup Erweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
 Wenn Sie eine Markuperweiterung verwenden, geben Sie in der Regel einen oder mehrere Parameter im Zeichenfolgenformat an, die von dieser speziellen Markuperweiterung verarbeitet werden, und nicht im Kontext der festzulegenden Eigenschaft ausgewertet werden. Die [statikresource-Markup Erweiterung](staticresource-markup-extension.md) verarbeitet einen Schlüssel, indem er in allen verfügbaren Ressourcen Wörterbüchern den Wert für diesen Schlüssel sucht. Dies geschieht beim Laden, d.h. zu dem Zeitpunkt, während der Ladeprozess dem statischen Ressourcenverweis einen Eigenschaftswert zuweisen muss. Die [dynamikresource-Markup Erweiterung](dynamicresource-markup-extension.md) verarbeitet stattdessen einen Schlüssel, indem ein Ausdruck erstellt wird. dieser Ausdruck wird nicht ausgewertet, bis die Anwendung tatsächlich ausgeführt wird. zu diesem Zeitpunkt wird der Ausdruck ausgewertet und stellt einen Wert bereit.  
  
 Wenn Sie auf eine Ressource verweisen, sind bei der Wahl zwischen einem statischen und einem dynamischen Ressourcenverweis folgende Aspekte zu beachten:  
  
- Der Gesamtentwurf der Art und Weise, wie Sie die Ressourcen für Ihre Anwendung erstellen (pro Seite, in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Anwendung in Lose, in einer reinen Ressourcenassembly).  
  
- Die Funktionalität der Anwendung: ist das Aktualisieren von Ressourcen in Echtzeit ein Teil der Anforderungen an Ihre Anwendung?  
  
- Das Suchverhalten des jeweiligen Ressourcenverweistyps.  
  
- Jeweiliger Eigenschafts- oder Ressourcentyp sowie dessen natives Verhalten.  
  
### <a name="static-resources"></a>Statische Ressourcen  
 Statische Ressourcenverweise funktionieren optimal unter folgenden Bedingungen:  
  
- Der Anwendungsentwurf behandelt die meisten Ressourcen auf der Seiten- oder Anwendungsebene. Statische Ressourcenverweise werden nicht basierend auf dem Laufzeitverhalten neu bewertet, z.B. beim Neuladen einer Seite. Daher kann durch die Verwendung statischer Ressourcenverweise ein Leistungsvorteil erzielt werden, da eine Vielzahl von dynamischen Verweisen vermieden wird, die nicht für Ihren Ressourcen- oder Anwendungsentwurf erforderlich sind.  
  
- Sie legen den Wert einer Eigenschaft fest, die sich nicht in einem <xref:System.Windows.DependencyObject> oder einem <xref:System.Windows.Freezable>befindet.  
  
- Sie erstellen ein Ressourcenverzeichnis, das in eine DLL kompiliert und als ein Teil der Anwendung verpackt oder von mehreren Anwendungen gemeinsam genutzt wird.  
  
- Sie erstellen ein Design für ein benutzerdefiniertes Steuerelement und definieren Ressourcen, die in den Designs verwendet werden. Für diesen Fall ist das Suchverhalten der dynamischen Verweise ungeeignet. Damit das Suchverhalten vorhersagbar und eigenständig für das Design gestaltet werden kann, sind statische Ressourcenverweise vorzuziehen. Dynamische Ressourcenverweise werden bis zur Laufzeit nicht ausgewertet. Es betrifft auch die Verweise innerhalb des Designs. Daher besteht die Möglichkeit, dass bei der Anwendung des Designs ein Schlüssel, auf den das Design zu verweisen versucht, von einem lokalen Element neu definiert wird, und das lokale Element statt des Designs bei der Suche gefunden wird. In diesem Fall wird Ihr Design sich nicht wie erwartet verhalten.  
  
- Ressourcen werden verwendet, um die große Anzahl von Abhängigkeitseigenschaften festzulegen. Abhängigkeitseigenschaften können auf das effektive Zwischenspeichern von Werten des Eigenschaftensystems zugreifen. Wenn Sie einer Abhängigkeitseigenschaft einen Wert bereitstellen, der zur Ladezeit ausgewertet werden kann, ist keine Neuauswertung des Ausdrucks von der Abhängigkeitseigenschaft erforderlich. Sie kann den letzten effektiven Wert zurückgeben. Mit diesem Verfahren kann ein Leistungsvorteil erzielt werden.  
  
- Sie möchten die zugrunde liegende Ressource für alle Consumer ändern, oder Sie möchten separate beschreibbare Instanzen für jeden Consumer mithilfe des [x:Shared-Attributs](../../xaml-services/x-shared-attribute.md)verwalten.  
  
#### <a name="static-resource-lookup-behavior"></a>Suchverhalten von statischen Ressourcen  
  
1. Der Suchprozess prüft den angeforderten Schlüssel im Ressourcenverzeichnis, das durch das Element definiert wird, das die Eigenschaft festlegt.  
  
2. Der Suchprozess durchläuft anschließend die logische Struktur aufwärts, zum übergeordneten Element und seinem Ressourcenverzeichnis. Die Suche wird fortgesetzt, bis das Stammelement erreicht ist.  
  
3. Als nächstes werden die Anwendungsressourcen geprüft. Anwendungs Ressourcen sind Ressourcen innerhalb des Ressourcen Wörterbuchs, das durch das <xref:System.Windows.Application> -Objekt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für die Anwendung definiert wird.  
  
 Statische Ressourcenverweise innerhalb eines Ressourcenverzeichnisses müssen auf eine Ressource verweisen, die bereits vor dem Ressourcenverweis lexikalisch definiert worden ist. Vorwärtsverweise können von einem statischen Ressourcenverweis nicht aufgelöst werden. Wenn Sie statische Ressourcenverweise verwenden, müssen Sie daher die Struktur des Ressourcenverzeichnisses so entwerfen, dass Ressourcen, die durch andere Ressourcen verwendet werden können, zu Beginn der jeweiligen Ressourcenverweise definiert werden.  
  
 Die statische Ressourcen Suche kann in Designs oder Systemressourcen erweitert werden. Dies wird jedoch nur unterstützt, da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] das Lade Modul die Anforderung absetzt. Die Verzögerung ist zwecks einer ordnungsgemäßen Anwendung des Laufzeit-Designs zu dem Zeitpunkt, als die Seite geladen ist, erforderlich. Jedoch ist von statischen Ressourcenverweisen auf Schlüssel abzuraten, die nur in Designs oder als Systemressourcen vorkommen. Der Grund hierfür ist, dass solche Verweise nicht neu ausgewertet werden, falls ein Benutzer das Design in Echtzeit ändert. Dynamische Ressourcenverweise sind zuverlässiger, wenn Sie Designs oder Systemressourcen abfragen. Eine Ausnahme bilden Abfragen, bei denen ein Designelement selbst andere Ressourcen abfragt. Diese Verweise sind aus den oben genannten Gründen als statische Ressourcenverweise zu definieren.  
  
 Falls statistische Verweise nicht gefunden werden, sind verschiedene Ausnahmeverhaltensmuster möglich. Falls die Ressource verzögert wurde, tritt die Ausnahme zur Laufzeit ein. Falls die Ressource nicht verzögert wurde, tritt die Ausnahme zur Ladezeit ein.  
  
### <a name="dynamic-resources"></a>Dynamische Ressourcen  
 Dynamische Ressourcenverweise funktionieren optimal unter folgenden Bedingungen:  
  
- Der Wert der Ressource hängt von Bedingungen ab, die bis zur Laufzeit unbekannt sind. Dies schließt Systemressourcen und Ressourcen ein, die andernfalls vom Benutzer festgelegt werden. Beispielsweise können Sie Setter-Werte erstellen, die auf Systemeigenschaften verweisen, die von <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>oder <xref:System.Windows.SystemParameters>verfügbar gemacht werden. Diese Werte sind wirklich dynamisch, da sie letztlich von der Laufzeitumgebung des Benutzers und dem Betriebssystem stammen. Möglicherweise haben Sie außerdem Designs auf der Anwendungsebene, die sich ändern können, und deren Veränderungen auch vom Ressourcenzugriff auf der Seitenebene erfasst werden müssen.  
  
- Sie erstellen Designstile für ein benutzerdefiniertes Steuerelement oder verweisen darauf.  
  
- Sie beabsichtigen, den Inhalt einer <xref:System.Windows.ResourceDictionary> während der Lebensdauer einer Anwendung anzupassen.  
  
- Sie haben eine komplizierte Ressourcenstruktur mit gegenseitigen Abhängigkeiten, die möglicherweise Vorwärtsverweise erfordert. Statische Ressourcen Verweise unterstützen keine Forward-Verweise, aber dynamische Ressourcen Verweise unterstützen diese, da die Ressource nicht bis zur Laufzeit ausgewertet werden muss und vorwärts Verweise daher kein relevantes Konzept sind.  
  
- Sie verweisen auf eine Ressource, die aus der Perspektive eines kompilieren oder Arbeitssatzes besonders groß ist, und möglicherweise beim Laden der Seite nicht sofort verwendet wird. Statische Ressourcen Verweise werden immer aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] geladen, wenn die Seite geladen wird. ein dynamischer Ressourcen Verweis wird jedoch erst geladen, wenn er tatsächlich verwendet wird.  
  
- Sie erstellen einen Stil, bei dem Setter-Werte von anderen Werten stammen könnten, die durch Designs oder andere Benutzereinstellungen beeinflusst werden.  
  
- Sie ordnen Ressourcen Elementen zu, die in der logischen Struktur während der Lebensdauer der Anwendung neu zugeordnet werden können. Beim erneuten Zuordnen der Elemente wird möglicherweise auch der Ressourcensuchbereich neu definiert. Wenn Sie wollen, dass die Ressource für ein neu zugeordnetes Element entsprechend dem neuen Suchbereich neu ausgewertet wird, verwenden Sie immer einen dynamischen Ressourcenverweis.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>Suchverhalten von dynamischen Ressourcen  
 Das Suchverhalten des Ressourcen Suchvorgangs für einen dynamischen Ressourcen Verweis ist mit dem Suchverhalten in Ihrem Code <xref:System.Windows.FrameworkElement.FindResource%2A> vergleichbar <xref:System.Windows.FrameworkElement.SetResourceReference%2A>, wenn Sie oder aufruft.  
  
1. Der Suchprozess prüft den angeforderten Schlüssel im Ressourcenverzeichnis, das durch das Element definiert wird, das die Eigenschaft festlegt.  
  
    - Wenn das-Element eine <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft definiert, <xref:System.Windows.Style.Resources%2A> wird das Wörter <xref:System.Windows.Style> Buch in der geprüft.  
  
    - Wenn das-Element eine <xref:System.Windows.Controls.Control.Template%2A> Eigenschaft definiert, <xref:System.Windows.FrameworkTemplate.Resources%2A> wird das Wörter <xref:System.Windows.FrameworkTemplate> Buch in der geprüft.  
  
2. Der Suchprozess durchläuft anschließend die logische Struktur aufwärts, zum übergeordneten Element und dessen Ressourcenverzeichnis. Die Suche wird fortgesetzt, bis das Stammelement erreicht ist.  
  
3. Als nächstes werden die Anwendungsressourcen geprüft. Anwendungs Ressourcen sind Ressourcen innerhalb des Ressourcen Wörterbuchs, das durch das <xref:System.Windows.Application> -Objekt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für die Anwendung definiert wird.  
  
4. Das Ressourcenverzeichnis des Designs wird für das derzeit aktive Design überprüft. Falls das Design zur Laufzeit geändert wird, wird der Wert neu ausgewertet.  
  
5. Systemressourcen werden geprüft.  
  
 Es sind verschiedene Ausnahmeverhaltensmuster möglich (sofern sie auftreten):  
  
- Wenn eine Ressource von einem <xref:System.Windows.FrameworkElement.FindResource%2A> -Befehl angefordert wurde und nicht gefunden wurde, wird eine-Ausnahme ausgelöst.  
  
- Wenn eine Ressource von einem <xref:System.Windows.FrameworkElement.TryFindResource%2A> -Befehl angefordert wurde und nicht gefunden wurde, wird keine Ausnahme ausgelöst, aber der zurückgegebene Wert ist. `null` Wenn die festgelegte Eigenschaft nicht akzeptiert `null`, ist es immer noch möglich, dass eine tiefere Ausnahme ausgelöst wird (Dies hängt davon ab, welche einzelne Eigenschaft festgelegt wird).  
  
- Wenn eine Ressource von einem dynamischen Ressourcen Verweis in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]angefordert wurde und nicht gefunden wurde, hängt das Verhalten vom allgemeinen Eigenschaften System ab. das allgemeine Verhalten ist jedoch so, als ob kein Eigenschafts Einstellungs Vorgang auf der Ebene aufgetreten ist, auf der die Ressource vorhanden ist. Wenn Sie z.B. versuchen, den Hintergrund eines einzelnen Schaltflächenelements mit einer Ressource festzulegen, die nicht ausgewertet werden konnte, wird als Ergebnis kein Wert festgelegt. Ein effektiver Wert kann aber dennoch von anderen Teilnehmern im Eigenschaftssystem und in der Wertrangfolge bereitgestellt werden. Beispielsweise kann der Wert für den Hintergrund von einem lokal definierten Schaltflächenstil oder vom Design-Stil zurückgegeben werden. Für Eigenschaften, die nicht von Design-Stilen definiert werden, kann nach einer fehlgeschlagenen Auswertung der Standardwert aus den Eigenschaftenmetadaten als effektiver Wert übernommen werden.  
  
#### <a name="restrictions"></a>Restrictions  
 Die Verwendung dynamischer Verweise ist mit einigen wichtigen Beschränkungen verbunden. Mindestens eine der folgenden Bedingungen muss erfüllt sein:  
  
- Die Eigenschaft, die festgelegt wird, muss eine <xref:System.Windows.FrameworkElement> Eigenschaft <xref:System.Windows.FrameworkContentElement>in einem oder sein. Diese Eigenschaft muss von einem <xref:System.Windows.DependencyProperty>unterstützt werden.  
  
- Der Verweis bezieht sich auf einen Wert in <xref:System.Windows.Style>einer <xref:System.Windows.Setter>.  
  
- Die festgelegte Eigenschaft muss eine <xref:System.Windows.Freezable> Eigenschaft für eine sein, die als Wert <xref:System.Windows.FrameworkElement> einer-Eigenschaft oder <xref:System.Windows.FrameworkContentElement> -Eigenschaft oder eines <xref:System.Windows.Setter> -Werts bereitgestellt wird.  
  
 Da die festgelegte Eigenschaft eine <xref:System.Windows.DependencyProperty> -Eigenschaft oder <xref:System.Windows.Freezable> -Eigenschaft sein muss, können die meisten Eigenschafts Änderungen an die Benutzeroberfläche weitergegeben werden, da eine Eigenschafts Änderung (der geänderte dynamische Ressourcen Wert) vom-Eigenschaften System bestätigt wird. Die meisten Steuerelemente enthalten eine Logik, die ein anderes Layout eines Steuer <xref:System.Windows.DependencyProperty> Elements erzwingt, wenn eine geändert wird und diese Eigenschaft das Layout beeinflussen kann. Allerdings bieten nicht alle Eigenschaften, die über eine [dynamikresource-Markup Erweiterung](dynamicresource-markup-extension.md) als Wert verfügen, sicher, dass der Wert auf eine Weise bereitgestellt wird, in der Sie in Echtzeit auf der Benutzeroberfläche aktualisiert werden. Diese Funktionalität kann dennoch variieren, abhängig sowohl von der Eigenschaft als auch vom Typ, der die Eigenschaft besitzt oder sogar von der logischen Struktur Ihrer Anwendung.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>Stile, Datenvorlagen und implizite Schlüssel  
 Früher wurde angegeben, dass alle Elemente in einem <xref:System.Windows.ResourceDictionary> über einen Schlüssel verfügen müssen. Dies bedeutet jedoch nicht, dass alle Ressourcen über eine explizite `x:Key`verfügen müssen. Manche Objekttypen unterstützen einen impliziten Schlüssel, wenn sie als Ressourcen definiert sind, wobei der Schlüsselwert an den Wert einer anderen Eigenschaft gebunden ist. Dies wird als impliziter Schlüssel bezeichnet, während `x:Key` ein Attribut ein expliziter Schlüssel ist. Sie können jegliche implizite Schlüssel durch die Angabe eines expliziten Schlüssels überschreiben.  
  
 Ein sehr wichtiges Szenario für Ressourcen ist, wenn Sie einen <xref:System.Windows.Style>definieren. Tatsächlich ist eine <xref:System.Windows.Style> fast immer als Eintrag in einem Ressourcen Wörterbuch definiert, da Stile grundsätzlich für die Wiederverwendung bestimmt sind. Weitere Informationen zu Stilen finden Sie unter Erstellen von Formaten [und](../controls/styling-and-templating.md)Vorlagen.  
  
 Mit einem impliziten Schlüssel können Stile für Steuerelemente erstellt werden, und es kann damit auf sie verwiesen werden. Die Design-Stile, die die Standarddarstellung eines Steuerelements definieren, basieren auf diesen impliziten Schlüsseln. Der implizite Schlüssel aus der Sicht der Anforderung ist der <xref:System.Type> des Steuer Elements selbst. Der implizite Schlüssel aus der Sicht der Definition der Ressource ist der <xref:System.Windows.Style.TargetType%2A> des Stils. Wenn Sie Designs für benutzerdefinierte Steuerelemente erstellen und Stile erstellen, die mit vorhandenen Designstilen interagieren, müssen Sie daher keine [x:Key-Direktive](../../xaml-services/x-key-directive.md) <xref:System.Windows.Style>angeben. Und wenn Sie die Design-Stile verwenden möchten, müssen Sie gar keinen Stil angeben. Beispielsweise funktioniert die folgende Format Definition, obwohl die <xref:System.Windows.Style> Ressource anscheinend keinen Schlüssel hat:  
  
 [!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 Dieser Stil hat tatsächlich einen Schlüssel: den impliziten Schlüssel `typeof(`. <xref:System.Windows.Controls.Button> `)` In Markup können Sie einen <xref:System.Windows.Style.TargetType%2A> direkt als Typnamen angeben (oder Sie können optional [{x:Type...}](../../xaml-services/x-type-markup-extension.md) verwenden. , um einen <xref:System.Type>zurückzugeben.  
  
 Mithilfe der von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verwendeten Standardverfahren für Designstile wird dieser Stil als Lauf Zeit Stil <xref:System.Windows.Controls.Button> eines auf der Seite angewendet, auch wenn der <xref:System.Windows.Controls.Button> selbst nicht versucht, seine <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft oder eine bestimmte Ressource anzugeben. Verweis auf den Stil. Ihr Stil, der auf der Seite definiert ist, wurde bereits in der Such Sequenz als der Design wörtertyp gefunden. dabei wird derselbe Schlüssel verwendet, den der Stil des Design Wörterbuchs besitzt. Sie können einfach an `<Button>Hello</Button>` einer `Button` beliebigen Stelle auf der Seite angeben, und der Stil <xref:System.Windows.Style.TargetType%2A> , den Sie mit definiert haben, gilt für diese Schaltfläche. Wenn Sie möchten, können Sie den Stil weiterhin explizit mit dem gleichen Typwert wie <xref:System.Windows.Style.TargetType%2A>, aus Gründen der Übersichtlichkeit in Ihrem Markup, aber optional.  
  
 Implizite Schlüssel für Stile gelten nicht für ein Steuerelement, <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> Wenn `true` ist (Beachten Sie <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> auch, dass möglicherweise als Teil des nativen Verhaltens für die Steuerelement Klasse und nicht explizit für eine Instanz des Steuer Elements festgelegt wird). Um implizite Schlüssel für abgeleitete Klassen Szenarios zu unterstützen, muss das Steuerelement <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> auch überschreiben (alle vorhandenen Steuerelemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , die im Rahmen dieses Szenarios bereitgestellt werden). Weitere Informationen zu Stilen, Designs und Steuerelementen finden Sie unter [Richtlinien zum Entwerfen von Formatierbaren Steuerelementen](../controls/guidelines-for-designing-stylable-controls.md).  
  
 <xref:System.Windows.DataTemplate>verfügt auch über einen impliziten Schlüssel. Der implizite Schlüssel für einen <xref:System.Windows.DataTemplate> ist der <xref:System.Windows.DataTemplate.DataType%2A> Eigenschafts Wert. <xref:System.Windows.DataTemplate.DataType%2A>kann auch als Name des Typs angegeben werden, anstatt explizit [{x:Type...}](../../xaml-services/x-type-markup-extension.md)zu verwenden. Weitere Informationen finden Sie unter [Übersicht über Daten](../data/data-templating-overview.md)Vorlagen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ResourceDictionary>
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Ressourcen und Code](resources-and-code.md)
- [Definieren einer Ressource und Verweisen auf eine Ressource](how-to-define-and-reference-a-resource.md)
- [Übersicht über die Anwendungsverwaltung](../app-development/application-management-overview.md)
- [x:Type-Markuperweiterung](../../xaml-services/x-type-markup-extension.md)
- [StaticResource-Markuperweiterung](staticresource-markup-extension.md)
- [DynamicResource-Markuperweiterung](dynamicresource-markup-extension.md)
