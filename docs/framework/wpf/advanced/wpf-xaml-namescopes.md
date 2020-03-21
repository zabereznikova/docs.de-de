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
ms.openlocfilehash: f9d4439c6b102d0d430b5201e3649985daee0b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186273"
---
# <a name="wpf-xaml-namescopes"></a>WPF-XAML-Namescopes
XAML-Namescopes sind ein Konzept, das Objekte bezeichnet, die in XAML definiert sind. Die Namen in einem XAML-Namescope können verwendet werden, um Beziehungen zwischen den XAML-definierten Namen der Objekte und ihren Entsprechungen in einer Objektstruktur herzustellen. In der Regel werden XAML-Namescopes in verwaltetem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code beim Laden der einzelnen XAML Seitenstämme für XAML-Anwendungen erstellt. XAML-Namescopes als Programmierobjekt werden <xref:System.Windows.Markup.INameScope> durch die Schnittstelle definiert <xref:System.Windows.NameScope>und auch von der praktischen Klasse implementiert.  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>
## <a name="namescopes-in-loaded-xaml-applications"></a>Namescopes in geladenen XAML-Anwendungen  
 Im weiter gefassten Kontext der Programmierung oder der Informatik beinhalten Programmierkonzepte oft einen eindeutigen Bezeichner oder Namen, der für den Objektzugriff verwendet werden kann. Für Systeme, die Bezeichner oder Namen verwenden, definiert der Namescope die Grenzen, innerhalb derer ein Prozess oder eine Technik sucht, wenn ein Objekt mit diesem Namen angefordert wird, oder die Grenzen, innerhalb derer die Eindeutigkeit von identifizierenden Namen erzwungen wird. Diese allgemeinen Prinzipien gelten für XAML-Namescopes. In WPF werden XAML-Namescopes für das Stammelement einer XAML-Seite erstellt, wenn die Seite geladen wird. Jeder in der XAML-Seite angegebene Name wird, vom Stammelement ausgehend, einem entsprechenden XAML-Namescope hinzugefügt.  
  
 In WPF XAML steuern Elemente, die <xref:System.Windows.Controls.Page>gemeinsame <xref:System.Windows.Window>Stammelemente sind (z. B. und ), immer ein XAML-Namescope. Wenn ein Element <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> wie das Stammelement der Seite im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup <xref:System.Windows.Controls.Page> oder das Stammelement ist, fügt ein Prozessor implizit einen Stamm hinzu, damit der <xref:System.Windows.Controls.Page> ein funktionierendes XAML-Namescope bereitstellen kann.  
  
