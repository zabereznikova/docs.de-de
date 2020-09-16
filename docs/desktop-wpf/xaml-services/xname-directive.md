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
ms.openlocfilehash: ddaa35b18d1c632fc49b18dabf0d992dc1c78fcc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549482"
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

Nachdem `x:Name` auf das Unterstützungs Programmiermodell eines Frameworks angewendet wurde, entspricht der Name der Variablen, die einen Objekt Verweis oder eine-Instanz enthält, die von einem Konstruktor zurückgegeben wird.

Der Wert einer `x:Name` direktivenverwendung muss innerhalb eines XAML-Namescope eindeutig sein. Standardmäßig wird der primäre XAML-Namescope bei Verwendung durch die .net XAML-Dienste-API im XAML-Stamm Element einer einzelnen XAML-Produktion definiert und umfasst die Elemente, die in dieser XAML-Produktion enthalten sind. Zusätzliche diskrete XAML-Namescopes, die möglicherweise in einer einzelnen XAML-Produktion auftreten, können von Frameworks definiert werden, um bestimmte Szenarien zu adressieren. In WPF werden z. b. neue XAML-Namescopes von jeder Vorlage definiert und erstellt, die auch in der XAML-Produktion definiert ist. Weitere Informationen zu XAML-Namescopes (für WPF geschrieben, aber für viele XAML-Namescope-Konzepte relevant) finden Sie unter [WPF-XAML-Namescopes](/dotnet/desktop/wpf/advanced/wpf-xaml-namescopes).

Im allgemeinen `x:Name` sollte nicht in Situationen angewendet werden, in denen auch verwendet wird `x:Key` . XAML-Implementierungen von bestimmten vorhandenen Frameworks haben Ersetzungs Konzepte zwischen `x:Key` und eingeführt `x:Name` , dies ist jedoch nicht empfehlenswert. .Net XAML-Dienste unterstützen diese Ersetzungs Konzepte nicht, wenn Name-/Schlüsselinformationen wie oder behandelt werden <xref:System.Windows.Markup.INameScope> <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> .

Regeln für die Durchführung von `x:Name` und die namens Eindeutigkeit werden potenziell durch spezifische implementierende Frameworks definiert. Damit Sie jedoch mit .net XAML-Diensten verwendet werden können, sollten die frameworkdefinitionen der XAML-Namescope-Eindeutigkeit mit der Definition der <xref:System.Windows.Markup.INameScope> Informationen in dieser Dokumentation konsistent sein und dieselben Regeln wie die Anwendung der Informationen verwenden. Beispielsweise [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] dividiert die-Implementierung verschiedene Markup Elemente in separate <xref:System.Windows.NameScope> Bereiche, z. b. Ressourcen Wörterbücher, die logische Struktur, die von XAML, Vorlagen und anderem verzögertem Inhalt auf Seitenebene erstellt wurde, und erzwingt dann die Eindeutigkeit des XAML-namens in jedem dieser XAML-Namescopes.

Für benutzerdefinierte Typen, die XAML-Objekt-Writer von .net XAML-Diensten verwenden, kann eine Eigenschaft, die einem Typ zugeordnet ist, `x:Name` eingerichtet oder geändert werden. Sie definieren dieses Verhalten, indem Sie auf den Namen der Eigenschaft verweisen, die im typdefinitions Code mit dem zugeordnet werden soll <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> .  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ist ein Attribut auf Typebene.

Using.net XAML-Dienste, die Unterstützungs Logik für die Unterstützung von XAML-Namescope kann durch Implementieren der-Schnittstelle auf eine frameworkneutrale Weise definiert werden <xref:System.Windows.Markup.INameScope> .

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Unter der Standardbuildkonfiguration für eine-Anwendung, die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML, partielle Klassen und Code Behind verwendet, wird der angegebene zum `x:Name` Namen eines Felds, das im zugrunde liegenden Code erstellt wird, wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] von einer Markup Kompilierungs Aufgabe erstellt wird, und dieses Feld einen Verweis auf das Objekt enthält. Standardmäßig ist das erstellte Feld intern. Sie können den Feld Zugriff ändern, indem Sie das [x:FieldModifier-Attribut](xfieldmodifier-directive.md)angeben. In WPF und Silverlight besteht die Sequenz darin, dass die Markup Kompilierung das Feld in einer partiellen Klasse definiert und benennt, der Wert jedoch anfänglich leer ist. Anschließend wird eine generierte Methode namens `InitializeComponent` innerhalb des Klassenkonstruktors aufgerufen. `InitializeComponent` besteht aus `FindName` aufrufen, die jeden der `x:Name` Werte verwenden, die im XAML-definierten Teil der partiellen Klasse als Eingabe Zeichenfolgen vorhanden sind. Die Rückgabewerte werden dann dem like-benannten Feldverweis zugewiesen, um die Feldwerte mit Objekten auszufüllen, die aus der XAML-Verarbeitung erstellt wurden. Die Ausführung von `InitializeComponent` ermöglicht das direkte verweisen auf das Laufzeitobjekt Diagramm mithilfe des `x:Name` /-Feldnamens, damit nicht explizit aufgerufen werden muss, wenn `FindName` Sie einen Verweis auf ein XAML-definiertes Objekt benötigen.

