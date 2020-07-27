---
title: Übersicht über angefügte Eigenschaften
description: Erfahren Sie mehr über angefügte Eigenschaften in Windows Presentation Foundation, die für jedes beliebige Objekt globale Eigenschaften haben können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 993f65024fcfc4f39a408c81af43b798360e6cf6
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168386"
---
# <a name="attached-properties-overview"></a>Übersicht über angefügte Eigenschaften

Eine angefügte Eigenschaft ist ein von XAML definiertes Konzept. Eine angefügte Eigenschaft ist für die Verwendung als Typ einer globalen Eigenschaft vorgesehen, der in jedem Objekt festgelegt werden kann. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden angefügte Eigenschaften in der Regel als eine spezielle Form der Abhängigkeitseigenschaft definiert, die nicht die herkömmliche Eigenschaft „Wrapper“ aufweist.

## <a name="prerequisites"></a>Voraussetzung<a name="prerequisites"></a>

In diesem Artikel wird davon ausgegangen, dass Sie Abhängigkeits Eigenschaften aus der Perspektive eines Consumers vorhandener Abhängigkeits Eigenschaften für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Klassen verstehen und die [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md)gelesen haben. Um den Beispielen in diesem Artikel zu folgen, sollten Sie sich auch mit XAML vertraut machen und wissen, wie WPF-Anwendungen geschrieben werden.

## <a name="why-use-attached-properties"></a>Verwendungs Gründe für angefügte Eigenschaften<a name="attached_properties_usage"></a>

Ein Zweck einer angefügten Eigenschaft besteht darin, dass verschiedene untergeordnete Elemente eindeutige Werte für eine Eigenschaft angeben können, die in einem übergeordneten Element definiert ist. Eine bestimmte Anwendung dieses Szenario: Untergeordnete Elemente informieren übergeordnete Element, wie diese im [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt werden sollen. Ein Beispiel ist die- <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Eigenschaft. Die- <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Eigenschaft wird als angefügte Eigenschaft erstellt, da Sie für Elemente festgelegt werden soll, die in einem enthalten sind, <xref:System.Windows.Controls.DockPanel> und nicht für <xref:System.Windows.Controls.DockPanel> sich selbst. Die <xref:System.Windows.Controls.DockPanel> -Klasse definiert das statische Feld mit dem <xref:System.Windows.DependencyProperty> Namen <xref:System.Windows.Controls.DockPanel.DockProperty> und stellt dann die <xref:System.Windows.Controls.DockPanel.GetDock%2A> -Methode und die- <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode als öffentliche Accessoren für die angefügte-Eigenschaft bereit.

## <a name="attached-properties-in-xaml"></a>Angefügte Eigenschaften in XAML<a name="attached_properties_xaml"></a>

In XAML legen Sie angefügte Eigenschaften mithilfe der Syntax *AttachedPropertyProvider*.*PropertyName* fest.

Im folgenden finden Sie ein Beispiel für die Festlegung von <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> in XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Die Verwendung ähnelt in gewisser Weise einer statischen Eigenschaft. Sie verweisen immer auf den Typ <xref:System.Windows.Controls.DockPanel> , der die angefügte Eigenschaft besitzt und registriert, anstatt auf eine durch den Namen angegebene Instanz zu verweisen.

Da eine angefügte Eigenschaft in XAML ein Attribut ist, das Sie im Markup festlegen, besitzt außerdem nur der Mengenvorgang Relevanz. Sie können eine Eigenschaft in XAML nicht direkt abrufen, obwohl einige indirekte Mechanismen zum Vergleichen von Werten vorhanden sind, wie z.B. Trigger in Formaten (weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)).

