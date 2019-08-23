---
title: WPF-XAML-Namescopes
ms.date: 03/30/2017
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
ms.openlocfilehash: edf5c8a828bea182cd87542276fb7eb2df1908be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917338"
---
# <a name="wpf-xaml-namescopes"></a>WPF-XAML-Namescopes
XAML-Namescopes sind ein Konzept, das Objekte bezeichnet, die in XAML definiert sind. Die Namen in einem XAML-Namescope können verwendet werden, um Beziehungen zwischen den XAML-definierten Namen der Objekte und ihren Entsprechungen in einer Objektstruktur herzustellen. In der Regel werden XAML-Namescopes in verwaltetem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code beim Laden der einzelnen XAML Seitenstämme für XAML-Anwendungen erstellt. XAML-Namescopes als Programmier Objekt werden von der <xref:System.Windows.Markup.INameScope> -Schnittstelle definiert und auch durch die praktische-Klasse <xref:System.Windows.NameScope>implementiert.  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>Namescopes in geladenen XAML-Anwendungen  
 Im weiter gefassten Kontext der Programmierung oder der Informatik beinhalten Programmierkonzepte oft einen eindeutigen Bezeichner oder Namen, der für den Objektzugriff verwendet werden kann. Für Systeme, die Bezeichner oder Namen verwenden, definiert der Namescope die Grenzen, innerhalb derer ein Prozess oder eine Technik sucht, wenn ein Objekt mit diesem Namen angefordert wird, oder die Grenzen, innerhalb derer die Eindeutigkeit von identifizierenden Namen erzwungen wird. Diese allgemeinen Prinzipien gelten für XAML-Namescopes. In WPF werden XAML-Namescopes für das Stammelement einer XAML-Seite erstellt, wenn die Seite geladen wird. Jeder in der XAML-Seite angegebene Name wird, vom Stammelement ausgehend, einem entsprechenden XAML-Namescope hinzugefügt.  
  
 In WPF-XAML steuern Elemente, die allgemeine Stamm Elemente sind ( <xref:System.Windows.Controls.Page>z. <xref:System.Windows.Window>b. und), immer einen XAML-Namescope. Wenn ein Element, z <xref:System.Windows.FrameworkElement> . <xref:System.Windows.FrameworkContentElement> b. oder, das Stamm Element der Seite im Markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist, fügt <xref:System.Windows.Controls.Page> ein Prozessor implizit einen Stamm <xref:System.Windows.Controls.Page> hinzu, sodass der einen funktionierenden XAML-Namescope bereitstellen kann.  
  
