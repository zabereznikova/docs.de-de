---
title: Übersicht über angefügte Eigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: b207db459776c9f8fa7ea247d01071eeb8c995cf
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739297"
---
# <a name="attached-properties-overview"></a>Übersicht über angefügte Eigenschaften

Eine angefügte Eigenschaft ist ein von XAML definiertes Konzept. Eine angefügte Eigenschaft ist für die Verwendung als Typ einer globalen Eigenschaft vorgesehen, der in jedem Objekt festgelegt werden kann. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden angefügte Eigenschaften in der Regel als eine spezielle Form der Abhängigkeitseigenschaft definiert, die nicht die herkömmliche Eigenschaft „Wrapper“ aufweist.

## <a name="prerequisites"></a>Voraussetzungen<a name="prerequisites"></a>

In diesem Artikel wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften aus der Perspektive eines Consumers vorhandener Abhängigkeitseigenschaften für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Klassen verstehen und die [Abhängigkeitseigenschaftenübersicht](dependency-properties-overview.md)gelesen haben. Um den Beispielen in diesem Artikel zu folgen, sollten Sie auch XAML verstehen und wissen, wie Man WPF-Anwendungen schreibt.

## <a name="why-use-attached-properties"></a>Warum angefügte Eigenschaften verwenden<a name="attached_properties_usage"></a>

Ein Zweck einer angefügten Eigenschaft besteht darin, verschiedenen untergeordneten Elementen das Angeben eindeutiger Werte für eine Eigenschaft zu ermöglichen, die in einem übergeordneten Element definiert ist. Eine bestimmte Anwendung dieses Szenario: Untergeordnete Elemente informieren übergeordnete Element, wie diese im [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt werden sollen. Ein Beispiel <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> ist die Eigenschaft. Die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Eigenschaft wird als angefügte Eigenschaft erstellt, da sie so <xref:System.Windows.Controls.DockPanel> konzipiert ist, dass sie für Elemente festgelegt wird, die in einer und nicht auf <xref:System.Windows.Controls.DockPanel> sich selbst enthalten sind. Die <xref:System.Windows.Controls.DockPanel> Klasse definiert <xref:System.Windows.DependencyProperty> das <xref:System.Windows.Controls.DockPanel.DockProperty>statische Feld mit <xref:System.Windows.Controls.DockPanel.GetDock%2A> <xref:System.Windows.Controls.DockPanel.SetDock%2A> dem Namen , und stellt dann die und Methoden als öffentliche Accessoren für die angefügte Eigenschaft bereit.

## <a name="attached-properties-in-xaml"></a>Angefügte Eigenschaften in XAML<a name="attached_properties_xaml"></a>

In XAML legen Sie angefügte Eigenschaften mithilfe der Syntax *AttachedPropertyProvider*.*PropertyName* fest.

Im Folgenden finden Sie ein <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Beispiel dafür, wie Sie XAML festlegen können:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Die Verwendung ähnelt einer statischen Eigenschaft. Sie verweisen immer <xref:System.Windows.Controls.DockPanel> auf den Typ, der die angehängte Eigenschaft besitzt und registriert, anstatt auf eine Instanz zu verweisen, die durch den Namen angegeben ist.

Da eine angefügte Eigenschaft in XAML ein Attribut ist, das Sie im Markup festlegen, besitzt außerdem nur der Mengenvorgang Relevanz. Sie können eine Eigenschaft in XAML nicht direkt abrufen, obwohl einige indirekte Mechanismen zum Vergleichen von Werten vorhanden sind, wie z.B. Trigger in Formaten (weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)).