### <a name="attached-property-implementation-in-wpf"></a>Implementierung von angefügten Eigenschaften in WPF

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden die meisten Benutzeroberflächen bezogenen Eigenschaften für WPF-Typen als Abhängigkeits Eigenschaften implementiert. Angefügte Eigenschaften sind ein XAML-Konzept, wohingegen Abhängigkeits Eigenschaften ein WPF-Konzept sind. Da WPF-Eigenschaften Abhängigkeits Eigenschaften sind, unterstützen Sie Abhängigkeits Eigenschafts Konzepte wie z. b. Eigenschafts Metadaten und Standardwerte aus diesen Eigenschafts Metadaten.

## <a name="how-attached-properties-are-used-by-the-owning-type"></a>Verwendung angefügter Eigenschaften durch den besitzenden Typ<a name="howused"></a>

Obwohl angefügte Eigenschaften für jedes beliebige Objekt festgelegt werden können, bedeutet dies nicht automatisch, dass die Eigenschaft ein reales Ergebnis erzeugt, oder der Wert jemals von einem anderen Objekt verwendet wird. Im Allgemeinen werden angefügte Eigenschaften vorgesehen, damit Objekte, die aus einer Vielzahl von möglichen Klassenhierarchien oder logischen Beziehungen stammen, dem Typ, der die angefügte Eigenschaft definiert, allgemeine Informationen melden können. Der Typ, der die angefügte Eigenschaft definiert, folgt in der Regel einem dieser Modelle:

- Der Typ, der die angefügte Eigenschaft definiert, ist so konzipiert, dass er das übergeordnete Element der Elemente sein kann, das Werte für die angefügte Eigenschaft festlegen wird. Der Typ durchläuft dann seine untergeordneten Objekte durch die interne Logik auf der Grundlage der Objektstruktur, ruft die Werte ab und fungiert auf irgendeine Weise für diese Werte.

- Der Typ, der die angefügte Eigenschaft definiert, wird als untergeordnetes Element für verschiedene mögliche übergeordnete Elemente und Inhaltsmodelle verwendet werden.

- Der Typ, der die angefügte Eigenschaft definiert, stellt einen Dienst dar. Andere Typen legen Werte für die angefügte Eigenschaft fest. Wenn das Element, das die Eigenschaft festlegt, im Kontext des Dienstes ausgewertet wird, werden über die interne Logik der Dienstklasse die angefügten Eigenschaftswerte abgerufen.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Ein Beispiel für eine übergeordnete definierte angefügte Eigenschaft

Das typische Szenario, in dem WPF eine angefügte Eigenschaft definiert, ist, wenn ein übergeordnetes Element eine Auflistung untergeordneter Elemente unterstützt und außerdem ein Verhalten implementiert, bei dem die Besonderheiten des Verhaltens für jedes untergeordnete Element einzeln gemeldet werden.

<xref:System.Windows.Controls.DockPanel>definiert die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte-Eigenschaft und <xref:System.Windows.Controls.DockPanel> verfügt über Code auf Klassenebene als Teil der Renderinglogik (insbesondere <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> und <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A> ). Eine- <xref:System.Windows.Controls.DockPanel> Instanz prüft immer, ob eines der unmittelbar untergeordneten Elemente einen Wert für festgelegt hat <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> . Wenn dies der Fall ist, werden diese Werte zur Eingabe für die Renderinglogik, die auf das jeweilige untergeordnete Element angewendet wird. <xref:System.Windows.Controls.DockPanel>In der Liste der Instanzen werden jeweils ihre eigenen unmittelbaren untergeordneten Element Auflistungen behandelt, aber dieses Verhalten ist Implementierungs spezifisch für die <xref:System.Windows.Controls.DockPanel> Verarbeitung von <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Werten. Es ist theoretisch möglich, angefügte Eigenschaften zu besitzen, die Elemente über das unmittelbar übergeordnete Element hinaus beeinflussen. Wenn die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte-Eigenschaft für ein Element festgelegt ist, das kein über <xref:System.Windows.Controls.DockPanel> geordnetes Element besitzt, um darauf zu reagieren, wird kein Fehler oder keine Ausnahme ausgelöst. Dies bedeutet einfach, dass ein globaler Eigenschafts Wert festgelegt wurde, jedoch kein Aktuelles über <xref:System.Windows.Controls.DockPanel> geordnetes Element, das die Informationen verarbeiten könnte.