> [!NOTE]
> WPF-Buildvorgänge erstellen für eine XAML-Produktion selbst dann einen XAML-Namescope, wenn für kein Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup `Name`- oder `x:Name`-Attribute definiert sind.  
  
 Wenn Sie versuchen, denselben Namen in einem beliebigen XAML-Namescope zweimal zu verwenden, wird eine Ausnahme ausgelöst. Für WPF-XAML, das CodeBehind verwendet und Teil einer kompilierten Anwendung ist, wird die Ausnahme während der Erstellung durch WPF-Buildaktionen ausgelöst, wenn die generierende Klasse für die Seite während der Kompilierung des ausgehenden Markups erstellt wird. Für XAML, dessen Markup nicht durch Buildaktionen kompiliert wird, können XAML-Namescope-bezogene Ausnahmen während des Ladens des XAML ausgelöst werden. XAML-Designer können XAML-Namescope-Probleme auch zur Entwurfszeit vorausschauend behandeln.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Hinzufügen von Objekten zu Laufzeit-Objektstrukturen  
 Der Zeitpunkt, an dem das XAML analysiert wird, stellt den Zeitpunkt dar, an dem ein WPF-XAML-Namescope erstellt und definiert wird. Wenn Sie ein Objekt zu einer Objektstruktur hinzufügen, nachdem der die Struktur erzeugende XAML-Code analysiert wurde, wird ein `Name`- oder `x:Name`-Wert für das neue Objekt nicht automatisch die Informationen in einem XAML-Namescope aktualisieren. Wenn Sie einen Namen für ein Objekt in einem WPF-XAML-Namescope nach dem Laden von XAML hinzufügen möchten, müssen <xref:System.Windows.Markup.INameScope.RegisterName%2A> Sie die entsprechende Implementierung von für das Objekt, das den XAML-Namescope definiert (in der Regel der XAML-Seiten Stamm), aufruft. Wenn der Name nicht registriert ist, kann auf das hinzugefügte Objekt nicht anhand des Namens über <xref:System.Windows.FrameworkElement.FindName%2A>Methoden wie verwiesen werden, und Sie können diesen Namen nicht für die Animations Ziel-Zielplattform verwenden.  
  
 Das häufigste Szenario für Anwendungsentwickler besteht darin, dass Sie zum <xref:System.Windows.FrameworkElement.RegisterName%2A> Registrieren von Namen im XAML-Namescope im aktuellen Stamm der Seite verwenden. <xref:System.Windows.FrameworkElement.RegisterName%2A>ist Teil eines wichtigen Szenarios für Storyboards, die auf Objekte für Animationen abzielen. Weitere Informationen finden Sie unter [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md).  
  
 Wenn Sie für <xref:System.Windows.FrameworkElement.RegisterName%2A> ein anderes Objekt als das Objekt aufrufen, das den XAML-Namescope definiert, wird der Name weiterhin für den XAML-Namescope registriert, in dem das aufrufende Objekt enthalten ist, <xref:System.Windows.FrameworkElement.RegisterName%2A> als ob Sie für das XAML-Namescope, das das Objekt definiert, aufgerufen hätten.  
  
