---
title: "Übersicht über angefügte Eigenschaften"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d1d0eb55e75cd450d55b69aadca9c60e157eb09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="attached-properties-overview"></a>Übersicht über angefügte Eigenschaften
Eine angefügte Eigenschaft ist ein von XAML definiertes Konzept. Eine angefügte Eigenschaft ist für die Verwendung als Typ einer globalen Eigenschaft vorgesehen, der in jedem Objekt festgelegt werden kann. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden angefügte Eigenschaften in der Regel als eine spezielle Form der Abhängigkeitseigenschaft definiert, die nicht die herkömmliche Eigenschaft „Wrapper“ aufweist.  
  
   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften von Klassen der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verstehen und die [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem XAML verstehen und wissen, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen geschrieben werden.  
  
<a name="attached_properties_usage"></a>   
## <a name="why-use-attached-properties"></a>Warum angefügte Eigenschaften verwendet werden sollen  
 Ein Zweck einer angefügten Eigenschaft ist die Berechtigung für verschiedene untergeordnete Elemente, eindeutige Werte für eine Eigenschaft anzugeben, die eigentlich in einem übergeordneten Element definiert ist. Eine bestimmte Anwendung dieses Szenario: Untergeordnete Elemente informieren übergeordnete Element, wie diese im [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt werden sollen. Ein Beispiel ist die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Eigenschaft. Die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Eigenschaft wird als eine angefügte Eigenschaft erstellt, da dieser Standard entwickelt wurde, die auf Elemente festgelegt werden, die in enthaltenen eine <xref:System.Windows.Controls.DockPanel>, anstatt auf <xref:System.Windows.Controls.DockPanel> selbst. Die <xref:System.Windows.Controls.DockPanel> Klasse definiert die statische <xref:System.Windows.DependencyProperty> Feld mit dem Namen <xref:System.Windows.Controls.DockPanel.DockProperty>, und Wiederherstellungsprozessen sowie die <xref:System.Windows.Controls.DockPanel.GetDock%2A> und <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methoden als öffentliche Accessoren für die angefügte Eigenschaft.  
  
<a name="attached_properties_xaml"></a>   
## <a name="attached-properties-in-xaml"></a>Angefügte Eigenschaften in XAML  
 In XAML legen Sie angefügte Eigenschaften mithilfe der Syntax *AttachedPropertyProvider*.*PropertyName* fest.  
  
 Im folgenden ist ein Beispiel, wie Sie festlegen können <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> in XAML:  
  
 [!code-xaml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]  
  
 Beachten Sie, dass die Verwendung einer statischen Eigenschaft ähnelt. verweisen Sie immer auf den Typ <xref:System.Windows.Controls.DockPanel> , besitzt und registriert die angefügte Eigenschaft anstatt in einer beliebigen Instanz namentlich angegebene verweisen.  
  
 Da eine angefügte Eigenschaft in XAML ein Attribut ist, das Sie im Markup festlegen, besitzt außerdem nur der Mengenvorgang Relevanz. Sie können eine Eigenschaft in XAML nicht direkt abrufen, obwohl einige indirekte Mechanismen zum Vergleichen von Werten vorhanden sind, wie z.B. Trigger in Formaten (weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)).  
  
### <a name="attached-property-implementation-in-wpf"></a>Implementierung von angefügten Eigenschaften in WPF  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden die meisten der angefügten Eigenschaften, die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Typen (in Bezug auf UI-Präsentation) vorhanden sind, als Abhängigkeitseigenschaften implementiert. Angefügte Eigenschaften sind ein XAML-Konzept, wohingegen Abhängigkeitseigenschaften ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Konzept sind. Da angefügte Eigenschaften von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Abhängigkeitseigenschaften sind, unterstützen sie die Konzepte der Abhängigkeitseigenschaften, wie z.B. Eigenschaftenmetadaten und Standardwerte aus diesen Eigenschaftenmetadaten.  
  
<a name="howused"></a>   
## <a name="how-attached-properties-are-used-by-the-owning-type"></a>Wie angefügte Eigenschaften durch den besitzenden Typ verwendet werden  
 Obwohl angefügte Eigenschaften für jedes beliebige Objekt festgelegt werden können, bedeutet dies nicht automatisch, dass die Eigenschaft ein reales Ergebnis erzeugt, oder der Wert jemals von einem anderen Objekt verwendet wird. Im Allgemeinen werden angefügte Eigenschaften vorgesehen, damit Objekte, die aus einer Vielzahl von möglichen Klassenhierarchien oder logischen Beziehungen stammen, dem Typ, der die angefügte Eigenschaft definiert, allgemeine Informationen melden können. Der Typ, der die angefügte Eigenschaft definiert, folgt in der Regel einem dieser Modelle:  
  
-   Der Typ, der die angefügte Eigenschaft definiert, ist so konzipiert, dass er das übergeordnete Element der Elemente sein kann, das Werte für die angefügte Eigenschaft festlegen wird. Der Typ durchläuft dann seine untergeordneten Objekte durch die interne Logik auf der Grundlage der Objektstruktur, ruft die Werte ab und fungiert auf irgendeine Weise für diese Werte.  
  
-   Der Typ, der die angefügte Eigenschaft definiert, wird als untergeordnetes Element für verschiedene mögliche übergeordnete Elemente und Inhaltsmodelle verwendet werden.  
  
-   Der Typ, der die angefügte Eigenschaft definiert, stellt einen Dienst dar. Andere Typen legen Werte für die angefügte Eigenschaft fest. Wenn das Element, das die Eigenschaft festlegt, im Kontext des Dienstes ausgewertet wird, werden über die interne Logik der Dienstklasse die angefügten Eigenschaftswerte abgerufen.  
  
### <a name="an-example-of-a-parent-defined-attached-property"></a>Ein Beispiel für eine übergeordnete definierte angefügte Eigenschaft  
 Das häufigste Szenario, in dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine angefügte Eigenschaft definiert: Wenn ein übergeordnetes Element eine Auflistung untergeordneter Elemente unterstützt und zusätzlich ein Verhalten implementiert, in dem die Einzelheiten des Verhaltens für jedes untergeordnete Element einzeln gemeldet werden.  
  
 <xref:System.Windows.Controls.DockPanel>definiert die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügten Eigenschaft, und <xref:System.Windows.Controls.DockPanel> verfügt auf Klassenebene Code als Teil seiner Renderinglogik (insbesondere <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> und <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Ein <xref:System.Windows.Controls.DockPanel> Instanz immer überprüft, ob der unmittelbaren untergeordneten Elemente für einen Wert festgelegt haben <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. Wenn dies der Fall ist, werden diese Werte zur Eingabe für die Renderinglogik, die auf das jeweilige untergeordnete Element angewendet wird. Geschachtelte <xref:System.Windows.Controls.DockPanel> Instanzen jeder behandeln eigene Sammlungen der unmittelbaren untergeordneten-Element, aber dieses Verhalten ist implementierungsspezifisch, wie <xref:System.Windows.Controls.DockPanel> Prozesse <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Werte. Es ist theoretisch möglich, angefügte Eigenschaften zu besitzen, die Elemente über das unmittelbar übergeordnete Element hinaus beeinflussen. Wenn die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügten Eigenschaft festgelegt ist, auf ein Element, das keine <xref:System.Windows.Controls.DockPanel> übergeordneten Element zu reagieren, keine Fehlermeldung oder Ausnahme wird ausgelöst. Dies bedeutet, dass ein globale Eigenschaft-Wert festgelegt wurde, verfügt aber über keine aktuelle <xref:System.Windows.Controls.DockPanel> übergeordneten Element, das die Informationen verarbeiten konnte.  
  
<a name="attached_properties_code"></a>   
## <a name="attached-properties-in-code"></a>Angefügte Eigenschaften in Code  
 Angefügte Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besitzen nicht die normalen „Wrapper“-Methoden von [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] für den einfachen Get/Set-Zugriff. Dies ist deshalb so, weil die angefügte Eigenschaft nicht unbedingt Teil der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Namespace für Instanzen ist, in denen die Eigenschaft festgelegt ist. Allerdings muss ein XAML-Prozessor in der Lage sein, diese Werte festzulegen, wenn XAML analysiert wird. Für die Unterstützung zur Verwendung einer effektiven angefügten Eigenschaft muss der Besitzertyp der angefügten Eigenschaft dedizierte Accessormethoden im Formular `Get`*PropertyName* und `Set`*PropertyName* implementieren. Diese dedizierten Accessormethoden eignen sich auch zum Abrufen oder Festlegen der angefügten Eigenschaft im Code. Im Hinblick auf Code ist eine angefügte Eigenschaft einem dahinter liegenden Feld ähnlich, das Methodenaccessoren anstelle von Eigenschaftenaccessoren besitzt, und das dahinter liegende Feld kann in jedem Objekt vorhanden sein, anstatt explizit definiert werden zu müssen.  
  
 Das folgende Beispiel zeigt, wie Sie eine angefügte Eigenschaft im Code festlegen können. In diesem Beispiel `myCheckBox` ist eine Instanz der <xref:System.Windows.Controls.CheckBox> Klasse.  
  
 [!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
 [!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]  
  
 Ähnlich wie in der XAML-Fall, wenn `myCheckBox` hatte nicht bereits als untergeordnetes Element von hinzugefügt wurden `myDockPanel` durch die dritte Zeile des Codes, würde die vierte Zeile des Codes keine Ausnahme auslösen, jedoch den Wert der Eigenschaft interagieren würde nicht mit einer <xref:System.Windows.Controls.DockPanel> übergeordneten und somit würde keine weiteren Aktionen erforderlich. Nur eine <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Wert festgelegt, auf dem untergeordneten Element zusammen mit dem Vorhandensein einer <xref:System.Windows.Controls.DockPanel> übergeordnete Element wird in der gerenderten Anwendung ein Verhalten verursachen. (In diesem Fall könnten Sie die angefügte Eigenschaft festlegen und anschließend an die Struktur anfügen. Oder Sie könnten die angefügte Eigenschaft an die Struktur anfügen und anschließend festlegen. Jede Reihenfolge stellt das gleiche Ergebnis bereit.)  
  
<a name="attached_properties_metadata"></a>   
## <a name="attached-property-metadata"></a>Metadaten von angefügten Eigenschaften  
 Beim Registrieren der Eigenschaft <xref:System.Windows.FrameworkPropertyMetadata> festgelegt ist, um die Merkmale der Eigenschaft, z. B., ob die Eigenschaft wirkt sich Rendering, Messung und So weiter auf anzugeben. Metadaten für eine angefügte Eigenschaft unterscheiden sich im Allgemeinen nicht von denen für eine Abhängigkeitseigenschaft. Wenn Sie einen Standardwert in einer Überschreibung für die Metadaten von angefügten Eigenschaften angeben, wird dieser Wert der Standardwert der impliziten angefügten Eigenschaft in Instanzen der überschreibenden Klasse. Der Standardwert wird insbesondere gemeldet, wenn ein Prozess den Wert einer angefügten Eigenschaft über die `Get`-Methodenaccessoren für diese Eigenschaft abfragt, die eine Instanz der Klasse angibt, in dem Sie die Metadaten festgelegt haben, und wenn der Wert für diese angefügte Eigenschaft andernfalls nicht festgelegt war.  
  
 Wenn Sie die Vererbung von Eigenschaftswerten für eine Eigenschaft aktivieren möchten, sollten Sie die angefügten Eigenschaften anstelle von nicht angefügten Abhängigkeitseigenschaften verwenden. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="custom"></a>   
## <a name="custom-attached-properties"></a>Benutzerdefinierte angefügte Eigenschaften  
  
<a name="create_attached_properties"></a>   
### <a name="when-to-create-an-attached-property"></a>Wann eine angefügte Eigenschaft erstellt werden soll  
 Sie können eine angefügte Eigenschaft erstellen, wenn ein Mechanismus für Eigenschafteneinstellungen für andere Klassen als die definierende Klasse zur Verfügung stehen muss. Das gängigste Szenario hierfür ist Layout. Beispiele für vorhandene Layouteigenschaften sind <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>, und <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. Das hier aktivierte Szenario: Elemente, die als untergeordnete Elemente für das Layout steuernde Elemente vorhanden sind, können Layoutanforderungen einzeln an die übergeordneten Layoutelemente stellen, für jede Einstellung einen Eigenschaftswert, den das übergeordnete Element als angefügte Eigenschaft definiert.  
  
 Ein weiteres Szenario für die Verwendung einer angefügten Eigenschaft: Wenn Ihre Klasse einen Dienst darstellt und Sie möchten, dass Klassen den Dienst auf transparentere Weise integrieren können.  
  
 Noch ein weiteres Szenario: Erhalt des [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]-Support, wie z.B. das Bearbeiten des Fensters **Eigenschaften**. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Wie bereits erwähnt, sollten Sie als eine angefügte Eigenschaft registrieren, wenn Sie die Vererbung von Eigenschaftswerten verwenden möchten.  
  
<a name="how_do_i_create_attached_properties"></a>   
### <a name="how-to-create-an-attached-property"></a>So erstellen Sie eine angefügte Eigenschaft  
 Wenn Ihre Klasse definiert die angefügte Eigenschaft nur für die Verwendung auf andere Typen, die Klasse keine Ableitung <xref:System.Windows.DependencyObject>. Aber das Ableiten von <xref:System.Windows.DependencyObject> Wenn Sie die gesamte führen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Modell, dass eine angefügte Eigenschaft werden auch eine Abhängigkeitseigenschaft.  
  
 Definieren Sie die angefügte Eigenschaft als Abhängigkeitseigenschaft durch Deklarieren einer `public` `static` `readonly` Feld des Typs <xref:System.Windows.DependencyProperty>. Definieren Sie dieses Feld mit dem Rückgabewert von der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode. Der Feldname muss mit dem Namen der angefügten Eigenschaft übereinstimmen, angefügt mit der Zeichenfolge `Property`, um dem geltenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Muster für die Benennung der identifizierenden Felder im Vergleich zu den Eigenschaften, die sie darstellen, zu folgen. Der angefügte Eigenschaftenanbieter muss auch die statische Methoden `Get`*PropertyName* und `Set`*PropertyName* als Accessoren für die angefügte Eigenschaft bereitstellen. Andernfalls führt dies dazu, dass das Eigenschaftensystem Ihre angefügte Eigenschaft nicht verwenden kann.  
  
> [!NOTE]
>  Wenn Sie den Get-Accessor der angefügten Eigenschaft auslassen, wird die Datenbindung für die Eigenschaft in Entwurfstools, wie z.B. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] und Expression Blend, nicht funktionieren.  
  
#### <a name="the-get-accessor"></a>Der Get-Accessor  
 Die Signatur für den Accessor `Get`*PropertyName* muss Folgende sein:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> Methode Typen den Parameter als <xref:System.Windows.UIElement>, da die angefügte Eigenschaft nur vorgesehen ist, festgelegt werden sollen <xref:System.Windows.UIElement> Instanzen.  
  
-   Der Rückgabewert kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.GetDock%2A> Methode Typen als <xref:System.Windows.Controls.Dock>, da der Wert kann nur auf dieser Enumeration festgelegt werden.  
  
#### <a name="the-set-accessor"></a>Der Set-Accessor  
 Die Signatur für den Accessoren `Set`*PropertyName* muss Folgende sein:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   Das `target`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode Typen als <xref:System.Windows.UIElement>, da die angefügte Eigenschaft nur vorgesehen ist, festgelegt werden sollen <xref:System.Windows.UIElement> Instanzen.  
  
-   Das `value`-Objekt kann als spezifischerer Typ in Ihrer Implementierung angegeben werden. Z. B. die <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode Typen als <xref:System.Windows.Controls.Dock>, da der Wert kann nur auf dieser Enumeration festgelegt werden. Denken Sie daran, dass der Wert für diese Methode die Eingabe des XAML-Loaders ist, wenn sie Ihre angefügte Eigenschaft in einer Verwendung der angefügten Eigenschaft im Markup erkennt. Diese Eingabe ist der Wert, der als XAML-Attributwert im Markup angegeben wird. Aus diesem Grund muss die Typkonvertierung, das Wertserialisierungsprogramm oder die Unterstützung von Markuperweiterungen für den verwendeten Typ vorhanden sein, damit der entsprechende Typ aus dem Attributwert (der letztendlich nur eine Zeichenfolge ist) erstellt werden kann.  
  
 Das folgende Beispiel zeigt die Registrierung der Abhängigkeitseigenschaft (mithilfe der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode), als auch die `Get` *PropertyName* und `Set` *PropertyName* Accessoren . Im Beispiel ist der Name der angefügten Eigenschaft `IsBubbleSource`. Deshalb müssen die Accessoren `GetIsBubbleSource` und `SetIsBubbleSource` genannt werden.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
#### <a name="attached-property-attributes"></a>Attribute von angefügten Eigenschaften  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definiert verschiedene [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)], die Informationen über angefügte Eigenschaften für Reflektionsprozesse und für typische Benutzer von Reflektions- und Eigenschaftsinformationen, wie z.B. Designern, bereitstellen sollen. Da angefügte Eigenschaften einen uneingeschränkten Bereich haben, benötigen Entwickler eine Möglichkeit, Benutzer nicht durch eine globale Liste aller angefügten Eigenschaften zu überwältigen, die in einer bestimmten Implementierung von Technologie definiert sind, die XAML verwendet. Die [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)], die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für angefügte Eigenschaften definiert, können verwendet werden, um Situationen zu festzulegen, in denen eine angefügte Eigenschaft in einem Eigenschaftenfenster angezeigt werden soll. Sie sollten diese Attribute auch auf Ihre eigenen benutzerdefinierten angefügten Eigenschaften anwenden. Der Zweck und die Syntax von [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] wird auf den entsprechenden Referenzseiten beschrieben:  
  
-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>  
  
<a name="more"></a>   
## <a name="learning-more-about-attached-properties"></a>Weitere Informationen über angefügte Eigenschaften  
  
-   Weitere Informationen zum Erstellen einer angefügten Eigenschaft finden Sie unter [Registrieren einer angefügten Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).  
  
-   Weitergehende Verwendungsszenarios für Abhängigkeitseigenschaften und angefügte Eigenschaften finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   Sie können auch eine Eigenschaft als angefügte Eigenschaft und als Abhängigkeitseigenschaft registrieren, dann jedoch trotzdem „Wrapper“-Implementierungen offenlegen. In diesem Fall kann die Eigenschaft entweder auf das Element festgelegt werden, oder auf ein beliebiges Element über die angefügte XAML-Eigenschaftssyntax. Ist ein Beispiel für eine Eigenschaft mit einem entsprechenden Szenario für die Verwendung von standardmäßigen und angefügte <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.DependencyProperty>  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Registrieren einer angefügten Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)