### <a name="attached-property-implementation-in-wpf"></a>Implementierung von angefügten Eigenschaften in WPF

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]werden die meisten UI-bezogenen angefügten Eigenschaften für WPF-Typen als Abhängigkeitseigenschaften implementiert. Angefügte Eigenschaften sind ein XAML-Konzept, während Abhängigkeitseigenschaften ein WPF-Konzept sind. Da von WPF angefügte Eigenschaften Abhängigkeitseigenschaften sind, unterstützen sie Abhängigkeitseigenschaftskonzepte wie Eigenschaftenmetadaten und Standardwerte aus diesen Eigenschaftenmetadaten.

## <a name="how-attached-properties-are-used-by-the-owning-type"></a>Wie angefügte Eigenschaften vom Besitzendentyp verwendet werden<a name="howused"></a>

Obwohl angefügte Eigenschaften für jedes beliebige Objekt festgelegt werden können, bedeutet dies nicht automatisch, dass die Eigenschaft ein reales Ergebnis erzeugt, oder der Wert jemals von einem anderen Objekt verwendet wird. Im Allgemeinen werden angefügte Eigenschaften vorgesehen, damit Objekte, die aus einer Vielzahl von möglichen Klassenhierarchien oder logischen Beziehungen stammen, dem Typ, der die angefügte Eigenschaft definiert, allgemeine Informationen melden können. Der Typ, der die angefügte Eigenschaft definiert, folgt in der Regel einem dieser Modelle:

- Der Typ, der die angefügte Eigenschaft definiert, ist so konzipiert, dass er das übergeordnete Element der Elemente sein kann, das Werte für die angefügte Eigenschaft festlegen wird. Der Typ durchläuft dann seine untergeordneten Objekte durch die interne Logik auf der Grundlage der Objektstruktur, ruft die Werte ab und fungiert auf irgendeine Weise für diese Werte.

- Der Typ, der die angefügte Eigenschaft definiert, wird als untergeordnetes Element für verschiedene mögliche übergeordnete Elemente und Inhaltsmodelle verwendet werden.

- Der Typ, der die angefügte Eigenschaft definiert, stellt einen Dienst dar. Andere Typen legen Werte für die angefügte Eigenschaft fest. Wenn das Element, das die Eigenschaft festlegt, im Kontext des Dienstes ausgewertet wird, werden über die interne Logik der Dienstklasse die angefügten Eigenschaftswerte abgerufen.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Ein Beispiel für eine übergeordnete definierte angefügte Eigenschaft

Das typischste Szenario, in dem WPF eine angefügte Eigenschaft definiert, ist, wenn ein übergeordnetes Element eine untergeordnete Elementauflistung unterstützt, und implementiert auch ein Verhalten, bei dem die Besonderheiten des Verhaltens für jedes untergeordnete Element einzeln gemeldet werden.

<xref:System.Windows.Controls.DockPanel>definiert die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte <xref:System.Windows.Controls.DockPanel> Eigenschaft und verfügt über Code auf Klassenebene <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>als Teil der Renderlogik (speziell und ). Eine <xref:System.Windows.Controls.DockPanel> Instanz überprüft immer, ob eines der unmittelbaren untergeordneten <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>Elemente einen Wert für festgelegt hat. Wenn dies der Fall ist, werden diese Werte zur Eingabe für die Renderinglogik, die auf das jeweilige untergeordnete Element angewendet wird. Geschachtelte <xref:System.Windows.Controls.DockPanel> Instanzen behandeln jeweils ihre eigenen unmittelbaren untergeordneten Elementauflistungen, aber dieses Verhalten ist implementierungsspezifisch für die Art und Weise, wie <xref:System.Windows.Controls.DockPanel> Werte verarbeitet <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> werden. Es ist theoretisch möglich, angefügte Eigenschaften zu besitzen, die Elemente über das unmittelbar übergeordnete Element hinaus beeinflussen. Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> die angefügte Eigenschaft für ein <xref:System.Windows.Controls.DockPanel> Element festgelegt ist, das kein übergeordnetes Element zum Handeln hat, wird kein Fehler oder eine Ausnahme ausgelöst. Dies bedeutet lediglich, dass ein globaler Eigenschaftswert festgelegt wurde, aber er hat kein aktuelles <xref:System.Windows.Controls.DockPanel> übergeordnetes Element, das die Informationen verwenden könnte.

