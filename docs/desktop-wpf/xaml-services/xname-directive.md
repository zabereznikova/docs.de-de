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
ms.openlocfilehash: 9f812a49a3217a563be1bd7f1d999b641c28463d
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432713"
---
# <a name="xname-directive"></a>x:Name-Anweisung

Identifiziert XAML-definierte Elemente eindeutig in einem XAML-Namescope. XAML-Namescopes und ihre Eindeutigkeitsmodelle können auf die instanziierten Objekte angewendet werden, wenn Frameworks APIs bereitstellen oder Verhaltensweisen implementieren, die zur Laufzeit auf das von XAML erstellte Objektdiagramm zugreifen.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`XAMLNameValue`|Eine Zeichenfolge, die den Einschränkungen der [XamlName-Grammatik](xamlname-grammar.md)entspricht.|

## <a name="remarks"></a>Bemerkungen

Nachdem `x:Name` der Name auf das Unterstützende Programmiermodell eines Frameworks angewendet wird, entspricht er der Variablen, die einen Objektverweis oder eine Instanz enthält, die von einem Konstruktor zurückgegeben wird.

Der Wert `x:Name` einer Direktivenverwendung muss innerhalb eines XAML-Namescopes eindeutig sein. Bei Verwendung durch .NET XAML Services API wird das primäre XAML-Namescope standardmäßig im XAML-Stammelement einer einzelnen XAML-Produktion definiert und umfasst die Elemente, die in dieser XAML-Produktion enthalten sind. Zusätzliche diskrete XAML-Namescopes, die in einer einzelnen XAML-Produktion auftreten können, können von Frameworks definiert werden, um bestimmte Szenarien zu adressieren. In WPF werden beispielsweise neue XAML-Namescopes von jeder Vorlage definiert und erstellt, die auch für diese XAML-Produktion definiert ist. Weitere Informationen zu XAML-Namescopes (für WPF geschrieben, aber für viele XAML-Namescope-Konzepte relevant) finden Sie unter [WPF XAML Namescopes](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

Im Allgemeinen `x:Name` sollte nicht in Situationen `x:Key`angewendet werden, die auch verwenden. XAML-Implementierungen durch bestimmte vorhandene Frameworks `x:Key` `x:Name`haben Substitutionskonzepte zwischen und eingeführt, aber das ist keine empfohlene Vorgehensweise. .NET XAML Services unterstützt solche Ersetzungskonzepte nicht, <xref:System.Windows.Markup.INameScope> <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>wenn Namens-/Schlüsselinformationen wie oder verarbeitet werden.

Regeln für die `x:Name` Genehmigung sowie die Durchsetzung der Eindeutigkeit des Namens werden möglicherweise durch spezifische Durchführungsrahmen definiert. Um jedoch mit .NET XAML Services verwendet werden zu können, sollten die Frameworkdefinitionen <xref:System.Windows.Markup.INameScope> der XAML-Namescope-Eindeutigkeit mit der Definition von Informationen in dieser Dokumentation übereinstimmen und dieselben Regeln für den Einsatz der Informationen verwenden. Die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Implementierung unterteilt z. B. verschiedene <xref:System.Windows.NameScope> Markupelemente in separate Bereiche, z. B. Ressourcenwörterbücher, die logische Struktur, die von XAML auf Seitenebene erstellt wird, Vorlagen und andere verzögerte Inhalte, und erzwingt dann die Eindeutigkeit des XAML-Namens in jedem dieser XAML-Namescopes.

Für benutzerdefinierte Typen, die XAML-Objektwriter von .NET `x:Name` XAML Services verwenden, kann eine Eigenschaft eingerichtet oder geändert werden, der einem Typ zugeordnet ist. Sie definieren dieses Verhalten, indem Sie auf den <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> Namen der Eigenschaft verweisen, die dem im Typdefinitionscode zugeordnet werden soll.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>ist ein Attribut auf Typebene.

Using.NET XAML-Diensten kann die Sicherungslogik für die XAML-Namescope-Unterstützung <xref:System.Windows.Markup.INameScope> durch Implementierung der Schnittstelle frameworkneutral definiert werden.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Unter der Standardbuildkonfiguration [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] für eine Anwendung, die XAML, Partielle Klassen und CodeBehind verwendet, wird das angegebene `x:Name` zum Namen eines Felds, das im zugrunde liegenden Code erstellt wird, wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] es von einer Markupkompilierungserstellungsaufgabe verarbeitet wird, und dieses Feld enthält einen Verweis auf das Objekt. Standardmäßig ist das erstellte Feld intern. Sie können den Feldzugriff ändern, indem Sie das [Attribut x:FieldModifier](xfieldmodifier-directive.md)angeben. In WPF und Silverlight besteht die Sequenz darin, dass die Markupkompilierung das Feld in einer partiellen Klasse definiert und benennt, der Wert jedoch zunächst leer ist. Anschließend wird eine `InitializeComponent` generierte Methode mit dem Namen innerhalb des Klassenkonstruktors aufgerufen. `InitializeComponent`besteht `FindName` aus Aufrufen, `x:Name` die jeden der Werte verwenden, die im XAML-definierten Teil der partiellen Klasse als Eingabezeichenfolgen vorhanden sind. Die Rückgabewerte werden dann dem gleichbenannten Feldverweis zugewiesen, um die Feldwerte mit Objekten auszufüllen, die aus der XAML-Analyse erstellt wurden. Die Ausführung `InitializeComponent` von machen es möglich, das `x:Name` Laufzeitobjektdiagramm direkt mit dem `FindName` /-Feldnamen zu referenzieren, anstatt explizit aufrufen zu müssen, wenn Sie einen Verweis auf ein XAML-definiertes Objekt benötigen.

