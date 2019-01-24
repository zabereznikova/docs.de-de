---
title: Übersicht über angefügte Eigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: e4f2b88b075a7806d2ca4c4a1e2cf3f027e71f51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706231"
---
# <a name="attached-properties-overview"></a>Übersicht über angefügte Eigenschaften

Eine angefügte Eigenschaft ist ein von XAML definiertes Konzept. Eine angefügte Eigenschaft ist für die Verwendung als Typ einer globalen Eigenschaft vorgesehen, der in jedem Objekt festgelegt werden kann. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden angefügte Eigenschaften in der Regel als eine spezielle Form der Abhängigkeitseigenschaft definiert, die nicht die herkömmliche Eigenschaft „Wrapper“ aufweist.

## Erforderliche Komponenten <a name="prerequisites"></a>

In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften von Klassen der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verstehen und die [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben. Um in den Beispielen in diesem Thema folgen zu können, sollten Sie auch XAML verstehen und wissen, wie Sie die WPF-Anwendungen zu schreiben.

## Warum verwendet angefügte Eigenschaften <a name="attached_properties_usage"></a>

Ein Zweck einer angefügten Eigenschaft ist die Berechtigung für verschiedene untergeordnete Elemente, eindeutige Werte für eine Eigenschaft anzugeben, die eigentlich in einem übergeordneten Element definiert ist. Eine bestimmte Anwendung dieses Szenario: Untergeordnete Elemente informieren übergeordnete Element, wie diese im [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt werden sollen. Ein Beispiel ist die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Eigenschaft. Die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Eigenschaft als angefügte Eigenschaft erstellt wird, es ist darauf ausgelegt, die für Elemente festgelegt werden, die innerhalb einer <xref:System.Windows.Controls.DockPanel>, anstatt auf <xref:System.Windows.Controls.DockPanel> selbst. Die <xref:System.Windows.Controls.DockPanel> -Klasse definiert die statische <xref:System.Windows.DependencyProperty> Feld mit dem Namen <xref:System.Windows.Controls.DockPanel.DockProperty>, und klicken Sie dann die <xref:System.Windows.Controls.DockPanel.GetDock%2A> und <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methoden als öffentliche Accessoren für die angefügte Eigenschaft.

## Angefügte Eigenschaften in XAML <a name="attached_properties_xaml"></a>

In XAML legen Sie angefügte Eigenschaften mithilfe der Syntax *AttachedPropertyProvider*.*PropertyName* fest.

Im folgenden werden verdeutlicht, wie Sie festlegen können <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> in XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Beachten Sie, dass die Verwendung einer statischen Eigenschaft ähnelt. Sie verweisen immer auf den Typ <xref:System.Windows.Controls.DockPanel> , besitzt und registriert die angefügte Eigenschaft anstatt an eine beliebige Instanz anhand des Namens verweisen.

Da eine angefügte Eigenschaft in XAML ein Attribut ist, das Sie im Markup festlegen, besitzt außerdem nur der Mengenvorgang Relevanz. Sie können eine Eigenschaft in XAML nicht direkt abrufen, obwohl einige indirekte Mechanismen zum Vergleichen von Werten vorhanden sind, wie z.B. Trigger in Formaten (weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)).

### <a name="attached-property-implementation-in-wpf"></a>Implementierung von angefügten Eigenschaften in WPF

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], die meisten angefügten Eigenschaften, die auf WPF-Typen vorhanden sind, die im Zusammenhang mit UI-Präsentation sind als Abhängigkeitseigenschaften implementiert. Angefügte Eigenschaften sind ein XAML-Konzept, wohingegen Abhängigkeitseigenschaften ein WPF-Konzept. Da WPF angefügte Eigenschaften Abhängigkeitseigenschaften sind, unterstützen sie die Konzepte der Abhängigkeitseigenschaften z. B. Eigenschaftenmetadaten und Standardwerte aus diesen Eigenschaftenmetadaten.

## Wie angefügte Eigenschaften durch den besitzenden Typ verwendet werden <a name="howused"></a>

Obwohl angefügte Eigenschaften für jedes beliebige Objekt festgelegt werden können, bedeutet dies nicht automatisch, dass die Eigenschaft ein reales Ergebnis erzeugt, oder der Wert jemals von einem anderen Objekt verwendet wird. Im Allgemeinen werden angefügte Eigenschaften vorgesehen, damit Objekte, die aus einer Vielzahl von möglichen Klassenhierarchien oder logischen Beziehungen stammen, dem Typ, der die angefügte Eigenschaft definiert, allgemeine Informationen melden können. Der Typ, der die angefügte Eigenschaft definiert, folgt in der Regel einem dieser Modelle:

