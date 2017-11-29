---
title: WPF-XAML-Namescopes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22b0354a0821021239140527793dc34e3911a733
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-xaml-namescopes"></a>WPF-XAML-Namescopes
XAML-Namescopes sind ein Konzept, das Objekte bezeichnet, die in XAML definiert sind. Die Namen in einem XAML-Namescope können verwendet werden, um Beziehungen zwischen den XAML-definierten Namen der Objekte und ihren Entsprechungen in einer Objektstruktur herzustellen. In der Regel werden XAML-Namescopes in verwaltetem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code beim Laden der einzelnen XAML Seitenstämme für XAML-Anwendungen erstellt. Verwendung von XAML-Namescopes als Programmierobjekte werden definiert, indem die <xref:System.Windows.Markup.INameScope> Schnittstelle und werden auch von der praktischen Klasse implementiert <xref:System.Windows.NameScope>.  
  
  
  
<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>Namescopes in geladenen XAML-Anwendungen  
 Im weiter gefassten Kontext der Programmierung oder der Informatik beinhalten Programmierkonzepte oft einen eindeutigen Bezeichner oder Namen, der für den Objektzugriff verwendet werden kann. Für Systeme, die Bezeichner oder Namen verwenden, definiert der Namescope die Grenzen, innerhalb derer ein Prozess oder eine Technik sucht, wenn ein Objekt mit diesem Namen angefordert wird, oder die Grenzen, innerhalb derer die Eindeutigkeit von identifizierenden Namen erzwungen wird. Diese allgemeinen Prinzipien gelten für XAML-Namescopes. In WPF werden XAML-Namescopes für das Stammelement einer XAML-Seite erstellt, wenn die Seite geladen wird. Jeder in der XAML-Seite angegebene Name wird, vom Stammelement ausgehend, einem entsprechenden XAML-Namescope hinzugefügt.  
  
 In WPF-XAML-Elemente, die allgemeine Stammelemente sind (z. B. <xref:System.Windows.Controls.Page>, und <xref:System.Windows.Window>) immer einen XAML-Namensbereich zu steuern. Wenn ein Element wie z. B. <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> ist das Stammelement der Seite im Markup eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Fügt eine <xref:System.Windows.Controls.Page> implizit root, damit die <xref:System.Windows.Controls.Page> bieten einen funktionierenden XAML-Namensbereich.  
  
