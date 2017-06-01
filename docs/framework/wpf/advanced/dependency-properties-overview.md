---
title: "&#220;bersicht &#252;ber Abh&#228;ngigkeitseigenschaften | Microsoft Docs"
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
  - "Angefügte Eigenschaften"
  - "Datenbindung"
  - "Abhängigkeitseigenschaften"
  - "Eigenschaften, Angefügt"
  - "Eigenschaften, Übersicht"
  - "Ressourcen, Verweise auf"
  - "Formate"
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# &#220;bersicht &#252;ber Abh&#228;ngigkeitseigenschaften
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt einen Satz von Diensten bereit, mit denen die Funktionalität einer [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaft erweitert werden kann.  Zusammen werden diese Dienste normalerweise als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem bezeichnet.  Eine Eigenschaft, die vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem unterstützt wird, wird als [Abhängigkeitseigenschaft](GTMT) bezeichnet. In dieser Übersicht werden das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem und die Funktionen einer [Abhängigkeitseigenschaft](GTMT) beschrieben. Dies beinhaltet auch die Verwendung vorhandener [Abhängigkeitseigenschaften](GTMT) in XAML und Code.  Außerdem werden spezielle Aspekte von Abhängigkeitseigenschaften behandelt, z. B. Abhängigkeitseigenschaft\-Metadaten, sowie die Erstellung Ihrer eigenen Abhängigkeitseigenschaft ein einer benutzerdefinierten Klasse.  
  
   
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie über Grundkenntnisse der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] und der objektorientierten Programmierung verfügen.  Um den Beispielen in diesem Thema folgen zu können, sollten Sie außerdem mit der Verwendung von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen vertraut sein.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
<a name="why_dependency_properties"></a>   
## Abhängigkeitseigenschaften und CLR\-Eigenschaften  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden Eigenschaften normalerweise als [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaften offengelegt.  Auf der Basisebene können Sie mit diesen Eigenschaften interagieren, ohne zu merken, dass sie als [Abhängigkeitseigenschaften](GTMT) implementiert sind.  Sie sollten jedoch mit einigen oder allen Features des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystems vertraut sein, damit Sie diese Features nutzen können.  
  
 Der Zweck von [Abhängigkeitseigenschaften](GTMT) besteht darin, es zu ermöglichen, den Wert einer Eigenschaft anhand des Werts anderer Eingaben zu berechnen.  Diese Eingaben können Folgendes umfassen: Systemeigenschaften wie Designs und Benutzerpräferenzen, Just\-In\-Time\-Mechanismen zur Ermittlung von Eigenschaften, z. B. Datenbindung und Animationen\/Storyboards, Vorlagen zur mehrfachen Verwendung, z. B. Ressourcen und Stile, oder Werte, die aufgrund von Beziehungen mit anderen Elementen in der Elementstruktur bekannt sind \(übergeordnete und untergeordnete Elemente\).  Außerdem kann eine [Abhängigkeitseigenschaft](GTMT) implementiert werden, um eine unabhängige Validierung, Standardwerte, Rückrufe, die Änderungen von Eigenschaften überwachen, und ein System bereitzustellen, das Eigenschaftswerte basierend auf Laufzeitinformationen umwandeln kann.  Abgeleitete Klassen können ebenfalls einige spezifische Merkmale einer vorhandenen Eigenschaft ändern, indem sie Abhängigkeitseigenschaft\-Metadaten überschreiben, anstatt die eigentliche Implementierung vorhandener Eigenschaften zu überschreiben oder neue Eigenschaften zu erstellen.  
  
 In der SDK\-Referenz sehen Sie, bei welcher Eigenschaft es sich um eine Abhängigkeitseigenschaft handelt, da diese auf ihren Referenzseiten jeweils über einen Abschnitt mit Informationen zur Abhängigkeitseigenschaft verfügen.  Der Abschnitt mit den Informationen zur Abhängigkeitseigenschaft enthält einen Link zum <xref:System.Windows.DependencyProperty>\-Bezeichnerfeld für die jeweilige Abhängigkeitseigenschaft sowie eine Liste der Metadatenoptionen, die für die Eigenschaft festgelegt sind, Überschreibungsinformationen pro Klasse und andere Details.  
  