> [!NOTE]
> WPF-Buildvorgänge erstellen für eine XAML-Produktion selbst dann einen XAML-Namescope, wenn für kein Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup `Name`- oder `x:Name`-Attribute definiert sind.  
  
 Wenn Sie versuchen, denselben Namen in einem beliebigen XAML-Namescope zweimal zu verwenden, wird eine Ausnahme ausgelöst. Für WPF-XAML, das CodeBehind verwendet und Teil einer kompilierten Anwendung ist, wird die Ausnahme während der Erstellung durch WPF-Buildaktionen ausgelöst, wenn die generierende Klasse für die Seite während der Kompilierung des ausgehenden Markups erstellt wird. Für XAML, dessen Markup nicht durch Buildaktionen kompiliert wird, können XAML-Namescope-bezogene Ausnahmen während des Ladens des XAML ausgelöst werden. XAML-Designer können XAML-Namescope-Probleme auch zur Entwurfszeit vorausschauend behandeln.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Hinzufügen von Objekten zu Laufzeit-Objektstrukturen  
 Der Zeitpunkt, an dem das XAML analysiert wird, stellt den Zeitpunkt dar, an dem ein WPF-XAML-Namescope erstellt und definiert wird. Wenn Sie ein Objekt zu einer Objektstruktur hinzufügen, nachdem der die Struktur erzeugende XAML-Code analysiert wurde, wird ein `Name`- oder `x:Name`-Wert für das neue Objekt nicht automatisch die Informationen in einem XAML-Namescope aktualisieren. Um einen Namen für ein Objekt zu einem WPF XAML-Namescope hinzuzufügen, nachdem <xref:System.Windows.Markup.INameScope.RegisterName%2A> XAML geladen wurde, müssen Sie die entsprechende Implementierung für das Objekt aufrufen, das den XAML-Namescope definiert, der in der Regel der XAML-Seitenstamm ist. Wenn der Name nicht registriert ist, kann nicht mit dem <xref:System.Windows.FrameworkElement.FindName%2A>Namen über Methoden wie , auf das hinzugefügte Objekt verwiesen werden, und Sie können diesen Namen nicht für animationszielartiger Ziele verwenden.  
  
 Das häufigste Szenario für Anwendungsentwickler ist, dass Sie <xref:System.Windows.FrameworkElement.RegisterName%2A> Namen im XAML-Namescope im aktuellen Stamm der Seite registrieren. <xref:System.Windows.FrameworkElement.RegisterName%2A>ist Teil eines wichtigen Szenarios für Storyboards, die Objekte für Animationen zielen. Weitere Informationen finden Sie unter [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md).  
  
 Wenn Sie <xref:System.Windows.FrameworkElement.RegisterName%2A> ein anderes Objekt als das Objekt aufrufen, das das XAML-Namescope definiert, wird der Name weiterhin im XAML-Namescope registriert, in dem sich das aufrufende Objekt befindet, als ob Sie das XAML-Namescope-definierende Objekt aufgerufen <xref:System.Windows.FrameworkElement.RegisterName%2A> hätten.  
  
