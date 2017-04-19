---
title: "WPF-XAML-Namescopes | Microsoft Docs"
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
  - "APIs, Namensbezogen"
  - "Klassen, FrameworkContentElement"
  - "Klassen, FrameworkElement"
  - "Klassen, RegisterName"
  - "FrameworkContentElement-Klasse"
  - "FrameworkElement-Klasse"
  - "Namensbezogene APIs"
  - "Namensbereiche"
  - "RegisterName-Klasse"
  - "Formate, Namensbereiche in"
  - "Vorlagen, Namensbereiche in"
  - "XAML, Namensbereiche"
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# WPF-XAML-Namescopes
XAML\-Namensbereiche sind ein Konzept zum Identifizieren von Objekten, die in XAML definiert sind.  Die Namen in einem XAML\-Namensbereich können verwendet werden, um Beziehungen zwischen den in XAML definierten Namen von Objekten und ihren Instanzentsprechungen in einer Objektstruktur herzustellen.  In der Regel werden XAML\-Namensbereiche in verwaltetem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Code beim Laden der einzelnen XAML\-Seitenstämme für eine XAML\-Anwendung erstellt.  XAML\-Namescopes als Programmierobjekte werden von der <xref:System.Windows.Markup.INameScope>\-Schnittstelle definiert und zudem von der praktischen Klasse <xref:System.Windows.NameScope> implementiert.  
  
   
  
<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## Namescopes in geladenen XAML\-Anwendungen  
 In einem breiteren Programmierungs\- oder Informatikkontext schließen Programmierungskonzepte oft das Prinzip eines eindeutigen Bezeichners oder Namens ein, der zum Zugriff auf ein Objekt verwendet werden kann.  Für Systeme, die Bezeichner oder Namen verwenden, definiert der Namensbereich die Grenzen des Bereichs, in dem ein Prozess oder eine Technik sucht, wenn ein Objekt mit diesem Namen angefordert wird, oder die Grenzen, innerhalb derer die Eindeutigkeit von identifizierenden Namen erzwungen wird.  Diese allgemeinen Prinzipien gelten für XAML\-Namensbereiche.  In WPF werden XAML\-Namensbereiche im Stammelement für eine XAML\-Seite erstellt, wenn die Seite geladen wird.  Jeder Name, der beginnend beim Seitenstamm in der XAML\-Seite angegeben ist, wird einem entsprechenden XAML\-Namensbereich hinzugefügt.  
  
 In WPF\-XAML steuern Elemente, bei denen es sich um allgemeine Stammelemente handelt \(z. B. <xref:System.Windows.Controls.Page> und <xref:System.Windows.Window>\), immer einen XAML\-Namensbereich.  Wenn ein Element wie <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> das Stammelement der Seite im Markup ist, fügt ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor implizit einen <xref:System.Windows.Controls.Page>\-Stamm hinzu, sodass die <xref:System.Windows.Controls.Page> einen funktionsfähigen XAML\-Namensbereich bereitstellen kann.  
  
> [!NOTE]
>  Bei WPF\-Buildvorgängen wird auch dann ein XAML\-Namensbereich für eine XAML\-Produktion erstellt, wenn keine `Name`\- oder `x:Name`\-Attribute für Elemente im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup definiert sind.  
  
 Wenn Sie versuchen, denselben Namen zweimal in einem XAML\-Namescope zu verwenden, wird eine Ausnahme ausgelöst.  Für WPF\-XAML, das CodeBehind enthält und Teil einer kompilierten Anwendung ist, wird die Ausnahme von WPF\-Buildvorgängen ausgelöst, wenn die generierte Klasse für die Seite während der ersten Markupkompilierung erstellt wird.  Für XAML, das nicht von einem Buildvorgang markupkompiliert wird, können Ausnahmen zu Problemen mit dem XAML\-Namensbereich beim Laden des XAML ausgelöst werden.  XAML\-Designer können auch zur Entwurfszeit Probleme mit dem XAML\-Namensbereich erwarten.  
  