<a name="back_dependency_properties"></a>   
## Abhängigkeitseigenschaften als Unterstützung für CLR\-Eigenschaften  
 [Abhängigkeitseigenschaften](GTMT) und das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem erweitern die Eigenschaftenfunktionalität, indem ein Typ als Unterstützung für eine Eigenschaft bereitgestellt wird. Dies dient als alternative Implementierung zur standardmäßigen Vorgehensweise, bei der die Eigenschaft als Unterstützung über ein privates Feld verfügt.  Der Name dieses Typs lautet <xref:System.Windows.DependencyProperty>.  Der andere wichtige Typ, der das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem definiert, ist <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject> definiert die Basisklasse, die eine [Abhängigkeitseigenschaft](GTMT) registrieren und besitzen kann.  
  
 Es folgt eine Zusammenfassung der Terminologie, die in dieser [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]\-Dokumentation bei der Beschreibung der [Abhängigkeitseigenschaften](GTMT) verwendet wird:  
  
-   **Abhängigkeitseigenschaft:** Eine Eigenschaft, die als Unterstützung über eine <xref:System.Windows.DependencyProperty> verfügt.  
  
-   **Abhängigkeitseigenschaftbezeichner:** Eine <xref:System.Windows.DependencyProperty>\-Instanz, die als Rückgabewert beim Registrieren einer [Abhängigkeitseigenschaft](GTMT) abgerufen und dann als statischer Member einer Klasse gespeichert wird.  Dieser Bezeichner wird als Parameter für viele der [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] verwendet, die mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem interagieren.  
  