-   Der Typ, der die angefügte Eigenschaft definiert, ist so konzipiert, dass er das übergeordnete Element der Elemente sein kann, das Werte für die angefügte Eigenschaft festlegen wird. Der Typ durchläuft dann seine untergeordneten Objekte durch die interne Logik auf der Grundlage der Objektstruktur, ruft die Werte ab und fungiert auf irgendeine Weise für diese Werte.

-   Der Typ, der die angefügte Eigenschaft definiert, wird als untergeordnetes Element für verschiedene mögliche übergeordnete Elemente und Inhaltsmodelle verwendet werden.

-   Der Typ, der die angefügte Eigenschaft definiert, stellt einen Dienst dar. Andere Typen legen Werte für die angefügte Eigenschaft fest. Wenn das Element, das die Eigenschaft festlegt, im Kontext des Dienstes ausgewertet wird, werden über die interne Logik der Dienstklasse die angefügten Eigenschaftswerte abgerufen.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Ein Beispiel für eine übergeordnete definierte angefügte Eigenschaft

Das häufigste Szenario, in denen WPF eine angefügte Eigenschaft definiert, ist, wenn ein übergeordnetes Element eine Auflistung untergeordneter Elemente unterstützt und zusätzlich ein Verhalten implementiert, in denen die Einzelheiten des Verhaltens für jedes untergeordnete Element einzeln gemeldet.

