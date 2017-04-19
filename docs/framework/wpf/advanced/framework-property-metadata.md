---
title: "Framework-Eigenschaftenmetadaten | Microsoft Docs"
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
  - "Framework-Eigenschaftenmetadaten"
  - "Metadaten, Framework-Eigenschaften"
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Framework-Eigenschaftenmetadaten
Framework\-Eigenschaftenmetadaten werden für die Eigenschaften von Objektelementen berichtet, die sich auf der [WPF\-Frameworkebene](GTMT) der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Architektur befinden.  Normalerweise führt die Bezeichnung [WPF\-Frameworkebene](GTMT) dazu, dass Funktionen wie Rendering, Datenbindung und Anpassungen des Eigenschaftensystems von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Präsentations\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] und den entsprechenden ausführbaren Dateien verarbeitet werden.  Framework\-Eigenschaftenmetadaten werden von diesen Systemen abgefragt, um funktionsspezifische Merkmale bestimmter Elementeigenschaften zu ermitteln.  
  
   
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit [Abhängigkeitseigenschaften](GTMT) aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften über [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Klassen auskennen und dass Sie die [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben.  Sie sollten außerdem den Abschnitt [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md) gelesen haben.  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## Was wird von den Framework\-Eigenschaftenmetadaten übermittelt?  
 Framework\-Eigenschaftenmetadaten können in die folgenden Kategorien unterteilt werden:  
  
-   Berichten von Layouteigenschaften, die sich auf ein Element auswirken \(<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>\).  Sie können diese Flags bei Bedarf in den Metadaten setzen, wenn sich die Eigenschaft auf diese Aspekte auswirkt und wenn Sie außerdem die Methoden <xref:System.Windows.FrameworkElement.MeasureOverride%2A> \/ <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> in Ihrer Klasse implementieren, um für das Layoutsystem ein bestimmtes Renderingverhalten und entsprechende Informationen bereitzustellen.  Normalerweise führt eine Implementierung dieser Art eine Prüfung auf Ungültigkeitserklärungen von Eigenschaften in Abhängigkeitseigenschaften durch, für die beliebige dieser Layouteigenschaften in den Eigenschaftenmetadaten wahr sind. Nur diese Ungültigkeiten erfordern dann die Anforderung eines neuen Layoutdurchlaufs.  
  
-   Melden von Layouteigenschaften, die sich auf das übergeordnete Element eines Elements auswirken \(<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>\).  Beispiele für Fälle, in denen diese Flags standardmäßig festgelegt sind, sind <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=fullName> und <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=fullName>.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>.  Standardmäßig werden von Abhängigkeitseigenschaften keine Werte geerbt.  Mithilfe von <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> kann der Kommunikationsweg der Vererbung auch durch eine visuelle Struktur verlaufen. Dies ist für einige Szenarien der Steuerelementzusammenstellung erforderlich.  
  
    > [!NOTE]
    >  Der Ausdruck "erben" hat im Zusammenhang mit Eigenschaftswerten für Abhängigkeitseigenschaften eine besondere Bedeutung. Er bedeutet, dass untergeordnete Elemente von übergeordneten Elementen den Wert der Abhängigkeitseigenschaft erben können. Dies ist mithilfe einer Funktion der [WPF\-Frameworkebene](GTMT) des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystems möglich.  Dabei besteht kein direkter Zusammenhang mit verwalteten Codetypen und mit der Membervererbung über abgeleitete Typen.  Ausführliche Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Berichten von Datenbindungsmerkmalen \(<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>\).  Standardmäßig handelt es sich um Abhängigkeitseigenschaften in der Frameworkunterstützungs\-Datenbindung mit einem unidirektionalen Bindungsverhalten.  Sie könnten die Datenbindung deaktivieren, wenn dafür kein Szenario vorhanden wäre \(da diese Elemente flexibel und erweiterbar gestaltet sind, enthält die standardmäßige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] nicht viele Beispiele hierfür\).  Sie können die Bindung so einrichten, dass sie einen bidirektionalen Standard für Eigenschaften verwendet, die die Verhalten eines Steuerelements mithilfe seiner Komponententeile zusammenhalten \(Beispiel: <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>\), oder dass die bidirektionale Bindung das gängige und erwartete Szenario für Benutzer ist \(Beispiel: <xref:System.Windows.Controls.TextBox.Text%2A>\).  Eine Änderung der für die Datenbindung relevanten Metadaten wirkt sich nur auf die Standardeinstellung aus. Diese Standardeinstellung kann pro Bindung jeweils individuell geändert werden.  Ausführliche Informationen zu den Bindungsmodi und zur Bindung im Allgemeinen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Berichten, ob Eigenschaften von Anwendungen oder Diensten in ein Journal eingetragen werden sollten, die diese Funktion unterstützen \(<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>\).  Für allgemeine Elemente ist die Journalfunktion standardmäßig nicht aktiviert, aber sie kann für bestimmte Benutzereingabe\-Steuerelemente bedarfsabhängig aktiviert werden.  Diese Eigenschaft soll von Journaldiensten gelesen werden, einschließlich der entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Implementierung, und wird in der Regel für Benutzersteuerelemente eingerichtet, z. B. Auswahlmöglichkeiten in Listen, die über mehrere Navigationsschritte hinweg beibehalten werden sollen.  Informationen zum Journal finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## Lesen von FrameworkPropertyMetadata  
 Bei allen oben mit Link angegebenen Eigenschaften handelt es sich um die spezifischen Eigenschaften, die die <xref:System.Windows.FrameworkPropertyMetadata> den direkten Basisklassen\-<xref:System.Windows.UIPropertyMetadata> hinzufügt.  Jede dieser Eigenschaften ist standardmäßig `false`.  Eine Metadatenanforderung für eine Eigenschaft, bei der es wichtig ist, dass der Wert dieser Eigenschaften bekannt ist, sollte versuchen, die zurückgegebenen Metadaten in <xref:System.Windows.FrameworkPropertyMetadata> umzuwandeln. Anschließend sollten je nach Bedarf die Werte der einzelnen Eigenschaften überprüft werden.  
  
<a name="Specifying_Metadata"></a>   
## Angeben von Metadaten  
 Wenn Sie eine neue Metadateninstanz erstellen, um Metadaten auf eine neue Registrierung einer Abhängigkeitseigenschaft anzuwenden, können Sie wählen, welche Metadatenklasse Sie verwenden: die <xref:System.Windows.PropertyMetadata>\-Basisversion oder eine abgeleitete Klasse wie <xref:System.Windows.FrameworkPropertyMetadata>.  Im Normalfall sollten Sie <xref:System.Windows.FrameworkPropertyMetadata> verwenden, besonders dann, wenn Ihre Eigenschaft über eine Interaktion mit Eigenschaftensystem\- und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Funktionen verfügt, z. B. in Verbindung mit Layout und Datenbindung.  Eine weitere Möglichkeit für anspruchsvollere Szenarien ist die Ableitung von <xref:System.Windows.FrameworkPropertyMetadata>, um eine eigene Klasse zum Melden von Metadaten zu erstellen, wobei die Member über zusätzliche Informationen verfügen.  Sie können auch <xref:System.Windows.PropertyMetadata> oder <xref:System.Windows.UIPropertyMetadata> verwenden, um den Unterstützungsgrad für Funktionen Ihrer Implementierung zu kommunizieren.  
  
 Für vorhandene Eigenschaften \(<xref:System.Windows.DependencyProperty.AddOwner%2A>\- oder <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>\-Aufruf\) sollten Sie stets eine Überschreibung mit dem Metadatentyp durchführen, der von der ursprünglichen Registrierung verwendet wird.  
  
 Wenn Sie eine <xref:System.Windows.FrameworkPropertyMetadata>\-Instanz erstellen, haben Sie zwei Möglichkeiten, diese Metadaten mit Werten für die spezifischen Eigenschaften zu füllen, die die Framework\-Eigenschaftenmerkmale kommunizieren:  
  
1.  Verwenden Sie die <xref:System.Windows.FrameworkPropertyMetadata>\-Konstruktorsignatur, die einen `flags`\-Parameter zulässt.  Dieser Parameter sollte mit allen gewünschten kombinierten Werten der <xref:System.Windows.FrameworkPropertyMetadataOptions>\-Enumerationsflags gefüllt werden.  
  
2.  Verwenden Sie eine der Signaturen ohne `flags`\-Parameter, und setzen Sie dann alle berichtenden booleschen Eigenschaften unter <xref:System.Windows.FrameworkPropertyMetadata> für die einzelnen gewünschten Merkmalsänderungen auf `true`.  Wenn Sie dies durchführen, müssen Sie diese Eigenschaften festlegen, bevor Elemente mit dieser Abhängigkeitseigenschaft erstellt werden. Die booleschen Eigenschaften verfügen über Schreib\-\/Lesezugriff, damit dieses Verhalten die Verwendung des `flags`\-Parameters vermeiden, die Metadaten jedoch trotzdem füllen kann. Die Metadaten müssen vor der Verwendung der Eigenschaften jedoch richtig versiegelt werden.  Der Versuch, die Eigenschaften festzulegen, nachdem die Metadaten angefordert wurden, ist somit ein ungültiger Vorgang.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## Zusammenführungsverhalten von Framework\-Eigenschaftenmetadaten  
 Wenn Sie Framework\-Eigenschaftenmetadaten überschreiben, werden die einzelnen Metadatenmerkmale entweder zusammengeführt oder ersetzt.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> wird zusammengeführt.  Wenn Sie einen neuen <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> hinzufügen, wird dieser Rückruf in den Metadaten gespeichert.  Wenn Sie in der Überschreibung keinen <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> als Verweis des nächsten Vorgängers höher gestuft, der diesen in den Metadaten angegeben hat.  
  
-   Das eigentliche Verhalten des Eigenschaftensystems für <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> besteht darin, dass Implementierungen für alle Metadatenbesitzer in der Hierarchie beibehalten und der Tabelle hinzugefügt werden. Für das Eigenschaftensystem gilt die Ausführungsreihenfolge, dass Rückrufe der am stärksten abgeleiteten Klasse zuerst aufgerufen werden.  Geerbte Rückrufe werden nur einmal ausgeführt. Sie werden als Eigentum der Klasse angesehen, die sie in die Metadaten eingefügt hat.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A> wird ersetzt.  Wenn Sie in der Überschreibung keinen <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> angeben, stammt der Wert von <xref:System.Windows.PropertyMetadata.DefaultValue%2A> vom nächsten Vorgänger, der diesen in den Metadaten angegeben hat.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>\-Implementierungen werden ersetzt.  Wenn Sie einen neuen <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> hinzufügen, wird dieser Rückruf in den Metadaten gespeichert.  Wenn Sie in der Überschreibung keinen <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> als Verweis des nächsten Vorgängers höher gestuft, der diesen in den Metadaten angegeben hat.  
  
-   Das Verhalten des Eigenschaftensystems besteht darin, dass nur der <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in den unmittelbaren Metadaten aufgerufen wird.  Es werden keine Verweise auf andere <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>\-Implementierungen in der Hierarchie beibehalten.  
  
-   Die Flags der <xref:System.Windows.FrameworkPropertyMetadataOptions>\-Enumeration werden als bitweise OR\-Operation kombiniert.  Bei Angabe von <xref:System.Windows.FrameworkPropertyMetadataOptions> werden die ursprünglichen Optionen nicht überschrieben.  Legen Sie zum Ändern einer Option die entsprechende Eigenschaft auf <xref:System.Windows.FrameworkPropertyMetadata> fest.  Wird beispielsweise vom ursprünglichen <xref:System.Windows.FrameworkPropertyMetadata>\-Objekt das <xref:System.Windows.FrameworkPropertyMetadataOptions?displayProperty=fullName>\-Flag festlegt, können Sie dies ändern, indem Sie <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=fullName> auf `false` festlegen.  
  
 Dieses Verhalten wird von <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A> implementiert und kann für abgeleitete Metadatenklassen überschrieben werden.  
  
## Siehe auch  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>   
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)