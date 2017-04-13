---
title: "Benutzerdefinierte Abh&#228;ngigkeitseigenschaften | Microsoft Docs"
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
  - "Benutzerdefinierte Abhängigkeitseigenschaften"
  - "Abhängigkeitseigenschaften, Benutzerdefiniert"
  - "Implementieren, Wrapper"
  - "Metadaten, Für Eigenschaften"
  - "Eigenschaften, Metadaten"
  - "Eigenschaften, Registrieren"
  - "Registrierungseigenschaften"
  - "Wrapper, Implementieren"
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Benutzerdefinierte Abh&#228;ngigkeitseigenschaften
In diesem Thema sind die Gründe beschrieben, aus denen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungs\- und Komponentenentwickler ggf. benutzerdefinierte [Abhängigkeitseigenschaften](GTMT) erstellen. Außerdem werden die Implementierungsschritte und einige Implementierungsoptionen beschrieben, mit denen Sie die Leistung, die Verwendbarkeit oder die Vielseitigkeit der Eigenschaft verbessern können.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klassen auskennen und das Thema [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben.  Um den Beispielen in diesem Thema folgen zu können, sollten Sie außerdem mit der Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen vertraut sein.  
  
<a name="whatis"></a>   
## Was ist eine Abhängigkeitseigenschaft?  
 Sie können eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaft so aktivieren, dass sie Stile, Datenbindung, Vererbung, Animationen und Standardwerte unterstützt, indem Sie die Eigenschaft als [Abhängigkeitseigenschaft](GTMT) implementieren.  Bei Abhängigkeitseigenschaften handelt es sich um Eigenschaften, die im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem registriert werden, indem die <xref:System.Windows.DependencyProperty.Register%2A>\-Methode \(oder <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>\) aufgerufen wird, und die als Unterstützung über ein <xref:System.Windows.DependencyProperty>\-Bezeichnerfeld verfügen.  Abhängigkeitseigenschaften können nur von <xref:System.Windows.DependencyObject>\-Typen verwendet werden, aber das <xref:System.Windows.DependencyObject> ist in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klassenhierarchie ziemlich weit oben angeordnet, so dass die Mehrzahl der in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügbaren Klassen Abhängigkeitseigenschaften unterstützen kann.  Weitere Informationen zu Abhängigkeitseigenschaften und zur Terminologie und den dazugehörigen Konventionen, die in diesem [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] verwendet werden, finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="example_dp"></a>   
## Beispiele für Abhängigkeitseigenschaften  
 Beispiele für Abhängigkeitseigenschaften, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klassen implementiert werden, sind u. a. die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft, die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft und die <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft.  Jede Abhängigkeitseigenschaft, die von einer Klasse verfügbar gemacht wird, verfügt über ein entsprechendes öffentliches, statisches Feld vom Typ <xref:System.Windows.DependencyProperty>, das für dieselbe Klasse verfügbar gemacht wird. Dies ist der Bezeichner für die Abhängigkeitseigenschaft.  Für die Benennung des Bezeichners wird eine Konvention verwendet: der Name der [Abhängigkeitseigenschaft](GTMT) mit der angehängten Zeichenfolge `Property`.  Zum Beispiel lautet das entsprechende <xref:System.Windows.DependencyProperty>\-Bezeichnerfeld für die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft <xref:System.Windows.Controls.Control.BackgroundProperty>.  Der Bezeichner speichert die Informationen zur [Abhängigkeitseigenschaft](GTMT), die bei der Registrierung gelten. Anschließend wird der Bezeichner dann für andere Vorgänge verwendet, die die [Abhängigkeitseigenschaft](GTMT) betreffen, z. B. das Aufrufen von <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
 Wie in der [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) erwähnt, sind alle Abhängigkeitseigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(mit Ausnahme der meisten [angefügten Eigenschaften](GTMT)\) aufgrund der Wrapperimplementierung auch [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaften.  Daher können Sie Abhängigkeitseigenschaften per Code abrufen oder festlegen, indem Sie [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Accessoren aufrufen, die die Wrapper auf dieselbe Weise wie andere [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaften definieren.  Als Consumer eingerichteter Abhängigkeitseigenschaften verwenden Sie die <xref:System.Windows.DependencyObject>\-Methoden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A>, die den Verbindungspunkt zum zugrunde liegenden Eigenschaftensystem bilden, normalerweise nicht.  Stattdessen hat die vorhandene Implementierung der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaften <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> bereits innerhalb der `get`\- und `set`\-Wrapperimplementierungen der Eigenschaft aufgerufen, so dass das Bezeichnerfeld richtig verwendet wird.  Wenn Sie eine benutzerdefinierte Abhängigkeitseigenschaft selbst implementieren, definieren Sie den Wrapper auf ähnliche Weise.  
  
<a name="backing_with_dp"></a>   
## Wann sollten Sie eine Abhängigkeitseigenschaft implementieren?  
 Beim Implementieren einer Eigenschaft für eine Klasse können Sie, sofern Ihre Klasse von <xref:System.Windows.DependencyObject> abgeleitet ist, die Eigenschaft mit einem <xref:System.Windows.DependencyProperty>\-Bezeichner versehen und diese zu einer Abhängigkeitseigenschaft machen.  Es ist nicht in allen Fällen erforderlich oder passend, dass eine Eigenschaft eine Abhängigkeitseigenschaft ist. Dies hängt von den Anforderungen des jeweiligen Szenarios ab.  Manchmal reicht das typische Verfahren aus, bei dem die Eigenschaft als Unterstützung mit einem privaten Feld versehen wird.  Sie sollten Ihre Eigenschaft jedoch stets als [Abhängigkeitseigenschaft](GTMT) implementieren, wenn die Eigenschaft eine oder mehrere der folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Funktionen unterstützen soll:  
  
-   Sie möchten, dass für die Eigenschaft ein Stil festgelegt werden kann.  Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
-   Sie möchten, dass die Eigenschaft die Datenbindung unterstützt.  Weitere Informationen zur Datenbindung für Abhängigkeitseigenschaften finden Sie unter [Binden der Eigenschaften von zwei Steuerelementen](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md).  
  
-   Sie möchten, dass für die Eigenschaft ein dynamischer Ressourcenverweis festgelegt werden kann.  Weitere Informationen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Sie möchten, dass ein Eigenschaftswert von einem übergeordneten Element in der Elementstruktur automatisch geerbt wird.  Führen Sie die Registrierung in diesem Fall mit der <xref:System.Windows.DependencyProperty.RegisterAttached%2A>\-Methode auch dann durch, wenn Sie für den [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Zugriff einen Eigenschaftenwrapper erstellen.  Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Sie möchten, dass die Eigenschaft animiert werden kann.  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Sie möchten, dass das Eigenschaftensystem es meldet, wenn sich der vorherige Wert der Eigenschaft aufgrund von Aktionen geändert hat, die das Eigenschaftensystem, die Umgebung oder der Benutzer ausgeführt hat, oder indem Stile gelesen und verwendet wurden.  Mithilfe von Eigenschaftenmetadaten kann Ihre Eigenschaft eine Rückrufmethode angeben, die jeweils aufgerufen wird, wenn das Eigenschaftensystem ermittelt hat, dass sich der Eigenschaftswert definitiv geändert hat.  Ein verwandter Begriff ist die Koersion des Eigenschaftswerts.  Weitere Informationen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Sie möchten geltende Metadatenkonventionen verwenden, die auch von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Prozessen verwendet werden, z. B. das Berichten, ob es beim Ändern eines Eigenschaftswerts erforderlich sein soll, dass das Layoutsystem die visuellen Objekte für ein Element neu zusammenstellt.  Oder Sie möchten Metadatenüberschreibungen verwenden können, damit abgeleitete Klassen auf Metadaten basierende Merkmale wie den Standardwert ändern können.  
  
-   Sie möchten, dass die Eigenschaften eines benutzerdefinierten Steuerelements die [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]\-[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]\-Unterstützung erhalten, z. B. die Bearbeitung im Fenster **Eigenschaften**.  Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Bei diesen Szenarios sollten Sie auch prüfen, ob Sie Ihr Ziel erreichen können, indem Sie die Metadaten einer vorhandenen [Abhängigkeitseigenschaft](GTMT) überschreiben, anstatt eine völlig neue Eigenschaft zu implementieren.  Ob eine Metadatenüberschreibung ratsam ist, hängt von Ihrem Szenario und davon ab, inwieweit das Szenario der Implementierung in vorhandenen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Abhängigkeitseigenschaften und \-Klassen ähnelt.  Weitere Informationen zum Überschreiben von Metadaten vorhandener Eigenschaften finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="checklist"></a>   
## Prüfliste für die Definition einer Abhängigkeitseigenschaft  
 Das Definieren einer Abhängigkeitseigenschaft umfasst vier unterschiedliche Begriffe bzw. Schritte.  Bei diesen Begriffen handelt es sich nicht um zwingend erforderliche einzelne Schritte, da einige Schritte bei der Implementierung im Code in einzelnen Codezeilen zusammengefasst werden:  
  
-   \(Optional\) Erstellen Sie Eigenschaftenmetadaten für die Abhängigkeitseigenschaft.  
  
-   Registrieren Sie den Eigenschaftennamen im Eigenschaftensystem, indem Sie einen Besitzertyp und den Typ des Eigenschaftswerts angeben.  Geben Sie auch die Eigenschaftenmetadaten an, falls diese verwendet werden.  
  
-   Definieren Sie einen <xref:System.Windows.DependencyProperty>\-Bezeichner als `public``static``readonly`\-Feld für den Besitzertyp.  
  
-   Definieren Sie eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Wrappereigenschaft, deren Name dem Namen der Abhängigkeitseigenschaft entspricht.  Implementieren Sie den `get`\-Accessor und den `set`\-Accessor der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Wrappereigenschaft, um eine Verbindung zu der Abhängigkeitseigenschaft herzustellen, die sie unterstützt.  
  
<a name="registering"></a>   
### Registrieren der Eigenschaft im Eigenschaftensystem  
 Damit Ihre Eigenschaft zu einer [Abhängigkeitseigenschaft](GTMT) wird, müssen Sie die Eigenschaft in einer Tabelle registrieren, die vom Eigenschaftensystem verwaltet wird. Außerdem müssen Sie der Eigenschaft einen eindeutigen Bezeichner zuweisen, der bei späteren Vorgängen des Eigenschaftensystems als Qualifizierer verwendet wird.  Bei diesen Vorgängen kann es sich um interne Vorgänge oder um Ihre eigenen [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] handeln, die Codeaufrufe durchführen.  Um die Eigenschaft zu registrieren, rufen Sie die <xref:System.Windows.DependencyProperty.Register%2A>\-Methode im Text Ihrer Klasse auf \(innerhalb der Klasse, aber außerhalb von Memberdefinitionen\).  Das Bezeichnerfeld wird auch vom <xref:System.Windows.DependencyProperty.Register%2A>\-Methodenaufruf als Rückgabewert bereitgestellt.  Der <xref:System.Windows.DependencyProperty.Register%2A>\-Aufruf erfolgt außerhalb von anderen Memberdefinitionen, weil Sie diesen Rückgabewert verwenden, um als Teil der Klasse ein `public` `static` `readonly`\-Feld vom Typ <xref:System.Windows.DependencyProperty> zuzuweisen und zu erstellen.  Dieses Feld wird zum Bezeichner für die Abhängigkeitseigenschaft.  
  
 [!code-csharp[WPFAquariumSln#RegisterAG](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
 [!code-vb[WPFAquariumSln#RegisterAG](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]  
  
<a name="nameconventions"></a>   
### Namenskonventionen für Abhängigkeitseigenschaften  
 Für Abhängigkeitseigenschaften gelten Namenskonventionen, die Sie bis auf bestimmte Ausnahmefälle befolgen müssen.  
  
 Die Abhängigkeitseigenschaft selbst hat einen Hauptnamen \(in diesem Beispiel "AquariumGraphic"\), der als erster Parameter von <xref:System.Windows.DependencyProperty.Register%2A> angegeben wird.  Dieser Name muss innerhalb eines Registrierungstyps eindeutig sein.  Für Abhängigkeitseigenschaften, die über Basistypen geerbt werden, gilt, dass sie bereits Teil des Registrierungstyps sind. Die Namen von geerbten Eigenschaften können nicht erneut registriert werden.  Es gibt jedoch ein Verfahren zum Hinzufügen einer Klasse als Besitzer einer Abhängigkeitseigenschaft, das Sie auch dann verwenden können, wenn die Abhängigkeitseigenschaft nicht geerbt wird. Ausführliche Informationen finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Benennen Sie dieses Feld beim Erstellen des Bezeichnerfelds mit dem Namen der Eigenschaft, unter dem diese registriert wurde, und hängen Sie das Suffix `Property` an.  Dieses Feld ist Ihr Bezeichner für die Abhängigkeitseigenschaft, der später als Eingabe für die Aufrufe <xref:System.Windows.DependencyObject.SetValue%2A> und <xref:System.Windows.DependencyObject.GetValue%2A> verwendet wird, die Sie in den Wrappern durchführen. Außerdem wird der Bezeichner für Ihre anderen Codezugriffe auf die Eigenschaft, für externe Codezugriffe, die Sie zulassen, für das Eigenschaftensystem und ggf. von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessoren verwendet.  
  
> [!NOTE]
>  Das Definieren der Abhängigkeitseigenschaft im Klassentext ist die gängigste Art der Implementierung, aber Sie können eine Abhängigkeitseigenschaft auch im statischen Konstruktor der Klasse definieren.  Dieser Ansatz eignet sich ggf., wenn Sie mehr als eine Codezeile benötigen, um die Abhängigkeitseigenschaft zu initialisieren.  
  
<a name="wrapper1"></a>   
### Implementieren des Wrappers  
 Ihre Wrapperimplementierung sollte <xref:System.Windows.DependencyObject.GetValue%2A> in der `get`\-Implementierung und <xref:System.Windows.DependencyObject.SetValue%2A> in der `set`\-Implementierung aufrufen \(um dies zu verdeutlichen, werden hier der ursprüngliche Registrierungsaufruf und das dazugehörige Feld dargestellt\).  
  
 Von Ausnahmefällen abgesehen, sollten Ihre Wrapperimplementierungen jeweils nur die Aktion <xref:System.Windows.DependencyObject.GetValue%2A> bzw. <xref:System.Windows.DependencyObject.SetValue%2A> ausführen.  Der Grund dafür wird im Thema [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md) erläutert.  
  
 Alle vorhandenen öffentlichen Abhängigkeitseigenschaften, die über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klassen bereitgestellt werden, verwenden dieses einfache Modell zur Wrapperimplementierung. Die meisten komplexen Schritte der Funktionsweise von Abhängigkeitseigenschaften sind entweder Teil eines Verhaltens des Eigenschaftensystems, oder sie werden mithilfe von anderen Maßnahmen wie Koersion oder Rückrufen bei Eigenschaftenänderungen über Eigenschaftenmetadaten implementiert.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
 Der Konvention nach muss der Name der Wrappereigenschaft wieder dem Namen entsprechen, der als erster Parameter des <xref:System.Windows.DependencyProperty.Register%2A>\-Aufrufs gewählt bzw. angegeben wurde, über den die Eigenschaft registriert wurde.  Wenn Sie die Konvention für die Eigenschaft nicht befolgen, werden nicht zwangsläufig alle Verwendungsmöglichkeiten deaktiviert, aber Sie müssen einige wichtige Punkte beachten:  
  
-   Bestimmte Aspekte von Stilen und Vorlagen funktionieren nicht.  
  
-   Die meisten Tools und Designer müssen sich auf die Namenskonventionen verlassen können, um [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] richtig serialisieren zu können oder um die Entwurfsumgebungsunterstützung für Eigenschaften individuell bereitstellen zu können.  
  
-   Die aktuelle Implementierung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ladeprogramms umgeht die Wrapper vollständig und verlässt sich beim Verarbeiten von Attributwerten auf die Namenskonvention.  Weitere Informationen finden Sie unter [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
<a name="metadata"></a>   
### Eigenschaftenmetadaten für eine neue Abhängigkeitseigenschaft  
 Wenn Sie eine Abhängigkeitseigenschaft registrieren, wird bei der Registrierung über das Eigenschaftensystem ein Metadatenobjekt erstellt, das die Eigenschaftenmerkmale speichert.  Viele dieser Merkmale verfügen über Standardwerte, die festgelegt werden, wenn die Eigenschaft mit den einfachen Signaturen von <xref:System.Windows.DependencyProperty.Register%2A> registriert wird.  Mithilfe von anderen Signaturen von <xref:System.Windows.DependencyProperty.Register%2A> können Sie beim Registrieren der Eigenschaft die gewünschten Metadaten angeben.  Die häufigste Art von Metadaten, die für Abhängigkeitseigenschaften angegeben werden, ist ein Standardwert, der auf neue Instanzen angewendet wird, die die Eigenschaft verwenden.  
  
 Wenn Sie eine Abhängigkeitseigenschaft erstellen, die für eine abgeleitete Klasse von <xref:System.Windows.FrameworkElement> vorhanden ist, können Sie die speziellere Metadatenklasse <xref:System.Windows.FrameworkPropertyMetadata> verwenden, anstatt die <xref:System.Windows.PropertyMetadata>\-Basisklasse.  Der Konstruktor für die <xref:System.Windows.FrameworkPropertyMetadata>\-Klasse hat mehrere Signaturen, mit deren Hilfe Sie verschiedene Metadatenmerkmale kombinieren können.  Wenn Sie nur den Standardwert angeben möchten, verwenden Sie die Signatur, die einen einzelnen Parameter vom Typ <xref:System.Object> erfordert.  Übergeben Sie diesen Objektparameter als typspezifischen Standardwert für Ihre Eigenschaft \(der angegebene Standardwert muss den Typ aufweisen, den Sie als `propertyType`\-Parameter im <xref:System.Windows.DependencyProperty.Register%2A>\-Aufruf angegeben haben\).  
  
 Bei Verwendung von <xref:System.Windows.FrameworkPropertyMetadata> können Sie für die Eigenschaft auch Flags für Metadatenoptionen angeben.  Diese Flags werden nach der Registrierung in den Eigenschaftenmetadaten in diskrete Eigenschaften konvertiert und verwendet, um bestimmte Bedingungen an andere Prozesse zu kommunizieren, z. B. an das Layoutmodul.  
  
#### Festlegen von geeigneten Metadatenflags  
  
-   Wenn sich die Eigenschaft \(oder Änderungen ihrer Werte\) auf die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] auswirkt und speziell beeinflusst, wie das Layoutsystem das Element auf einer Seite rendert und diesem eine Größe zuordnet, müssen Sie eine oder mehrere der folgenden Flags festlegen: <xref:System.Windows.FrameworkPropertyMetadataOptions>, <xref:System.Windows.FrameworkPropertyMetadataOptions>, <xref:System.Windows.FrameworkPropertyMetadataOptions>.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions> gibt an, dass eine Änderung dieser Eigenschaft eine Änderung der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Darstellung erfordert, weil das enthaltende Objekt innerhalb des übergeordneten Objekts ggf. mehr oder weniger Platz benötigt.  Sie sollten dieses Flag z. B. für eine Eigenschaft festlegen, die für die Breite \(width\) zuständig ist.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions> gibt an, dass eine Änderung dieser Eigenschaft eine Änderung der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Darstellung erfordert, bei der sich normalerweise keine Änderung des zugewiesenen Bereichs ergibt, die jedoch angibt, dass sich die Positionierung innerhalb des Bereichs geändert hat.  Sie sollten dieses Flag z. B. für eine Eigenschaft festlegen, die für die Ausrichtung \(alignment\) zuständig ist.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions> gibt an, dass eine andere Änderung durchgeführt wurde, die sich nicht auf das Layout und die Maße auswirkt, die jedoch ein weiteres Rendering erfordert.  Ein Beispiel hierfür ist eine Eigenschaft, die eine Farbe eines vorhandenen Elements ändert, z. B. den Hintergrund \(background\).  
  
    -   Diese Flags werden häufig als Protokoll in Metadaten für Ihre eigenen Überschreibungsimplementierungen von Eigenschaftensystem\- oder Layoutrückrufen verwendet.  Sie können z. B. einen <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>\-Rückruf verwenden, der <xref:System.Windows.UIElement.InvalidateArrange%2A> aufruft, wenn eine Eigenschaft der Instanz eine Wertänderung berichtet und <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> in ihren Metadaten auf `true` gesetzt ist.  
  
-   Einige Eigenschaften können sich auf die Renderingmerkmale des enthaltenden übergeordneten Elements auf eine Art und Weise auswirken, die über die oben erwähnten Änderungen der erforderlichen Größe hinausgeht.  Ein Beispiel hierfür ist die <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A>\-Eigenschaft im Flussdokumentmodell, wo Änderungen dieser Eigenschaft das allgemeine Rendering des Flussdokuments ändern können, das den Absatz enthält.  Verwenden Sie <xref:System.Windows.FrameworkPropertyMetadataOptions> oder <xref:System.Windows.FrameworkPropertyMetadataOptions>, um in Ihren Eigenschaften ähnliche Fälle zu identifizieren.  
  
-   Standardmäßig unterstützen Abhängigkeitseigenschaften die Datenbindung.  Sie können die Datenbindung für Fälle deaktivieren, in denen kein realistisches Szenario für die Datenbindung vorhanden ist oder in denen die Leistung der Datenbindung für ein großes Projekt ein Problem darstellt.  
  
-   Standardmäßig hat das <xref:System.Windows.Data.Binding.Mode%2A>\-Element der Datenbindung für Abhängigkeitseigenschaften den Wert <xref:System.Windows.Data.BindingMode>.  Sie können die Bindung pro Bindungsinstanz immer in <xref:System.Windows.Data.BindingMode> ändern. Ausführliche Informationen finden Sie unter [Angeben der Bindungsrichtung](../../../../docs/framework/wpf/data/how-to-specify-the-direction-of-the-binding.md).  Aber als Entwickler, der die Abhängigkeitseigenschaft erstellt, können Sie festlegen, dass die Eigenschaft standardmäßig den Bindungsmodus <xref:System.Windows.Data.BindingMode> verwendet.  Ein Beispiel für eine vorhandene Abhängigkeitseigenschaft ist <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=fullName>. Bei dieser Eigenschaft interagieren die <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>\-Festlegungslogik und die Zusammenstellung von <xref:System.Windows.Controls.MenuItem> mit dem standardmäßigen Designstil.  Die Logik der <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>\-Eigenschaft verwendet die systemeigene Datenbindung, um den Zustand der Eigenschaft im Hinblick auf andere Zustandseigenschaften und Methodenaufrufe beizubehalten.  Eine andere Beispieleigenschaft, die standardmäßig die <xref:System.Windows.Data.BindingMode>\-Datenbindung verwendet, ist <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>.  
  
-   Sie können in einer benutzerdefinierten Abhängigkeitseigenschaft auch die Eigenschaftenvererbung aktivieren, indem Sie das <xref:System.Windows.FrameworkPropertyMetadataOptions>\-Flag festlegen.  Die Eigenschaftenvererbung ist nützlich, wenn übergeordnete und untergeordnete Elemente eine gemeinsame Eigenschaft aufweisen und wenn es für die untergeordneten Elemente sinnvoll ist, dass der jeweilige Eigenschaftswert auf den Wert des übergeordneten Elements festgelegt wird.  Ein Beispiel für eine vererbbare Eigenschaft ist <xref:System.Windows.FrameworkElement.DataContext%2A>. Diese Eigenschaft wird für Bindungsvorgänge verwendet, um das wichtige Master\/Detail\-Szenario für die Darstellung von Daten zu ermöglichen.  Indem Sie <xref:System.Windows.FrameworkElement.DataContext%2A> vererbbar machen, erben auch alle untergeordneten Elemente diesen Datenkontext.  Aufgrund der Vererbung von Eigenschaftswerten können Sie im Stammelement der Seite oder Anwendung einen Datenkontext angeben und müssen diese Angabe nicht für Bindungen in allen untergeordneten Elementen wiederholen.  <xref:System.Windows.FrameworkElement.DataContext%2A> ist ebenfalls ein gutes Beispiel, um zu zeigen, dass die Vererbung den Standardwert überschreibt. Der Wert kann für ein bestimmtes untergeordnetes Element jedoch jederzeit lokal festgelegt werden. Ausführliche Informationen finden Sie unter [Verwenden des Master\-\/Detailmusters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  Die Vererbung von Eigenschaftswerten kann zu Leistungseinbußen führen und sollte daher sparsam eingesetzt werden. Ausführliche Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Legen Sie das <xref:System.Windows.FrameworkPropertyMetadataOptions>\-Flag fest, um anzugeben, ob Ihre Abhängigkeitseigenschaft von Journaldiensten der Navigation erkannt und verwendet werden soll.  Ein Beispiel hierfür ist die <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>\-Eigenschaft. Jedes Element, das über ein Auswahlsteuerelement ausgewählt wird, sollte beim Navigieren im Journalverlauf beibehalten werden.  
  
<a name="RODP"></a>   
## Schreibgeschützte Abhängigkeitseigenschaften  
 Sie können eine Abhängigkeitseigenschaft definieren, die schreibgeschützt ist.  Die Szenarios, in denen Sie Ihre Eigenschaft ggf. als schreibgeschützt definieren sollten, weisen jedoch einige Unterschiede auf. Dies ist auch für die Prozedur zum Registrieren der Eigenschaften beim Eigenschaftensystem und zum Offenlegen des Bezeichners der Fall.  Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
<a name="CTDP"></a>   
## Abhängigkeitseigenschaften vom Typ "Auflistung"  
 Bei Abhängigkeitseigenschaften vom Typ "Auflistung" sind einige zusätzliche Implementierungsaspekte zu beachten.  Weitere Informationen finden Sie unter [Abhängigkeitseigenschaften vom Auflistungstyp](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md).  
  
<a name="SecurityC"></a>   
## Sicherheitsüberlegungen für Abhängigkeitseigenschaften  
 Abhängigkeitseigenschaften sollten als öffentliche Eigenschaften deklariert werden.  Abhängigkeitseigenschaften\-Bezeichnerfelder sollten as öffentliche statische Felder deklariert werden.  Auch wenn Sie versuchen, andere Zugriffsebenen \(z. B. "protected"\) zu deklarieren, können Sie auf eine Abhängigkeitseigenschaft immer zugreifen, indem Sie den Bezeichner in Verbindung mit den [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] des Eigenschaftensystems verwenden.  Es kann ggf. sogar auf ein geschütztes Bezeichnerfeld zugegriffen werden, weil [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Berichten von Metadaten oder zur Wertermittlung Teil des Eigenschaftensystems sind, z. B. <xref:System.Windows.LocalValueEnumerator>.  Weitere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
<a name="DPCtor"></a>   
## Abhängigkeitseigenschaften und Klassenkonstruktoren  
 Bei der Programmierung von verwaltetem Code gilt der allgemeine Grundsatz, dass Klassenkonstruktoren keine virtuellen Methoden aufrufen sollten \(wird häufig mithilfe von Codeanalysetools erzwungen, z. B. FxCop\).  Der Grund ist, dass Konstruktoren als Basisinitialisierung eines abgeleiteten Klassenkonstruktors aufgerufen werden können, und das Eingeben der virtuellen Methode über den Konstruktor könnte zu einem Zeitpunkt erfolgen, zu dem das erstellte Objekte einen unvollständigen Initialisierungszustand aufweist.  Wenn Sie eine Ableitung von einer Klasse durchführen, die bereits von <xref:System.Windows.DependencyObject> abgeleitet ist, sollten Sie bedenken, dass das Eigenschaftensystem intern selbst virtuelle Methoden aufruft und offenlegt.  Diese virtuellen Methoden sind Teil der Dienste des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystems.  Das Überschreiben der Methoden ermöglicht es, dass abgeleitete Klassen an der Wertermittlung teilnehmen.  Um mögliche Probleme mit der Laufzeitinitialisierung zu vermeiden, sollten Sie in Konstruktoren von Klassen keine Werte von Abhängigkeitseigenschaften festlegen, es sei denn, Sie wenden ein spezielles Konstruktormuster an.  Weitere Informationen finden Sie unter [Sichere Konstruktormuster für DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md).  
  
## Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Abhängigkeitseigenschaften vom Auflistungstyp](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)   
 [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md)   
 [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)   
 [Sichere Konstruktormuster für DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)