-   **CLR\-Wrapper:** Die get\- und set\-Implementierungen für die Eigenschaft.  Diese Implementierungen beziehen den Abhängigkeitseigenschaftbezeichner ein, indem sie ihn in den Aufrufen <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> verwenden. Auf diese Weise wird die Unterstützung für die Eigenschaft mithilfe des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystems bereitgestellt.  
  
 Im folgenden Beispiel wird die `IsSpinning`\-[Abhängigkeitseigenschaft](GTMT) definiert und die Beziehung des <xref:System.Windows.DependencyProperty>\-Bezeichners mit der Eigenschaft gezeigt, die dieser unterstützt.  
  
 [!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
 [!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
[!code-csharp[PropertiesOvwSupport#DPFormBasic2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic2)]  
  
 Die Namenskonvention der Eigenschaft und ihres unterstützenden <xref:System.Windows.DependencyProperty>\-Felds ist wichtig.  Der Name des Felds muss immer der Name der Eigenschaft sein, an den das Suffix `Property` angehängt ist.  Weitere Informationen zu dieser Konvention und die Gründe dafür finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
<a name="setting_property_values"></a>   
## Festlegen von Eigenschaftswerten  
 Sie können Eigenschaften in Code oder in XAML festlegen.  
  
<a name="local_property_values"></a>   
### Festlegen von Eigenschaftswerten in XAML  
 Im folgenden XAML\-Beispiel wird die Hintergrundfarbe einer Schaltfläche auf Rot festgelegt.  Dieses Beispiel zeigt einen Fall, bei dem der einfache Zeichenfolgenwert für ein XAML\-Attribut im generierten Code vom WPF\-XAML\-Parser in einen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Typ konvertiert wird \(eine <xref:System.Windows.Media.Color> mithilfe eines <xref:System.Windows.Media.SolidColorBrush>\).  
  
 [!code-xml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]  
  
 XAML unterstützt zum Festlegen von Eigenschaften eine Vielzahl von Syntaxformaten.  Welche Syntax Sie für eine bestimmte Eigenschaft verwenden, hängt vom verwendeten Werttyp einer Eigenschaft ab, sowie von anderen Faktoren, z. B. dem Vorhandensein eines Typkonverters.  Weitere Informationen zur XAML\-Syntax zum Festlegen von Eigenschaften finden Sie unter [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) und [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Das folgende XAML\-Beispiel zeigt einen anderen Schaltflächenhintergrund, der mithilfe einer Syntax ohne Attribute festgelegt wird.  In diesem Fall wird keine einfache Füllfarbe festgelegt, sondern als Hintergrund wird ein Bild verwendet, wobei ein Element dieses Bild und die Quelle des Bilds darstellt, das als Attribut des geschachtelten Elements angegeben ist.  Dies ist ein Beispiel für Eigenschaftenelementsyntax.  
  
 [!code-xml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]  
  
<a name="setting_properties_code"></a>   
### Festlegen von Eigenschaften in Code  
 Zum Festlegen der Werte von [Abhängigkeitseigenschaften](GTMT) im Code ist normalerweise nur ein Aufruf an die festgelegte Implementierung erforderlich, die vom [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Wrapper offengelegt wird.  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]  
  
 Das Abrufen eines Eigenschaftswerts erfordert im Wesentlichen auch nur einen Aufruf an die Get\-Wrapper\-Implementierung:  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]  
  
 Sie können die Eigenschaft\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> auch direkt aufrufen.  Dies ist in der Regel nicht erforderlich, wenn Sie vorhandene Eigenschaften verwenden \(Wrapper sind benutzerfreundlicher und bieten Entwicklertools eine bessere Zugänglichkeit zu Eigenschaften\), aber das direkte Aufrufen von [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] ist in bestimmten Fällen notwendig.  
  
 Sie können Eigenschaften auch in XAML festlegen und dann per CodeBehind im Code später darauf zugreifen.  Weitere Informationen finden Sie unter [Code\-Behind und XAML in WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
<a name="functionality"></a>   
## Eigenschaftenfunktionalität, die von einer Abhängigkeitseigenschaft bereitgestellt wird  
 Eine Abhängigkeitseigenschaft stellt Funktionalität bereit, die die Funktionen einer Eigenschaft erweitert, anstatt eine Eigenschaft nur mit einem Feld zu unterstützen.  Häufig umfassen diese Funktionalitäten ein bestimmtes Feature der gesamten Gruppe von Features von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   [Ressourcen](#setting_properties_resources)  
  
-   [Datenbindung](#setting_properties_data_binding)  
  
-   [Stile](#setting_properties_styles)  
  
-   [Animationen](#animations)  
  
-   [Metadatenüberschreibungen](#metadata)  
  
-   [Vererbung von Eigenschaftswerten](#setting_properties_inheritance)  
  
-   [WPF\-Designerintegration](#vs2008_integration)  
  
<a name="setting_properties_resources"></a>   
### Ressourcen  
 Sie können den Wert einer Abhängigkeitseigenschaft festlegen, indem Sie auf eine Ressource verweisen.  Ressourcen werden normalerweise als `Resources`\-Eigenschaftswert eines Seitenstammelements oder der Anwendung angegeben \(diese Positionen ermöglichen den einfachsten Zugriff auf die Ressource\).  Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Media.SolidColorBrush>\-Ressource definieren.  
  
 [!code-xml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]  
  
 Nachdem die Ressource definiert wurde, können Sie auf die Ressource verweisen und sie verwenden, um einen Eigenschaftswert anzugeben:  
  
 [!code-xml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]  
  
 Auf diese Ressource wird als [DynamicResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) verwiesen \(in WPF\-XAML können Sie einen statischen oder einen dynamischen Ressourcenverweis verwenden\).  Um einen dynamischen Ressourcenverweis zu verwenden, müssen Sie eine Abhängigkeitseigenschaft festlegen. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem aktiviert also die Verwendung von dynamischen Ressourcenverweisen.  Weitere Informationen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
> [!NOTE]
>  Ressourcen werden als lokaler Wert behandelt. Dies bedeutet, dass Sie den Ressourcenverweis entfernen, wenn Sie einen anderen lokalen Wert festlegen.  Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
<a name="setting_properties_data_binding"></a>   
### Datenbindung  
 Eine Abhängigkeitseigenschaft kann per Datenbindung auf einen Wert verweisen.  Die Datenbindung kann mithilfe einer spezifischen Markuperweiterungssyntax in XAML oder mithilfe des <xref:System.Windows.Data.Binding>\-Objekts im Code erfolgen.  Bei der Datenbindung wird die endgültige Ermittlung des Eigenschaftswerts bis zur Laufzeit verzögert, wo der Wert dann aus einer Datenquelle abgerufen wird.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft mit einer in XAML deklarierten Bindung für eine <xref:System.Windows.Controls.Button> festgelegt.  Die Bindung verwendet einen geerbten Datenkontext und eine <xref:System.Windows.Data.XmlDataProvider>\-Datenquelle \(nicht gezeigt\).  Die Bindung selbst gibt die gewünschte Quelleigenschaft mithilfe von <xref:System.Windows.Data.Binding.XPath%2A> innerhalb der Datenquelle an.  
  
 [!code-xml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]  
  
> [!NOTE]
>  Bindungen werden als lokaler Wert behandelt. Dies bedeutet, dass Sie die Bindung entfernen, wenn Sie einen anderen lokalen Wert festlegen.  Ausführliche Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Abhängigkeitseigenschaften bzw. die <xref:System.Windows.DependencyObject>\-Klasse weisen keine systemeigene Unterstützung von <xref:System.ComponentModel.INotifyPropertyChanged> auf, die der Erstellung von Änderungsbenachrichtigungen im <xref:System.Windows.DependencyObject>\-Quelleigenschaftswert für Datenbindungsvorgänge dient.  Weitere Informationen zur Erstellung von Eigenschaften für die Verwendung bei der Datenbindung, die Änderungen an ein Datenbindungsziel berichten können, finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="setting_properties_styles"></a>   
### Stile  
 Stile und Vorlagen sind zwei Hauptgründe für die Verwendung von Abhängigkeitseigenschaften.  Stile eignen sich besonders gut zum Festlegen von Eigenschaften, die eine Anwendungs\-[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] definieren.  Stile werden in XAML normalerweise als Ressourcen definiert.  Stile interagieren mit dem Eigenschaftensystem, da sie in der Regel sog. "Setter" für bestimmte Eigenschaften enthalten, sowie "Trigger", die einen Eigenschaftswert basierend auf dem Echtzeitwert einer anderen Eigenschaft ändern.  
  
 Im folgenden Beispiel wird ein einfacher Stil erstellt \(der in einem <xref:System.Windows.FrameworkElement.Resources%2A>\-Wörterbuch definiert wird, nicht gezeigt\), der direkt auf die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft für ein <xref:System.Windows.Controls.Button>\-Element angewendet wird.  Der Setter im Stil legt die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft für ein formatiertes <xref:System.Windows.Controls.Button>\-Element auf Grün fest.  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]  
  
 Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="animations"></a>   
### Animationen  
 Abhängigkeitseigenschaften können animiert werden.  Wenn eine Animation angewendet wurde und ausgeführt wird, verfügt der animierte Wert über eine höhere Priorität in der Rangfolge als alle anderen Werte \(z. B. ein lokaler Wert\), die der Eigenschaft sonst noch zugeordnet sind.  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Controls.Control.Background%2A> einer <xref:System.Windows.Controls.Button>\-Eigenschaft animiert \(eigentlich wird der <xref:System.Windows.Controls.Control.Background%2A> animiert, indem mithilfe der Eigenschaftenelementsyntax ein leeres <xref:System.Windows.Media.SolidColorBrush>\-Element als <xref:System.Windows.Controls.Control.Background%2A> angegeben wird, und dann wird die <xref:System.Windows.Media.SolidColorBrush.Color%2A>\-Eigenschaft dieses <xref:System.Windows.Media.SolidColorBrush>\-Elements direkt animiert\).  
  
 [!code-xml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]  
  
 Weitere Informationen zur Animation von Eigenschaften finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="metadata"></a>   
### Metadatenüberschreibungen  
 Sie können bestimmte Verhalten einer [Abhängigkeitseigenschaft](GTMT) ändern, indem Sie die Metadaten für diese Eigenschaft überschreiben, wenn Sie die Ableitung von der Klasse durchführen, die die [Abhängigkeitseigenschaft](GTMT) ursprünglich registriert hat.  Beim Überschreiben von Metadaten wird der <xref:System.Windows.DependencyProperty>\-Bezeichner verwendet.  Das Überschreiben von Metadaten erfordert keine Neuimplementierung der Eigenschaft.  Die Metadatenänderung wird vom Eigenschaftensystem selbst vorgenommen. Jede Klasse kann pro Typ individuelle Metadaten für alle Eigenschaften enthalten, die von den Basisklassen geerbt werden.  
  
 Im folgenden Beispiel werden Metadaten für den <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> einer Abhängigkeitseigenschaft überschrieben.  Das Überschreiben dieser Abhängigkeitseigenschaft\-Metadaten ist Teil eines Implementierungsmusters, bei dem Steuerelemente erstellt werden, die Standardstile aus Designs verwenden können.  
  
 [!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
 [!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]  
  
 Weitere Informationen über das Überschreiben oder Abrufen von Eigenschaftenmetadaten finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="setting_properties_inheritance"></a>   
### Vererbung von Eigenschaftswerten  
 Ein Element kann den Wert einer Abhängigkeitseigenschaft von seinem übergeordneten Element in der Objektstruktur erben.  
  
> [!NOTE]
>  Das Verhalten zur Vererbung von Eigenschaftswerten ist nicht global für alle Abhängigkeitseigenschaften aktiviert, da die Berechnungszeit für die Vererbung zu Leistungseinbußen führt.  Die Vererbung von Eigenschaftswerten ist normalerweise nur für Eigenschaften aktiviert, bei denen ein bestimmtes Szenario es erfordert, dass die Vererbung von Eigenschaftswerten verwendet wird.  Im Abschnitt mit den **Informationen zur Abhängigkeitseigenschaft** der SDK\-Referenz für die Abhängigkeitseigenschaft können Sie feststellen, ob eine Abhängigkeitseigenschaft Elemente erbt.  
  
 Das folgende Beispiel zeigt eine Bindung und legt die <xref:System.Windows.FrameworkElement.DataContext%2A>\-Eigenschaft fest, die die Quelle der Bindung angibt. Dies wurde im Bindungsbeispiel weiter oben nicht gezeigt.  Alle nachfolgenden Bindungen in untergeordneten Objekten müssen die Quelle nicht angeben, sie können den geerbten Wert der <xref:System.Windows.FrameworkElement.DataContext%2A>\-Eigenschaft im übergeordneten <xref:System.Windows.Controls.StackPanel>\-Objekt verwenden.  \(Alternativ könnte ein untergeordnetes Objekt eine eigene <xref:System.Windows.FrameworkElement.DataContext%2A>\-Eigenschaft oder eine <xref:System.Windows.Data.Binding.Source%2A>\-Eigenschaft im <xref:System.Windows.Data.Binding>\-Element angeben und den geerbten Wert für den Datenkontext seiner Bindungen absichtlich nicht verwenden.\)  
  
 [!code-xml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]  
  
 Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="vs2008_integration"></a>   
### WPF\-Designerintegration  
 Ein benutzerdefiniertes Steuerelement mit Eigenschaften, die als Abhängigkeitseigenschaften implementiert sind, erhält entsprechende [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]\-Unterstützung.  Ein Beispiel hierfür ist die Fähigkeit, direkte und angefügte Abhängigkeitseigenschaften im Fenster **Eigenschaften** zu bearbeiten.  Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="value_determination"></a>   
## Rangfolge von Abhängigkeitseigenschaftswerten  
 Wenn Sie den Wert einer [Abhängigkeitseigenschaft](GTMT) abrufen, rufen Sie ggf. einen Wert ab, der für die Eigenschaft mithilfe von einer der anderen auf Eigenschaften basierenden Eingaben festgelegt wurde, die Teil des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystems sind.  Die Rangfolge von Abhängigkeitseigenschaftswerten wird verwendet, damit für verschiedene Szenarios zur Versorgung der Eigenschaften mit Werten Klarheit herrscht.  
  
 Betrachten Sie das folgende Beispiel.  Das Beispiel enthält einen Stil, der für alle Schaltflächen und ihre <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaften gilt, aber es wird auch eine Schaltfläche mit einem lokal festgelegten <xref:System.Windows.Controls.Control.Background%2A>\-Wert angegeben.  
  
> [!NOTE]
>  In der SDK\-Dokumentation werden die Begriffe "lokaler Wert" bzw. "lokal festgelegter Wert" gelegentlich verwendet, wenn Abhängigkeitseigenschaften beschrieben werden.  Ein lokal festgelegter Wert ist ein Eigenschaftswert, der für eine Objektinstanz direkt im Code oder als Attribut eines Elements in XAML festgelegt ist.  
  
 Für die erste Schaltfläche wird die Eigenschaft grundsätzlich zweimal festgelegt, aber es gilt nur ein Wert: der Wert mit der höchsten Priorität in der Rangfolge.  Ein lokal festgelegter Wert weist die höchste Priorität auf \(gilt nicht für eine ausgeführte Animation, aber dieses Beispiel enthält keine Animation\), und aus diesem Grund wird für den Hintergrund der ersten Schaltfläche der lokal festgelegte Wert verwendet, nicht der Wert des Setters für den Stil.  Die zweite Schaltfläche weist keinen lokalen Wert auf \(und auch keinen anderen Wert mit einer höheren Priorität als ein Stil\-Setter\), also wird für den Hintergrund der Schaltfläche der Wert des Stil\-Setters verwendet.  
  
 [!code-xml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  
  
### Warum wird für Abhängigkeitseigenschaften eine Rangfolge verwendet?  
 Normalerweise liegt es in Ihrem Interesse, dass Stile immer gelten und auch Vorrang vor einem lokal festgelegten Wert eines einzelnen Elements haben \(andernfalls wäre es sehr schwierig, Stile oder Elemente überhaupt zu verwenden\).  Deshalb verfügen die Werte, die von Stilen stammen, über eine niedrigere Priorität als ein lokal festgelegter Wert.  Eine ausführliche Liste der Abhängigkeitseigenschaften und der dazugehörigen geltenden Werte finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
> [!NOTE]
>  Es gibt eine Reihe von Eigenschaften, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elemente definiert sind, bei denen es sich nicht um Abhängigkeitseigenschaften handelt.  In der Regel werden Eigenschaften nur als Abhängigkeitseigenschaften implementiert, wenn es erforderlich ist, mindestens eines der vom Eigenschaftensystem bereitgestellten Szenarios zu unterstützen: Datenbindung, Stile, Animation, Standardwertunterstützung, Vererbung, angefügte Eigenschaften oder Ungültigkeit.  
  
<a name="dp_implement_roadmap"></a>   
## Weitere Informationen zu Abhängigkeitseigenschaften  
  
-   Eine [angefügte Eigenschaft](GTMT) ist ein Eigenschaftentyp, der eine spezielle Syntax in XAML unterstützt.  Eine angefügte Eigenschaft verfügt häufig nicht über eine 1:1\-Beziehung mit einer [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaft und ist nicht immer eine [Abhängigkeitseigenschaft](GTMT).  Der Hauptzweck einer [angefügten Eigenschaft](GTMT) besteht darin, es untergeordneten Elementen zu ermöglichen, Eigenschaftswerte an ein übergeordnetes Element zu berichten, sogar wenn das übergeordnete Element und das untergeordnete Element diese Eigenschaft nicht als Teil der Klassenmemberauflistungen enthalten.  Ein Hauptszenario besteht darin, es untergeordneten Elementen zu ermöglichen, dem übergeordneten Element mitzuteilen, welche [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Darstellung erforderlich ist. Ein Beispiel hierzu finden Sie unter <xref:System.Windows.Controls.DockPanel.Dock%2A> oder <xref:System.Windows.Controls.Canvas.Left%2A>.  Ausführliche Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
-   Für Komponenten\- oder Anwendungsentwickler kann es ratsam sein, eigene [Abhängigkeitseigenschaften](GTMT) zu erstellen, um Funktionen wie Datenbindung oder Stilunterstützung zu ermöglichen oder um Unterstützung von Ungültigkeit und Wertkoersion bereitzustellen.  Ausführliche Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   Abhängigkeitseigenschaften sollten in der Regel als öffentliche Eigenschaften angesehen werden, die für jeden Aufrufer zugänglich bzw. mindestens erkennbar sind, der über Zugriff auf eine Instanz verfügt.  Weitere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
## Siehe auch  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Schreibgeschützte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [WPF\-Architektur](../../../../docs/framework/wpf/advanced/wpf-architecture.md)