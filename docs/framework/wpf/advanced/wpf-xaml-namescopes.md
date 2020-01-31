---
title: XAML-Namescopes
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
ms.openlocfilehash: 4383492157191f61cf04a2fdd6ce27e9183bda8b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744417"
---
# <a name="wpf-xaml-namescopes"></a>WPF-XAML-Namescopes
XAML-Namescopes sind ein Konzept, das Objekte bezeichnet, die in XAML definiert sind. Die Namen in einem XAML-Namescope können verwendet werden, um Beziehungen zwischen den XAML-definierten Namen der Objekte und ihren Entsprechungen in einer Objektstruktur herzustellen. In der Regel werden XAML-Namescopes in verwaltetem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code beim Laden der einzelnen XAML Seitenstämme für XAML-Anwendungen erstellt. XAML-Namescopes als Programmier Objekt werden durch die <xref:System.Windows.Markup.INameScope>-Schnittstelle definiert und auch durch die praktische Klasse <xref:System.Windows.NameScope>implementiert.  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>Namescopes in geladenen XAML-Anwendungen  
 Im weiter gefassten Kontext der Programmierung oder der Informatik beinhalten Programmierkonzepte oft einen eindeutigen Bezeichner oder Namen, der für den Objektzugriff verwendet werden kann. Für Systeme, die Bezeichner oder Namen verwenden, definiert der Namescope die Grenzen, innerhalb derer ein Prozess oder eine Technik sucht, wenn ein Objekt mit diesem Namen angefordert wird, oder die Grenzen, innerhalb derer die Eindeutigkeit von identifizierenden Namen erzwungen wird. Diese allgemeinen Prinzipien gelten für XAML-Namescopes. In WPF werden XAML-Namescopes für das Stammelement einer XAML-Seite erstellt, wenn die Seite geladen wird. Jeder in der XAML-Seite angegebene Name wird, vom Stammelement ausgehend, einem entsprechenden XAML-Namescope hinzugefügt.  
  
 In WPF-XAML steuern Elemente, bei denen es sich um allgemeine Stamm Elemente handelt (z. b. <xref:System.Windows.Controls.Page>und <xref:System.Windows.Window>), immer einen XAML-Namescope. Wenn ein Element, z. b. <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, das Stamm Element der Seite in Markup ist, fügt ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor einen <xref:System.Windows.Controls.Page> Stamm implizit hinzu, damit der <xref:System.Windows.Controls.Page> einen funktionierenden XAML-Namescope bereitstellen kann.  
  
> [!NOTE]
> WPF-Buildvorgänge erstellen für eine XAML-Produktion selbst dann einen XAML-Namescope, wenn für kein Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup `Name`- oder `x:Name`-Attribute definiert sind.  
  
 Wenn Sie versuchen, denselben Namen in einem beliebigen XAML-Namescope zweimal zu verwenden, wird eine Ausnahme ausgelöst. Für WPF-XAML, das CodeBehind verwendet und Teil einer kompilierten Anwendung ist, wird die Ausnahme während der Erstellung durch WPF-Buildaktionen ausgelöst, wenn die generierende Klasse für die Seite während der Kompilierung des ausgehenden Markups erstellt wird. Für XAML, dessen Markup nicht durch Buildaktionen kompiliert wird, können XAML-Namescope-bezogene Ausnahmen während des Ladens des XAML ausgelöst werden. XAML-Designer können XAML-Namescope-Probleme auch zur Entwurfszeit vorausschauend behandeln.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Hinzufügen von Objekten zu Laufzeit-Objektstrukturen  
 Der Zeitpunkt, an dem das XAML analysiert wird, stellt den Zeitpunkt dar, an dem ein WPF-XAML-Namescope erstellt und definiert wird. Wenn Sie ein Objekt zu einer Objektstruktur hinzufügen, nachdem der die Struktur erzeugende XAML-Code analysiert wurde, wird ein `Name`- oder `x:Name`-Wert für das neue Objekt nicht automatisch die Informationen in einem XAML-Namescope aktualisieren. Wenn Sie einen Namen für ein Objekt in einem WPF-XAML-Namescope nach dem Laden von XAML hinzufügen möchten, müssen Sie die entsprechende Implementierung von <xref:System.Windows.Markup.INameScope.RegisterName%2A> für das Objekt, das den XAML-Namescope definiert (in der Regel der XAML-Seiten Stamm), abrufen. Wenn der Name nicht registriert ist, kann auf das hinzugefügte Objekt nicht anhand von Methoden wie <xref:System.Windows.FrameworkElement.FindName%2A>verwiesen werden, und Sie können diesen Namen nicht für Animations Ziele verwenden.  
  
 Das häufigste Szenario für Anwendungsentwickler besteht darin, dass Sie <xref:System.Windows.FrameworkElement.RegisterName%2A> verwenden, um Namen im XAML-Namescope im aktuellen Stamm der Seite zu registrieren. <xref:System.Windows.FrameworkElement.RegisterName%2A> ist Teil eines wichtigen Szenarios für Storyboards, die auf Objekte für Animationen abzielen. Weitere Informationen finden Sie unter [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md).  
  
 Wenn Sie <xref:System.Windows.FrameworkElement.RegisterName%2A> für ein anderes Objekt als das Objekt aufrufen, das den XAML-Namescope definiert, wird der Name weiterhin für den XAML-Namescope registriert, in dem das aufrufende Objekt enthalten ist, als ob Sie <xref:System.Windows.FrameworkElement.RegisterName%2A> auf dem XAML-Namescope, das das Objekt definiert, aufgerufen hätten.  
  
