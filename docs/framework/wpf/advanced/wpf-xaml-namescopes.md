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
ms.openlocfilehash: 52fc542996f2fe691b62aeff5296e045643fcc7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498345"
---
# <a name="wpf-xaml-namescopes"></a>WPF-XAML-Namescopes
XAML-Namescopes sind ein Konzept, das Objekte bezeichnet, die in XAML definiert sind. Die Namen in einem XAML-Namescope können verwendet werden, um Beziehungen zwischen den XAML-definierten Namen der Objekte und ihren Entsprechungen in einer Objektstruktur herzustellen. In der Regel werden XAML-Namescopes in verwaltetem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code beim Laden der einzelnen XAML Seitenstämme für XAML-Anwendungen erstellt. XAML-Namescopes als Programmierobjekte sind definiert, durch die <xref:System.Windows.Markup.INameScope> Schnittstelle und werden auch von der praktischen Klasse implementiert <xref:System.Windows.NameScope>.  
  
  
  
<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>Namescopes in geladenen XAML-Anwendungen  
 Im weiter gefassten Kontext der Programmierung oder der Informatik beinhalten Programmierkonzepte oft einen eindeutigen Bezeichner oder Namen, der für den Objektzugriff verwendet werden kann. Für Systeme, die Bezeichner oder Namen verwenden, definiert der Namescope die Grenzen, innerhalb derer ein Prozess oder eine Technik sucht, wenn ein Objekt mit diesem Namen angefordert wird, oder die Grenzen, innerhalb derer die Eindeutigkeit von identifizierenden Namen erzwungen wird. Diese allgemeinen Prinzipien gelten für XAML-Namescopes. In WPF werden XAML-Namescopes für das Stammelement einer XAML-Seite erstellt, wenn die Seite geladen wird. Jeder in der XAML-Seite angegebene Name wird, vom Stammelement ausgehend, einem entsprechenden XAML-Namescope hinzugefügt.  
  
 In WPF XAML, Elemente, die allgemeine Stammelemente sind (z. B. <xref:System.Windows.Controls.Page>, und <xref:System.Windows.Window>) immer einen XAML-Namescope zu steuern. Wenn ein Element wie z. B. <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> ist das Stammelement der Seite im Markup einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Fügt eine <xref:System.Windows.Controls.Page> implizit root, damit die <xref:System.Windows.Controls.Page> bieten einen XAML-Namescope arbeiten.  
  
> [!NOTE]
>  WPF-Buildvorgänge erstellen für eine XAML-Produktion selbst dann einen XAML-Namescope, wenn für kein Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup `Name`- oder `x:Name`-Attribute definiert sind.  
  
 Wenn Sie versuchen, denselben Namen in einem beliebigen XAML-Namescope zweimal zu verwenden, wird eine Ausnahme ausgelöst. Für WPF-XAML, das CodeBehind verwendet und Teil einer kompilierten Anwendung ist, wird die Ausnahme während der Erstellung durch WPF-Buildaktionen ausgelöst, wenn die generierende Klasse für die Seite während der Kompilierung des ausgehenden Markups erstellt wird. Für XAML, dessen Markup nicht durch Buildaktionen kompiliert wird, können XAML-Namescope-bezogene Ausnahmen während des Ladens des XAML ausgelöst werden. XAML-Designer können XAML-Namescope-Probleme auch zur Entwurfszeit vorausschauend behandeln.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Hinzufügen von Objekten zu Laufzeit-Objektstrukturen  
 Der Zeitpunkt, an dem das XAML analysiert wird, stellt den Zeitpunkt dar, an dem ein WPF-XAML-Namescope erstellt und definiert wird. Wenn Sie ein Objekt zu einer Objektstruktur hinzufügen, nachdem der die Struktur erzeugende XAML-Code analysiert wurde, wird ein `Name`- oder `x:Name`-Wert für das neue Objekt nicht automatisch die Informationen in einem XAML-Namescope aktualisieren. Um einen Namen für ein Objekt in einer WPF XAML-Namescope hinzuzufügen, nachdem XAML geladen wurde, müssen Sie die entsprechende Implementierung von Aufrufen <xref:System.Windows.Markup.INameScope.RegisterName%2A> für das Objekt, das den XAML-Namescope definiert, die normalerweise ist der Stamm der XAML-Seite. Wenn der Name nicht registriert ist, das hinzugefügte Objekt kann nicht verwiesen werden anhand des Namens durch Methoden wie z. B. <xref:System.Windows.FrameworkElement.FindName%2A>, und Sie können diesen Namen für die Animationsziel-nicht verwenden.  
  
 Das häufigste Szenario für Anwendungsentwickler ist, den Sie verwenden <xref:System.Windows.FrameworkElement.RegisterName%2A> Namen im XAML-Namescope auf dem aktuellen Stammelement der Seite zu registrieren. <xref:System.Windows.FrameworkElement.RegisterName%2A> ist Teil des Storyboards ein wichtiger Aspekt dieses Zielobjekten für Animationen. Weitere Informationen finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Wenn Sie aufrufen <xref:System.Windows.FrameworkElement.RegisterName%2A> auf ein anderes Objekt als das Objekt, das die XAML-Namescope definiert, der Name ist immer noch registriert auf der XAML-Namescope, der das aufrufende Objekt enthalten ist wie bei einem Aufruf <xref:System.Windows.FrameworkElement.RegisterName%2A> auf der XAML-Namescope definieren-Objekts.  
  