Für eine WPF-Anwendung, die die Microsoft Visual Basic-Ziele verwendet und XAML-Dateien `Page` mit `WithEvents` Buildaktion enthält, `x:Name`wird während `Handles` der Kompilierung eine separate Referenzeigenschaft erstellt, die das Schlüsselwort allen Elementen mit einem hinzufügt, um die Syntax für Ereignishandlerdelegaten zu unterstützen. Diese Unterkunft ist immer öffentlich. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../../framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).

`x:Name`wird vom WPF-XAML-Prozessor verwendet, um einen Namen zum Zeitpunkt des Ladens in einem XAML-Namescope zu registrieren, auch in Fällen, in denen die Seite nicht durch Buildaktionen (z. B. loses XAML eines Ressourcenwörterbuchs) markupkompiliert wird. Ein Grund für dieses `x:Name` Verhalten ist, <xref:System.Windows.Data.Binding.ElementName%2A> dass die möglicherweise für die Bindung benötigt wird. Weitere Informationen finden Sie unter [Datenbindungsübersicht](../data/data-binding-overview.md).

Wie bereits `x:Name` erwähnt, `Name`(oder ) sollte nicht `x:Key`in Situationen angewendet werden, die auch verwenden . Der [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> hat ein spezielles Verhalten, sich selbst als XAML-Namescope zu definieren, aber Nicht implementierte oder null Werte für <xref:System.Windows.Markup.INameScope> APIs zurückzugeben, um dieses Verhalten zu erzwingen. Wenn der WPF XAML-Parser auf trifft `Name` oder `x:Name` in einem XAML-definierten <xref:System.Windows.ResourceDictionary>, wird der Name keinem XAML-Namescope hinzugefügt. Der Versuch, diesen Namen aus einem Beliebigen `FindName` XAML-Namescope und den Methoden zu finden, gibt keine gültigen Ergebnisse zurück.

### <a name="xname-and-name"></a>x:Name und Name

Viele WPF-Anwendungsszenarien können jede `x:Name` Verwendung des `Name` Attributs vermeiden, da die Abhängigkeitseigenschaft, wie im Standard-XAML-Namespace für mehrere wichtige Basisklassen angegeben, wie <xref:System.Windows.FrameworkElement> z. B. <xref:System.Windows.FrameworkContentElement> und diesen Zweck erfüllt. Es gibt immer noch einige gängige XAML- und WPF-Szenarien, in denen der Codezugriff auf ein Element ohne `Name` Eigenschaft auf Frameworkebene wichtig ist. Bestimmte Animations- und Storyboard-Unterstützungsklassen `Name` unterstützen z. B. keine Eigenschaft, müssen jedoch häufig im Code referenziert werden, um die Animation zu steuern. Sie sollten `x:Name` als Attribut für Zeitachsen und Transformationen angeben, die in XAML erstellt werden, wenn Sie sie später aus Code referenzieren möchten.

Wenn <xref:System.Windows.FrameworkElement.Name%2A> als Eigenschaft für die <xref:System.Windows.FrameworkElement.Name%2A> Klasse `x:Name` verfügbar ist und austauschbar als Attribute verwendet werden kann, ergibt sich jedoch eine Analyseausnahme, wenn beide für dasselbe Element angegeben sind. Wenn das XAML-Markup kompiliert wird, tritt die Ausnahme beim Markupkompilieren auf, andernfalls beim Laden.

<xref:System.Windows.FrameworkElement.Name%2A>kann mithilfe der XAML-Attributsyntax und <xref:System.Windows.DependencyObject.SetValue%2A>im Code mit festgelegt werden. Beachten Sie jedoch, dass das Festlegen der <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft im Code in den meisten Fällen, in denen das XAML bereits geladen ist, nicht den repräsentativen Feldverweis innerhalb des XAML-Namescopes erstellt. Anstatt zu versuchen, <xref:System.Windows.FrameworkElement.Name%2A> Code festzulegen, verwenden Sie <xref:System.Windows.NameScope> Methoden aus Code für das entsprechende Namescope.

<xref:System.Windows.FrameworkElement.Name%2A>kann auch mithilfe der Eigenschaftenelementsyntax mit innerem Text festgelegt werden, aber das ist ungewöhnlich. Im Gegensatz `x:Name` dazu kann nicht in der XAML-Eigenschaftselementsyntax oder im Code mit <xref:System.Windows.DependencyObject.SetValue%2A>festgelegt werden. Sie kann nur mithilfe der Attributsyntax für Objekte festgelegt werden, da es sich um eine Direktive handelt.

## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise

`x:Name` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML Namespace (x:) Sprachfunktionen (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Strukturen in WPF](../../framework/wpf/advanced/trees-in-wpf.md)