> [!NOTE]
>  WPF-Buildvorgänge erstellen für eine XAML-Produktion selbst dann einen XAML-Namescope, wenn für kein Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup `Name`- oder `x:Name`-Attribute definiert sind.  
  
 Wenn Sie versuchen, denselben Namen in einem beliebigen XAML-Namescope zweimal zu verwenden, wird eine Ausnahme ausgelöst. Für WPF-XAML, das CodeBehind verwendet und Teil einer kompilierten Anwendung ist, wird die Ausnahme während der Erstellung durch WPF-Buildaktionen ausgelöst, wenn die generierende Klasse für die Seite während der Kompilierung des ausgehenden Markups erstellt wird. Für XAML, dessen Markup nicht durch Buildaktionen kompiliert wird, können XAML-Namescope-bezogene Ausnahmen während des Ladens des XAML ausgelöst werden. XAML-Designer können XAML-Namescope-Probleme auch zur Entwurfszeit vorausschauend behandeln.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Hinzufügen von Objekten zu Laufzeit-Objektstrukturen  
 Der Zeitpunkt, an dem das XAML analysiert wird, stellt den Zeitpunkt dar, an dem ein WPF-XAML-Namescope erstellt und definiert wird. Wenn Sie ein Objekt zu einer Objektstruktur hinzufügen, nachdem der die Struktur erzeugende XAML-Code analysiert wurde, wird ein `Name`- oder `x:Name`-Wert für das neue Objekt nicht automatisch die Informationen in einem XAML-Namescope aktualisieren. Um einen Namen für ein Objekt in einer WPF-XAML-Namensbereich hinzuzufügen, nachdem XAML geladen wurde, rufen Sie die entsprechende Implementierung von <xref:System.Windows.Markup.INameScope.RegisterName%2A> auf das Objekt, das die Verwendung von XAML-Namensbereich definiert, wird die in der Regel den Stamm der XAML-Seite. Wenn der Name nicht registriert ist, das hinzugefügte Objekt kann nicht referenziert werden anhand des Namens durch Methoden wie z. B. <xref:System.Windows.FrameworkElement.FindName%2A>, und Sie können diesen Namen für die Animation Zielgruppenadressierung verwenden.  
  
 Das häufigste Szenario für Anwendungsentwickler ist, das Sie verwenden <xref:System.Windows.FrameworkElement.RegisterName%2A> um Namen in der XAML-Namensbereich auf dem aktuellen Stamm der Seite zu registrieren. <xref:System.Windows.FrameworkElement.RegisterName%2A>ist Teil eines wichtigen Szenarios für Storyboards, in denen Objekte für Animationen. Weitere Informationen finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Beim Aufrufen <xref:System.Windows.FrameworkElement.RegisterName%2A> auf ein anderes Objekt als das Objekt, das die Verwendung von XAML-Namensbereich definiert, der Name noch registriert ist, die XAML-Namensbereich, die das aufrufende Objekt enthalten ist wie bei einem Aufruf <xref:System.Windows.FrameworkElement.RegisterName%2A> auf die Verwendung von XAML-Namensbereich definiert.  
  