## <a name="attached-properties-in-code"></a>Angefügte Eigenschaften im Code<a name="attached_properties_code"></a>

Angefügte Eigenschaften in WPF verfügen nicht über die typischen CLR-"Wrapper"-Methoden für einfachen Zugriff auf den Zugriff. Dies liegt daran, dass die angefügte Eigenschaft nicht unbedingt Teil des CLR-Namespace für Instanzen ist, in denen die Eigenschaft festgelegt ist. Allerdings muss ein XAML-Prozessor in der Lage sein, diese Werte festzulegen, wenn XAML analysiert wird. Um eine effektive Verwendung von angefügten Eigenschaften zu unterstützen, muss der Besitzertyp der angefügten Eigenschaft dedizierte Accessormethoden in der Form **Get_PropertyName_** und **Set_PropertyName_** implementieren. Diese dedizierten Accessormethoden eignen sich auch zum Abrufen oder Festlegen der angefügten Eigenschaft im Code. Im Hinblick auf Code ist eine angefügte Eigenschaft einem dahinter liegenden Feld ähnlich, das Methodenaccessoren anstelle von Eigenschaftenaccessoren besitzt, und das dahinter liegende Feld kann in jedem Objekt vorhanden sein, anstatt explizit definiert werden zu müssen.

Das folgende Beispiel zeigt, wie Sie eine angefügte Eigenschaft im Code festlegen können. In diesem `myCheckBox` Beispiel ist eine <xref:System.Windows.Controls.CheckBox> Instanz der Klasse.

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Ähnlich wie im XAML-Fall würde die fünfte Codezeile keine Ausnahme auslösen, wenn `myCheckBox` sie nicht bereits als untergeordnetes Element der `myDockPanel` vierten <xref:System.Windows.Controls.DockPanel> Codezeile hinzugefügt worden wäre, aber der Eigenschaftswert würde nicht mit einem übergeordneten Element interagieren und somit nichts bewirken. Nur <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> ein Wert, der für ein untergeordnetes Element in Kombination mit dem Vorhandensein eines <xref:System.Windows.Controls.DockPanel> übergeordneten Elements festgelegt wird, führt zu einem effektiven Verhalten in der gerenderten Anwendung. (In diesem Fall könnten Sie die angefügte Eigenschaft festlegen und anschließend an die Struktur anfügen. Oder Sie könnten die angefügte Eigenschaft an die Struktur anfügen und anschließend festlegen. Jede Reihenfolge stellt das gleiche Ergebnis bereit.)

## <a name="attached-property-metadata"></a>Angefügte Eigenschaftenmetadaten<a name="attached_properties_metadata"></a>

Beim Registrieren der <xref:System.Windows.FrameworkPropertyMetadata> Eigenschaft wird festgelegt, dass Merkmale der Eigenschaft angegeben werden, z. B. ob sich die Eigenschaft auf rendering, measurement usw. auswirkt. Metadaten für eine angefügte Eigenschaft unterscheiden sich im Allgemeinen nicht von denen für eine Abhängigkeitseigenschaft. Wenn Sie einen Standardwert in einer Überschreibung für die Metadaten von angefügten Eigenschaften angeben, wird dieser Wert der Standardwert der impliziten angefügten Eigenschaft in Instanzen der überschreibenden Klasse. Der Standardwert wird insbesondere gemeldet, wenn ein Prozess den Wert einer angefügten Eigenschaft über die `Get`-Methodenaccessoren für diese Eigenschaft abfragt, die eine Instanz der Klasse angibt, in dem Sie die Metadaten festgelegt haben, und wenn der Wert für diese angefügte Eigenschaft andernfalls nicht festgelegt war.

