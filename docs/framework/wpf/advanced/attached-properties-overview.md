---
title: Übersicht über angefügte Eigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 403c4e76e302536513b9de0694ab7b0de621d5d2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455523"
---
# <a name="attached-properties-overview"></a>Übersicht über angefügte Eigenschaften

Eine angefügte Eigenschaft ist ein von XAML definiertes Konzept. Eine angefügte Eigenschaft ist für die Verwendung als Typ einer globalen Eigenschaft vorgesehen, der in jedem Objekt festgelegt werden kann. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden angefügte Eigenschaften in der Regel als eine spezielle Form der Abhängigkeitseigenschaft definiert, die nicht die herkömmliche Eigenschaft „Wrapper“ aufweist.

## Voraussetzung<a name="prerequisites"></a>

Dieses Thema setzt voraus, dass Sie Abhängigkeitseigenschaften vorhandener Abhängigkeitseigenschaften von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen aus Sicht eines Kunden verstehen und die [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema zu folgen, sollten Sie sich auch mit XAML vertraut machen und wissen, wie WPF-Anwendungen geschrieben werden.

## Verwendungs Gründe für angefügte Eigenschaften<a name="attached_properties_usage"></a>

Ein Zweck einer angefügten Eigenschaft ist die Berechtigung für verschiedene untergeordnete Elemente, eindeutige Werte für eine Eigenschaft anzugeben, die eigentlich in einem übergeordneten Element definiert ist. Eine bestimmte Anwendung dieses Szenario: Untergeordnete Elemente informieren übergeordnete Element, wie diese im [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt werden sollen. Ein Beispiel ist die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>-Eigenschaft. Die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>-Eigenschaft wird als angefügte Eigenschaft erstellt, da Sie auf Elemente festgelegt werden soll, die in einem <xref:System.Windows.Controls.DockPanel>enthalten sind, und nicht auf <xref:System.Windows.Controls.DockPanel> selbst. Die <xref:System.Windows.Controls.DockPanel>-Klasse definiert das statische <xref:System.Windows.DependencyProperty> Feld mit dem Namen <xref:System.Windows.Controls.DockPanel.DockProperty>und stellt dann die Methoden <xref:System.Windows.Controls.DockPanel.GetDock%2A> und <xref:System.Windows.Controls.DockPanel.SetDock%2A> als öffentliche Accessoren für die angefügte-Eigenschaft bereit.

## Angefügte Eigenschaften in XAML<a name="attached_properties_xaml"></a>

In XAML legen Sie angefügte Eigenschaften mithilfe der Syntax *AttachedPropertyProvider*.*PropertyName* fest.

Im folgenden finden Sie ein Beispiel dafür, wie Sie <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> in XAML festlegen können:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Beachten Sie, dass die Verwendung einer statischen Eigenschaft etwas ähnlich ist. Sie verweisen immer auf den Typ <xref:System.Windows.Controls.DockPanel>, der die angefügte Eigenschaft besitzt und registriert, anstatt auf eine durch den Namen angegebene Instanz zu verweisen.

Da eine angefügte Eigenschaft in XAML ein Attribut ist, das Sie im Markup festlegen, besitzt außerdem nur der Mengenvorgang Relevanz. Sie können eine Eigenschaft in XAML nicht direkt abrufen, obwohl einige indirekte Mechanismen zum Vergleichen von Werten vorhanden sind, wie z.B. Trigger in Formaten (weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)).

### <a name="attached-property-implementation-in-wpf"></a>Implementierung von angefügten Eigenschaften in WPF

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]werden die meisten angefügten Eigenschaften, die auf WPF-Typen im Zusammenhang mit der UI-Darstellung vorhanden sind, als Abhängigkeits Eigenschaften implementiert. Angefügte Eigenschaften sind ein XAML-Konzept, wohingegen Abhängigkeits Eigenschaften ein WPF-Konzept sind. Da WPF-Eigenschaften Abhängigkeits Eigenschaften sind, unterstützen Sie Abhängigkeits Eigenschafts Konzepte wie z. b. Eigenschafts Metadaten und Standardwerte aus diesen Eigenschafts Metadaten.

## Verwendung angefügter Eigenschaften durch den besitzenden Typ<a name="howused"></a>

Obwohl angefügte Eigenschaften für jedes beliebige Objekt festgelegt werden können, bedeutet dies nicht automatisch, dass die Eigenschaft ein reales Ergebnis erzeugt, oder der Wert jemals von einem anderen Objekt verwendet wird. Im Allgemeinen werden angefügte Eigenschaften vorgesehen, damit Objekte, die aus einer Vielzahl von möglichen Klassenhierarchien oder logischen Beziehungen stammen, dem Typ, der die angefügte Eigenschaft definiert, allgemeine Informationen melden können. Der Typ, der die angefügte Eigenschaft definiert, folgt in der Regel einem dieser Modelle:

