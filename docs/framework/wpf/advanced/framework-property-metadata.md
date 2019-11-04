---
title: Framework-Eigenschaftenmetadaten
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 3e40dfbcbe88f424337ee5a32fb3e3aaaddd68d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460462"
---
# <a name="framework-property-metadata"></a>Framework-Eigenschaftenmetadaten
Die Optionen für Framework-Eigenschaftenmetadaten werden für die Eigenschaften von Objektelementen gemeldet, die in der WPF-Frameworkebene in der Architektur [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vorhanden sein sollen. Im allgemeinen umfasst die Bezeichnung auf der WPF-Frameworkebene, dass Features wie Rendering, Datenbindung und Eigenschafts Systemoptimierungen von den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Präsentations-APIs und ausführbaren Dateien behandelt werden. Framework-Eigenschaftenmetadaten werden von diesen Systemen zur Ermittlung funktionsspezifischer Merkmale von bestimmten Elementeigenschaften abgefragt.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Voraussetzungen  
 Dieses Thema setzt voraus, dass Sie Abhängigkeitseigenschaften vorhandener Abhängigkeitseigenschaften von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen aus Sicht eines Kunden verstehen und die [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Folgenden Artikel sollten Sie auch gelesen haben: [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Was wird von Framework-Eigenschaftenmetadaten übermittelt?  
 Framework-Eigenschaftenmetadaten können in folgende Kategorien unterteilt werden:  
  
- Berichtslayouteigenschaften, die sich auf ein Element (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>) auswirken. Sie können diese Flags in den Metadaten festlegen, wenn sich die-Eigenschaft auf die jeweiligen Aspekte auswirkt, und Sie implementieren auch die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> / <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>-Methoden in der-Klasse, um dem Layoutsystem ein bestimmtes Renderingverhalten und Informationen bereitzustellen. In der Regel würde eine solche Implementierung nach Eigenschafteninvalidierungen in Abhängigkeitseigenschaften suchen, wo die Layouteigenschaften in den Eigenschaftenmetadaten wahr waren. Nur diese Validierungen würde einen neuen Layoutdurchlauf erforderlich machen.  
  
- Berichtslayouteigenschaften, die sich auf das übergeordnete Element eines Elements (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A><xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>) auswirken. Einige Beispiele, in denen diese Flags standardmäßig festgelegt werden, sind <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> und <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> Standardmäßig erben Abhängigkeitseigenschaften keine Werte. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> ermöglicht es, dass der Vererbungs Weg auch in eine visuelle Struktur übertragen wird, die für einige Szenarios zur Steuerung der Zusammensetzung notwendig ist.  
  
    > [!NOTE]
    > Im Kontext mit Eigenschaftswerten bedeutet der Begriff „erbt“ für Abhängigkeitseigenschaften etwas Bestimmtes. Das bedeutet, dass untergeordnete Elemente den tatsächlichen Abhängigkeitseigenschaftswert von übergeordneten Elementen erben können, aufgrund einer Funktion der WPF-Frameworkebene des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems. Dies hat nichts mit verwaltetem Codetypen und Vererbung der Member über abgeleitete Typen zu tun. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).  
  
- Eigenschaften der Berichtsdaten Bindung (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A><xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). Standardmäßig unterstützen Abhängigkeitseigenschaften im Framework die Datenbindung mit einem unidirektionalen Bindungsverhalten. Sie können die Datenbindung deaktivieren, wenn überhaupt kein Szenario vorhanden wäre (da Sie flexibel und erweiterbar sein sollen, gibt es in den standardmäßigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs nicht viele Beispiele solcher Eigenschaften). Sie können die Bindung so festlegen, dass Sie eine bidirektionale Standardeinstellung für Eigenschaften hat, die das Verhalten eines Steuer Elements zwischen den Komponenten teilen (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> ist ein Beispiel) oder die bidirektionale Bindung das gängige und erwartete Szenario für Benutzer (<xref:System.Windows.Controls.TextBox.Text%2A> ist ein Beispiel). Das Ändern der auf die Datenbindung bezogenen Metadaten beeinflusst nur den Standardwert. Bei einer Basis pro Bindung kann dieser Standardwert immer geändert werden. Weitere Informationen zu den Bindungsmodi und zur Bindung im Allgemeinen finden Sie unter [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Es wird gemeldet, ob Eigenschaften von Anwendungen oder Diensten, die Journal Unterstützung unterstützen (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>), erfasst werden sollen. Für allgemeine Elemente ist Journaling nicht standardmäßig aktiviert, aber es ist selektiv für bestimmte Benutzereingabe-Steuerelemente aktiviert. Diese Eigenschaft soll von Journaling-Diensten gelesen werden, einschließlich der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung von Journaling, und wird in der Regel auf Benutzersteuerelemente festgelegt, z.B. Auswahlmöglichkeiten des Benutzers in Listen, die über Navigationsschritte hinweg beibehalten werden soll. Informationen zur Erfassung finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Lesen von FrameworkPropertyMetadata  
 Jede der oben verknüpften Eigenschaften sind die spezifischen Eigenschaften, die der <xref:System.Windows.FrameworkPropertyMetadata> seiner unmittelbaren Basisklasse <xref:System.Windows.UIPropertyMetadata>hinzufügt. Jede dieser Eigenschaften wird standardmäßig `false` sein. Eine metadatenanforderung für eine Eigenschaft, bei der das Wissen des Werts dieser Eigenschaften wichtig ist, sollte versuchen, die zurückgegebenen Metadaten in <xref:System.Windows.FrameworkPropertyMetadata>umzuwandeln und dann die Werte der einzelnen Eigenschaften nach Bedarf zu überprüfen.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Angeben von Metadaten  
 Beim Erstellen einer neuen Metadateninstanz zum Anwenden von Metadaten auf eine neue Registrierung der Abhängigkeits Eigenschaft haben Sie die Wahl, welche Metadatenklasse verwendet werden soll: die Basis <xref:System.Windows.PropertyMetadata> oder eine abgeleitete Klasse, z. b. <xref:System.Windows.FrameworkPropertyMetadata>. Im Allgemeinen sollten Sie <xref:System.Windows.FrameworkPropertyMetadata>verwenden, insbesondere dann, wenn Ihre Eigenschaft eine Interaktion mit Eigenschaften System-und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionen wie Layout und Datenbindung hat. Eine weitere Option für anspruchsvollere Szenarien ist die Ableitung von <xref:System.Windows.FrameworkPropertyMetadata>, um eine eigene metadatenberichterstattungs Klasse mit zusätzlichen Informationen zu erstellen, die in ihren Membern übernommen werden. Sie können auch <xref:System.Windows.PropertyMetadata> oder <xref:System.Windows.UIPropertyMetadata> verwenden, um den Grad der Unterstützung für Features Ihrer Implementierung zu übermitteln.  
  
 Für vorhandene Eigenschaften (<xref:System.Windows.DependencyProperty.AddOwner%2A> oder <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>-Aufrufvorgang) sollten Sie immer mit dem von der ursprünglichen Registrierung verwendeten Metadatentyp überschreiben.  
  
 Wenn Sie eine <xref:System.Windows.FrameworkPropertyMetadata>-Instanz erstellen, gibt es zwei Möglichkeiten, diese Metadaten mit Werten für die spezifischen Eigenschaften aufzufüllen, die die Eigenschaften der frameworkeigenschaft übermitteln:  
  
1. Verwenden Sie die <xref:System.Windows.FrameworkPropertyMetadata>-Konstruktorsignatur, die einen `flags`-Parameter zulässt. Dieser Parameter sollte mit allen gewünschten kombinierten Werten der <xref:System.Windows.FrameworkPropertyMetadataOptions> Enumerationsflags ausgefüllt werden.  
  
2. Verwenden Sie eine der Signaturen ohne einen `flags`-Parameter, und legen Sie dann jede boolesche Eigenschaft für Berichte auf <xref:System.Windows.FrameworkPropertyMetadata> auf `true` für jede gewünschte Merkmals Änderung fest. Wenn Sie dies tun, müssen Sie diese Eigenschaften festlegen, bevor Elemente mit dieser Abhängigkeitseigenschaft erstellt werden. Die booleschen Eigenschaften verfügen über Lese-/Schreibzugriff, um dieses Verhalten zur Vermeidung des `flags`-Parameters zu ermöglichen und trotzdem die Metadaten zu füllen, aber die Metadaten müssen vor der Verwendung der Eigenschaft effektiv versiegelt werden. Daher wird der Versuch, Eigenschaften nach der Anforderung von Metadaten festzulegen, ein ungültiger Vorgang sein.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Zusammenführungsverhalten von Framework-Eigenschaftenmetadaten  
 Wenn Sie Framework-Eigenschaftenmetadaten überschreiben, werden die verschiedenen Metadaten-Eigenschaften entweder zusammengeführt oder ersetzt.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> wird zusammengeführt. Wenn Sie einen neuen <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>hinzufügen, wird dieser Rückruf in den Metadaten gespeichert. Wenn Sie keine <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in der Überschreibung angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> als Verweis vom nächstgelegenen Vorgänger herauf gestuft, der ihn in den Metadaten angegeben hat.  
  
- Das tatsächliche Eigenschaften Systemverhalten für <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> besteht darin, dass Implementierungen für alle metadatenbesitzer in der Hierarchie beibehalten und einer Tabelle hinzugefügt werden, wobei die Ausführungsreihenfolge des Eigenschaften Systems darin besteht, dass die Rückrufe der am stärksten abgeleiteten Klasse aufgerufen werden. erstes. Geerbte Rückrufe werden nur einmal ausgeführt und gelten als im Besitz der Klasse, die sie in den Metadaten gespeichert hat.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A> wird ersetzt. Wenn Sie keine <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in der Überschreibung angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.DefaultValue%2A> vom nächstgelegenen Vorgänger, der ihn in den Metadaten angegeben hat, empfangen.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>-Implementierungen werden ersetzt. Wenn Sie einen neuen <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>hinzufügen, wird dieser Rückruf in den Metadaten gespeichert. Wenn Sie keine <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in der Überschreibung angeben, wird der Wert von <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> als Verweis vom nächstgelegenen Vorgänger herauf gestuft, der ihn in den Metadaten angegeben hat.  
  
- Das Verhalten des Eigenschaften Systems besteht darin, dass nur die <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in den unmittelbaren Metadaten aufgerufen wird. Es werden keine Verweise auf andere <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> Implementierungen in der Hierarchie beibehalten.  
  
- Die Flags <xref:System.Windows.FrameworkPropertyMetadataOptions> Enumeration werden als bitweise OR-Operation kombiniert.  Wenn Sie <xref:System.Windows.FrameworkPropertyMetadataOptions>angeben, werden die ursprünglichen Optionen nicht überschrieben.  Um eine Option zu ändern, legen Sie die entsprechende Eigenschaft für <xref:System.Windows.FrameworkPropertyMetadata>fest. Wenn beispielsweise das ursprüngliche <xref:System.Windows.FrameworkPropertyMetadata> Objekt das <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType>-Flag festlegt, können Sie dies ändern, indem Sie <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> auf `false`festlegen.  
  
 Dieses Verhalten wird von <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>implementiert und kann für abgeleitete Metadatenklassen überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