### <a name="xaml-namescopes-in-code"></a>XAML Namescopes im Code  
 Sie können XAML-Namescopes im Code erstellen und anschließend verwenden. Die an der XAML-Namescope beteiligten APIs und Konzepte sind auch bei reiner Codeverwendung dieselben, da der XAML-Prozessor von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diese APIs und Konzepte beim Verarbeiten des XAML selbst verwendet. Die Aufgaben dieser Konzepte und -APIs sind hauptsächlich, Objekte anhand des Namens innerhalb einer Objektstruktur zu finden, die in der Regel teilweise oder vollständig in XAML definiert ist.  
  
 Für Anwendungen, die programmgesteuert erstellt werden, und nicht geladenen XAML, muss das Objekt, das einen XAML-Namescope definiert implementieren <xref:System.Windows.Markup.INameScope>, oder eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse sein, um die Unterstützung der Erstellung eines XAML-Namescopes auf seine -Instanzen.  
  
 Ebenso gilt, das bei jedem Element, das nicht von einem XAML-Prozessor geladen und verarbeitet wird, der XAML-Namescope für das Objekt standardmäßig nicht erstellt oder initialisiert wird. Sie müssen explizit für jedes Objekt einen neuen XAML-Namescope erstellen, für das Sie anschließend Namen registrieren möchten. Um einen XAML-Namescope zu erstellen, rufen Sie die statische <xref:System.Windows.NameScope.SetNameScope%2A> Methode. Geben Sie das Objekt, das sie als besitzt die `dependencyObject` Parameter und ein neues <xref:System.Windows.NameScope.%23ctor%2A> Konstruktoraufruf als die `value` Parameter.  
  
 Wenn Sie das Objekt als bereitgestellt `dependencyObject` für <xref:System.Windows.NameScope.SetNameScope%2A> keine <xref:System.Windows.Markup.INameScope> Implementierung <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, wird beim Aufruf <xref:System.Windows.FrameworkElement.RegisterName%2A> für keines der untergeordneten Elemente hat keine Auswirkungen. Wenn Sie nicht explizit zu den neuen XAML-Namescope erstellen, klicken Sie dann Aufrufe von <xref:System.Windows.FrameworkElement.RegisterName%2A> wird eine Ausnahme ausgelöst.  
  
 Ein Beispiel der Verwendung von XAML-Namescope-APIs in Code finden Sie unter [Definieren eines Namensbereichs](../../../../docs/framework/wpf/graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>XAML-Namescopes in Stilen und Vorlagen  
 Stile und Vorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten die Möglichkeit, Inhalte auf einfache Weise wieder zu verwenden und sie erneut anzuwenden. Allerdings können Stile und Vorlagen auch Elemente mit XAML-Namen, die auf der Vorlagenebene definiert sind, enthalten. Dieselbe Vorlage wird möglicherweise mehrmals auf einer Seite verwendet. Aus diesem Grund definieren Stile und Vorlagen ihre eigenen XAML-Namescopes, unabhängig davon, an welcher Position in einer Objektstruktur der Stil oder die Vorlage angewendet wird.  
  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Hier wird dieselbe Vorlage auf zwei verschiedene Schaltflächen angewendet. Hätten Vorlagen keine diskreten XAML-Namensbereiche, würde der in der Vorlage verwendete `TheBorder`-Name einen Namenskonflikt im XAML-Namescope verursachen. Jede Vorlageninstanz hat ihren eigenen XAML-Namescope, weshalb in diesem Beispiel der Namescope jeder Instanz der Vorlage genau einen Namen enthält.  
  
 Auch Stile definieren ihre eigenen XAML-Namensbereich. Dies dient vor allem dazu, dass Teilen von Storyboards bestimmte Namen zugewiesen werden können. Diese Namen ermöglichen steuerelementspezifische Verhalten, die auf Elemente dieses Namens selbst dann angewendet werden, wenn die Vorlage als Teil einer Anpassung von Steuerelementen neu definiert wurde.  
  
 Aufgrund der separaten XAML-Namescopes ist die Suche nach benannten Elementen in einer Vorlage schwieriger, als die Suche nach einem ohne Vorlage benannten Element in einer Seite. Müssen Sie zuerst die angewendete Vorlage durch Abrufen von bestimmen die <xref:System.Windows.Controls.Control.Template%2A> -Eigenschaftswert des Steuerelements, in dem die Vorlage angewendet wird. Anschließend rufen Sie die Vorlagenversion von <xref:System.Windows.FrameworkTemplate.FindName%2A>, übergeben das Steuerelement, auf die Vorlage als zweiter Parameter angewendet wurde.  
  
 Wenn Sie Autor eines Steuerelements sind, und generieren Sie eine Konvention, in denen ein bestimmtes benanntes Element in einer angewendeten Vorlage ist das Ziel für ein Verhalten, das vom Steuerelement selbst definiert ist, können Sie die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> Methode aus dem Code des Steuerelements-Implementierung. Die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> Methode geschützt werden, sodass nur der Autor des Steuerelements Zugriff darauf hat.  
  
 Wenn es sich bei dem aus Sie arbeiten in einer Vorlage und erforderlich, um den XAML-Namescope zu erhalten, in dem die Vorlage angewendet wird, erhalten Sie den Wert der <xref:System.Windows.FrameworkElement.TemplatedParent%2A>, und rufen dann <xref:System.Windows.FrameworkElement.FindName%2A> vorhanden. Ein Beispiel für das Arbeiten innerhalb der Vorlage wäre, wenn Sie einen Ereignis-Handler dort implementieren möchten, wo das Ereignis von einem Element in einer angewendeten Vorlage ausgelöst wird.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML-Namescopes und namensbezogene APIs  
 <xref:System.Windows.FrameworkElement> verfügt über <xref:System.Windows.FrameworkElement.FindName%2A>, <xref:System.Windows.FrameworkElement.RegisterName%2A> und <xref:System.Windows.FrameworkElement.UnregisterName%2A> Methoden. Wenn das Objekt, für das Sie diese Methoden aufrufen, einen XAML-Namescope besitzt, rufen die Methoden die Methoden des entsprechenden XAML-Namescopes auf. Andernfalls wird das übergeordnete Element daraufhin überprüft, ob es einen XAML-Namescope besitzt. Dieser Vorgang wird rekursiv fortgesetzt, bis ein XAML-Namescope gefunden wird (wobei Erfolg garantiert ist, da aufgrund des Verhaltens des XAML-Prozessors das Stammelement immer einen XAML-Namescope hat). <xref:System.Windows.FrameworkContentElement> hat analoge Verhaltensweisen, mit der Ausnahme, die keine <xref:System.Windows.FrameworkContentElement> wird jemals einen XAML-Namescope besitzen. Die Methoden existieren auf <xref:System.Windows.FrameworkContentElement> , damit die Aufrufe letztendlich zu weitergeleitet werden, können ein <xref:System.Windows.FrameworkElement> übergeordneten Elements.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A> wird verwendet, um ein vorhandenes Objekt einen neuen XAML-Namescope zuzuordnen. Rufen Sie <xref:System.Windows.NameScope.SetNameScope%2A> mehr als einmal zum Zurücksetzen oder deaktivieren Sie die XAML-Namescope, ist jedoch keine häufige Verwendung. Darüber hinaus <xref:System.Windows.NameScope.GetNameScope%2A> wird nicht in der Regel aus Code verwendet.  
  
### <a name="xaml-namescope-implementations"></a>Implementierungen von XAML-Namescopes  
 Die folgenden Klassen implementieren <xref:System.Windows.Markup.INameScope> direkt:  
  
-   <xref:System.Windows.NameScope>  
  
-   <xref:System.Windows.Style>  
  
-   <xref:System.Windows.ResourceDictionary>  
  
-   <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary> XAML-Namen oder -Namescopes wird nicht verwendet werden. Stattdessen verwendet es Schlüssel, da es die Implementierung eines Wörterbuch handelt. Nur deshalb, <xref:System.Windows.ResourceDictionary> implementiert <xref:System.Windows.Markup.INameScope> ist, damit es Ausnahmen für Benutzercode auslösen kann, die verdeutlichen den Unterschied zwischen einem wahren XAML-Namescope, und wie ein <xref:System.Windows.ResourceDictionary> verarbeitet Tasten, und um sicherzustellen, dass die XAML-Namescopes auf nicht angewendet werden ein <xref:System.Windows.ResourceDictionary> durch übergeordnete Elemente.  
  
 <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> implementieren <xref:System.Windows.Markup.INameScope> durch explizite Schnittstellendefinitionen. Die expliziten Implementierungen ermöglichen diese XAML-Namescopes konventionell zu Verhalten, wenn darauf zugegriffen werden die <xref:System.Windows.Markup.INameScope> -Schnittstelle, die ist, wie XAML-Namescopes kommuniziert werden durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] interne Prozesse. Die expliziten Schnittstellendefinitionen sind jedoch nicht Teil der konventionellen API-Oberfläche <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style>, da Sie nur selten zum Aufrufen benötigen der <xref:System.Windows.Markup.INameScope> Methoden <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> direkt aus, und stattdessen andere API verwenden wie z. B. <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>.  
  
 Die folgenden Klassen definieren ihren eigenen XAML-Namescope, mit der <xref:System.Windows.NameScope?displayProperty=nameWithType> Hilfsklasse und Herstellen einer Verbindung mit der XAML-Namescope-Implementierung, über die <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> angefügte Eigenschaft:  
  
-   <xref:System.Windows.FrameworkElement>  
  
-   <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Siehe auch
- [XAML-Namespaces und Namespacezuordnung für WPF-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [x:Name-Anweisung](../../../../docs/framework/xaml-services/x-name-directive.md)