- Der Typ, der die angefügte Eigenschaft definiert, ist so konzipiert, dass er das übergeordnete Element der Elemente sein kann, das Werte für die angefügte Eigenschaft festlegen wird. Der Typ durchläuft dann seine untergeordneten Objekte durch die interne Logik auf der Grundlage der Objektstruktur, ruft die Werte ab und fungiert auf irgendeine Weise für diese Werte.

- Der Typ, der die angefügte Eigenschaft definiert, wird als untergeordnetes Element für verschiedene mögliche übergeordnete Elemente und Inhaltsmodelle verwendet werden.

- Der Typ, der die angefügte Eigenschaft definiert, stellt einen Dienst dar. Andere Typen legen Werte für die angefügte Eigenschaft fest. Wenn das Element, das die Eigenschaft festlegt, im Kontext des Dienstes ausgewertet wird, werden über die interne Logik der Dienstklasse die angefügten Eigenschaftswerte abgerufen.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Ein Beispiel für eine übergeordnete definierte angefügte Eigenschaft

Das typische Szenario, in dem WPF eine angefügte Eigenschaft definiert, ist, wenn ein übergeordnetes Element eine Auflistung untergeordneter Elemente unterstützt und außerdem ein Verhalten implementiert, bei dem die Besonderheiten des Verhaltens für jedes untergeordnete Element einzeln gemeldet werden.

<xref:System.Windows.Controls.DockPanel> die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte Eigenschaft definiert, und <xref:System.Windows.Controls.DockPanel> auf Klassenebene Code als Teil der Renderinglogik (insbesondere <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> und <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Eine <xref:System.Windows.Controls.DockPanel> Instanz prüft immer, ob eines der unmittelbar untergeordneten Elemente einen Wert für <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>festgelegt hat. Wenn dies der Fall ist, werden diese Werte zur Eingabe für die Renderinglogik, die auf das jeweilige untergeordnete Element angewendet wird. In der <xref:System.Windows.Controls.DockPanel>-Instanzen werden jeweils ihre eigenen unmittelbaren untergeordneten Element Auflistungen behandelt, aber dieses Verhalten ist Implementierungs spezifisch, um zu erfahren, wie <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Werte verarbeitet. Es ist theoretisch möglich, angefügte Eigenschaften zu besitzen, die Elemente über das unmittelbar übergeordnete Element hinaus beeinflussen. Wenn die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte-Eigenschaft für ein Element festgelegt ist, das über kein <xref:System.Windows.Controls.DockPanel> übergeordnetes Element verfügt, um darauf zu reagieren, wird kein Fehler oder keine Ausnahme ausgelöst. Dies bedeutet einfach, dass ein globaler Eigenschafts Wert festgelegt wurde, aber es hat keine aktuelle <xref:System.Windows.Controls.DockPanel> übergeordnetes Element, das die Informationen verarbeiten könnte.

## Angefügte Eigenschaften im Code<a name="attached_properties_code"></a>

Angefügte Eigenschaften in WPF haben nicht die typischen CLR-Wrapper Methoden für den einfachen Get-/Set-Zugriff. Dies liegt daran, dass die angefügte Eigenschaft nicht notwendigerweise Teil des CLR-Namespace für Instanzen ist, in denen die Eigenschaft festgelegt ist. Allerdings muss ein XAML-Prozessor in der Lage sein, diese Werte festzulegen, wenn XAML analysiert wird. Um eine effektive Verwendung angefügter Eigenschaften zu unterstützen, muss der Besitzertyp der angefügten Eigenschaft dedizierte Accessormethoden in der Form **Get_PropertyName_** und **Set_PropertyName_** implementieren. Diese dedizierten Accessormethoden eignen sich auch zum Abrufen oder Festlegen der angefügten Eigenschaft im Code. Im Hinblick auf Code ist eine angefügte Eigenschaft einem dahinter liegenden Feld ähnlich, das Methodenaccessoren anstelle von Eigenschaftenaccessoren besitzt, und das dahinter liegende Feld kann in jedem Objekt vorhanden sein, anstatt explizit definiert werden zu müssen.

Das folgende Beispiel zeigt, wie Sie eine angefügte Eigenschaft im Code festlegen können. In diesem Beispiel ist `myCheckBox` eine Instanz der <xref:System.Windows.Controls.CheckBox>-Klasse.

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Ähnlich wie beim XAML-Fall, wenn `myCheckBox` nicht bereits als untergeordnetes Element von `myDockPanel` durch die dritte Codezeile hinzugefügt worden wären, würde die vierte Codezeile keine Ausnahme auslöst, aber der Eigenschafts Wert interagiert nicht mit einem übergeordneten <xref:System.Windows.Controls.DockPanel> und führt daher Folgendes aus: Schweigen. Nur ein <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Wert, der für ein untergeordnetes Element mit dem vorhanden sein eines übergeordneten Elements <xref:System.Windows.Controls.DockPanel> festgelegt wird, führt zu einem effektiven Verhalten in der gerenderten Anwendung. (In diesem Fall könnten Sie die angefügte Eigenschaft festlegen und anschließend an die Struktur anfügen. Oder Sie könnten die angefügte Eigenschaft an die Struktur anfügen und anschließend festlegen. Jede Reihenfolge stellt das gleiche Ergebnis bereit.)

## Metadaten der angefügten Eigenschaft<a name="attached_properties_metadata"></a>

Beim Registrieren der Eigenschaft wird <xref:System.Windows.FrameworkPropertyMetadata> festgelegt, um die Merkmale der Eigenschaft anzugeben, z. b. ob sich die Eigenschaft auf Rendering, Messung usw. auswirkt. Metadaten für eine angefügte Eigenschaft unterscheiden sich im Allgemeinen nicht von denen für eine Abhängigkeitseigenschaft. Wenn Sie einen Standardwert in einer Überschreibung für die Metadaten von angefügten Eigenschaften angeben, wird dieser Wert der Standardwert der impliziten angefügten Eigenschaft in Instanzen der überschreibenden Klasse. Der Standardwert wird insbesondere gemeldet, wenn ein Prozess den Wert einer angefügten Eigenschaft über die `Get`-Methodenaccessoren für diese Eigenschaft abfragt, die eine Instanz der Klasse angibt, in dem Sie die Metadaten festgelegt haben, und wenn der Wert für diese angefügte Eigenschaft andernfalls nicht festgelegt war.

Wenn Sie die Vererbung von Eigenschaftswerten für eine Eigenschaft aktivieren möchten, sollten Sie die angefügten Eigenschaften anstelle von nicht angefügten Abhängigkeitseigenschaften verwenden. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).

