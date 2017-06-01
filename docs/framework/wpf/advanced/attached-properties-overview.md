---
title: "&#220;bersicht &#252;ber angef&#252;gte Eigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Angefügte Eigenschaften [WPF-Designer]"
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# &#220;bersicht &#252;ber angef&#252;gte Eigenschaften
Angefügte Eigenschaft ist ein in XAML definierter Begriff.  Angefügte Eigenschaften sollen als Typ einer globalen Eigenschaft verwendet werden, die für jedes Objekt festgelegt werden können.  In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]angefügte Eigenschaften werden in der Regel als Sonderform der Abhängigkeitseigenschaft definiert, die nicht die herkömmliche Eigenschaft besitzt.  
  
   
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie sich aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Klassen auskennen und die [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben.  Um den Beispielen in diesem Thema folgen zu können, sollten Sie außerdem XAML verstehen und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen schreiben.  
  
<a name="attached_properties_usage"></a>   
## Gründe für die Verwendung von angefügten Eigenschaften  
 Ein Zweck einer angefügten Eigenschaft besteht darin, es verschiedenen untergeordneten Elementen zu ermöglichen, eindeutige Werte für eine Eigenschaft anzugeben, die eigentlich in einem übergeordneten Element definiert ist.  Eine spezielle Anwendung dieses Szenarios ist zum Beispiel, wenn untergeordnete Elemente das übergeordnete Element darüber informieren, wie sie in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dargestellt werden sollen.  Ein Beispiel hierfür ist die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>\-Eigenschaft.  Die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>\-Eigenschaft wird als angefügte Eigenschaft erstellt, da sie zum Festlegen für Elemente vorgesehen ist, die sich in einem <xref:System.Windows.Controls.DockPanel> befinden, nicht zum Festlegen für <xref:System.Windows.Controls.DockPanel> selbst.  Die <xref:System.Windows.Controls.DockPanel>\-Klasse definiert das statische Feld <xref:System.Windows.DependencyProperty> mit dem Namen <xref:System.Windows.Controls.DockPanel.DockProperty> und stellt dann die Methoden <xref:System.Windows.Controls.DockPanel.GetDock%2A> und <xref:System.Windows.Controls.DockPanel.SetDock%2A> als öffentliche Accessoren für die [angefügte Eigenschaft](GTMT) bereit.  
  
<a name="attached_properties_xaml"></a>   
## Angefügte Eigenschaften in XAML  
 In XAML legen Sie angefügte Eigenschaften fest, indem Sie die Syntax *Anbieter der angefügten Eigenschaft*.*Eigenschaftenname* verwenden.  
  
 Im Folgenden finden Sie ein Beispiel für das Festlegen von <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> in XAML:  
  
 [!code-xml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]  
  
 Beachten Sie, dass die Verwendung einer statischen Eigenschaft ähnelt. Sie verweisen jeweils auf den Typ <xref:System.Windows.Controls.DockPanel>, der die [angefügte Eigenschaft](GTMT) besitzt und registriert, anstatt auf eine Instanz zu verweisen, die über den Namen angegeben ist.  
  
 Da eine angefügte Eigenschaft in XAML festgelegt, dass Sie ein Attribut im Markup handelt, kann nur der Set\-Vorgang jede Bedeutung hat.  Sie können eine Eigenschaft in XAML nicht direkt abrufen, obwohl einige indirekte Mechanismen zum Vergleichen von Werten, z. B. Trigger in Stilen gibt Einzelheiten finden [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)\(\).  
  
### Implementierung von angefügten Eigenschaften in WPF  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]werden die meisten angefügten Eigenschaften, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Typ vorhanden, die Benutzeroberfläche\-Präsentation verknüpft sind, als Abhängigkeitseigenschaften implementiert.  Angefügte Eigenschaften sind ein XAML\-Konzept, während Abhängigkeitseigenschaften ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Konzept handelt.  Da angefügte Eigenschaften sind  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Abhängigkeitseigenschaften unterstützen sie Abhängigkeitseigenschaften Begriffe wie Eigenschaftenmetadaten und Standardwerte aus den Metadaten dieser Eigenschaft.  
  
<a name="howused"></a>   
## Verwendung der angefügten Eigenschaften durch den besitzenden Typ  
 Obwohl angefügte Eigenschaften für jedes Objekt festgelegt werden können, bedeutet dies nicht automatisch, dass das Festlegen der Eigenschaft zu einem greifbaren Ergebnis führt oder dass der Wert jemals von einem anderen Objekt verwendet wird.  Im Allgemeinen werden angefügte Eigenschaften mit der Absicht verwendet, dass Objekte, die aus den verschiedensten Klassenhierarchien oder logischen Beziehungen stammen, jeweils gemeinsame Informationen an den Typ melden können, der die angefügte Eigenschaft definiert.  Der Typ, der die angefügte Eigenschaft definiert, folgt in der Regel einem dieser Modelle:  
  
-   Der Typ, der die angefügte Eigenschaft definiert, ist so konzipiert, dass er das übergeordnete Element der Elemente sein kann, die die Werte für die angefügte Eigenschaft festlegen.  Der Typ durchläuft seine untergeordneten Objekte dann mithilfe von interner Logik entsprechend der Objektstruktur, ruft die Werte ab und führt basierend auf den Werten entsprechende Schritte aus.  
  
-   Der Typ, der die angefügte Eigenschaft definiert, wird als untergeordnetes Element für verschiedene mögliche übergeordnete Elemente und Inhaltsmodelle verwendet.  
  
-   Der Typ, der die angefügte Eigenschaft definiert, stellt einen Dienst dar.  Andere Typen legen Werte für die angefügte Eigenschaft fest.  Wenn das Element, das die Eigenschaft festgelegt hat, dann im Kontext des Dienstes ausgewertet wird, werden die Werte der angefügten Eigenschaft mithilfe der internen Logik der Dienstklasse abgerufen.  
  
### Beispiel für eine von einem übergeordneten Element definierte angefügte Eigenschaft  
 Das häufigste Szenario, bei dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine angefügte Eigenschaft definiert, besteht darin, dass ein übergeordnetes Element eine Auflistung untergeordneter Elemente unterstützt und zusätzlich ein Verhalten implementiert, bei dem die spezifischen Merkmale des Verhaltens für jedes untergeordnete Element einzeln gemeldet werden.  
  
 <xref:System.Windows.Controls.DockPanel> definiert die angefügte <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>\-Eigenschaft, und <xref:System.Windows.Controls.DockPanel> verfügt als Teil der Renderinglogik über Klassenebenencode \(<xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> und <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>\).  Eine <xref:System.Windows.Controls.DockPanel>\-Instanz prüft immer, ob eines ihrer direkt untergeordneten Elemente für <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> einen Wert festgelegt haben.  Wenn dies der Fall ist, werden diese Werte zur Eingabe für die Renderinglogik, die auf das jeweilige untergeordnete Element angewendet wird.  Geschachtelte <xref:System.Windows.Controls.DockPanel>\-Instanzen behandeln jeweils ihre eigenen Auflistungen direkt untergeordneter Elemente. Dieses Verhalten richtet sich jedoch spezifisch für die jeweilige Implementierung danach, wie das <xref:System.Windows.Controls.DockPanel>\-Element die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>\-Werte verarbeitet.  Es ist theoretisch möglich, angefügte Eigenschaften zu verwenden, die sich auf Elemente über das unmittelbar übergeordnete Element hinaus auswirken.  Wenn die angefügte <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>\-Eigenschaft für ein Element festgelegt wird, das nicht über ein übergeordnetes <xref:System.Windows.Controls.DockPanel>\-Element verfügt, das auf dieses Element wirkt, wird kein Fehler und keine Ausnahme ausgelöst.  Dies bedeutet lediglich, dass ein globaler Eigenschaftswert festgelegt wurde, der jedoch kein übergeordnetes <xref:System.Windows.Controls.DockPanel>\-Element aufweist, das die Informationen verwenden könnte.  
  
<a name="attached_properties_code"></a>   
## Angefügte Eigenschaften in Code  
 Angefügte Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen nicht über die typischen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Wrappermethoden für den einfachen get\/set\-Zugriff.  Dies liegt daran, dass die angefügte Eigenschaft nicht zwingend Teil des [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Namespace für Instanzen ist, für die die Eigenschaft festgelegt ist.  Allerdings muss ein XAML\-Prozessor in der Lage sein, diese Werte festzulegen, wenn XAML analysiert wird.  Um eine effektive angefügte Eigenschaft verwenden zu unterstützen, muss der Besitzertyp der angefügten Eigenschaft dedizierte Accessormethoden in der Form `Get`*PropertyName* und `Set`*PropertyName*implementieren.  Diese dedizierten Accessormethoden sind außerdem nützlich, um die angefügte Eigenschaft im Code festzulegen bzw. abzurufen.  Aus Codesicht ähnelt eine angefügte Eigenschaft einem dahinter liegenden Feld, das anstelle von Eigenschaftenaccessoren über Methodenaccessoren verfügt. Das dahinter liegende Feld kann für ein Objekt vorhanden sein und muss nicht speziell definiert werden.  
  
 Das folgende Beispiel zeigt, wie Sie im Code eine angefügte Eigenschaft festlegen können.  In diesem Beispiel ist `myCheckBox` eine Instanz der <xref:System.Windows.Controls.CheckBox>\-Klasse.  
  
 [!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
 [!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]  
  
 Ähnelt dem XAML\-Fall, wenn `myCheckBox` nicht bereits als untergeordnetes Element `myDockPanel` durch die dritte Codezeile hinzugefügt worden wäre, würde die vierte Zeile keine Ausnahme auslösen, aber der Eigenschaftswert würde nicht mit Elementen <xref:System.Windows.Controls.DockPanel> interagieren und somit nichts tun würden.  Nur ein <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>\-Wert, der für ein untergeordnetes Element in Kombination mit dem Vorhandensein eines übergeordneten <xref:System.Windows.Controls.DockPanel>\-Elements festgelegt wird, ruft in der gerenderten Anwendung ein Verhalten hervor.  \(In diesem Fall könnten Sie die angefügte Eigenschaft festlegen und dann an die Struktur anfügen.  Oder Sie könnten die angefügte Eigenschaft an die Struktur anfügen und dann festlegen.  Das Ergebnis ist unabhängig von der Reihenfolge dasselbe.\)  
  
<a name="attached_properties_metadata"></a>   
## Metadaten von angefügten Eigenschaften  
 Beim Registrieren der Eigenschaft wird <xref:System.Windows.FrameworkPropertyMetadata> festgelegt, um die Merkmale der Eigenschaft anzugeben, zum Beispiel ob sich die Eigenschaft auf das Rendering, die Messung usw. auswirkt.  Die Metadaten für eine [angefügte Eigenschaft](GTMT) unterscheiden sich im Allgemeinen nicht von denen einer [Abhängigkeitseigenschaft](GTMT).  Wenn Sie in einer Überschreibung für die Metadaten einer angefügten Eigenschaft einen Standardwert angeben, wird dieser Wert zum Standardwert der impliziten angefügten Eigenschaft von Instanzen der überschreibenden Klasse.  Der Standardwert wird gemeldet, wenn ein Prozess den Wert einer angefügten Eigenschaft über den `Get`\-Methodenaccessor für diese Eigenschaft abfragt und dabei eine Instanz der Klasse angibt, in der Sie die Metadaten festgelegt haben, und der Wert für diese angefügte Eigenschaft nicht auf andere Weise festgelegt wurde.  
  
 Wenn Sie für eine Eigenschaft die Vererbung von Eigenschaftswerten aktivieren möchten, sollten Sie anstelle von nicht angefügten Abhängigkeitseigenschaften angefügte Eigenschaften verwenden.  Ausführliche Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="custom"></a>   
## Benutzerdefinierte angefügte Eigenschaften  
  
<a name="create_attached_properties"></a>   
### Wann wird eine angefügte Eigenschaft erstellt?  
 Sie können eine [angefügte Eigenschaft](GTMT) erstellen, wenn es erforderlich ist, einen Mechanismus zum Festlegen von Eigenschaften für andere Klassen als die definierende Klasse bereitzustellen.  Am häufigsten werden für dieses Szenario die Layoutfunktionen verwendet.  Beispiele für vorhandene Layouteigenschaften sind <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> und <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=fullName>.  Bei diesem Szenario sind Elemente, die als untergeordnete Elemente von Elementen der Layoutsteuerung vorhanden sind, dazu in der Lage, Layoutanforderungen einzeln für ihre übergeordneten Layoutelemente auszudrücken. Die Elemente legen jeweils einen Eigenschaftswert fest, den das übergeordnete Element als angefügte Eigenschaft definiert hat.  
  
 Ein anderes Szenario der Verwendung einer angefügten Eigenschaft ist, wenn Ihre Klasse einen Dienst darstellt und Sie möchten, dass Klassen den Dienst auf transparentere Weise integrieren können.  
  
 Ein weiteres Szenario ist die [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]\-[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]\-Unterstützung, zum Beispiel die Bearbeitung im Fenster **Eigenschaften**.  Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Wie bereits erwähnt, sollten Sie die Registrierung als angefügte Eigenschaft durchführen, wenn Sie die Vererbung von Eigenschaftswerten verwenden möchten.  
  
<a name="how_do_i_create_attached_properties"></a>   
### Erstellen einer angefügten Eigenschaft  
 Wenn Ihre Klasse die [angefügte Eigenschaft](GTMT) nur für die Verwendung auf anderen Typen definiert, muss die Klasse keine Ableitung von <xref:System.Windows.DependencyObject> durchführen.  Sie müssen jedoch <xref:System.Windows.DependencyObject> berechnen, wenn Sie den gesamten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] des Modells, der angefügten Eigenschaft ist ebenfalls eine Abhängigkeitseigenschaft folgen.  
  
 Definieren Sie die angefügte Eigenschaft als Abhängigkeitseigenschaft, indem Sie ein `public` `static` `readonly`\-Feld vom Typ <xref:System.Windows.DependencyProperty> deklarieren.  Sie definieren dieses Feld, indem Sie den Rückgabewert der <xref:System.Windows.DependencyProperty.RegisterAttached%2A>\-Methode verwenden.  Der Feldname muss mit dem Namen der angefügten Eigenschaft übereinstimmen, dem die Zeichenfolge `Property` angehängt wird, um das gängige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Muster für die Benennung der identifizierenden Felder und der zugrunde liegenden Eigenschaften einzuhalten.  Der angefügte Eigenschaftenanbieter muss statische `Get`*PropertyName* und `Set`*PropertyName*\-Methoden als Accessoren für die angefügte Eigenschaft bereitstellen. Zu diesem Zweck können nicht das das Eigenschaftensystem, das nicht in der Lage ist, die angefügte Eigenschaft zu verwenden.  
  
> [!NOTE]
>  Wenn Sie den get\-Accessor der angefügten Eigenschaft ausschließen, funktioniert die Datenbindung für die Eigenschaft nicht in Entwurfstools wie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] und Expression Blend.  
  
#### get\-Accessor  
 Die Signatur für den `Get`*PropertyName* Accessor muss wie folgt lauten:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   Das `target`\-Objekt kann in der Implementierung als spezifischerer Typ angegeben werden.  Die <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=fullName>\-Methode verwendet den Parameter zum Beispiel in der Form <xref:System.Windows.UIElement>, da die angefügte Eigenschaft nur für die Festlegung für <xref:System.Windows.UIElement>\-Instanzen vorgesehen ist.  
  
-   Der Rückgabewert kann in der Implementierung als spezifischerer Typ angegeben werden.  Die <xref:System.Windows.Controls.DockPanel.GetDock%2A>\-Methode verwendet zum Beispiel die Form <xref:System.Windows.Controls.Dock>, da der Wert nur für diese Enumeration festgelegt werden kann.  
  
#### set\-Accessor  
 Die Signatur für den `Set`*PropertyName* Accessor muss wie folgt lauten:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   Das `target`\-Objekt kann in der Implementierung als spezifischerer Typ angegeben werden.  Die <xref:System.Windows.Controls.DockPanel.SetDock%2A>\-Methode verwendet zum Beispiel die Form <xref:System.Windows.UIElement>, da die angefügte Eigenschaft nur für die Festlegung für <xref:System.Windows.UIElement>\-Instanzen vorgesehen ist.  
  
-   Das `value`\-Objekt kann in der Implementierung als spezifischerer Typ angegeben werden.  Die <xref:System.Windows.Controls.DockPanel.SetDock%2A>\-Methode verwendet zum Beispiel die Form <xref:System.Windows.Controls.Dock>, da der Wert nur für diese Enumeration festgelegt werden kann.  Denken Sie daran, dass der Wert für diese Methode die Eingabe darstellt, die vom XAML\-Ladeprogramm eingeht, wenn er die angefügte Eigenschaft in einer angefügten Eigenschaft werden im Markup trifft.  Die Eingabe ist der Wert, der als XAML\-Attributwert im Markup angegeben wird.  Aus diesem Grund muss für den verwendeten Typ Unterstützung für die Typkonvertierung, ein Wertserialisierungsprogramm oder die Markuperweiterung vorhanden sein, damit aus dem Attributwert \(eigentlich nur eine Zeichenfolge\) der jeweils erforderliche Typ erstellt werden kann.  
  
 Im folgenden Beispiel wird die Registrierung der Abhängigkeitseigenschaft \(mithilfe der <xref:System.Windows.DependencyProperty.RegisterAttached%2A>\-Methode\) sowie die `Get`*PropertyName* und `Set`*PropertyName* Accessoren an.  Im Beispiel lautet der Name der angefügten Eigenschaft `IsBubbleSource`.  Deshalb müssen die Accessoren `GetIsBubbleSource` und `SetIsBubbleSource` genannt werden.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
#### Attribute von angefügten Eigenschaften  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definiert mehrere [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)]\-Elemente, mit deren Hilfe für Reflektionsprozesse und typische Nutzer von Reflektions\- und Eigenschaftendaten Informationen zu angefügten Eigenschaften bereitgestellt werden sollen.  Da angefügte Eigenschaften einen Typ unbegrenzter Bereich haben, benötigen Designer eine Möglichkeit, eine überwältigende globalen Liste aller angefügten Eigenschaften zu vermeiden, die in einer bestimmten Technologie Implementierung definiert werden, die XAML verwendet.  Sie können die [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)]\-Elemente, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für angefügte Eigenschaften definiert, verwenden, um den Umfang für Situationen festzulegen, in denen eine bestimmte angefügte Eigenschaft in einem Eigenschaftenfenster angezeigt werden soll.  Sie können es in Betracht ziehen, diese Attribute auch für Ihre eigenen benutzerdefinierten angefügten Eigenschaften anzuwenden.  Der Zweck und die Syntax von [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] sind auf den entsprechenden Verweisseiten beschrieben:  
  
-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>  
  
<a name="more"></a>   
## Weitere Informationen – Angefügte Eigenschaften  
  
-   Weitere Informationen zum Erstellen einer angefügten Eigenschaft finden Sie unter [Registrieren einer angefügten Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).  
  
-   Weitergehende Nutzungsszenarios für Abhängigkeitseigenschaften und angefügte Eigenschaften finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   Sie können eine Eigenschaft auch als angefügte Eigenschaft und als Abhängigkeitseigenschaft registrieren, dann jedoch trotzdem Wrapperimplementierungen offenlegen.  In diesem Fall kann der Eigenschaft entweder auf dieses Element festgelegt werden, oder für jedes Element von XAML Syntax der angefügten Eigenschaft an.  Ein Beispiel für eine Eigenschaft mit einem entsprechenden Szenario für die standardmäßige und die angefügte Nutzung ist <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.DependencyProperty>   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Registrieren einer angefügten Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)