---
title: Framework-Eigenschaftenmetadaten
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: c08cf28880d86331e3b561f1749333d401ba903e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964214"
---
# <a name="framework-property-metadata"></a>Framework-Eigenschaftenmetadaten
Die Optionen für Framework-Eigenschaftenmetadaten werden für die Eigenschaften von Objektelementen gemeldet, die in der WPF-Frameworkebene in der Architektur [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vorhanden sein sollen. Im allgemeinen umfasst die Bezeichnung auf der WPF-Frameworkebene, dass Features wie Rendering, Datenbindung und Eigenschafts Systemoptimierungen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den Präsentations-APIs und ausführbaren Dateien behandelt werden. Framework-Eigenschaftenmetadaten werden von diesen Systemen zur Ermittlung funktionsspezifischer Merkmale von bestimmten Elementeigenschaften abgefragt.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen verstehen und die [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Folgenden Artikel sollten Sie auch gelesen haben: [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Was wird von Framework-Eigenschaftenmetadaten übermittelt?  
 Framework-Eigenschaftenmetadaten können in folgende Kategorien unterteilt werden:  
  
- Berichtslayouteigenschaften,<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>die <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>sich <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>auf ein Element (,,) auswirken Sie können diese Flags in den Metadaten festlegen, wenn sich die-Eigenschaft auf die jeweiligen Aspekte auswirkt, und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Sie implementieren auch die  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden in der Klasse, um ein bestimmtes Renderingverhalten und Informationen für das Layout bereitzustellen. Anlage. In der Regel würde eine solche Implementierung nach Eigenschafteninvalidierungen in Abhängigkeitseigenschaften suchen, wo die Layouteigenschaften in den Eigenschaftenmetadaten wahr waren. Nur diese Validierungen würde einen neuen Layoutdurchlauf erforderlich machen.  
  
- Berichtslayouteigenschaften, die sich auf das<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>über <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>geordnete Element eines Elements (,) auswirken. Einige Beispiele, in denen diese Flags standardmäßig fest <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> gelegt <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>werden, sind und.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> Standardmäßig erben Abhängigkeitseigenschaften keine Werte. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>ermöglicht dem Weg der Vererbung auch, in eine visuelle Struktur zu wechseln, die für einige Szenarios zur Steuerung der Zusammensetzung notwendig ist.  
  
    > [!NOTE]
    > Im Kontext mit Eigenschaftswerten bedeutet der Begriff „erbt“ für Abhängigkeitseigenschaften etwas Bestimmtes. Das bedeutet, dass untergeordnete Elemente den tatsächlichen Abhängigkeitseigenschaftswert von übergeordneten Elementen erben können, aufgrund einer Funktion der WPF-Frameworkebene des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems. Dies hat nichts mit verwaltetem Codetypen und Vererbung der Member über abgeleitete Typen zu tun. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).  
  
- Eigenschaften von Berichtsdaten Bindungen<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>( <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>,). Standardmäßig unterstützen Abhängigkeitseigenschaften im Framework die Datenbindung mit einem unidirektionalen Bindungsverhalten. Sie können die Datenbindung deaktivieren, wenn überhaupt kein Szenario vorhanden wäre (da Sie flexibel und erweiterbar sein sollen, gibt es in den Standard [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -APIs keine vielen Beispiele solcher Eigenschaften). Sie können die Bindung auf einen bidirektionalen Standard für Eigenschaften festlegen, die das Verhalten eines Steuer Elements zwischen den Komponenten teilen<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> (ist ein Beispiel) oder die bidirektionale Bindung das gängige und erwartete Szenario für Benutzer<xref:System.Windows.Controls.TextBox.Text%2A> (ist ein Beispiel). Das Ändern der auf die Datenbindung bezogenen Metadaten beeinflusst nur den Standardwert. Bei einer Basis pro Bindung kann dieser Standardwert immer geändert werden. Weitere Informationen zu den Bindungsmodi und zur Bindung im Allgemeinen finden Sie unter [Übersicht zur Datenbindung](../data/data-binding-overview.md).  
  
- Es wird gemeldet, ob Eigenschaften von Anwendungen oder Diensten, die Journal Unterstützung (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>) unterstützen, erfasst werden sollen. Für allgemeine Elemente ist Journaling nicht standardmäßig aktiviert, aber es ist selektiv für bestimmte Benutzereingabe-Steuerelemente aktiviert. Diese Eigenschaft soll von Journaling-Diensten gelesen werden, einschließlich der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung von Journaling, und wird in der Regel auf Benutzersteuerelemente festgelegt, z.B. Auswahlmöglichkeiten des Benutzers in Listen, die über Navigationsschritte hinweg beibehalten werden soll. Informationen zur Erfassung finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Lesen von FrameworkPropertyMetadata  
 Jede der oben verknüpften Eigenschaften sind die spezifischen Eigenschaften, die <xref:System.Windows.FrameworkPropertyMetadata> von der unmittelbaren Basisklasse <xref:System.Windows.UIPropertyMetadata>hinzugefügt werden. Jede dieser Eigenschaften wird standardmäßig `false` sein. Eine metadatenanforderung für eine Eigenschaft, bei der das Wissen des Werts dieser Eigenschaften wichtig ist, sollte versuchen, die <xref:System.Windows.FrameworkPropertyMetadata>zurückgegebenen Metadaten in umzuwandeln und dann die Werte der einzelnen Eigenschaften nach Bedarf zu überprüfen.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Angeben von Metadaten  
 Beim Erstellen einer neuen Metadateninstanz für das Anwenden von Metadaten auf eine neue Registrierung der Abhängigkeits Eigenschaft können Sie auswählen, welche Metadatenklasse verwendet werden soll: <xref:System.Windows.PropertyMetadata> die Basisklasse oder eine abgeleitete Klasse, <xref:System.Windows.FrameworkPropertyMetadata>z. b. Im Allgemeinen sollten Sie verwenden <xref:System.Windows.FrameworkPropertyMetadata>, insbesondere wenn Ihre Eigenschaft eine Interaktion mit dem Eigenschaften System und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionen wie Layout und Datenbindung aufweist. Eine weitere Option für anspruchsvollere Szenarien ist das ableiten <xref:System.Windows.FrameworkPropertyMetadata> von, um eine eigene metadatenberichterstattungs Klasse mit zusätzlichen Informationen zu erstellen, die in ihren Membern übernommen werden. Oder Sie können oder <xref:System.Windows.PropertyMetadata> <xref:System.Windows.UIPropertyMetadata> verwenden, um den Grad der Unterstützung für Features Ihrer Implementierung zu übermitteln.  
  
 Für vorhandene Eigenschaften (<xref:System.Windows.DependencyProperty.AddOwner%2A> oder <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> den-Befehl) sollten Sie immer mit dem von der ursprünglichen Registrierung verwendeten Metadatentyp überschreiben.  
  
 Wenn Sie eine <xref:System.Windows.FrameworkPropertyMetadata> -Instanz erstellen, gibt es zwei Möglichkeiten, diese Metadaten mit Werten für die spezifischen Eigenschaften aufzufüllen, die die Eigenschaften der frameworkeigenschaft übermitteln:  
  
1. Verwenden Sie <xref:System.Windows.FrameworkPropertyMetadata> die Konstruktorsignatur, die `flags` einen Parameter zulässt. Dieser Parameter sollte mit allen gewünschten kombinierten Werten der <xref:System.Windows.FrameworkPropertyMetadataOptions> Enumerationsflags ausgefüllt werden.  
  
2. Verwenden Sie eine der Signaturen ohne einen `flags` -Parameter, und legen Sie `true` dann jede berichtsboolesche Eigenschaft für jede gewünschte Merkmals Änderung auf <xref:System.Windows.FrameworkPropertyMetadata> fest. Wenn Sie dies tun, müssen Sie diese Eigenschaften festlegen, bevor Elemente mit dieser Abhängigkeitseigenschaft erstellt werden. Die booleschen Eigenschaften verfügen über Lese-/Schreibzugriff, um dieses Verhalten zur Vermeidung des `flags`-Parameters zu ermöglichen und trotzdem die Metadaten zu füllen, aber die Metadaten müssen vor der Verwendung der Eigenschaft effektiv versiegelt werden. Daher wird der Versuch, Eigenschaften nach der Anforderung von Metadaten festzulegen, ein ungültiger Vorgang sein.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Zusammenführungsverhalten von Framework-Eigenschaftenmetadaten  
 Wenn Sie Framework-Eigenschaftenmetadaten überschreiben, werden die verschiedenen Metadaten-Eigenschaften entweder zusammengeführt oder ersetzt.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>wird zusammengeführt. Wenn Sie einen neuen <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>hinzufügen, wird dieser Rückruf in den Metadaten gespeichert. Wenn Sie <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in der Überschreibung keine angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> als Verweis vom nächstgelegenen Vorgänger herauf gestuft, der ihn in den Metadaten angegeben hat.  
  
- Das tatsächliche Eigenschaften Systemverhalten für <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> besteht darin, dass Implementierungen für alle metadatenbesitzer in der Hierarchie beibehalten und einer Tabelle hinzugefügt werden, wobei die Ausführungsreihenfolge des Eigenschaften Systems darin besteht, dass die Rückrufe der am stärksten abgeleiteten Klasse wird zuerst aufgerufen. Geerbte Rückrufe werden nur einmal ausgeführt und gelten als im Besitz der Klasse, die sie in den Metadaten gespeichert hat.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>wird ersetzt. Wenn Sie <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in der Überschreibung keine angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.DefaultValue%2A> vom nächstgelegenen Vorgänger, der ihn in den Metadaten angegeben hat, empfangen.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>Implementierungen werden ersetzt. Wenn Sie einen neuen <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>hinzufügen, wird dieser Rückruf in den Metadaten gespeichert. Wenn Sie <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in der Überschreibung keine angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> als Verweis vom nächstgelegenen Vorgänger herauf gestuft, der ihn in den Metadaten angegeben hat.  
  
- Das Verhalten des Eigenschaften Systems besteht darin, <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> dass nur das in den unmittelbaren Metadaten aufgerufen wird. Es werden keine Verweise <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> auf andere Implementierungen in der Hierarchie beibehalten.  
  
- Die Flags der <xref:System.Windows.FrameworkPropertyMetadataOptions> Enumeration werden als bitweise OR-Operation kombiniert.  Wenn Sie angeben <xref:System.Windows.FrameworkPropertyMetadataOptions>, werden die ursprünglichen Optionen nicht überschrieben.  Um eine Option zu ändern, legen Sie die entsprechende <xref:System.Windows.FrameworkPropertyMetadata>-Eigenschaft für fest. Wenn das- <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> Flag beispielsweise <xref:System.Windows.FrameworkPropertyMetadata> durch das ursprüngliche-Objekt festgelegt wird, können Sie dies `false`ändern, indem Sie auf festlegen <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> .  
  
 Dieses Verhalten wird von <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>implementiert und kann für abgeleitete Metadatenklassen überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
