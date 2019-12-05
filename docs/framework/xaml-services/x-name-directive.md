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
ms.openlocfilehash: d17d977384962980839fbe2b2c0a4708412d403d
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837219"
---
# <a name="xname-directive"></a>x:Name-Anweisung
Identifiziert XAML-definierte Elemente in einem XAML-Namescope eindeutig. XAML-Namescopes und ihre Eindeutigkeits Modelle können auf instanziierte Objekte angewendet werden, wenn Frameworks APIs bereitstellen oder Verhalten implementieren, die zur Laufzeit auf das von XAML erstellte Objekt Diagramm zugreifen.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`XAMLNameValue`|Eine Zeichenfolge, die den Einschränkungen der [XamlName-Grammatik](xamlname-grammar.md)entspricht.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem `x:Name` auf das Unterstützungs Programmiermodell eines Frameworks angewendet wurde, entspricht der Name der Variablen, die einen Objekt Verweis oder eine-Instanz enthält, wie von einem Konstruktor zurückgegeben.  
  
 Der Wert einer `x:Name` direktivenverwendung muss innerhalb eines XAML-Namescope eindeutig sein. Standardmäßig wird der primäre XAML-Namescope bei Verwendung durch .NET Framework XAML-Dienste-API im XAML-Stamm Element einer einzelnen XAML-Produktion definiert und umfasst die Elemente, die in dieser XAML-Produktion enthalten sind. Zusätzliche diskrete XAML-Namescopes, die möglicherweise in einer einzelnen XAML-Produktion auftreten, können von Frameworks definiert werden, um bestimmte Szenarien zu adressieren. In WPF werden z. b. neue XAML-Namescopes von jeder Vorlage definiert und erstellt, die auch in der XAML-Produktion definiert ist. Weitere Informationen zu XAML-Namescopes (für WPF geschrieben, aber für viele XAML-Namescope-Konzepte relevant) finden Sie unter [WPF-XAML-Namescopes](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 Im Allgemeinen sollten `x:Name` in Situationen, in denen auch `x:Key`verwendet wird, nicht angewendet werden. XAML-Implementierungen von bestimmten vorhandenen Frameworks haben Ersetzungs Konzepte zwischen `x:Key` und `x:Name`eingeführt, dies ist jedoch nicht empfehlenswert. .NET Framework XAML-Dienste unterstützen diese Ersetzungs Konzepte nicht, wenn Name-/Schlüsselinformationen wie <xref:System.Windows.Markup.INameScope> oder <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>behandelt werden.  
  
 Regeln für die Durchführung von `x:Name` sowie die Erzwingung der namens Eindeutigkeit werden potenziell durch spezifische implementierende Frameworks definiert. Um jedoch mit .NET Framework XAML-Diensten verwendbar zu sein, sollten die frameworkdefinitionen der XAML-Namescope-Eindeutigkeit mit der Definition der <xref:System.Windows.Markup.INameScope> Informationen in dieser Dokumentation konsistent sein und dieselben Regeln wie die Informationen verwenden, auf die die Informationen angewendet werden. Beispielsweise dividiert die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]-Implementierung verschiedene Markup Elemente in separate <xref:System.Windows.NameScope> Bereiche, z. b. Ressourcen Wörterbücher, die logische Struktur, die von der XAML-Datei auf Seitenebene, Vorlagen und anderen verzögerten Inhalt erstellt wird, und erzwingt dann die Eindeutigkeit des XAML-namens innerhalb jedes dieser XAML-Namescopes.  
  
 Bei benutzerdefinierten Typen, die XAML-objektwriter .NET Framework XAML-Dienste verwenden, kann eine Eigenschaft, die `x:Name` für einen Typ zugeordnet ist, eingerichtet oder geändert werden. Sie definieren dieses Verhalten, indem Sie auf den Namen der Eigenschaft verweisen, die dem <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> im typdefinitions Code zugeordnet werden soll.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ist ein Attribut auf Typebene.  
  
 Using.NET Framework-XAML-Dienste, die Unterstützungs Logik für die Unterstützung von XAML-Namescope kann auf eine frameworkneutrale Weise definiert werden, indem die <xref:System.Windows.Markup.INameScope>-Schnittstelle implementiert wird.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Unter der Standardbuildkonfiguration für eine [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Anwendung, die XAML, partielle Klassen und Code Behind verwendet, wird der angegebene `x:Name` der Name eines Felds, das im zugrunde liegenden Code erstellt wird, wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] von einer Markup Kompilierungs Aufgabe erstellt wird, und dieses Feld enthält einen Verweis auf das Objekt. Standardmäßig ist das erstellte Feld intern. Sie können den Feld Zugriff ändern, indem Sie das [x:FieldModifier-Attribut](x-fieldmodifier-directive.md)angeben. In WPF und Silverlight besteht die Sequenz darin, dass die Markup Kompilierung das Feld in einer partiellen Klasse definiert und benennt, der Wert jedoch anfänglich leer ist. Anschließend wird eine generierte Methode namens "`InitializeComponent`" innerhalb des Klassenkonstruktors aufgerufen. `InitializeComponent` besteht aus `FindName` aufrufen, die jeden der `x:Name` Werte verwenden, die im XAML-definierten Teil der partiellen Klasse als Eingabe Zeichenfolgen vorhanden sind. Die Rückgabewerte werden dann dem like-benannten Feldverweis zugewiesen, um die Feldwerte mit Objekten auszufüllen, die aus der XAML-Verarbeitung erstellt wurden. Durch die Ausführung von `InitializeComponent` können Sie auf das Laufzeitobjekt Diagramm direkt mithilfe des `x:Name`/Feldnamens verweisen, anstatt `FindName` explizit aufrufen zu müssen, wenn Sie einen Verweis auf ein XAML-definiertes Objekt benötigen.  
  
 Für eine WPF-Anwendung, die die Microsoft Visual Basic-Ziele verwendet und XAML-Dateien mit `Page` Build-Aktion enthält, wird während der Kompilierung eine separate Verweis Eigenschaft erstellt, die das `WithEvents`-Schlüsselwort allen Elementen mit `x:Name`hinzufügt, um `Handles` Syntax für Ereignishandlerdelegaten zu unterstützen. Diese Eigenschaft ist immer öffentlich. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name` wird vom WPF-XAML-Prozessor zum Registrieren eines Namens bei einem XAML-Namescope zur Ladezeit verwendet. Dies gilt auch für Fälle, in denen die Seite nicht durch Buildaktionen (z. b. lose XAML eines Ressourcen Wörterbuchs) von Markup kompiliert wird. Ein Grund für dieses Verhalten ist, dass die `x:Name` für <xref:System.Windows.Data.Binding.ElementName%2A> Bindung potenziell benötigt wird. Weitere Informationen finden Sie unter [Übersicht über die Datenbindung](../../desktop-wpf/data/data-binding-overview.md).  
  
 Wie bereits erwähnt, sollten `x:Name` (oder `Name`) in Situationen, in denen auch `x:Key`verwendet wird, nicht angewendet werden. Der [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> weist ein besonderes Verhalten auf, sich selbst als XAML-Namescope zu definieren, jedoch nicht implementierte oder NULL-Werte für <xref:System.Windows.Markup.INameScope> APIs zurückzugeben, um dieses Verhalten zu erzwingen. Wenn der WPF-XAML-Parser auf `Name` oder `x:Name` in einem XAML-definierten <xref:System.Windows.ResourceDictionary>stößt, wird der Name keinem XAML-Namescope hinzugefügt. Wenn Sie versuchen, diesen Namen aus einem XAML-Namescope und den `FindName`-Methoden zu finden, werden keine gültigen Ergebnisse zurückgegeben.  
  
### <a name="xname-and-name"></a>x:Name und Name  
 Viele WPF-Anwendungsszenarien können die Verwendung des `x:Name`-Attributs vermeiden, da die `Name`-Abhängigkeits Eigenschaft, wie im XAML-Standard Namespace für mehrere der wichtigen Basisklassen wie <xref:System.Windows.FrameworkElement> und <xref:System.Windows.FrameworkContentElement> angegeben, denselben Zweck erfüllt. Es gibt noch einige gängige XAML-und WPF-Szenarien, in denen der Code Zugriff auf ein Element ohne `Name`-Eigenschaft auf Frameworkebene wichtig ist. Beispielsweise unterstützen bestimmte Animations-und Storyboard-Unterstützungs Klassen keine `Name`-Eigenschaft, aber Sie müssen häufig im Code darauf verweisen, um die Animation zu steuern. Sie sollten `x:Name` als Attribut für Zeitachsen und Transformationen angeben, die in XAML erstellt werden, wenn Sie auf diese später aus Code verweisen möchten.  
  
 Wenn <xref:System.Windows.FrameworkElement.Name%2A> als Eigenschaft für die Klasse verfügbar ist, können <xref:System.Windows.FrameworkElement.Name%2A> und `x:Name` austauschbar als Attribute verwendet werden, aber eine Analyse Ausnahme ergibt sich, wenn beide für das gleiche Element angegeben werden. Wenn die XAML-Datei Markup kompiliert ist, tritt die Ausnahme bei der Markup Kompilierung auf; andernfalls tritt sie bei der Auslastung auf.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> können mithilfe der XAML-Attribut Syntax und in Code, der <xref:System.Windows.DependencyObject.SetValue%2A>verwendet, festgelegt werden. Beachten Sie jedoch, dass das Festlegen der <xref:System.Windows.FrameworkElement.Name%2A>-Eigenschaft im Code nicht den repräsentativen Feldverweis innerhalb des XAML-Namescope in den meisten Fällen erstellt, in denen der XAML-Code bereits geladen wurde. Anstatt zu versuchen, <xref:System.Windows.FrameworkElement.Name%2A> im Code festzulegen, verwenden Sie <xref:System.Windows.NameScope> Methoden aus Code für den entsprechenden Namescope.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> können auch mithilfe der Eigenschafts Element Syntax mit innerem Text festgelegt werden, dies ist jedoch nicht üblich. Im Gegensatz dazu können `x:Name` in der XAML-Eigenschafts Element Syntax oder in Code, der <xref:System.Windows.DependencyObject.SetValue%2A>verwendet, nicht festgelegt werden. Sie kann nur mithilfe der Attribut Syntax für Objekte festgelegt werden, da Sie eine-Direktive ist.  
  
## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise  
 `x:Name` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace (x:). Sprach Features (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Strukturen in WPF](../wpf/advanced/trees-in-wpf.md)