### Hinzufügen von Objekten zu Laufzeitobjektstrukturen  
 Der Zeitpunkt, zu dem XAML analysiert wird, stellt den Zeitpunkt dar, zu dem ein WPF\-XAML\-Namensbereich erstellt und definiert wird.  Wenn Sie einer Objektstruktur nach dem Analysieren des XAML, von dem diese Struktur erzeugt wurde, ein Objekt hinzufügen, werden die Informationen in einem XAML\-Namensbereich nicht automatisch mit einem `Name`\- oder `x:Name`\-Wert für das neue Objekt aktualisiert.  Um nach dem Laden des XAML einen Namen für ein Objekt in einem XAML\-Namensbereich hinzuzufügen, muss die entsprechende Implementierung von <xref:System.Windows.Markup.INameScope.RegisterName%2A> für das Objekt aufgerufen werden, das den XAML\-Namensbereich definiert. Normalerweise ist dies der Stamm der XAML\-Seite.  Wenn der Name nicht registriert ist, kann in Methoden wie <xref:System.Windows.FrameworkElement.FindName%2A> nicht anhand des Namens auf das hinzugefügte Objekt verwiesen werden, und der Name kann nicht als Animationsziel verwendet werden.  
  
 Das häufigste Szenario bei der Anwendungsentwicklung stellt die Registrierung von Namen im XAML\-Namescope auf dem aktuellen Stamm der Seite mithilfe von <xref:System.Windows.FrameworkElement.RegisterName%2A> dar.  <xref:System.Windows.FrameworkElement.RegisterName%2A> ist Teil eines wichtigen Szenarios für Storyboards, in denen Objekte als Animationsziel verwendet werden.  Weitere Informationen finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Wenn Sie <xref:System.Windows.FrameworkElement.RegisterName%2A> für ein anderes Objekt als das Objekt aufrufen, das den XAML\-Namensbereich definiert, wird der Name wie beim Aufrufen von <xref:System.Windows.FrameworkElement.RegisterName%2A> für das Objekt, das den XAML\-Namensbereich definiert, dennoch im XAML\-Namensbereich registriert, in dem das aufrufende Objekt enthalten ist.  
  