## Benutzerdefinierte angefügte Eigenschaften<a name="custom"></a>

### Wann sollte eine angefügte Eigenschaft erstellt werden?<a name="create_attached_properties"></a>

Sie können eine angefügte Eigenschaft erstellen, wenn ein Mechanismus für Eigenschafteneinstellungen für andere Klassen als die definierende Klasse zur Verfügung stehen muss. Das gängigste Szenario hierfür ist Layout. Beispiele für vorhandene Layouteigenschaften sind <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>und <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. Das hier aktivierte Szenario: Elemente, die als untergeordnete Elemente für das Layout steuernde Elemente vorhanden sind, können Layoutanforderungen einzeln an die übergeordneten Layoutelemente stellen, für jede Einstellung einen Eigenschaftswert, den das übergeordnete Element als angefügte Eigenschaft definiert.

Ein weiteres Szenario für die Verwendung einer angefügten Eigenschaft: Wenn Ihre Klasse einen Dienst darstellt und Sie möchten, dass Klassen den Dienst auf transparentere Weise integrieren können.

Ein weiteres Szenario ist jedoch die Unterstützung des Visual Studio WPF-Designers, wie z. b. die Bearbeitung von **Eigenschaften** Fenstern. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).

Wie bereits erwähnt, sollten Sie als eine angefügte Eigenschaft registrieren, wenn Sie die Vererbung von Eigenschaftswerten verwenden möchten.

### Erstellen einer angefügten Eigenschaft<a name="how_do_i_create_attached_properties"></a>

Wenn die Klasse die angefügte Eigenschaft ausschließlich für die Verwendung in anderen Typen definiert, muss die Klasse nicht von <xref:System.Windows.DependencyObject>abgeleitet werden. Sie müssen jedoch von <xref:System.Windows.DependencyObject> abgeleitet werden, wenn Sie dem WPF-Gesamtmodell folgen, wenn die angefügte Eigenschaft auch eine Abhängigkeits Eigenschaft ist.

Definieren Sie die angefügte Eigenschaft als Abhängigkeits Eigenschaft, indem Sie ein `public static readonly` Feld vom Typ <xref:System.Windows.DependencyProperty>deklarieren. Sie definieren dieses Feld, indem Sie den Rückgabewert der <xref:System.Windows.DependencyProperty.RegisterAttached%2A>-Methode verwenden. Der Feldname muss mit dem Namen der angefügten Eigenschaft, angefügt an die Zeichenfolge `Property`, dem festgelegten WPF-Muster für die Benennung der identifizierenden Felder im Vergleich zu den Eigenschaften, die Sie darstellen, entsprechen. Der angefügte Eigenschaften Anbieter muss auch statische **Get_PropertyName_** -und **Set_PropertyName_** -Methoden als Accessoren für die angefügte Eigenschaft bereitstellen. Wenn dies nicht der Fall ist, kann das Eigenschaften System die angefügte Eigenschaft nicht verwenden.