### <a name="xaml-namescopes-in-code"></a>XAML Namescopes im Code  
 Sie können XAML-Namescopes im Code erstellen und anschließend verwenden. Die an der XAML-Namescope beteiligten APIs und Konzepte sind auch bei reiner Codeverwendung dieselben, da der XAML-Prozessor von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diese APIs und Konzepte beim Verarbeiten des XAML selbst verwendet. Die Aufgaben dieser Konzepte und -APIs sind hauptsächlich, Objekte anhand des Namens innerhalb einer Objektstruktur zu finden, die in der Regel teilweise oder vollständig in XAML definiert ist.  
  
 Für Anwendungen, die programmgesteuert und nicht aus geladenem XAML erstellt werden, muss <xref:System.Windows.Markup.INameScope>das Objekt, <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> das ein XAML-Namescope definiert, implementieren , oder eine oder abgeleitete Klasse sein, um die Erstellung eines XAML-Namescopes für seine Instanzen zu unterstützen.  
  
 Ebenso gilt, das bei jedem Element, das nicht von einem XAML-Prozessor geladen und verarbeitet wird, der XAML-Namescope für das Objekt standardmäßig nicht erstellt oder initialisiert wird. Sie müssen explizit für jedes Objekt einen neuen XAML-Namescope erstellen, für das Sie anschließend Namen registrieren möchten. Um ein XAML-Namescope zu <xref:System.Windows.NameScope.SetNameScope%2A> erstellen, rufen Sie die statische Methode auf. Geben Sie das Objekt, `dependencyObject` das es besitzt, als Parameter und einen neuen <xref:System.Windows.NameScope.%23ctor%2A> Konstruktoraufruf als `value` Parameter an.  
  
 Wenn es sich `dependencyObject` <xref:System.Windows.NameScope.SetNameScope%2A> bei dem <xref:System.Windows.Markup.INameScope> bereitgestellten Objekt nicht um eine Implementierung <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>um das Aufrufen <xref:System.Windows.FrameworkElement.RegisterName%2A> von untergeordneten Elementen handelt, hat dies keine Auswirkungen. Wenn Sie das neue XAML-Namescope nicht <xref:System.Windows.FrameworkElement.RegisterName%2A> explizit erstellen können, wird bei Aufrufen zu eine Ausnahme ausgelöst.  
  
 Ein Beispiel der Verwendung von XAML-Namescope-APIs in Code finden Sie unter [Definieren eines Namensbereichs](../graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>
## <a name="xaml-namescopes-in-styles-and-templates"></a>XAML-Namescopes in Stilen und Vorlagen  
 Stile und Vorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten die Möglichkeit, Inhalte auf einfache Weise wieder zu verwenden und sie erneut anzuwenden. Allerdings können Stile und Vorlagen auch Elemente mit XAML-Namen, die auf der Vorlagenebene definiert sind, enthalten. Dieselbe Vorlage wird möglicherweise mehrmals auf einer Seite verwendet. Aus diesem Grund definieren Stile und Vorlagen ihre eigenen XAML-Namescopes, unabhängig davon, an welcher Position in einer Objektstruktur der Stil oder die Vorlage angewendet wird.  
  
 Betrachten Sie das folgenden Beispiel:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Hier wird dieselbe Vorlage auf zwei verschiedene Schaltflächen angewendet. Hätten Vorlagen keine diskreten XAML-Namensbereiche, würde der in der Vorlage verwendete `TheBorder`-Name einen Namenskonflikt im XAML-Namescope verursachen. Jede Vorlageninstanz hat ihren eigenen XAML-Namescope, weshalb in diesem Beispiel der Namescope jeder Instanz der Vorlage genau einen Namen enthält.  
  
 Auch Stile definieren ihre eigenen XAML-Namensbereich. Dies dient vor allem dazu, dass Teilen von Storyboards bestimmte Namen zugewiesen werden können. Diese Namen ermöglichen steuerelementspezifische Verhalten, die auf Elemente dieses Namens selbst dann angewendet werden, wenn die Vorlage als Teil einer Anpassung von Steuerelementen neu definiert wurde.  
  
 Aufgrund der separaten XAML-Namescopes ist die Suche nach benannten Elementen in einer Vorlage schwieriger, als die Suche nach einem ohne Vorlage benannten Element in einer Seite. Sie müssen zuerst die angewendete Vorlage <xref:System.Windows.Controls.Control.Template%2A> bestimmen, indem Sie den Eigenschaftswert des Steuerelements abrufen, auf das die Vorlage angewendet wird. Anschließend rufen Sie die <xref:System.Windows.FrameworkTemplate.FindName%2A>Vorlagenversion von auf, indem Sie das Steuerelement übergeben, an dem die Vorlage als zweiter Parameter angewendet wurde.  
  
 Wenn Sie ein Steuerelementautor sind und eine Konvention generieren, bei der ein bestimmtes benanntes Element in einer angewendeten <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> Vorlage das Ziel für ein Verhalten ist, das vom Steuerelement selbst definiert wird, können Sie die Methode aus dem Steuerelementimplementierungscode verwenden. Die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> Methode ist geschützt, sodass nur der Steuerelementautor Zugriff darauf hat.  
  
 Wenn Sie innerhalb einer Vorlage arbeiten und zum XAML-Namescope gelangen müssen, in <xref:System.Windows.FrameworkElement.TemplatedParent%2A>dem die <xref:System.Windows.FrameworkElement.FindName%2A> Vorlage angewendet wird, rufen Sie den Wert von ab, und rufen Sie dann dort auf. Ein Beispiel für das Arbeiten innerhalb der Vorlage wäre, wenn Sie einen Ereignis-Handler dort implementieren möchten, wo das Ereignis von einem Element in einer angewendeten Vorlage ausgelöst wird.  
  
<a name="Namescopes_and_Name_related_APIs"></a>
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML-Namescopes und namensbezogene APIs  
 <xref:System.Windows.FrameworkElement>hat <xref:System.Windows.FrameworkElement.FindName%2A> <xref:System.Windows.FrameworkElement.RegisterName%2A> , <xref:System.Windows.FrameworkElement.UnregisterName%2A> und Methoden. Wenn das Objekt, für das Sie diese Methoden aufrufen, einen XAML-Namescope besitzt, rufen die Methoden die Methoden des entsprechenden XAML-Namescopes auf. Andernfalls wird das übergeordnete Element daraufhin überprüft, ob es einen XAML-Namescope besitzt. Dieser Vorgang wird rekursiv fortgesetzt, bis ein XAML-Namescope gefunden wird (wobei Erfolg garantiert ist, da aufgrund des Verhaltens des XAML-Prozessors das Stammelement immer einen XAML-Namescope hat). <xref:System.Windows.FrameworkContentElement>hat analoge Verhaltensweisen, mit der <xref:System.Windows.FrameworkContentElement> Ausnahme, dass kein XAML-Namescope jemals besitzen wird. Die Methoden <xref:System.Windows.FrameworkContentElement> sind vorhanden, sodass die Aufrufe <xref:System.Windows.FrameworkElement> schließlich an ein übergeordnetes Element weitergeleitet werden können.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>wird verwendet, um einem vorhandenen Objekt ein neues XAML-Namescope zuzuordnen. Sie können <xref:System.Windows.NameScope.SetNameScope%2A> mehr als einmal aufrufen, um das XAML-Namescope zurückzusetzen oder zu löschen, aber das ist keine häufige Verwendung. Außerdem <xref:System.Windows.NameScope.GetNameScope%2A> wird in der Regel nicht aus Code verwendet.  
  
### <a name="xaml-namescope-implementations"></a>Implementierungen von XAML-Namescopes  
 Die folgenden <xref:System.Windows.Markup.INameScope> Klassen werden direkt implementiert:  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>XAML-Namen oder Namescopes nicht verwendet; Stattdessen werden Schlüssel verwendet, da es sich um eine Wörterbuchimplementierung handelt. Der einzige <xref:System.Windows.ResourceDictionary> Grund, <xref:System.Windows.Markup.INameScope> der implementiert wird, ist, dass es Ausnahmen von Benutzercode auslösen kann, <xref:System.Windows.ResourceDictionary> die helfen, die Unterscheidung zwischen einem echten XAML-Namescope und dem Behandeln von Schlüsseln zu verdeutlichen und sicherzustellen, dass XAML-Namescopes nicht <xref:System.Windows.ResourceDictionary> von übergeordneten Elementen angewendet werden.  
  
 <xref:System.Windows.FrameworkTemplate>und <xref:System.Windows.Style> <xref:System.Windows.Markup.INameScope> durch explizite Schnittstellendefinitionen zu implementieren. Die expliziten Implementierungen ermöglichen es diesen XAML-Namescopes, <xref:System.Windows.Markup.INameScope> sich konventionell zu verhalten, wenn über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schnittstelle darauf zugegriffen wird, wie XAML-Namescopes durch interne Prozesse kommuniziert werden. Die expliziten Schnittstellendefinitionen sind jedoch nicht <xref:System.Windows.FrameworkTemplate> Teil <xref:System.Windows.Style>der herkömmlichen API-Oberfläche <xref:System.Windows.Markup.INameScope> von <xref:System.Windows.FrameworkTemplate> <xref:System.Windows.Style> und , da Sie die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>Methoden selten auf und direkt aufrufen müssen und stattdessen eine andere API wie verwenden würden.  
  
 Die folgenden Klassen definieren ihr eigenes XAML-Namescope, indem sie die <xref:System.Windows.NameScope?displayProperty=nameWithType> Hilfsklasse verwenden <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> und über die angefügte Eigenschaft eine Verbindung mit der XAML-Namescope-Implementierung herstellen:  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Weitere Informationen

- [XAML-Namespaces und Namespacezuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [x:Name-Anweisung](../../../desktop-wpf/xaml-services/xname-directive.md)