### <a name="xaml-namescopes-in-code"></a>XAML Namescopes im Code  
 Sie können XAML-Namescopes im Code erstellen und anschließend verwenden. Die an der XAML-Namescope beteiligten APIs und Konzepte sind auch bei reiner Codeverwendung dieselben, da der XAML-Prozessor von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diese APIs und Konzepte beim Verarbeiten des XAML selbst verwendet. Die Aufgaben dieser Konzepte und -APIs sind hauptsächlich, Objekte anhand des Namens innerhalb einer Objektstruktur zu finden, die in der Regel teilweise oder vollständig in XAML definiert ist.  
  
 Für Anwendungen, die programmgesteuert erstellt werden, und nicht aus XAML geladen, muss das Objekt, das einen XAML-Namensbereich definiert implementieren <xref:System.Windows.Markup.INameScope>, oder eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse, um die Erstellung von einem XAML-Namensbereich auf unterstützt die Instanzen.  
  
 Ebenso gilt, das bei jedem Element, das nicht von einem XAML-Prozessor geladen und verarbeitet wird, der XAML-Namescope für das Objekt standardmäßig nicht erstellt oder initialisiert wird. Sie müssen explizit für jedes Objekt einen neuen XAML-Namescope erstellen, für das Sie anschließend Namen registrieren möchten. Um einen XAML-Namensbereich zu erstellen, rufen Sie die statische <xref:System.Windows.NameScope.SetNameScope%2A> Methode. Geben Sie das Objekt, das als Besitzer ist die `dependencyObject` Parameter und eine neue <xref:System.Windows.NameScope.%23ctor%2A> Konstruktoraufruf als die `value` Parameter.  
  
 Wenn das Objekt als bereitgestellt `dependencyObject` für <xref:System.Windows.NameScope.SetNameScope%2A> ist keine <xref:System.Windows.Markup.INameScope> Implementierung <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>Aufrufen <xref:System.Windows.FrameworkElement.RegisterName%2A> für alle untergeordneten Elemente hat keine Auswirkungen. Wenn Sie nicht die neuen XAML-Namensbereich explizit zu erstellen, klicken Sie dann Aufrufe von <xref:System.Windows.FrameworkElement.RegisterName%2A> wird eine Ausnahme ausgelöst.  
  
 Ein Beispiel der Verwendung von XAML-Namescope-APIs in Code finden Sie unter [Definieren eines Namensbereichs](../../../../docs/framework/wpf/graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>XAML-Namescopes in Stilen und Vorlagen  
 Stile und Vorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten die Möglichkeit, Inhalte auf einfache Weise wieder zu verwenden und sie erneut anzuwenden. Allerdings können Stile und Vorlagen auch Elemente mit XAML-Namen, die auf der Vorlagenebene definiert sind, enthalten. Dieselbe Vorlage wird möglicherweise mehrmals auf einer Seite verwendet. Aus diesem Grund definieren Stile und Vorlagen ihre eigenen XAML-Namescopes, unabhängig davon, an welcher Position in einer Objektstruktur der Stil oder die Vorlage angewendet wird.  
  
 Betrachten Sie das folgende Beispiel:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Hier wird dieselbe Vorlage auf zwei verschiedene Schaltflächen angewendet. Hätten Vorlagen keine diskreten XAML-Namensbereiche, würde der in der Vorlage verwendete `TheBorder`-Name einen Namenskonflikt im XAML-Namescope verursachen. Jede Vorlageninstanz hat ihren eigenen XAML-Namescope, weshalb in diesem Beispiel der Namescope jeder Instanz der Vorlage genau einen Namen enthält.  
  
 Auch Stile definieren ihre eigenen XAML-Namensbereich. Dies dient vor allem dazu, dass Teilen von Storyboards bestimmte Namen zugewiesen werden können. Diese Namen ermöglichen steuerelementspezifische Verhalten, die auf Elemente dieses Namens selbst dann angewendet werden, wenn die Vorlage als Teil einer Anpassung von Steuerelementen neu definiert wurde.  
  
 Aufgrund der separaten XAML-Namescopes ist die Suche nach benannten Elementen in einer Vorlage schwieriger, als die Suche nach einem ohne Vorlage benannten Element in einer Seite. Müssen Sie zuerst bestimmen die angewendete Vorlage durch Abrufen der <xref:System.Windows.Controls.Control.Template%2A> Eigenschaftswert des Steuerelements, in dem die Vorlage angewendet wird. Rufen Sie dann die Vorlagenversion der <xref:System.Windows.FrameworkTemplate.FindName%2A>, übergeben das Steuerelement, in dem die Vorlage als zweiter Parameter angewendet wurde.  
  
 Wenn Sie der Autor eines Steuerelements sind, und generieren Sie eine Konvention, die ein bestimmtes benanntes Element in einer Vorlage angewendet wird, in dem das Ziel für ein Verhalten, das vom Steuerelement selbst definiert wird, können Sie die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> -Methode aus dem Code der Steuerelement-Implementierung. Die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> Methode wird geschützt, sodass nur der Steuerelementautor hat den Zugriff darauf.  
  
 Wenn dem aus Sie in einer Vorlage und müssen arbeiten, um den XAML-Namensbereich zu erhalten, in dem die Vorlage angewendet wird, rufen Sie den Wert der <xref:System.Windows.FrameworkElement.TemplatedParent%2A>, und rufen dann <xref:System.Windows.FrameworkElement.FindName%2A> vorhanden. Ein Beispiel für das Arbeiten innerhalb der Vorlage wäre, wenn Sie einen Ereignis-Handler dort implementieren möchten, wo das Ereignis von einem Element in einer angewendeten Vorlage ausgelöst wird.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML-Namescopes und namensbezogene APIs  
 <xref:System.Windows.FrameworkElement>hat <xref:System.Windows.FrameworkElement.FindName%2A>, <xref:System.Windows.FrameworkElement.RegisterName%2A> und <xref:System.Windows.FrameworkElement.UnregisterName%2A> Methoden. Wenn das Objekt, für das Sie diese Methoden aufrufen, einen XAML-Namescope besitzt, rufen die Methoden die Methoden des entsprechenden XAML-Namescopes auf. Andernfalls wird das übergeordnete Element daraufhin überprüft, ob es einen XAML-Namescope besitzt. Dieser Vorgang wird rekursiv fortgesetzt, bis ein XAML-Namescope gefunden wird (wobei Erfolg garantiert ist, da aufgrund des Verhaltens des XAML-Prozessors das Stammelement immer einen XAML-Namescope hat). <xref:System.Windows.FrameworkContentElement>hat analoge Verhaltensweisen, mit der Ausnahme, die keine <xref:System.Windows.FrameworkContentElement> wird nie einen XAML-Namensbereich besitzen. Die Methoden vorhanden sind, auf <xref:System.Windows.FrameworkContentElement> , damit die Aufrufe schließlich zur weitergeleitet werden können eine <xref:System.Windows.FrameworkElement> übergeordneten Elements.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>wird verwendet, um ein vorhandenes Objekt einen neuen XAML-Namensbereich zuzuordnen. Sie können Aufrufen <xref:System.Windows.NameScope.SetNameScope%2A> mehr als einmal um zurücksetzen oder deaktivieren Sie das XAML Namensbereich, dies ist jedoch keine allgemeine Verwendung. Darüber hinaus <xref:System.Windows.NameScope.GetNameScope%2A> wird nicht in der Regel aus Code verwendet.  
  
### <a name="xaml-namescope-implementations"></a>Implementierungen von XAML-Namescopes  
 Die folgenden Klassen implementieren <xref:System.Windows.Markup.INameScope> direkt:  
  
-   <xref:System.Windows.NameScope>  
  
-   <xref:System.Windows.Style>  
  
-   <xref:System.Windows.ResourceDictionary>  
  
-   <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>Verwendung von XAML-Namen oder Namescopes wird nicht verwendet werden. Es verwendet Schlüssel stattdessen, da es sich um eine wörterbuchimplementierung handelt. Der einzige Grund an, <xref:System.Windows.ResourceDictionary> implementiert <xref:System.Windows.Markup.INameScope> ist für Benutzercode Ausnahmen auslösen kann, die verdeutlichen, dass den Unterschied zwischen einem "true" Verwendung von XAML-Namensbereich und wie eine <xref:System.Windows.ResourceDictionary> verarbeitet Tasten, und um sicherzustellen, dass die Verwendung von XAML-Namescopes nicht zugewiesen werden ein <xref:System.Windows.ResourceDictionary> von übergeordneten Elementen.  
  
 <xref:System.Windows.FrameworkTemplate>und <xref:System.Windows.Style> implementieren <xref:System.Windows.Markup.INameScope> über explizite Definitionen. Die explizite Implementierungen ermöglichen diese XAML-Namescopes konventionell verhält, wenn darauf zugegriffen wird, über die <xref:System.Windows.Markup.INameScope> -Schnittstelle, wie die Verwendung von XAML-Namescopes kommuniziert werden durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] interne Prozesse. Aber die explizite Definitionen sind nicht Teil der konventionellen API-Oberfläche des <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style>, da Sie nur selten aufrufen müssen die <xref:System.Windows.Markup.INameScope> Methoden auf <xref:System.Windows.FrameworkTemplate> und <xref:System.Windows.Style> direkt und stattdessen andere API verwenden z. B. <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>.  
  
 Die folgenden Klassen definieren ihrer eigenen XAML-Namensbereich mithilfe der <xref:System.Windows.NameScope?displayProperty=nameWithType> Hilfsklasse und Herstellen einer Verbindung mit der Verwendung von XAML-Namensbereich der XAML-Implementierung über die <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> -Eigenschaft:  
  
-   <xref:System.Windows.FrameworkElement>  
  
-   <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Siehe auch  
 [XAML-Namespaces und Namespacezuordnung für WPF-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)  
 [x:Name-Anweisung](../../../../docs/framework/xaml-services/x-name-directive.md)