> [!NOTE]
> Wenn Sie den Get-Accessor der angefügten Eigenschaft weglassen, funktioniert die Datenbindung für die Eigenschaft nicht in Entwurfs Tools wie Visual Studio und Blend für Visual Studio.

#### <a name="the-get-accessor"></a>Der Get-Accessor

Die Signatur für den **Get_PropertyName_** -Accessor muss wie folgt lauten:

`public static object GetPropertyName(object target)`

- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType>-Methode den-Parameter als <xref:System.Windows.UIElement>ein, da die angefügte-Eigenschaft nur für <xref:System.Windows.UIElement>-Instanzen festgelegt werden soll.

- Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die <xref:System.Windows.Controls.DockPanel.GetDock%2A>-Methode Sie als <xref:System.Windows.Controls.Dock>ein, da der Wert nur auf diese Enumeration festgelegt werden kann.

#### <a name="the-set-accessor"></a>Der Set-Accessor

Die Signatur für den **Set_PropertyName_** -Accessor muss wie folgt lauten:

`public static void SetPropertyName(object target, object value)`

- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die <xref:System.Windows.Controls.DockPanel.SetDock%2A>-Methode Sie als <xref:System.Windows.UIElement>ein, da die angefügte-Eigenschaft nur für <xref:System.Windows.UIElement>-Instanzen festgelegt werden soll.

- Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die <xref:System.Windows.Controls.DockPanel.SetDock%2A>-Methode Sie als <xref:System.Windows.Controls.Dock>ein, da der Wert nur auf diese Enumeration festgelegt werden kann. Denken Sie daran, dass der Wert für diese Methode die Eingabe des XAML-Loaders ist, wenn sie Ihre angefügte Eigenschaft in einer Verwendung der angefügten Eigenschaft im Markup erkennt. Diese Eingabe ist der Wert, der als XAML-Attributwert im Markup angegeben wird. Aus diesem Grund muss die Typkonvertierung, das Wertserialisierungsprogramm oder die Unterstützung von Markuperweiterungen für den verwendeten Typ vorhanden sein, damit der entsprechende Typ aus dem Attributwert (der letztendlich nur eine Zeichenfolge ist) erstellt werden kann.

Das folgende Beispiel zeigt die Registrierung der Abhängigkeits Eigenschaft (mit der <xref:System.Windows.DependencyProperty.RegisterAttached%2A>-Methode) sowie die Accessoren **Get_PropertyName_** und **Set_PropertyName_** . Im Beispiel ist der Name der angefügten Eigenschaft `IsBubbleSource`. Deshalb müssen die Accessoren `GetIsBubbleSource` und `SetIsBubbleSource` genannt werden.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Attribute von angefügten Eigenschaften

WPF definiert mehrere [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)], die für die Bereitstellung von Informationen zu angefügten Eigenschaften für reflektionsprozesse und für typische Benutzer von Reflektion und Eigenschafts Informationen wie Designern vorgesehen sind. Da angefügte Eigenschaften einen uneingeschränkten Bereich haben, benötigen Entwickler eine Möglichkeit, Benutzer nicht durch eine globale Liste aller angefügten Eigenschaften zu überwältigen, die in einer bestimmten Implementierung von Technologie definiert sind, die XAML verwendet. Der [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)], den WPF für angefügte Eigenschaften definiert, kann verwendet werden, um die Situationen festzustellen, in denen eine angegebene angefügte Eigenschaft in einem Eigenschaften Fenster angezeigt werden soll. Sie sollten diese Attribute auch auf Ihre eigenen benutzerdefinierten angefügten Eigenschaften anwenden. Der Zweck und die Syntax von [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] wird auf den entsprechenden Referenzseiten beschrieben:

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## Weitere Informationen zu angefügten Eigenschaften<a name="more"></a>

- Weitere Informationen zum Erstellen einer angefügten Eigenschaft finden Sie unter [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md).

- Weitergehende Verwendungsszenarios für Abhängigkeitseigenschaften und angefügte Eigenschaften finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).

- Sie können auch eine Eigenschaft als angefügte Eigenschaft und als Abhängigkeitseigenschaft registrieren, dann jedoch trotzdem „Wrapper“-Implementierungen offenlegen. In diesem Fall kann die Eigenschaft entweder auf das Element festgelegt werden, oder auf ein beliebiges Element über die angefügte XAML-Eigenschaftssyntax. Ein Beispiel für eine Eigenschaft mit einem geeigneten Szenario für Standard-und angefügte Verwendungen ist <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty>
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md)
