---
title: "XAML-Ressourcen | Microsoft Docs"
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
  - "Wiederverwenden von Ressourcen"
  - "Wiederverwenden von Ressourcen"
  - "Wiederverwenden von häufig definierten Objekten"
  - "XAML-Code wiederverwenden von Ressourcen"
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# XAML-Ressourcen
Eine Ressource ist ein Objekt, das an unterschiedlichen Stellen in Ihrer Anwendung wiederverwendet werden kann. Ressourcen gehören beispielsweise Pinsel und Stile. In dieser Übersicht wird beschrieben, wie Ressourcen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Sie können auch Zugriff auf Ressourcen mithilfe von Code oder im Wechsel zwischen Code und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Weitere Informationen finden Sie unter [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md).  
  
> [!NOTE]
>  Die Ressourcendateien, die in diesem Thema beschriebenen unterscheiden die Ressourcendateien in beschriebenen [WPF-Anwendungsressource, Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md) und unterscheidet sich die eingebetteten oder verknüpften Ressourcen, die in beschriebenen [Verwalten von Ressourcen (.NET)](../Topic/Managing%20Application%20Resources%20\(.NET\).md).  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>Verwenden von Ressourcen in XAML  
 Das folgende Beispiel definiert eine <xref:System.Windows.Media.SolidColorBrush> als Ressource für das Stammelement einer Seite. Anschließend verweist auf die Ressource und zum Festlegen der Eigenschaften von mehreren untergeordneten Elementen, einschließlich verwendet ein <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Controls.TextBlock>, und ein <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[FEResourceSH_snip#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 Jedes Element auf Frameworkebene ( <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>) hat eine <xref:System.Windows.FrameworkElement.Resources%2A> -Eigenschaft, die die Eigenschaft ist die Ressourcen enthält (als ein <xref:System.Windows.ResourceDictionary>), die eine Ressource definiert. Sie können Ressourcen für jedes Element definieren. Ressourcen werden jedoch am häufigsten definiert, auf das Root-Element, das <xref:System.Windows.Controls.Page> im Beispiel.  
  
 Jede Ressource in einem Ressourcenverzeichnis muss einen eindeutigen Schlüssel verfügen. Wenn Sie Ressourcen in Markup definieren, weisen Sie den eindeutigen Schlüssel durch die [X: Key-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md). In der Regel ist der Schlüssel eine Zeichenfolge. Allerdings können Sie auch diese für andere Objekttypen festlegen mithilfe der entsprechenden Markuperweiterungen. Nichtzeichenfolgeschlüssel für Ressourcen werden verwendet, indem bestimmte Funktionsbereiche in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], insbesondere für Formatvorlagen, Ressourcen und Daten formatieren.  
  
 Nachdem Sie eine Ressource definiert haben, können Sie die Ressource für einen Eigenschaftswert verwendet werden, mithilfe einer Ressource Markuperweiterungssyntax, die den Schlüsselnamen, z. B. angibt verweisen:  
  
 [!code-xml[FEResourceSH_snip#KeyNameUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 Im vorherigen Beispiel bei der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ladeprogramm verarbeitet den Wert `{StaticResource MyBrush}` für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft auf <xref:System.Windows.Controls.Button>, Suchlogik der Ressource zunächst das Ressourcenwörterbuch auf überprüft die <xref:System.Windows.Controls.Button> Element. Wenn <xref:System.Windows.Controls.Button> keine Definition der Ressourcenschlüssel `MyBrush` (nicht der Fall, der ressourcenauflistung leer ist), die Suche als Nächstes überprüft das übergeordnete Element des <xref:System.Windows.Controls.Button>, also <xref:System.Windows.Controls.Page>. Folglich beim Definieren einer Ressourcenpools auf der <xref:System.Windows.Controls.Page> Root-Element, das alle Elemente in der logischen Struktur der <xref:System.Windows.Controls.Page> darauf zugreifen können, und Sie können die gleiche Ressource wiederverwenden, für den Wert einer Eigenschaft festlegen, akzeptiert der <xref:System.Type> , das die Ressource darstellt. Im vorherigen Beispiel identisch `MyBrush` Ressourcensätze zwei verschiedene Eigenschaften: die <xref:System.Windows.Controls.Control.Background%2A> von einer <xref:System.Windows.Controls.Button>, und die <xref:System.Windows.Shapes.Shape.Fill%2A> von eine <xref:System.Windows.Shapes.Rectangle>.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>Statische und dynamische Ressourcen  
 Eine Ressource kann entweder eine statische Ressource oder eine dynamische Ressource verwiesen werden. Dies erfolgt entweder über die [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) oder [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Eine Markuperweiterung ist ein Feature von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] bei dem Sie einen Objektverweis angeben können, indem die Markuperweiterung die Attributzeichenfolge verarbeitet und das Objekt zum Zurückgeben einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ladeprogramm. Weitere Informationen zum Verhalten von Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Wenn Sie eine Markuperweiterung verwenden, geben Sie in der Regel einen oder mehrere Parameter in Form einer Zeichenfolge, die von dieser speziellen Markuperweiterung verarbeitet werden und nicht im Kontext der festzulegenden Eigenschaft ausgewertet wird. Die [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) verarbeitet einen Schlüssel, indem der Wert für diesen Schlüssel in allen verfügbaren Ressourcenwörterbüchern gesucht. Dies geschieht beim Laden, die die Zeit wird bei der Ladeprozess muss den Wert der Eigenschaft zuweisen, der Verweis auf die statische Ressource akzeptiert. Die [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) stattdessen Prozesse ein Schlüssel durch Erstellen eines Ausdrucks, nicht die Anwendung tatsächlich ausgeführt wird, bis zu diesem Zeitpunkt der Ausdruck wird ausgewertet, und stellt einen Wert bereit.  
  
 Wenn Sie eine Ressource verweisen, können folgende Aspekte beeinflussen, ob Sie einen statischen Ressourcenverweis oder einen dynamischen Ressourcenverweis verwenden:  
  
-   Der allgemeine Entwurf dargestellt, wie Sie die Ressourcen für Ihre Anwendung erstellen (pro Seite, in der Anwendung, in loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in eine einzige Ressourcenassembly).  
  
-   Die Funktionalität der Anwendung: Ressourcen in Echtzeit-Teil der Anforderungen Ihrer Anwendung aktualisiert wird?  
  
-   Das jeweilige Suchverhalten dieses Ressourcentyps Verweis einbezogen.  
  
-   Die betreffende Eigenschaft oder Ressourcentyp und das systemeigene Verhalten dieser Typen.  
  
### <a name="static-resources"></a>Statische Ressourcen  
 Verweise auf statische Ressourcen arbeiten am besten für die folgenden Situationen:  
  
-   Der Anwendungsentwurf konzentriert sich vor allem der Ressourcen in Seiten oder auf Anwendungsebene Wörterbücher. Statische Ressourcenverweise nicht erneut bewertet werden basierend auf der Common Language Runtime-Verhalten wie das erneute Laden einer Seite, und daher werden einige Leistungsvorteil, viele dynamische Verweise zu vermeiden, wenn sie nicht pro Entwurfs Ressource und Anwendung erforderlich sind.  
  
-   Sie legen den Wert einer Eigenschaft, die nicht in einem <xref:System.Windows.DependencyObject> oder <xref:System.Windows.Freezable>.  
  
-   Erstellen Sie ein Ressourcenverzeichnis, die in eine DLL kompiliert und als Teil der Anwendung verpackt oder zwischen Anwendungen freigegeben werden.  
  
-   Sie erstellen ein Design für ein benutzerdefiniertes Steuerelement und definieren Ressourcen, die in den Designs verwendet werden. Für diesen Fall Sie in der Regel nicht möchten, dass das Suchverhalten des dynamischen Verweis an, stattdessen die statische Ressource Verweis Verhalten, damit die Suche vorhersagbare und das Design des eigenständig ist. Bei einem dynamischen Ressourcenverweis Verweis selbst ein Verweis innerhalb eines Designs gelassen wird erst zur Laufzeit ausgewertet, und besteht die Möglichkeit, dass das Design angewendet wird, ein lokales Element einen Schlüssel, den das Design verweisen möchte definieren und das lokale Element greift auf das Design in der Suche vorherige wird. In diesem Fall wird das Design nicht wie erwartet Verhalten.  
  
-   Verwenden Sie Ressourcen, um die große Anzahl von Abhängigkeitseigenschaften festzulegen. Abhängigkeitseigenschaften verfügen über effektive Wert Zwischenspeichern von Eigenschaftenwerten aktiviert, sodass, wenn Sie einen Wert für eine Abhängigkeitseigenschaft bereitstellen, die werden können, zur Ladezeit ausgewertet die Abhängigkeitseigenschaft nicht für einen reevaluated Ausdruck überprüfen muss und kann den letzten effektiven Wert zurück. Diese Technik kann einen Leistungsvorteil bieten.  
  
-   Sollen die zugrunde liegende Ressource für alle Consumer ändern oder separate Instanzen mit Schreibzugriff für jeden einzelnen Consumer mit beibehalten möchten die [X: Shared-Attribut](../../../../docs/framework/xaml-services/x-shared-attribute.md).  
  
#### <a name="static-resource-lookup-behavior"></a>Suchverhalten von statischen Ressourcen  
  
1.  Der Suchprozess prüft den angeforderten Schlüssel in dem Ressourcenwörterbuch, definiert durch das Element, das die Eigenschaft festlegt.  
  
2.  Der Suchprozess durchläuft dann die logische Struktur aufwärts zum übergeordneten Element und seinem Ressourcenwörterbuch. Dies wird fortgesetzt, bis das Stammelement erreicht ist.  
  
3.  Als Nächstes werden die Anwendungsressourcen geprüft. Anwendungsressourcen sind diese Ressourcen in dem Ressourcenwörterbuch, das vom definiert ist die <xref:System.Windows.Application> -Objekt für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  
  
 Statische Ressourcenverweise aus einem Ressourcenwörterbuch müssen auf eine Ressource verweisen, die bereits vor dem Ressourcenverweis lexikalisch definiert wurde. Vorwärtsverweise können nicht von einem statischen Ressourcenverweis aufgelöst werden. Aus diesem Grund Wenn Sie statische Ressourcenverweise verwenden, müssen Sie Struktur des Ressourcenwörterbuchs so entwerfen, dass Ressourcen, die zur Verwendung durch eine Ressource an oder am Anfang der jeweiligen Ressourcenwörterbuchs definiert werden.  
  
 Statische Ressourcensuche kann auf Designs oder die Systemressourcen ausgedehnt, aber dies wird unterstützt, da die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ladeprogramm verzögert die Anforderung. Die Verzögerung ist erforderlich, damit das Common Language Runtime-Design zu dem Zeitpunkt, den Laden der Seite ordnungsgemäß für die Anwendung gilt. Jedoch Ressourcenverweise statische auf Schlüssel nur vorhanden sein, Designs oder als System sind nicht empfehlenswert. Dies ist, da solche Verweise nicht neu ausgewertet werden, wenn der Benutzer in Echtzeit das Design geändert wird. Ein dynamischen Ressourcenverweis ist zuverlässiger, wenn Sie Designs oder Systemressourcen anfordern. Die Ausnahme ist, wenn ein Designelement selbst eine andere Ressource anfordert. Diese Verweise sollten den oben genannten Gründen statische Ressourcenverweise sein.  
  
 Variiert in das Ausnahmeverhalten bei ein statischen Ressourcenverweis nicht gefunden wird. Wenn die Ressource zurückgestellt wurde, tritt die Ausnahme zur Laufzeit. Wenn die Ressource nicht zurückgestellt wurde, tritt die Ausnahme beim Laden.  
  
### <a name="dynamic-resources"></a>Dynamische Ressourcen  
 Dynamische Ressourcen sind am besten für die folgenden Situationen:  
  
-   Der Wert der Ressource hängt von Bedingungen, die nicht erst zur Laufzeit bekannt sind. Dies schließt Systemressourcen oder Ressourcen, die andernfalls vom Benutzer festgelegt sind. Sie können z. B. Setter-Werte, die auf Systemeigenschaften verweisen erstellen, wie von verfügbar gemacht <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>, oder <xref:System.Windows.SystemParameters>. Diese Werte sind wirklich dynamischen, da sie letztlich von der Common Language Runtime-Umgebung des Benutzers und Betriebssystem stammen. Außerdem müssen Sie möglicherweise auf Anwendungsebene Designs, die sich ändern können, in denen Zugriff auf Seitenebene die Änderung ebenfalls erfassen muss.  
  
-   Sie erstellen oder verweisen auf Designstile für ein benutzerdefiniertes Steuerelement.  
  
-   Sie beabsichtigen, passen Sie den Inhalt einer <xref:System.Windows.ResourceDictionary> während der Anwendungslebensdauer einer.  
  
-   Sie haben eine komplizierte Ressource-Struktur, die Abhängigkeiten, aufweist, kann ein Vorwärtsverweis erforderlich sein. Statische Ressourcenverweise unterstützen keine Vorwärtsverweise jedoch dynamische Ressourcenverweise unterstützen, da die Ressource nicht erst zur Laufzeit ausgewertet werden muss, und Vorwärtsverweise sind daher nicht relevante Konzept.  
  
-   Sie verweisen auf eine Ressource, die aus der Perspektive eines kompilieren oder Workingsets besonders groß ist, und die Ressource möglicherweise nicht sofort beim Laden der Seite verwendet werden. Statische Ressourcenverweise werden immer aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beim Laden der Seite, jedoch ein dynamischen Ressourcenverweis wird nicht geladen, bis sie tatsächlich verwendet werden.  
  
-   Sie erstellen eine Formatvorlage Setter-Werte von anderen Werten kommen können, die durch Designs oder anderer benutzereinstellungen beeinflusst werden.  
  
-   Sie wenden Ressourcen auf Elemente, die in der logischen Struktur während der Lebensdauer der Anwendung erneut übergeordnet sein kann. Ändern des übergeordneten Elements möglicherweise auch Suche Ressourcenbereichs ändert, was Sie ggf. die Ressource für einen neuen übergeordneten Element Element erneut ausgewertet werden basierend auf den neuen Bereich immer einen dynamischen Ressourcenverweis.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>Suchverhalten von dynamischen Ressourcen  
 Verhalten bei der Ressourcensuche für einen dynamischen Ressourcenverweis entspricht dem Suchverhalten im Code, wenn Sie aufrufen <xref:System.Windows.FrameworkElement.FindResource%2A> oder <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.  
  
1.  Der Suchprozess prüft den angeforderten Schlüssel in dem Ressourcenwörterbuch, definiert durch das Element, das die Eigenschaft festlegt.  
  
    -   Wenn das Element definiert eine <xref:System.Windows.FrameworkElement.Style%2A> -Eigenschaft, die <xref:System.Windows.Style.Resources%2A> Wörterbuch innerhalb der <xref:System.Windows.Style> aktiviert ist.  
  
    -   Wenn das Element definiert eine <xref:System.Windows.Controls.Control.Template%2A> -Eigenschaft, die <xref:System.Windows.FrameworkTemplate.Resources%2A> Wörterbuch innerhalb der <xref:System.Windows.FrameworkTemplate> aktiviert ist.  
  
2.  Der Suchprozess durchläuft dann die logische Struktur aufwärts zum übergeordneten Element und seinem Ressourcenwörterbuch. Dies wird fortgesetzt, bis das Stammelement erreicht ist.  
  
3.  Als Nächstes werden die Anwendungsressourcen geprüft. Anwendungsressourcen sind diese Ressourcen in dem Ressourcenwörterbuch, das vom definiert ist die <xref:System.Windows.Application> -Objekt für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  
  
4.  Design-Ressourcenverzeichnis wird für das aktuell aktive Design überprüft. Wenn das Design zur Laufzeit ändert, wird der Wert neu ausgewertet.  
  
5.  Ressourcen werden überprüft.  
  
 Ausnahmeverhalten (sofern vorhanden) variiert:  
  
-   Wenn eine Ressource von angefordert wurde eine <xref:System.Windows.FrameworkElement.FindResource%2A> aufrufen und nicht gefunden wurde, wird eine Ausnahme ausgelöst.  
  
-   Wenn eine Ressource, durch angefordert wurde eine <xref:System.Windows.FrameworkElement.TryFindResource%2A> aufrufen und nicht gefunden wurde, wird keine Ausnahme ausgelöst, aber der zurückgegebene Wert ist `null`. Wenn die Eigenschaft akzeptiert keine `null`, ist es dennoch möglich, dass eine tiefere Ausnahme ausgelöst wird (Dies hängt von der jeweiligen Eigenschaft festgelegt wird).  
  
-   Wenn eine Ressource von einem dynamischen Ressourcenverweis in angefordert wurde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und nicht gefunden wurde, und klicken Sie dann das Verhalten hängt von der allgemeinen Eigenschaftensystem, aber das allgemeine Verhalten ist, als ob keine Eigenschaft Einstellung auf der Ebene aufgetreten ist, in dem die Ressource vorhanden ist. Z. B. Wenn Sie versuchen, auf den Hintergrund festlegen einer ein einzelnes Schaltflächenelement mit einer Ressource, die nicht ausgewertet werden konnte, klicken Sie dann kein Wert festgelegt, Ergebnisse, aber der tatsächliche Wert kommen immer noch von anderen Teilnehmern in der Priorität von System- und Wert. Beispielsweise kann dem Wert für den weiterhin von einer lokal definierten Schaltflächenstil oder vom Designstil stammen. Für Eigenschaften, die nicht von Designstile definiert werden, kann der tatsächliche Wert nach einer Evaluierung ausgefallene Ressource vom Standardwert in den Metadaten stammen.  
  
#### <a name="restrictions"></a>Beschränkungen  
 Dynamische Verweise müssen einige wichtige Einschränkungen. Mindestens eine der folgenden muss erfüllt sein:  
  
-   Das Festlegen der-Eigenschaft muss eine Eigenschaft auf einen <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Die Eigenschaft von gesichert werden muss ein <xref:System.Windows.DependencyProperty>.  
  
-   Der Verweis ist für einen Wert innerhalb einer <xref:System.Windows.Style><xref:System.Windows.Setter>.  
  
-   Eigenschaft muss eine Eigenschaft sein, auf eine <xref:System.Windows.Freezable> , dient als entweder den Wert eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> -Eigenschaft, oder ein <xref:System.Windows.Setter> Wert.  
  
 Da die-Eigenschaft festgelegt sein muss ein <xref:System.Windows.DependencyProperty> oder <xref:System.Windows.Freezable> -Eigenschaft, die meisten Eigenschaft können weiterleiten an Benutzeroberfläche, da die Änderung einer Eigenschaft (der Wert des geänderten dynamische Ressourcen) vom Eigenschaftensystem bestätigt wird. Die meisten Steuerelemente enthalten Logik, die ein anderes Layout eines Steuerelements erzwungen wird, wenn ein <xref:System.Windows.DependencyProperty> ändert, und diese Eigenschaft Layout auswirken. Allerdings nicht alle Eigenschaften haben eine [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) als Wert garantiert Mehrwert so, dass sie in Echtzeit in der Benutzeroberfläche aktualisieren. Diese Funktionen kann weiterhin variieren, je nach Eigenschaft sowie je nach Typ, der die Eigenschaft oder sogar die logische Struktur Ihrer Anwendung besitzt.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>Stile, Datenvorlagen und implizite Schlüssel  
 Es wurde bereits angemerkt, dass alle Elemente in einem <xref:System.Windows.ResourceDictionary> muss über einen Schlüssel verfügen. Jedoch das bedeutet nicht, dass alle Ressourcen, eine explizite benötigen `x:Key`. Einige Objekttypen unterstützen einen impliziten Schlüssel, wenn als Ressource definiert, wobei der Schlüssel-Wert auf den Wert einer anderen Eigenschaft gebunden ist. Dies wird als impliziter Schlüssel bezeichnet, während ein `x:Key` -Attribut ist ein expliziter Schlüssel. Sie können jeden impliziten Schlüssel durch Angabe eines expliziten Schlüssels überschreiben.  
  
 Ein sehr wichtiges Szenario für Ressourcen stellt das Definieren einer <xref:System.Windows.Style>. In der Tat ein <xref:System.Windows.Style> wird fast immer als Eintrag in einem Ressourcenwörterbuch definiert, weil Stile grundsätzlich zur Wiederverwendung vorgesehen sind. Weitere Informationen zu Stilen finden Sie unter [von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Stile für Steuerelemente können sowohl mit erstellt und mit einem impliziten Schlüssel verwiesen werden. Die Designstile, die die standarddarstellung eines Steuerelements definieren basieren auf diese impliziten Schlüssel. Der implizite Schlüssel aus Sicht der Anforderung, es ist die <xref:System.Type> des Steuerelements selbst. Aus Sicht der Ressource definieren der implizite Schlüssel ist der <xref:System.Windows.Style.TargetType%2A> des Formats. Daher, wenn Sie Designs für benutzerdefinierte Steuerelemente erstellen, Erstellen von Stilen, die Interaktion mit vorhandenen Designstile, nicht müssen Sie an einer [X: Key-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) , <xref:System.Windows.Style>. Und wenn Sie Designstile verwenden möchten, müssen Sie keines Format angeben. Z. B. die folgenden Formatdefinition funktioniert, obwohl die <xref:System.Windows.Style> Ressource scheint nicht über einen Schlüssel verfügen:  
  
 [!code-xml[FEResourceSH_snip#ImplicitStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 Dieser Stil verfügt tatsächlich über einen Schlüssel: den impliziten Schlüssel `typeof(` <xref:System.Windows.Controls.Button>`)`. Im Markup können Sie angeben einer <xref:System.Windows.Style.TargetType%2A> direkt als Typ name (oder optional können Sie [{X: Type...}](../../../../docs/framework/xaml-services/x-type-markup-extension.md) Zurückgeben einer <xref:System.Type>.  
  
 Über die Standardmechanismen für Designstile verwendeten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], wie die Common Language Runtime-Stil der Stil angewendet wird ein <xref:System.Windows.Controls.Button> auf der Seite, obwohl die <xref:System.Windows.Controls.Button> selbst versucht nicht, geben Sie die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft oder einen bestimmten Ressourcenverweis auf den Stil. Auf der Seite definierte Stil befindet sich weiter oben in der Suchsequenz vor dem Wörterbuch Designstil mithilfe desselben Schlüssels, der dem Wörterbuch Designstil verfügt. Geben Sie einfach `<Button>Hello</Button>` überall auf der Seite und die Formatvorlagen, die Sie mit definiert <xref:System.Windows.Style.TargetType%2A> von `Button` auf diese Schaltfläche angewendet. Wenn Sie möchten, können Sie explizit Schlüssel für den Stil mit demselben Typwert als <xref:System.Windows.Style.TargetType%2A>für Klarheit im Markup, aber optional ist.  
  
 Implizite Schlüssel für Stile werden nicht auf ein Steuerelement angewendet, wenn <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> ist `true` (Beachten Sie, dass <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> als Teil des systemeigenen Verhaltens für den Steuerelementtyp und nicht explizit für eine Instanz des Steuerelements festgelegt werden kann). Darüber hinaus um implizite Schlüssel für abgeleitete zu unterstützen, das Steuerelement muss außer Kraft setzen <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (alle vorhandenen Steuerelemente, die als Teil des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dazu). Weitere Informationen über Stile, Designs und Entwurf von Steuerelementen finden Sie unter [Richtlinien zum Entwerfen formatierbarer Steuerelemente](../../../../docs/framework/wpf/controls/guidelines-for-designing-stylable-controls.md).  
  
 <xref:System.Windows.DataTemplate> verfügt auch über einen impliziten Schlüssel. Der implizite Schlüssel für eine <xref:System.Windows.DataTemplate> ist die <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaftswert.                  <xref:System.Windows.DataTemplate.DataType%2A> kann auch als Name des Typs angegeben werden, nicht explizit mit [{X: Type...} ](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Weitere Informationen finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.ResourceDictionary>   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [Definieren Sie und verweisen auf eine Ressource](../../../../docs/framework/wpf/advanced/how-to-define-and-reference-a-resource.md)   
 [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [X: Type-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)