<xref:System.Windows.Controls.DockPanel> definiert die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügten Eigenschaft, und <xref:System.Windows.Controls.DockPanel> verfügt auf Klassenebene Code als Teil der Renderinglogik (insbesondere <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> und <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Ein <xref:System.Windows.Controls.DockPanel> -Instanz überprüft immer, um festzustellen, ob eines seiner unmittelbar untergeordneten Elemente für einen Wert festgelegt haben <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. Wenn dies der Fall ist, werden diese Werte zur Eingabe für die Renderinglogik, die auf das jeweilige untergeordnete Element angewendet wird. Geschachtelte <xref:System.Windows.Controls.DockPanel> -Instanzen behandeln jeweils ihre eigenen Auflistungen der unmittelbar untergeordneter Elemente, aber dieses Verhalten ist implementierungsspezifisch wie <xref:System.Windows.Controls.DockPanel> Prozesse <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Werte. Es ist theoretisch möglich, angefügte Eigenschaften zu besitzen, die Elemente über das unmittelbar übergeordnete Element hinaus beeinflussen. Wenn die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte Eigenschaft festgelegt ist, auf ein Element, das keine <xref:System.Windows.Controls.DockPanel> übergeordnetes Element zu reagieren, bis es, keine Fehler oder eine Ausnahme ausgelöst wird. Dies bedeutet einfach, dass ein globaler Eigenschaftswert festgelegt wurde, aber es verfügt über keine aktuelle <xref:System.Windows.Controls.DockPanel> übergeordneten, die die Informationen nutzen kann.

## Angefügte Eigenschaften in Code <a name="attached_properties_code"></a>

Angefügte Eigenschaften in WPF haben nicht die typische [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "Wrapper"-Methoden für den einfachen Get/Set-Zugriff. Dies ist deshalb so, weil die angefügte Eigenschaft nicht unbedingt Teil der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Namespace für Instanzen ist, in denen die Eigenschaft festgelegt ist. Allerdings muss ein XAML-Prozessor in der Lage sein, diese Werte festzulegen, wenn XAML analysiert wird. Zur Unterstützung der Verwendung einer effektiven angefügten Eigenschaft muss der Besitzertyp der angefügten Eigenschaft dedizierte Accessormethoden im Formular implementieren **Get_PropertyName_** und **Set_PropertyName_**. Diese dedizierten Accessormethoden eignen sich auch zum Abrufen oder Festlegen der angefügten Eigenschaft im Code. Im Hinblick auf Code ist eine angefügte Eigenschaft einem dahinter liegenden Feld ähnlich, das Methodenaccessoren anstelle von Eigenschaftenaccessoren besitzt, und das dahinter liegende Feld kann in jedem Objekt vorhanden sein, anstatt explizit definiert werden zu müssen.

Das folgende Beispiel zeigt, wie Sie eine angefügte Eigenschaft im Code festlegen können. In diesem Beispiel `myCheckBox` ist eine Instanz der <xref:System.Windows.Controls.CheckBox> Klasse.

[!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Ähnlich wie in der XAML-Fall: Wenn `myCheckBox` noch nicht als untergeordnetes Element hinzugefügt wurde `myDockPanel` durch die dritte Zeile des Codes, würde die vierte Zeile des Codes keine Ausnahme auslösen, aber den Wert der Eigenschaft interagieren nicht mit einem <xref:System.Windows.Controls.DockPanel> übergeordneten und somit wird keine Aktion aus. Nur ein <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Wert festgelegt, die auf einem untergeordneten-Element, das in Kombination mit dem Vorhandensein einer <xref:System.Windows.Controls.DockPanel> übergeordnete Element wird in der gerenderten Anwendung ein effektives Verhalten verursachen. (In diesem Fall könnten Sie die angefügte Eigenschaft festlegen und anschließend an die Struktur anfügen. Oder Sie könnten die angefügte Eigenschaft an die Struktur anfügen und anschließend festlegen. Jede Reihenfolge stellt das gleiche Ergebnis bereit.)

## Metadaten von angefügten Eigenschaften <a name="attached_properties_metadata"></a>

Beim Registrieren der Eigenschaft, <xref:System.Windows.FrameworkPropertyMetadata> festgelegt ist, um die Merkmale der Eigenschaft, z. B., ob die Eigenschaft wirkt sich Rendering, Messung und So weiter auf anzugeben. Metadaten für eine angefügte Eigenschaft unterscheiden sich im Allgemeinen nicht von denen für eine Abhängigkeitseigenschaft. Wenn Sie einen Standardwert in einer Überschreibung für die Metadaten von angefügten Eigenschaften angeben, wird dieser Wert der Standardwert der impliziten angefügten Eigenschaft in Instanzen der überschreibenden Klasse. Der Standardwert wird insbesondere gemeldet, wenn ein Prozess den Wert einer angefügten Eigenschaft über die `Get`-Methodenaccessoren für diese Eigenschaft abfragt, die eine Instanz der Klasse angibt, in dem Sie die Metadaten festgelegt haben, und wenn der Wert für diese angefügte Eigenschaft andernfalls nicht festgelegt war.

Wenn Sie die Vererbung von Eigenschaftswerten für eine Eigenschaft aktivieren möchten, sollten Sie die angefügten Eigenschaften anstelle von nicht angefügten Abhängigkeitseigenschaften verwenden. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).

## Benutzerdefinierte angefügte Eigenschaften <a name="custom"></a>

### Wann sollte eine angefügte Eigenschaft erstellt werden. <a name="create_attached_properties"></a>

Sie können eine angefügte Eigenschaft erstellen, wenn ein Mechanismus für Eigenschafteneinstellungen für andere Klassen als die definierende Klasse zur Verfügung stehen muss. Das gängigste Szenario hierfür ist Layout. Beispiele für vorhandene Layouteigenschaften sind <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>, und <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. Das hier aktivierte Szenario: Elemente, die als untergeordnete Elemente für das Layout steuernde Elemente vorhanden sind, können Layoutanforderungen einzeln an die übergeordneten Layoutelemente stellen, für jede Einstellung einen Eigenschaftswert, den das übergeordnete Element als angefügte Eigenschaft definiert.

Ein weiteres Szenario für die Verwendung einer angefügten Eigenschaft: Wenn Ihre Klasse einen Dienst darstellt und Sie möchten, dass Klassen den Dienst auf transparentere Weise integrieren können.

Ein weiteres Szenario ist zum Empfangen von WPF-Designer von Visual Studio-Unterstützung, z. B. **Eigenschaften** Bearbeiten des Fensters. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).

Wie bereits erwähnt, sollten Sie als eine angefügte Eigenschaft registrieren, wenn Sie die Vererbung von Eigenschaftswerten verwenden möchten.

### Vorgehensweise: Erstellen Sie eine angefügte Eigenschaft <a name="how_do_i_create_attached_properties"></a>

Wenn Ihre Klasse ist die angefügte Eigenschaft nur für die Verwendung auf anderen Typen definieren, die Klasse keine Ableitung von <xref:System.Windows.DependencyObject>. Aber Sie benötigen für die Ableitung <xref:System.Windows.DependencyObject> Wenn Sie das WPF-Gesamtmodell, müssen Sie die angefügte Eigenschaft auch eine Abhängigkeitseigenschaft sein folgen.

Definieren Sie die angefügte Eigenschaft als Abhängigkeitseigenschaft, indem Sie deklarieren eine `public static readonly` -Feld des Typs <xref:System.Windows.DependencyProperty>. Sie definieren dieses Feld den Rückgabewert mit dem <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode. Der Name des Felds muss die Namen der angefügten Eigenschaft, angefügt mit der Zeichenfolge übereinstimmen `Property`, um das folgende Namensgebungsmuster eingerichteten WPF für die Benennung der identifizierenden Felder im Vergleich zu den Eigenschaften, die sie darstellen. Der angefügte Eigenschaftenanbieter muss auch statische bereitstellen **Get_PropertyName_** und **Set_PropertyName_** Methoden als Accessoren für die angefügte Eigenschaft ist; andernfalls führt dies dazu führt in der Eigenschaft das System nicht auf die angefügte Eigenschaft zu verwenden.

> [!NOTE]
> Wenn Sie Get-Accessor der angefügten Eigenschaft auslassen, funktioniert die Datenbindung für die Eigenschaft in Entwurfstools wie Visual Studio und Expression Blend nicht.

#### <a name="the-get-accessor"></a>Der Get-Accessor

Die Signatur für die **Get_PropertyName_** Accessor muss:

`public static object GetPropertyName(object target)`

-   Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> -Methode verwendet den Parameter als <xref:System.Windows.UIElement>, da die angefügte Eigenschaft nur für festgelegt werden soll <xref:System.Windows.UIElement> Instanzen.

-   Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.GetDock%2A> Methode Typen als <xref:System.Windows.Controls.Dock>, da der Wert nur für diese Enumeration festgelegt werden kann.

#### <a name="the-set-accessor"></a>Der Set-Accessor

Die Signatur für die **Set_PropertyName_** Accessor muss:

`public static void SetPropertyName(object target, object value)`

-   Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode Typen als <xref:System.Windows.UIElement>, da die angefügte Eigenschaft nur für festgelegt werden soll <xref:System.Windows.UIElement> Instanzen.

-   Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode Typen als <xref:System.Windows.Controls.Dock>, da der Wert nur für diese Enumeration festgelegt werden kann. Denken Sie daran, dass der Wert für diese Methode die Eingabe des XAML-Loaders ist, wenn sie Ihre angefügte Eigenschaft in einer Verwendung der angefügten Eigenschaft im Markup erkennt. Diese Eingabe ist der Wert, der als XAML-Attributwert im Markup angegeben wird. Aus diesem Grund muss die Typkonvertierung, das Wertserialisierungsprogramm oder die Unterstützung von Markuperweiterungen für den verwendeten Typ vorhanden sein, damit der entsprechende Typ aus dem Attributwert (der letztendlich nur eine Zeichenfolge ist) erstellt werden kann.

Das folgende Beispiel zeigt die Registrierung der Abhängigkeitseigenschaft (mithilfe der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode), als auch die **Get_PropertyName_** und **Set_PropertyName_** Accessoren. Im Beispiel ist der Name der angefügten Eigenschaft `IsBubbleSource`. Deshalb müssen die Accessoren `GetIsBubbleSource` und `SetIsBubbleSource` genannt werden.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Attribute von angefügten Eigenschaften

WPF definiert verschiedene [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] , vorgesehen sind, um Informationen über angefügte Eigenschaften für reflektionsprozesse und für typische Benutzer von Reflektions- und Eigenschaftsinformationen Informationen wie z. B. Designern bereitzustellen. Da angefügte Eigenschaften einen uneingeschränkten Bereich haben, benötigen Entwickler eine Möglichkeit, Benutzer nicht durch eine globale Liste aller angefügten Eigenschaften zu überwältigen, die in einer bestimmten Implementierung von Technologie definiert sind, die XAML verwendet. Die [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] definiert, die von WPF, angefügte Eigenschaften verwendet werden können, um Situationen zu festzulegen, in denen eine angefügte Eigenschaft in einem Eigenschaftenfenster angezeigt werden soll. Sie sollten diese Attribute auch auf Ihre eigenen benutzerdefinierten angefügten Eigenschaften anwenden. Der Zweck und die Syntax von [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] wird auf den entsprechenden Referenzseiten beschrieben:

-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## Weitere Informationen über angefügte Eigenschaften <a name="more"></a>

-   Weitere Informationen zum Erstellen einer angefügten Eigenschaft finden Sie unter [Registrieren einer angefügten Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).

-   Weitergehende Verwendungsszenarios für Abhängigkeitseigenschaften und angefügte Eigenschaften finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).

-   Sie können auch eine Eigenschaft als angefügte Eigenschaft und als Abhängigkeitseigenschaft registrieren, dann jedoch trotzdem „Wrapper“-Implementierungen offenlegen. In diesem Fall kann die Eigenschaft entweder auf das Element festgelegt werden, oder auf ein beliebiges Element über die angefügte XAML-Eigenschaftssyntax. Ein Beispiel für eine Eigenschaft mit einem entsprechenden Szenario für standard und die angefügten Verwendungen ist <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty>
- [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Registrieren einer angefügten Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)