Bei einer WPF-Anwendung, die die Microsoft Visual Basic-Ziele verwendet und XAML-Dateien mit `Page` Buildaktion einschließt, wird während der Kompilierung eine separate Verweis Eigenschaft erstellt, die das- `WithEvents` Schlüsselwort allen Elementen mit einem hinzufügt `x:Name` , um die `Handles` Syntax für Ereignishandlerdelegaten zu unterstützen. Diese Eigenschaft ist immer öffentlich. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](/dotnet/desktop/wpf/advanced/visual-basic-and-wpf-event-handling).

`x:Name` wird vom WPF-XAML-Prozessor zum Registrieren eines Namens bei einem XAML-Namescope zur Ladezeit verwendet. Dies gilt auch für Fälle, in denen die Seite nicht durch Buildaktionen (z. b. lose XAML eines Ressourcen Wörterbuchs) von Markup kompiliert wird. Ein Grund für dieses Verhalten ist, dass `x:Name` möglicherweise für die <xref:System.Windows.Data.Binding.ElementName%2A> Bindung benötigt wird. Weitere Informationen finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).

Wie bereits erwähnt, `x:Name` sollte (oder `Name` ) in Situationen, in denen auch verwendet wird, nicht angewendet werden `x:Key` . Das [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> hat ein spezielles Verhalten, sich selbst als XAML-Namescope zu definieren, jedoch nicht implementierte oder NULL-Werte für <xref:System.Windows.Markup.INameScope> APIs als Möglichkeit zur Durchsetzung dieses Verhaltens zurückzugeben. Wenn der WPF-XAML `Name` -Parser oder `x:Name` eine XAML-Definition erkennt <xref:System.Windows.ResourceDictionary> , wird der Name keinem XAML-Namescope hinzugefügt. Wenn Sie versuchen, diesen Namen aus einem XAML-Namescope und den-Methoden zu finden, `FindName` werden keine gültigen Ergebnisse zurückgegeben.

### <a name="xname-and-name"></a>x:Name und Name

Viele WPF-Anwendungsszenarien können die Verwendung des- `x:Name` Attributs vermeiden, da die `Name` Abhängigkeits Eigenschaft, wie im XAML-Standard Namespace für mehrere der wichtigen Basisklassen wie und angegeben, <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> denselben Zweck erfüllt. Es gibt noch einige gängige XAML-und WPF-Szenarien, in denen der Code Zugriff auf ein Element ohne `Name` Eigenschaft auf Frameworkebene wichtig ist. Beispielsweise unterstützen bestimmte Animations-und Storyboard-Unterstützungs Klassen keine- `Name` Eigenschaft, aber häufig muss im Code auf Sie verwiesen werden, um die Animation zu steuern. Sie sollten `x:Name` als Attribut für Zeitachsen und Transformationen angeben, die in XAML erstellt werden, wenn Sie auf diese später aus Code verweisen möchten.

Wenn <xref:System.Windows.FrameworkElement.Name%2A> als Eigenschaft für die Klasse verfügbar ist und austauschbar <xref:System.Windows.FrameworkElement.Name%2A> `x:Name` als Attribute verwendet werden kann, wird eine Analyse Ausnahme ausgelöst, wenn beide für das gleiche Element angegeben werden. Wenn die XAML-Datei Markup kompiliert ist, tritt die Ausnahme bei der Markup Kompilierung auf; andernfalls tritt sie bei der Auslastung auf.

<xref:System.Windows.FrameworkElement.Name%2A> kann mithilfe der XAML-Attribut Syntax und im Code mithilfe von festgelegt werden <xref:System.Windows.DependencyObject.SetValue%2A> . Beachten Sie jedoch, dass das Festlegen der- <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft im Code nicht den repräsentativen Feldverweis innerhalb des XAML-Namescope in den meisten Fällen erstellt, in denen der XAML-Code bereits geladen wurde. Anstatt zu versuchen <xref:System.Windows.FrameworkElement.Name%2A> , im Code festzulegen, verwenden Sie <xref:System.Windows.NameScope> Methoden aus Code für den entsprechenden Namescope.

<xref:System.Windows.FrameworkElement.Name%2A> kann auch mit der Eigenschafts Element Syntax mit innerem Text festgelegt werden, dies ist jedoch nicht üblich. Im Gegensatz dazu `x:Name` kann nicht in der XAML-Eigenschafts Element Syntax oder im Code mithilfe von festgelegt werden <xref:System.Windows.DependencyObject.SetValue%2A> . Sie kann nur mithilfe der Attribut Syntax für Objekte festgelegt werden, da es sich um eine-Anweisung handelt.

## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise

`x:Name` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace (x:). Sprach Features (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Strukturen in WPF](/dotnet/desktop/wpf/advanced/trees-in-wpf)