Wenn Sie die Vererbung von Eigenschaftswerten für eine Eigenschaft aktivieren möchten, sollten Sie die angefügten Eigenschaften anstelle von nicht angefügten Abhängigkeitseigenschaften verwenden. Weitere Informationen finden Sie unter [Eigenschaftenwertvererbung](property-value-inheritance.md).

## <a name="custom-attached-properties"></a>Benutzerdefinierte angefügte Eigenschaften<a name="custom"></a>

### <a name="when-to-create-an-attached-property"></a>Wann eine angefügte Eigenschaft erstellt werden soll<a name="create_attached_properties"></a>

Sie können eine angefügte Eigenschaft erstellen, wenn ein Mechanismus für Eigenschafteneinstellungen für andere Klassen als die definierende Klasse zur Verfügung stehen muss. Das gängigste Szenario hierfür ist Layout. Beispiele für vorhandene <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>Layouteigenschaften sind , <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>und <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. Das hier aktivierte Szenario: Elemente, die als untergeordnete Elemente für das Layout steuernde Elemente vorhanden sind, können Layoutanforderungen einzeln an die übergeordneten Layoutelemente stellen, für jede Einstellung einen Eigenschaftswert, den das übergeordnete Element als angefügte Eigenschaft definiert.

Ein weiteres Szenario für die Verwendung einer angefügten Eigenschaft: Wenn Ihre Klasse einen Dienst darstellt und Sie möchten, dass Klassen den Dienst auf transparentere Weise integrieren können.

Ein weiteres Szenario besteht darin, Visual Studio WPF Designer-Unterstützung zu erhalten, z. B. die Bearbeitung von **Eigenschaftenfenstern.** Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).

Wie bereits erwähnt, sollten Sie als eine angefügte Eigenschaft registrieren, wenn Sie die Vererbung von Eigenschaftswerten verwenden möchten.

### <a name="how-to-create-an-attached-property"></a>So erstellen Sie eine angefügte Eigenschaft<a name="how_do_i_create_attached_properties"></a>

Wenn Ihre Klasse die angefügte Eigenschaft strikt für die Verwendung für andere <xref:System.Windows.DependencyObject>Typen definiert, muss die Klasse nicht von ableiten. Sie müssen jedoch ableiten, <xref:System.Windows.DependencyObject> wenn Sie dem gesamten WPF-Modell folgen, dass Ihre angefügte Eigenschaft auch eine Abhängigkeitseigenschaft ist.

Definieren Sie Ihre angefügte Eigenschaft als `public static readonly` Abhängigkeitseigenschaft, indem Sie ein Feld vom Typ <xref:System.Windows.DependencyProperty>deklarieren. Sie definieren dieses Feld mithilfe des <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Rückgabewerts der Methode. Der Feldname muss mit dem angehängten `Property`Eigenschaftsnamen übereinstimmen, der an die Zeichenfolge angehängt wird, um dem festgelegten WPF-Muster zu folgen, bei dem die identifizierenden Felder im Vergleich zu den Eigenschaften, die sie darstellen, benannt werden. Der angefügte Eigenschaftsanbieter muss auch statische **Get_PropertyName_** und **Set_PropertyName_** Methoden als Accessoren für die angefügte Eigenschaft bereitstellen. Andernfalls kann das Eigenschaftensystem ihre angefügte Eigenschaft nicht verwenden.

> [!NOTE]
> Wenn Sie den get-Accessor der angefügten Eigenschaft weglassen, funktioniert die Datenbindung für die Eigenschaft in Entwurfstools wie Visual Studio und Blend für Visual Studio nicht.

#### <a name="the-get-accessor"></a>Der Get-Accessor

Die Signatur für den **Get_PropertyName_-Accessor** muss sein:

`public static object GetPropertyName(object target)`

- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Die <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> Methode gibt z. <xref:System.Windows.UIElement>B. den Parameter als ein, <xref:System.Windows.UIElement> da die angefügte Eigenschaft nur für Instanzen festgelegt werden soll.

- Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Die <xref:System.Windows.Controls.DockPanel.GetDock%2A> Methode typt sie <xref:System.Windows.Controls.Dock>z. B. als , da der Wert nur auf diese Enumeration festgelegt werden kann.

#### <a name="the-set-accessor"></a>Der Set-Accessor

Die Signatur für den **Set_PropertyName_-Accessor** muss sein:

`public static void SetPropertyName(object target, object value)`

- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Die <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode gibt sie <xref:System.Windows.UIElement>z. B. als ein, da <xref:System.Windows.UIElement> die angefügte Eigenschaft nur für Instanzen festgelegt werden soll.

- Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Die <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode typt sie <xref:System.Windows.Controls.Dock>z. B. als , da der Wert nur auf diese Enumeration festgelegt werden kann. Denken Sie daran, dass der Wert für diese Methode die Eingabe des XAML-Loaders ist, wenn sie Ihre angefügte Eigenschaft in einer Verwendung der angefügten Eigenschaft im Markup erkennt. Diese Eingabe ist der Wert, der als XAML-Attributwert im Markup angegeben wird. Aus diesem Grund muss die Typkonvertierung, das Wertserialisierungsprogramm oder die Unterstützung von Markuperweiterungen für den verwendeten Typ vorhanden sein, damit der entsprechende Typ aus dem Attributwert (der letztendlich nur eine Zeichenfolge ist) erstellt werden kann.

Das folgende Beispiel zeigt die Abhängigkeitseigenschaftsregistrierung (mit der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode) sowie die **Get_PropertyName_** und **Set_PropertyName_** Accessoren. Im Beispiel ist der Name der angefügten Eigenschaft `IsBubbleSource`. Deshalb müssen die Accessoren `GetIsBubbleSource` und `SetIsBubbleSource` genannt werden.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Attribute von angefügten Eigenschaften

WPF definiert mehrere .NET-Attribute, die Informationen über angefügte Eigenschaften für Reflektionsprozesse und für typische Benutzer von Reflektions- und Eigenschaftsinformationen wie Designerbereitstellen, bereitstellen sollen. Da angefügte Eigenschaften einen uneingeschränkten Bereich haben, benötigen Entwickler eine Möglichkeit, Benutzer nicht durch eine globale Liste aller angefügten Eigenschaften zu überwältigen, die in einer bestimmten Implementierung von Technologie definiert sind, die XAML verwendet. Die .NET-Attribute, die WPF für angefügte Eigenschaften definiert, können verwendet werden, um die Situationen zu erweitern, in denen eine bestimmte angefügte Eigenschaft in einem Eigenschaftenfenster angezeigt werden soll. Sie sollten diese Attribute auch auf Ihre eigenen benutzerdefinierten angefügten Eigenschaften anwenden. Der Zweck und die Syntax der .NET-Attribute werden auf den entsprechenden Referenzseiten beschrieben:

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## <a name="learning-more-about-attached-properties"></a>Weitere Informationen zu attachedproperties<a name="more"></a>

- Weitere Informationen zum Erstellen einer angefügten Eigenschaft finden Sie unter [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md).

- Weitergehende Verwendungsszenarios für Abhängigkeitseigenschaften und angefügte Eigenschaften finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).

- Sie können auch eine Eigenschaft als angefügte Eigenschaft und als Abhängigkeitseigenschaft registrieren, dann jedoch trotzdem „Wrapper“-Implementierungen offenlegen. In diesem Fall kann die Eigenschaft entweder auf das Element festgelegt werden, oder auf ein beliebiges Element über die angefügte XAML-Eigenschaftssyntax. Ein Beispiel für eine Eigenschaft mit einem geeigneten Szenario <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>für Standard- und angefügte Verwendungen ist .

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty>
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md)
