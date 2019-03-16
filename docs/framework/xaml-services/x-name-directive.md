---
title: x:Name-Anweisung
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: 3d188038526570761c2e50dc607fd4aac165fda5
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58034341"
---
# <a name="xname-directive"></a>x:Name-Anweisung
Identifiziert eindeutig die XAML-definierte Elemente in einem XAML-Namescope. XAML-Namescopes und ihre Eindeutigkeitsmodelle können auf die instanziierten Objekte angewendet werden, Frameworks bieten APIs oder zum Implementieren von Verhaltensweisen, die das XAML erstellte Objektdiagramm zur Laufzeit zugreifen.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`XAMLNameValue`|Eine Zeichenfolge, die die Einschränkungen der entspricht der [XamlName-Grammatik](xamlname-grammar.md).|  
  
## <a name="remarks"></a>Hinweise  
 Nach dem `x:Name` angewendet wird, um ein Framework des Programmiermodell, das Sichern, entspricht der Name der Variablen, die einen Objektverweis oder eine Instanz, so wie vom Konstruktor enthält.  
  
 Der Wert des einem `x:Name` -Direktive Nutzung muss in einem XAML-Namescope eindeutig sein. Wird standardmäßig bei der Verwendung von .NET Framework XAML-Dienste-API, der primäre XAML-Namescope ist im XAML-Stammelement einer einzelnen XAML-Produktion definiert und umfasst die Elemente, die in der diese XAML-Produktion enthalten sind. Zusätzliche diskreten XAML-Namensbereiche, die innerhalb einer einzelnen XAML-Produktion auftreten können, können von Frameworks für bestimmte Szenarien definiert werden. Z. B. in WPF können sind neue XAML-Namescopes definiert und erstellt, die von beliebigen Vorlagen, die auch für diese XAML-Produktion definiert ist. Weitere Informationen zu XAML-Namescopes (geschrieben für WPF, aber für viele Konzepte von XAML-Namescope relevant), finden Sie unter [WPF-XAML-Namescopes](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 Im allgemeinen `x:Name` sollten in Situationen, in denen auch verwenden, nicht angewendet werden `x:Key`. XAML-Implementierungen von bestimmten vorhandenen Frameworks eingeführt, Ersetzungskonzepte zwischen `x:Key` und `x:Name`, allerdings wird nicht empfohlen. .NET Framework-XAML-Dienste unterstützt keine solche Ersetzungskonzepte beim Behandeln von Namen/Schlüssel Informationen wie z. B. <xref:System.Windows.Markup.INameScope> oder <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Regeln für Permittance von `x:Name` sowie die Namen Eindeutigkeit Erzwingung werden möglicherweise von bestimmten implementierende Frameworks definiert. Allerdings um mit .NET Framework-XAML-Diensten verwendet werden, die Frameworkdefinitionen von XAML-Namescope Eindeutigkeit muss konsistent mit der Definition der <xref:System.Windows.Markup.INameScope> Informationen in dieser Dokumentation und sollten die gleichen Regeln in Bezug auf den Speicherort der Informationen wird angewendet. Z. B. die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Implementierung teilt verschiedene Markupelemente in separaten <xref:System.Windows.NameScope> Bereiche, z. B. Ressourcenverzeichnisse, die logische Struktur erstellt, indem der auf Seitenebene XAML, Vorlagen und andere verzögerte Inhalt, und klicken Sie dann erzwingt XAML Eindeutigkeit des Namens innerhalb aller dieser XAML-Namescopes.  
  
 Für benutzerdefinierte Typen, die .NET Framework XAML Services XAML-Objektwriter verwenden, eine Eigenschaft, der zugeordnet `x:Name` auf ein Typ festgelegt oder geändert werden kann. Definieren Sie dieses Verhalten durch Verweis auf den Namen der Eigenschaft zugeordnet werden soll die <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> in den Typcode der Definition.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ist ein Attribut auf Typebene.  
  
 Frameworkneutrale Framework-XAML-Dienste, die dahinter liegende Logik für XAML-Namescope-Unterstützung kann in einer Weise definiert werden, durch die Implementierung der <xref:System.Windows.Markup.INameScope> Schnittstelle.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 In der standard Buildkonfiguration für eine [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Anwendung, die XAML, partielle Klassen und Code-Behind muss die angegebene verwendet `x:Name` wird der Name eines Felds, das in der zugrunde liegenden erstellt wird code, wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] wird durch ein Markup verarbeitet Kompilierung-Buildaufgabe erstellen und dieses Feld enthält einen Verweis auf das Objekt. Standardmäßig ist das erstellte Feld intern. Sie können den Feldzugriff ändern, durch Angabe der [X: FieldModifier-Attribut](x-fieldmodifier-directive.md). In WPF und Silverlight ist die Sequenz an, dass die Markupkompilierung definiert und Namen das Feld in einer partiellen Klasse, aber der Wert zunächst leer ist. Klicken Sie dann eine generierte Methode mit dem Namen `InitializeComponent` innerhalb der Konstruktor der Klasse aufgerufen wird. `InitializeComponent` besteht aus `FindName` aufruft, indem Sie die `x:Name` Zeichenfolgen zur Eingabe von Werten, die in der XAML-definierten Teil der partiellen Klasse als vorhanden sind. Die Rückgabewerte werden anschließend füllen die Feldwerte mit Objekten, die aus XAML erstellt wurden, analysieren, den Feldverweis mit ähnlichen Namen zugewiesen. Die Ausführung von `InitializeComponent` ermöglichen es zu verweisen, das zur Laufzeit Diagramm mit den `x:Name` / Feldname direkt aufrufen, anstatt `FindName` explizit jederzeit benötigen Sie einen Verweis auf ein XAML-Objekt.  
  
 Für eine WPF-Anwendung, das Microsoft Visual Basic verwendet, ausgerichtet ist, und umfasst XAML-Dateien mit der `Page` Buildaktion, eine Eigenschaft für einen separaten wird erstellt, während der Kompilierung der `WithEvents` Schlüsselwort, um alle Elemente, deren ein `x:Name`Unterstützung `Handles` Syntax für Ereignishandlerdelegaten. Diese Eigenschaft ist immer öffentlich. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name` wird von der WPF XAML-Prozessor verwendet, um einen Namen in einem XAML-Namescope zur Ladezeit auch registrieren, in dem die Seite nicht von Buildvorgängen (z. B. loose XAML eines Ressourcenverzeichnisses) markupkompiliert ist. Ein Grund für dieses Verhalten ist, da die `x:Name` ist ggf. für <xref:System.Windows.Data.Binding.ElementName%2A> Bindung. Weitere Informationen finden Sie unter [Übersicht über die Datenbindung](../wpf/data/data-binding-overview.md).  
  
 Wie bereits erwähnt, `x:Name` (oder `Name`) sollten in Situationen, in denen auch verwenden, nicht angewendet werden `x:Key`. Die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> verfügt über ein spezielles Verhalten von sich selbst als ein XAML-Namescope definiert, aber nicht implementiert oder null-Werte zurückgegeben <xref:System.Windows.Markup.INameScope> -APIs als eine Möglichkeit, dieses Verhalten zu erzwingen. Wenn der WPF XAML-Parser erkennt `Name` oder `x:Name` in einer XAML-definierten <xref:System.Windows.ResourceDictionary>, der Name wird nicht auf einem XAML-Namescope hinzugefügt. Es wird versucht, diesen Namen in einem XAML-Namescope gefunden und die `FindName` Methoden keine gültige Ergebnisse zurück.  
  
### <a name="xname-and-name"></a>X: Name und Name  
 Viele WPF-Anwendungsszenarien können vermeiden, dass jede Verwendung von der `x:Name` Attribut, da die `Name` Abhängigkeitseigenschaft wie angegeben in der Standard-XAML-Namespace für eine Reihe von wichtigen Basisklassen wie z. B. <xref:System.Windows.FrameworkElement> und <xref:System.Windows.FrameworkContentElement> denselben Zweck erfüllt. Es gibt noch einige häufig verwendete XAML und WPF-Szenarien, in denen code Zugriff auf ein Element ohne `Name` Eigenschaft auf der Frameworkebene ist wichtig. Bestimmte Animationen und Storyboards Unterstützungsklassen unterstützen z. B. keine `Name` -Eigenschaft, aber sie müssen häufig im Code verwiesen werden, um die Animation zu steuern. Geben Sie `x:Name` als Attribut für die Zeitachsen und Transformationen, die in XAML, erstellt werden, wenn Sie beabsichtigen, die sie später in Code verweisen.  
  
 Wenn <xref:System.Windows.FrameworkElement.Name%2A> steht als Eigenschaft in der Klasse <xref:System.Windows.FrameworkElement.Name%2A> und `x:Name` Synonym als Attribute verwendet werden können, aber eine Analyseausnahme führt, wenn beide auf dasselbe Element angegeben werden. Ist die XAML-Markup kompiliert, wird die Ausnahme bei der Markupkompilierung auftreten tritt sie andernfalls beim Laden.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> kann mithilfe der XAML-Attributsyntax festgelegt werden und in Code mit <xref:System.Windows.DependencyObject.SetValue%2A>; Beachten Sie jedoch die Einstellung der <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft im Code erstellt den repräsentativen Feldverweis innerhalb des XAML-Namescope keine in den meisten Fällen, in dem die XAML bereits wird, geladen. Nicht versucht wird, legen Sie <xref:System.Windows.FrameworkElement.Name%2A> im Code verwenden, <xref:System.Windows.NameScope> Methoden aus dem Code für den entsprechenden Namensbereich.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> kann auch mithilfe von Eigenschaftenelement-Syntax mit dem inneren Text festgelegt werden, aber das ist nicht üblich. Im Gegensatz dazu `x:Name` kann nicht festgelegt werden, im Eigenschaftenelement-Syntax XAML oder in Code mit <xref:System.Windows.DependencyObject.SetValue%2A>; es kann nur festgelegt werden mithilfe der Attributsyntax für Objekte, da es sich um eine Direktive ist.  
  
## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise  
 `x:Name` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace (x:)) Sprachfunktionen (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Strukturen in WPF](../wpf/advanced/trees-in-wpf.md)