### XAML\-Namescopes in Code  
 Sie können XAML\-Namescopes erstellen und dann im Code verwenden.  Die APIs und Konzepte im Zusammenhang mit der Erstellung von XAML\-Namensbereichen gelten auch für die reine Codeverwendung, da der XAML\-Prozessor für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diese APIs und Konzepte beim Verarbeiten des XAML selbst verwendet.  Der primäre Zweck der Konzepte und der API ist es, die Objektsuche anhand des Namens innerhalb einer Objektstruktur zu ermöglichen, die normalerweise teilweise oder vollständig in XAML definiert ist.  
  
 Bei Anwendungen, die programmgesteuert erstellt und nicht über XAML geladen werden, muss das Objekt, das einen XAML\-Namensbereich definiert, <xref:System.Windows.Markup.INameScope> implementieren oder eine abgeleitete <xref:System.Windows.FrameworkElement>\- oder <xref:System.Windows.FrameworkContentElement>\-Klasse sein, um die Erstellung eines XAML\-Namensbereichs für die zugehörigen Instanzen zu unterstützen.  
  
 Zudem wird für jedes Element, das nicht von einem XAML\-Prozessor geladen und verarbeitet wird, der XAML\-Namensbereich für das Objekt nicht standardmäßig erstellt oder initialisiert.  Für jedes Objekt, in dem anschließend Namen registriert werden sollen, muss explizit ein neuer XAML\-Namensbereich erstellt werden.  Um einen XAML\-Namescope zu erstellen, rufen Sie die statische <xref:System.Windows.NameScope.SetNameScope%2A>\-Methode auf.  Geben Sie das Objekt, das der Besitzer davon ist, als `dependencyObject`\-Parameter und einen neuen <xref:System.Windows.NameScope.%23ctor%2A>\-Konstruktoraufruf als `value`\-Parameter an.  
  
 Wenn es sich bei dem als `dependencyObject` für <xref:System.Windows.NameScope.SetNameScope%2A> bereitgestellten Objekt nicht um eine <xref:System.Windows.Markup.INameScope>\-Implementierung, ein <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.FrameworkContentElement> handelt, hat das Aufrufen von <xref:System.Windows.FrameworkElement.RegisterName%2A> für untergeordnete Elemente keine Auswirkungen.  Wenn Sie den neuen XAML\-Namescope nicht explizit erstellen, wird durch Aufrufe von <xref:System.Windows.FrameworkElement.RegisterName%2A> eine Ausnahme ausgelöst.  
  
 Ein Beispiel zur Verwendung von XAML\-Namensbereich\-APIs in Code finden Sie unter [Definieren eines Namensbereichs](../../../../docs/framework/wpf/graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## XAML\-Namescopes in Stilen und Vorlagen  
 Stile und Vorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten die Möglichkeit, Inhalt auf einfache Weise wiederzuverwenden und erneut anzuwenden.  Stile und Vorlagen können jedoch auch Elemente mit XAML\-Namen enthalten, die auf der Vorlagenebene definiert sind.  Dieselbe Vorlage kann in einer Seite mehrmals verwendet werden.  Aus diesem Grund definieren Stile und Vorlagen unabhängig von der Position, an der sie in einer Objektstruktur angewendet werden, ihre eigenen XAML\-Namensbereiche.  
  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-xml[XamlOvwSupport#NameScopeTemplates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Hier wird dieselbe Vorlage auf zwei verschiedene Schaltflächen angewendet.  Wenn Vorlagen keine diskreten XAML\-Namensbereiche enthalten würden, würde der in der Vorlage verwendete `TheBorder`\-Name einen Namenskonflikt im XAML\-Namensbereich verursachen.  Jede Instanziierung der Vorlage verfügt über einen eigenen XAML\-Namescope, sodass in diesem Beispiel der XAML\-Namescope jeder instanziierten Vorlage genau einen Namen enthält.  
  
 Auch Stile definieren einen eigenen XAML\-Namescope, und zwar in der Regel so, dass Teilen von Storyboards bestimmte Namen zugewiesen werden können.  Diese Namen ermöglichen steuerelementspezifische Verhalten, die sich auf Elemente mit diesem Namen beziehen, selbst wenn die Vorlage im Zusammenhang mit einer Anpassung von Steuerelementen neu definiert wurde.  
  
 Aufgrund der separaten XAML\-Namescopes ist die Suche nach benannten Elementen in einer Vorlage schwieriger als die Suche nach einem benannten Element in einer Seite, das nicht auf einer Vorlage basiert.  Sie müssen die angewendete Vorlage zunächst durch Abrufen des <xref:System.Windows.Controls.Control.Template%2A>\-Eigenschaftswerts des Steuerelements festlegen, auf das die Vorlage angewendet wird.  Anschließend rufen Sie die Vorlagenversion von <xref:System.Windows.FrameworkTemplate.FindName%2A> auf und übergeben das Steuerelement, auf das die Vorlage als zweiter Parameter angewendet wurde.  
  
 Wenn Sie Autor eines Steuerelements sind und eine Konvention erstellen, in der ein bestimmtes benanntes Element in einer angewendeten Vorlage das Ziel für ein Verhalten darstellt, das vom Steuerelement selbst definiert wird, können Sie die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>\-Methode aus dem Code zur Implementierung des Steuerelements verwenden.  Die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>\-Methode ist geschützt, sodass nur der Steuerelementautor Zugriff darauf hat.  
  
 Wenn Sie in einer Vorlage arbeiten und den XAML\-Namescope abrufen müssen, auf den die Vorlage angewendet wird, rufen Sie den Wert von <xref:System.Windows.FrameworkElement.TemplatedParent%2A> ab, und rufen Sie dort dann <xref:System.Windows.FrameworkElement.FindName%2A> auf.  Ein Beispiel für das Arbeiten innerhalb der Vorlage wäre das Schreiben der Ereignishandlerimplementierung, wobei das Ereignis von einem Element in einer angewendeten Vorlage ausgelöst wird.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## XAML\-Namescopes und namensbezogene APIs  
 <xref:System.Windows.FrameworkElement> verfügt über <xref:System.Windows.FrameworkElement.FindName%2A>\-, <xref:System.Windows.FrameworkElement.RegisterName%2A>\- und <xref:System.Windows.FrameworkElement.UnregisterName%2A>\-Methoden.  Falls das Objekt, für das diese Methoden aufgerufen werden, über einen XAML\-Namescope verfügt, werden die Methoden einfach in den Methoden des relevanten XAML\-Namescopes aufgerufen.  Andernfalls wird das übergeordnete Element daraufhin überprüft, ob es über einen XAML\-Namensbereich verfügt, und dieser Prozess wird rekursiv fortgesetzt, bis ein XAML\-Namensbereich gefunden wird \(aufgrund des Verhaltens des XAML\-Prozessors befindet sich am Stamm immer ein XAML\-Namensbereich\).  Ein <xref:System.Windows.FrameworkContentElement>\-Element hat analoge Verhaltensweisen, wobei jedoch ein <xref:System.Windows.FrameworkContentElement>\-Element niemals über einen XAML\-Namescope verfügt.  Die Methoden befinden sich auf <xref:System.Windows.FrameworkContentElement>, sodass die Aufrufe schließlich an ein übergeordnetes <xref:System.Windows.FrameworkElement>\-Element weitergeleitet werden können.  
  
 Mit <xref:System.Windows.NameScope.SetNameScope%2A> wird einem vorhandenen Objekt ein neuer XAML\-Namescope zugeordnet.  Sie können <xref:System.Windows.NameScope.SetNameScope%2A> mehrmals aufrufen, um den XAML\-Namescope zurückzusetzen oder zu löschen, diese Verwendung ist jedoch nicht üblich.  Auch <xref:System.Windows.NameScope.GetNameScope%2A> wird in der Regel nicht über Code verwendet.  
  
### XAML\-Namescope\-Implementierungen  
 Die folgenden Klassen implementieren <xref:System.Windows.Markup.INameScope> direkt:  
  
-   <xref:System.Windows.NameScope>  
  
-   <xref:System.Windows.Style>  
  
-   <xref:System.Windows.ResourceDictionary>  
  
-   <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary> verwendet Schlüssel anstelle von XAML\-Namen oder \-Namescopes, da es die Implementierung eines Wörterbuchs ist.  <xref:System.Windows.ResourceDictionary> implementiert <xref:System.Windows.Markup.INameScope> nur deshalb, um Ausnahmen für Benutzercode auslösen zu können, die den Unterschied zwischen einem wahren XAML\-Namescope und der Verwendung von Schlüsseln durch <xref:System.Windows.ResourceDictionary> verdeutlichen, und um sicherzustellen, dass XAML\-Namescopes nicht durch übergeordnete Elemente auf ein <xref:System.Windows.ResourceDictionary> angewendet werden.  
  
 <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> implementieren <xref:System.Windows.Markup.INameScope> durch explizite Schnittstellendefinitionen.  Die expliziten Implementierungen ermöglichen ein konventionelles Verhalten dieser XAML\-Namescopes, wenn über die <xref:System.Windows.Markup.INameScope>\-Schnittstelle auf sie zugegriffen wird. Auf diese Weise werden XAML\-Namescopes durch interne [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Prozesse übermittelt.  Die expliziten Schnittstellendefinitionen sind jedoch nicht Teil der konventionellen API\-Schnittstelle von <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style>, da die <xref:System.Windows.Markup.INameScope>\-Methoden für <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> nur selten direkt aufgerufen werden müssen. Stattdessen wird gewöhnlich <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> verwendet.  
  
 Folgende Klassen definieren ihren eigenen XAML\-Namescope, indem sie die <xref:System.Windows.NameScope?displayProperty=fullName>\-Hilfsklasse verwenden und über die angefügte <xref:System.Windows.NameScope.NameScope%2A?displayProperty=fullName>\-Eigenschaft eine Verbindung zur XAML\-Namescope\-Implementierung herstellen:  
  
-   <xref:System.Windows.FrameworkElement>  
  
-   <xref:System.Windows.FrameworkContentElement>  
  
## Siehe auch  
 [XAML\-Namespaces und Namespacezuordnung für WPF\-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)   
 [x:Name\-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md)