## <a name="attached-properties-in-code"></a>Angefügte Eigenschaften im Code<a name="attached_properties_code"></a>

Angefügte Eigenschaften in WPF haben nicht die typischen CLR-Wrapper Methoden für den einfachen Get-/Set-Zugriff. Dies liegt daran, dass die angefügte Eigenschaft nicht notwendigerweise Teil des CLR-Namespace für Instanzen ist, in denen die Eigenschaft festgelegt ist. Allerdings muss ein XAML-Prozessor in der Lage sein, diese Werte festzulegen, wenn XAML analysiert wird. Um eine effektive Verwendung angefügter Eigenschaften zu unterstützen, muss der Besitzertyp der angefügten Eigenschaft dedizierte Accessormethoden in der Form **Get_PropertyName_** und **Set_PropertyName_** implementieren. Diese dedizierten Accessormethoden eignen sich auch zum Abrufen oder Festlegen der angefügten Eigenschaft im Code. Im Hinblick auf Code ist eine angefügte Eigenschaft einem dahinter liegenden Feld ähnlich, das Methodenaccessoren anstelle von Eigenschaftenaccessoren besitzt, und das dahinter liegende Feld kann in jedem Objekt vorhanden sein, anstatt explizit definiert werden zu müssen.

Das folgende Beispiel zeigt, wie Sie eine angefügte Eigenschaft im Code festlegen können. In diesem Beispiel `myCheckBox` ist eine Instanz der- <xref:System.Windows.Controls.CheckBox> Klasse.

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Ähnlich wie beim XAML-Fall, wenn `myCheckBox` nicht bereits als untergeordnetes Element von `myDockPanel` durch die vierte Codezeile hinzugefügt wurde, würde die fünfte Codezeile keine Ausnahme auslöst, aber der Eigenschafts Wert würde nicht mit einem übergeordneten Element interagieren und somit keine Aktion durch <xref:System.Windows.Controls.DockPanel> führen. Nur ein <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> für ein untergeordnetes Element festgelegter Wert, in dem ein übergeordnetes Element vorhanden ist, führt zu <xref:System.Windows.Controls.DockPanel> einem effektiven Verhalten in der gerenderten Anwendung. (In diesem Fall könnten Sie die angefügte Eigenschaft festlegen und anschließend an die Struktur anfügen. Oder Sie könnten die angefügte Eigenschaft an die Struktur anfügen und anschließend festlegen. Jede Reihenfolge stellt das gleiche Ergebnis bereit.)

## <a name="attached-property-metadata"></a>Metadaten der angefügten Eigenschaft<a name="attached_properties_metadata"></a>

Beim Registrieren der Eigenschaft <xref:System.Windows.FrameworkPropertyMetadata> wird festgelegt, um die Eigenschaften der Eigenschaft anzugeben, z. b. ob sich die Eigenschaft auf Rendering, Messung usw. auswirkt. Metadaten für eine angefügte Eigenschaft unterscheiden sich im Allgemeinen nicht von denen für eine Abhängigkeitseigenschaft. Wenn Sie einen Standardwert in einer Überschreibung für die Metadaten von angefügten Eigenschaften angeben, wird dieser Wert der Standardwert der impliziten angefügten Eigenschaft in Instanzen der überschreibenden Klasse. Der Standardwert wird insbesondere gemeldet, wenn ein Prozess den Wert einer angefügten Eigenschaft über die `Get`-Methodenaccessoren für diese Eigenschaft abfragt, die eine Instanz der Klasse angibt, in dem Sie die Metadaten festgelegt haben, und wenn der Wert für diese angefügte Eigenschaft andernfalls nicht festgelegt war.