### <a name="xaml-namescopes-in-code"></a>XAML Namescopes im Code  
 Sie können XAML-Namescopes im Code erstellen und anschließend verwenden. Die an der XAML-Namescope beteiligten APIs und Konzepte sind auch bei reiner Codeverwendung dieselben, da der XAML-Prozessor von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diese APIs und Konzepte beim Verarbeiten des XAML selbst verwendet. Die Aufgaben dieser Konzepte und -APIs sind hauptsächlich, Objekte anhand des Namens innerhalb einer Objektstruktur zu finden, die in der Regel teilweise oder vollständig in XAML definiert ist.  
  
 Bei Anwendungen, die Programm gesteuert erstellt werden, und nicht aus der geladenen XAML-Datei, muss das Objekt, das einen XAML-Namescope definiert, <xref:System.Windows.Markup.INameScope>implementieren oder eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse sein, um die Erstellung eines XAML-Namescope für seine Instanzen zu unterstützen.  
  
 Ebenso gilt, das bei jedem Element, das nicht von einem XAML-Prozessor geladen und verarbeitet wird, der XAML-Namescope für das Objekt standardmäßig nicht erstellt oder initialisiert wird. Sie müssen explizit für jedes Objekt einen neuen XAML-Namescope erstellen, für das Sie anschließend Namen registrieren möchten. Um einen XAML-Namescope zu erstellen, rufen Sie die statische <xref:System.Windows.NameScope.SetNameScope%2A> Methode auf. Geben Sie das Objekt, dessen Besitzer es ist, als `dependencyObject`-Parameter und einen neuen <xref:System.Windows.NameScope.%23ctor%2A> konstruktoraufrufals `value`-Parameter an.  
  
 Wenn das als `dependencyObject` für <xref:System.Windows.NameScope.SetNameScope%2A> bereitgestellte Objekt keine <xref:System.Windows.Markup.INameScope> Implementierung, <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>ist, hat das Aufrufen von <xref:System.Windows.FrameworkElement.RegisterName%2A> für untergeordnete Elemente keine Auswirkung. Wenn Sie den neuen XAML-Namescope nicht explizit erstellen, wird bei Aufrufen von <xref:System.Windows.FrameworkElement.RegisterName%2A> eine Ausnahme ausgelöst.  
  
 Ein Beispiel der Verwendung von XAML-Namescope-APIs in Code finden Sie unter [Definieren eines Namensbereichs](../graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>XAML-Namescopes in Stilen und Vorlagen  
 Stile und Vorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten die Möglichkeit, Inhalte auf einfache Weise wieder zu verwenden und sie erneut anzuwenden. Allerdings können Stile und Vorlagen auch Elemente mit XAML-Namen, die auf der Vorlagenebene definiert sind, enthalten. Dieselbe Vorlage wird möglicherweise mehrmals auf einer Seite verwendet. Aus diesem Grund definieren Stile und Vorlagen ihre eigenen XAML-Namescopes, unabhängig davon, an welcher Position in einer Objektstruktur der Stil oder die Vorlage angewendet wird.  
  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Hier wird dieselbe Vorlage auf zwei verschiedene Schaltflächen angewendet. Hätten Vorlagen keine diskreten XAML-Namensbereiche, würde der in der Vorlage verwendete `TheBorder`-Name einen Namenskonflikt im XAML-Namescope verursachen. Jede Vorlageninstanz hat ihren eigenen XAML-Namescope, weshalb in diesem Beispiel der Namescope jeder Instanz der Vorlage genau einen Namen enthält.  
  
 Auch Stile definieren ihre eigenen XAML-Namensbereich. Dies dient vor allem dazu, dass Teilen von Storyboards bestimmte Namen zugewiesen werden können. Diese Namen ermöglichen steuerelementspezifische Verhalten, die auf Elemente dieses Namens selbst dann angewendet werden, wenn die Vorlage als Teil einer Anpassung von Steuerelementen neu definiert wurde.  
  
 Aufgrund der separaten XAML-Namescopes ist die Suche nach benannten Elementen in einer Vorlage schwieriger, als die Suche nach einem ohne Vorlage benannten Element in einer Seite. Sie müssen zuerst die angewendete Vorlage ermitteln, indem Sie den <xref:System.Windows.Controls.Control.Template%2A>-Eigenschafts Wert des Steuer Elements erhalten, in dem die Vorlage angewendet wird. Anschließend wird die Vorlagen Version von <xref:System.Windows.FrameworkTemplate.FindName%2A>aufgerufen, wobei das Steuerelement übergeben wird, in dem die Vorlage als zweiter Parameter angewendet wurde.  
  
 Wenn Sie ein Steuerelement Autor sind und Sie eine Konvention erstellen, bei der ein bestimmtes benanntes Element in einer angewendeten Vorlage das Ziel für ein Verhalten ist, das durch das Steuerelement selbst definiert ist, können Sie die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>-Methode aus dem Implementierungs Code des Steuer Elements verwenden. Die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>-Methode ist geschützt, sodass nur der Autor des Steuer Elements darauf zugreifen kann.  
  
 Wenn Sie in einer Vorlage arbeiten und zum XAML-Namespace gelangen müssen, in dem die Vorlage angewendet wird, können Sie den Wert <xref:System.Windows.FrameworkElement.TemplatedParent%2A>abrufen und dann <xref:System.Windows.FrameworkElement.FindName%2A> dort abrufen. Ein Beispiel für das Arbeiten innerhalb der Vorlage wäre, wenn Sie einen Ereignis-Handler dort implementieren möchten, wo das Ereignis von einem Element in einer angewendeten Vorlage ausgelöst wird.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML-Namescopes und namensbezogene APIs  
 <xref:System.Windows.FrameworkElement> verfügt über <xref:System.Windows.FrameworkElement.FindName%2A>-, <xref:System.Windows.FrameworkElement.RegisterName%2A>-und <xref:System.Windows.FrameworkElement.UnregisterName%2A>-Methoden. Wenn das Objekt, für das Sie diese Methoden aufrufen, einen XAML-Namescope besitzt, rufen die Methoden die Methoden des entsprechenden XAML-Namescopes auf. Andernfalls wird das übergeordnete Element daraufhin überprüft, ob es einen XAML-Namescope besitzt. Dieser Vorgang wird rekursiv fortgesetzt, bis ein XAML-Namescope gefunden wird (wobei Erfolg garantiert ist, da aufgrund des Verhaltens des XAML-Prozessors das Stammelement immer einen XAML-Namescope hat). <xref:System.Windows.FrameworkContentElement> hat analoge Verhalten, mit der Ausnahme, dass kein <xref:System.Windows.FrameworkContentElement> einen XAML-Namescope besitzen wird. Die-Methoden sind auf <xref:System.Windows.FrameworkContentElement> vorhanden, sodass die Aufrufe schließlich an ein <xref:System.Windows.FrameworkElement> übergeordnetes Element weitergeleitet werden können.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A> wird verwendet, um einem vorhandenen-Objekt einen neuen XAML-Namescope zuzuordnen. Sie können <xref:System.Windows.NameScope.SetNameScope%2A> mehrmals aufzurufen, um den XAML-Namescope zurückzusetzen oder zu löschen. Dies ist jedoch keine häufige Verwendung. Außerdem wird <xref:System.Windows.NameScope.GetNameScope%2A> in der Regel nicht im Code verwendet.  
  
### <a name="xaml-namescope-implementations"></a>Implementierungen von XAML-Namescopes  
 Die folgenden Klassen implementieren <xref:System.Windows.Markup.INameScope> direkt:  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary> verwendet keine XAML-Namen oder-Namescopes. Stattdessen werden Schlüssel verwendet, da es sich um eine Wörterbuch Implementierung handelt. Der einzige Grund, <xref:System.Windows.ResourceDictionary> <xref:System.Windows.Markup.INameScope> implementiert, ist, dass es Ausnahmen für Benutzercode ausgelöst werden kann, um den Unterschied zwischen einem echten XAML-Namescope und der Art und Weise zu verdeutlichen, wie ein <xref:System.Windows.ResourceDictionary> Schlüssel behandelt, und um sicherzustellen, dass XAML-Namescopes nicht auf eine <xref:System.Windows.ResourceDictionary> durch übergeordnete Elemente angewendet werden.  
  
 <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> mithilfe expliziter Schnittstellendefinitionen <xref:System.Windows.Markup.INameScope> implementieren. Die expliziten Implementierungen ermöglichen es diesen XAML-Namescopes, sich konsistent zu Verhalten, wenn über die <xref:System.Windows.Markup.INameScope>-Schnittstelle auf Sie zugegriffen wird, sodass XAML-Namescopes durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] internen Prozesse kommuniziert werden. Die expliziten Schnittstellendefinitionen sind jedoch nicht Teil der herkömmlichen API-Oberfläche von <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style>, da Sie nur selten die <xref:System.Windows.Markup.INameScope> Methoden auf <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> direkt aufzurufen müssen und stattdessen eine andere API wie <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>verwenden müssen.  
  
 Die folgenden Klassen definieren ihren eigenen XAML-Namescope, indem Sie die <xref:System.Windows.NameScope?displayProperty=nameWithType>-Hilfsklasse verwenden und eine Verbindung mit ihrer XAML-Namescope-Implementierung über die <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> angefügte-Eigenschaft herstellen:  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Namespaces und Namespacezuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [x:Name-Anweisung](../../../desktop-wpf/xaml-services/xname-directive.md)