### <a name="xaml-namescopes-in-code"></a>XAML Namescopes im Code  
 Sie können XAML-Namescopes im Code erstellen und anschließend verwenden. Die an der XAML-Namescope beteiligten APIs und Konzepte sind auch bei reiner Codeverwendung dieselben, da der XAML-Prozessor von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diese APIs und Konzepte beim Verarbeiten des XAML selbst verwendet. Die Aufgaben dieser Konzepte und -APIs sind hauptsächlich, Objekte anhand des Namens innerhalb einer Objektstruktur zu finden, die in der Regel teilweise oder vollständig in XAML definiert ist.  
  
 Bei Anwendungen, die Programm gesteuert erstellt werden, und nicht aus der geladenen XAML-Datei, muss das Objekt, das einen XAML <xref:System.Windows.Markup.INameScope>-Namescope <xref:System.Windows.FrameworkElement> definiert <xref:System.Windows.FrameworkContentElement> , eine oder eine abgeleitete Klasse implementieren, um die Erstellung eines XAML-Namescope in seinem Verein.  
  
 Ebenso gilt, das bei jedem Element, das nicht von einem XAML-Prozessor geladen und verarbeitet wird, der XAML-Namescope für das Objekt standardmäßig nicht erstellt oder initialisiert wird. Sie müssen explizit für jedes Objekt einen neuen XAML-Namescope erstellen, für das Sie anschließend Namen registrieren möchten. Um einen XAML-Namescope zu erstellen, rufen Sie <xref:System.Windows.NameScope.SetNameScope%2A> die statische-Methode auf. Geben Sie das Objekt, dessen Besitzer es ist `dependencyObject` , als den-Parameter <xref:System.Windows.NameScope.%23ctor%2A> und einen neuen `value` konstruktorbefehl als-Parameter an.  
  
 `dependencyObject` Wenn das als für <xref:System.Windows.NameScope.SetNameScope%2A> bereitgestellte Objekt <xref:System.Windows.Markup.INameScope> <xref:System.Windows.FrameworkElement> keine-<xref:System.Windows.FrameworkElement.RegisterName%2A> Implementierung ist, hatdasAufrufenvonfüruntergeordneteElementekeineAuswirkung.<xref:System.Windows.FrameworkContentElement> Wenn Sie den neuen XAML-Namescope nicht explizit erstellen, wird von Aufrufen <xref:System.Windows.FrameworkElement.RegisterName%2A> von eine Ausnahme ausgelöst.  
  
 Ein Beispiel der Verwendung von XAML-Namescope-APIs in Code finden Sie unter [Definieren eines Namensbereichs](../graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>XAML-Namescopes in Stilen und Vorlagen  
 Stile und Vorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten die Möglichkeit, Inhalte auf einfache Weise wieder zu verwenden und sie erneut anzuwenden. Allerdings können Stile und Vorlagen auch Elemente mit XAML-Namen, die auf der Vorlagenebene definiert sind, enthalten. Dieselbe Vorlage wird möglicherweise mehrmals auf einer Seite verwendet. Aus diesem Grund definieren Stile und Vorlagen ihre eigenen XAML-Namescopes, unabhängig davon, an welcher Position in einer Objektstruktur der Stil oder die Vorlage angewendet wird.  
  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Hier wird dieselbe Vorlage auf zwei verschiedene Schaltflächen angewendet. Hätten Vorlagen keine diskreten XAML-Namensbereiche, würde der in der Vorlage verwendete `TheBorder`-Name einen Namenskonflikt im XAML-Namescope verursachen. Jede Vorlageninstanz hat ihren eigenen XAML-Namescope, weshalb in diesem Beispiel der Namescope jeder Instanz der Vorlage genau einen Namen enthält.  
  
 Auch Stile definieren ihre eigenen XAML-Namensbereich. Dies dient vor allem dazu, dass Teilen von Storyboards bestimmte Namen zugewiesen werden können. Diese Namen ermöglichen steuerelementspezifische Verhalten, die auf Elemente dieses Namens selbst dann angewendet werden, wenn die Vorlage als Teil einer Anpassung von Steuerelementen neu definiert wurde.  
  
 Aufgrund der separaten XAML-Namescopes ist die Suche nach benannten Elementen in einer Vorlage schwieriger, als die Suche nach einem ohne Vorlage benannten Element in einer Seite. Sie müssen zuerst die angewendete Vorlage ermitteln, indem Sie <xref:System.Windows.Controls.Control.Template%2A> den Eigenschafts Wert des Steuer Elements, an dem die Vorlage angewendet wird, erhalten. Anschließend wird die Vorlagen Version von <xref:System.Windows.FrameworkTemplate.FindName%2A>aufgerufen, wobei das Steuerelement übergeben wird, in dem die Vorlage als zweiter Parameter angewendet wurde.  
  
 Wenn Sie ein Steuerungs Autor sind und Sie eine Konvention erstellen, bei der ein bestimmtes benanntes Element in einer angewendeten Vorlage das Ziel für ein Verhalten ist, das durch das Steuerelement selbst <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> definiert ist, können Sie die-Methode aus dem Implementierungs Code des Steuer Elements verwenden. Die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> -Methode ist geschützt, sodass nur der Autor des Steuer Elements darauf zugreifen kann.  
  
 Wenn Sie in einer Vorlage arbeiten und den XAML-Namescope abrufen müssen, in dem die Vorlage angewendet wird, können Sie den Wert von <xref:System.Windows.FrameworkElement.TemplatedParent%2A>abrufen und dort anrufen. <xref:System.Windows.FrameworkElement.FindName%2A> Ein Beispiel für das Arbeiten innerhalb der Vorlage wäre, wenn Sie einen Ereignis-Handler dort implementieren möchten, wo das Ereignis von einem Element in einer angewendeten Vorlage ausgelöst wird.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML-Namescopes und namensbezogene APIs  
 <xref:System.Windows.FrameworkElement>verfügt <xref:System.Windows.FrameworkElement.FindName%2A>über <xref:System.Windows.FrameworkElement.RegisterName%2A> die <xref:System.Windows.FrameworkElement.UnregisterName%2A> Methoden, und. Wenn das Objekt, für das Sie diese Methoden aufrufen, einen XAML-Namescope besitzt, rufen die Methoden die Methoden des entsprechenden XAML-Namescopes auf. Andernfalls wird das übergeordnete Element daraufhin überprüft, ob es einen XAML-Namescope besitzt. Dieser Vorgang wird rekursiv fortgesetzt, bis ein XAML-Namescope gefunden wird (wobei Erfolg garantiert ist, da aufgrund des Verhaltens des XAML-Prozessors das Stammelement immer einen XAML-Namescope hat). <xref:System.Windows.FrameworkContentElement>hat analoge Verhalten, mit der Ausnahme, dass <xref:System.Windows.FrameworkContentElement> kein XAML-Namescope besitzen wird. Die-Methoden sind <xref:System.Windows.FrameworkContentElement> in vorhanden, sodass die Aufrufe letztendlich an ein <xref:System.Windows.FrameworkElement> übergeordnetes Element weitergeleitet werden können.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>wird verwendet, um einen neuen XAML-Namescope einem vorhandenen-Objekt zuzuordnen. Sie können mehr <xref:System.Windows.NameScope.SetNameScope%2A> als einmal aufzurufen, um den XAML-Namescope zurückzusetzen oder zu löschen, dies ist jedoch keine häufige Verwendung. <xref:System.Windows.NameScope.GetNameScope%2A> Außerdem wird in der Regel nicht im Code verwendet.  
  
### <a name="xaml-namescope-implementations"></a>Implementierungen von XAML-Namescopes  
 Die folgenden Klassen implementieren <xref:System.Windows.Markup.INameScope> direkt:  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>verwendet keine XAML-Namen oder-Namescopes. Stattdessen werden Schlüssel verwendet, da es sich um eine Wörterbuch Implementierung handelt. Der einzige Grund, <xref:System.Windows.ResourceDictionary> den <xref:System.Windows.Markup.INameScope> implementiert, besteht darin, dass damit Ausnahmen für Benutzercode ausgelöst werden können, um den Unterschied zwischen einem echten XAML- <xref:System.Windows.ResourceDictionary> Namescope und der Handhabung von Schlüsseln zu verdeutlichen und sicherzustellen, dass XAML-Namescopes nicht auf einen <xref:System.Windows.ResourceDictionary> durch übergeordnete Elemente.  
  
 <xref:System.Windows.FrameworkTemplate>und <xref:System.Windows.Style> implementieren<xref:System.Windows.Markup.INameScope> Sie durch explizite Schnittstellendefinitionen. Die expliziten Implementierungen ermöglichen es diesen XAML-Namescopes, sich konsistent zu Verhalten, wenn <xref:System.Windows.Markup.INameScope> über die-Schnittstelle auf Sie zugegriffen wird, sodass XAML- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Namescopes durch interne Prozesse kommuniziert werden. Die expliziten Schnittstellendefinitionen sind jedoch nicht Teil der herkömmlichen API-Ober <xref:System.Windows.FrameworkTemplate> Fläche <xref:System.Windows.Style>von und, da Sie die <xref:System.Windows.Markup.INameScope> Methoden nur selten für <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> direkt aufzurufen müssen und stattdessen eine andere API verwenden müssen. <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>z. b.  
  
 Die folgenden Klassen definieren ihren eigenen XAML-Namescope, indem Sie <xref:System.Windows.NameScope?displayProperty=nameWithType> die-Hilfsklasse verwenden und eine Verbindung mit ihrer XAML-Namescope-Implementierung über die <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> angefügte-Eigenschaft herstellen:  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Namespaces und Namespacezuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [x:Name-Anweisung](../../xaml-services/x-name-directive.md)