Wenn Sie die Vererbung von Eigenschaftswerten für eine Eigenschaft aktivieren möchten, sollten Sie die angefügten Eigenschaften anstelle von nicht angefügten Abhängigkeitseigenschaften verwenden. Weitere Informationen finden Sie unter [Vererbung von Eigenschafts Werten](property-value-inheritance.md).

## <a name="custom-attached-properties"></a>Benutzerdefinierte angefügte Eigenschaften<a name="custom"></a>

### <a name="when-to-create-an-attached-property"></a>Wann sollte eine angefügte Eigenschaft erstellt werden?<a name="create_attached_properties"></a>

Sie können eine angefügte Eigenschaft erstellen, wenn ein Mechanismus für Eigenschafteneinstellungen für andere Klassen als die definierende Klasse zur Verfügung stehen muss. Das gängigste Szenario hierfür ist Layout. Beispiele für vorhandene Layouteigenschaften sind <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType> . Das hier aktivierte Szenario: Elemente, die als untergeordnete Elemente für das Layout steuernde Elemente vorhanden sind, können Layoutanforderungen einzeln an die übergeordneten Layoutelemente stellen, für jede Einstellung einen Eigenschaftswert, den das übergeordnete Element als angefügte Eigenschaft definiert.

Ein weiteres Szenario für die Verwendung einer angefügten Eigenschaft: Wenn Ihre Klasse einen Dienst darstellt und Sie möchten, dass Klassen den Dienst auf transparentere Weise integrieren können.

Ein weiteres Szenario ist jedoch die Unterstützung des Visual Studio WPF-Designers, wie z. b. die Bearbeitung von **Eigenschaften** Fenstern. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).

Wie bereits erwähnt, sollten Sie als eine angefügte Eigenschaft registrieren, wenn Sie die Vererbung von Eigenschaftswerten verwenden möchten.

### <a name="how-to-create-an-attached-property"></a>Erstellen einer angefügten Eigenschaft<a name="how_do_i_create_attached_properties"></a>

Wenn die Klasse die angefügte Eigenschaft ausschließlich für die Verwendung in anderen Typen definiert, muss die Klasse nicht von abgeleitet werden <xref:System.Windows.DependencyObject> . Sie müssen jedoch von abgeleitet werden, <xref:System.Windows.DependencyObject> Wenn Sie dem WPF-Gesamtmodell folgen, wenn die angefügte Eigenschaft auch eine Abhängigkeits Eigenschaft ist.

Definieren Sie die angefügte Eigenschaft als Abhängigkeits Eigenschaft, indem Sie ein `public static readonly` Feld vom Typ deklarieren <xref:System.Windows.DependencyProperty> . Sie definieren dieses Feld mithilfe des Rückgabewerts der- <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode. Der Feldname muss mit dem Namen der angefügten Eigenschaft, angefügt an die Zeichenfolge, mit dem `Property` festgelegten WPF-Muster für die Benennung der identifizierenden Felder und der Eigenschaften, die Sie darstellen, identisch sein. Der angefügte Eigenschaften Anbieter muss auch statische **Get_PropertyName_** und **Set_PropertyName_** Methoden als Accessoren für die angefügte Eigenschaft bereitstellen. Wenn dies nicht der Fall ist, kann das Eigenschaften System die angefügte Eigenschaft nicht verwenden.

> [!NOTE]
> Wenn Sie den Get-Accessor der angefügten Eigenschaft weglassen, funktioniert die Datenbindung für die Eigenschaft nicht in Entwurfs Tools wie Visual Studio und Blend für Visual Studio.

#### <a name="the-get-accessor"></a>Der Get-Accessor

Die Signatur für den **Get_PropertyName_** -Accessor muss wie folgt lauten:

`public static object GetPropertyName(object target)`

- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die- <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> Methode den-Parameter als ein <xref:System.Windows.UIElement> , da die angefügte-Eigenschaft nur für-Instanzen festgelegt werden soll <xref:System.Windows.UIElement> .

- Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die- <xref:System.Windows.Controls.DockPanel.GetDock%2A> Methode Sie als ein <xref:System.Windows.Controls.Dock> , da der Wert nur auf diese Enumeration festgelegt werden kann.

#### <a name="the-set-accessor"></a>Der Set-Accessor

Die Signatur für den **Set_PropertyName_** -Accessor muss wie folgt lauten:

`public static void SetPropertyName(object target, object value)`

- Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die- <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode Sie als ein <xref:System.Windows.UIElement> , da die angefügte-Eigenschaft nur für-Instanzen festgelegt werden soll <xref:System.Windows.UIElement> .

- Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Beispielsweise gibt die- <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode Sie als ein <xref:System.Windows.Controls.Dock> , da der Wert nur auf diese Enumeration festgelegt werden kann. Denken Sie daran, dass der Wert für diese Methode die Eingabe des XAML-Loaders ist, wenn sie Ihre angefügte Eigenschaft in einer Verwendung der angefügten Eigenschaft im Markup erkennt. Diese Eingabe ist der Wert, der als XAML-Attributwert im Markup angegeben wird. Aus diesem Grund muss die Typkonvertierung, das Wertserialisierungsprogramm oder die Unterstützung von Markuperweiterungen für den verwendeten Typ vorhanden sein, damit der entsprechende Typ aus dem Attributwert (der letztendlich nur eine Zeichenfolge ist) erstellt werden kann.

Das folgende Beispiel zeigt die Registrierung der Abhängigkeits Eigenschaft (mit der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> -Methode) sowie die- **Get_PropertyName_** -und- **Set_PropertyName_** Accessoren. Im Beispiel ist der Name der angefügten Eigenschaft `IsBubbleSource`. Deshalb müssen die Accessoren `GetIsBubbleSource` und `SetIsBubbleSource` genannt werden.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Attribute von angefügten Eigenschaften

WPF definiert mehrere .NET-Attribute, die für die Bereitstellung von Informationen zu angefügten Eigenschaften für reflektionsprozesse und für typische Benutzer von Reflektion und Eigenschafts Informationen wie Designern vorgesehen sind. Da angefügte Eigenschaften einen uneingeschränkten Bereich haben, benötigen Entwickler eine Möglichkeit, Benutzer nicht durch eine globale Liste aller angefügten Eigenschaften zu überwältigen, die in einer bestimmten Implementierung von Technologie definiert sind, die XAML verwendet. Die .NET-Attribute, die von WPF für angefügte Eigenschaften definiert werden, können verwendet werden, um die Situationen festzustellen, in denen eine angefügte Eigenschaft in einem Eigenschaften Fenster angezeigt werden soll. Sie sollten diese Attribute auch auf Ihre eigenen benutzerdefinierten angefügten Eigenschaften anwenden. Der Zweck und die Syntax der .NET-Attribute werden auf den entsprechenden Referenzseiten beschrieben:

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## <a name="learning-more-about-attached-properties"></a>Weitere Informationen zu angefügten Eigenschaften<a name="more"></a>

- Weitere Informationen zum Erstellen einer angefügten Eigenschaft finden Sie unter [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md).

- Weitergehende Verwendungsszenarios für Abhängigkeitseigenschaften und angefügte Eigenschaften finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).

- Sie können auch eine Eigenschaft als angefügte Eigenschaft und als Abhängigkeitseigenschaft registrieren, dann jedoch trotzdem „Wrapper“-Implementierungen offenlegen. In diesem Fall kann die Eigenschaft entweder auf das Element festgelegt werden, oder auf ein beliebiges Element über die angefügte XAML-Eigenschaftssyntax. Ein Beispiel für eine Eigenschaft mit einem geeigneten Szenario für Standard-und angefügte Verwendungen ist <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType> .

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.DependencyProperty>
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeits Eigenschaften](custom-dependency-properties.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md)
