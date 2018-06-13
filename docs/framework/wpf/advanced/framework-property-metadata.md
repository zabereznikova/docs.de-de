---
title: Framework-Eigenschaftenmetadaten
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: d968bc7a3033bd994590520c5cd5062d3c212b4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547461"
---
# <a name="framework-property-metadata"></a>Framework-Eigenschaftenmetadaten
Die Optionen für Framework-Eigenschaftenmetadaten werden für die Eigenschaften von Objektelementen gemeldet, die in der WPF-Frameworkebene in der Architektur [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vorhanden sein sollen. Im Allgemeinen bedeutet die Bezeichnung WPF-Frameworkebene, dass Funktionen wie das Rendering, die Datenbindung und die Verbesserungen des Eigenschaftensystems von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Präsentations-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] und von ausführbaren Dateien behandelt werden. Framework-Eigenschaftenmetadaten werden von diesen Systemen zur Ermittlung funktionsspezifischer Merkmale von bestimmten Elementeigenschaften abgefragt.  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen verstehen und die [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben. Folgenden Artikel sollten Sie auch gelesen haben: [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Was wird von Framework-Eigenschaftenmetadaten übermittelt?  
 Framework-Eigenschaftenmetadaten können in folgende Kategorien unterteilt werden:  
  
-   Layouteigenschaften, die ein Element betreffen Reporting (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). Diese Flags möglicherweise in den Metadaten festgelegt werden, wenn die Eigenschaft wirkt sich auf die jeweiligen Aspekte und Sie außerdem implementieren die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden in Ihrer Klasse, um spezifische Renderingverhalten und Informationen zum Layout angeben System. In der Regel würde eine solche Implementierung nach Eigenschafteninvalidierungen in Abhängigkeitseigenschaften suchen, wo die Layouteigenschaften in den Eigenschaftenmetadaten wahr waren. Nur diese Validierungen würde einen neuen Layoutdurchlauf erforderlich machen.  
  
-   Layouteigenschaften, die das übergeordnete Element eines Elements betreffen Reporting (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). Einige Beispiele, in dem diese Flags, in der Standardeinstellung festgelegt sind, sind <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> und <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> Standardmäßig erben Abhängigkeitseigenschaften keine Werte. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> ermöglicht den Weg der Vererbung auch in einer visuellen Struktur zu übertragen, der für einige Compositing Steuerelementszenarien erforderlich ist.  
  
    > [!NOTE]
    >  Im Kontext mit Eigenschaftswerten bedeutet der Begriff „erbt“ für Abhängigkeitseigenschaften etwas Bestimmtes. Das bedeutet, dass untergeordnete Elemente den tatsächlichen Abhängigkeitseigenschaftswert von übergeordneten Elementen erben können, aufgrund einer Funktion der WPF-Frameworkebene des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems. Dies hat nichts mit verwaltetem Codetypen und Vererbung der Member über abgeleitete Typen zu tun. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Bindung von Dateneigenschaften Reporting (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). Standardmäßig unterstützen Abhängigkeitseigenschaften im Framework die Datenbindung mit einem unidirektionalen Bindungsverhalten. Sie können möglicherweise die Datenbindung deaktivieren, wenn es dafür überhaupt kein Szenario gäbe (da sie flexibel und erweiterbar vorgesehen sind, sind nicht viele Beispiele für solche Eigenschaften in den standardmäßigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]). Möglicherweise legen Sie die Bindung an einen bidirektionalen Standard für Eigenschaften verfügen, die ein Steuerelement Verhalten seiner Komponententeile zu verbinden (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> ist ein Beispiel für) oder, wenn bidirektionale Bindung ist im Allgemeinen und erwartete Szenario für Benutzer (<xref:System.Windows.Controls.TextBox.Text%2A> ist ein Beispiel). Das Ändern der auf die Datenbindung bezogenen Metadaten beeinflusst nur den Standardwert. Bei einer Basis pro Bindung kann dieser Standardwert immer geändert werden. Weitere Informationen zu den Bindungsmodi und zur Bindung im Allgemeinen finden Sie unter [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Reporting, ob die Eigenschaften von Anwendungen oder Dienste, die Journaling unterstützen in Journalen werden soll (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>). Für allgemeine Elemente ist Journaling nicht standardmäßig aktiviert, aber es ist selektiv für bestimmte Benutzereingabe-Steuerelemente aktiviert. Diese Eigenschaft soll von Journaling-Diensten gelesen werden, einschließlich der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung von Journaling, und wird in der Regel auf Benutzersteuerelemente festgelegt, z.B. Auswahlmöglichkeiten des Benutzers in Listen, die über Navigationsschritte hinweg beibehalten werden soll. Informationen zur Erfassung finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Lesen von FrameworkPropertyMetadata  
 Jede Eigenschaft, die weiter oben Bezug genommen handelt es sich um die spezifischen Eigenschaften, die die <xref:System.Windows.FrameworkPropertyMetadata> hinzugefügt, dessen sofortige Basisklasse <xref:System.Windows.UIPropertyMetadata>. Jede dieser Eigenschaften wird standardmäßig `false` sein. Eine Metadatenanforderung für eine Eigenschaft, in dem wichtig den Wert dieser Eigenschaften kennen ist, sollten, um die zurückgegebene Metadaten umzuwandeln versuchen <xref:System.Windows.FrameworkPropertyMetadata>, und überprüfen Sie dann die Werte der einzelnen Eigenschaften nach Bedarf.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Angeben von Metadaten  
 Wenn Sie eine neue Metadateninstanz für die Zwecke des Anwendens von Metadaten auf eine neue Registrierung der Abhängigkeitseigenschaft erstellen, stehen Ihnen die Auswahl des welche Metadatenklasse verwenden: die Basis <xref:System.Windows.PropertyMetadata> oder eine abgeleitete Klasse wie z. B. <xref:System.Windows.FrameworkPropertyMetadata>. Sie sollten im Allgemeinen verwenden <xref:System.Windows.FrameworkPropertyMetadata>, insbesondere, wenn Ihre Eigenschaft jegliche Interaktion mit dem Eigenschaftensystem hat und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionen, z. B. Layout und die Datenbindung. Eine weitere Option für komplexere Szenarien ist die Ableitung <xref:System.Windows.FrameworkPropertyMetadata> berichterstattungsklasse mit zusätzlichen Informationen zum Erstellen eigener Metadaten in Membern durchgeführt. Oder Sie können <xref:System.Windows.PropertyMetadata> oder <xref:System.Windows.UIPropertyMetadata> den Grad der Unterstützung für Funktionen Ihrer Implementierung zu kommunizieren.  
  
 Für vorhandene Eigenschaften (<xref:System.Windows.DependencyProperty.AddOwner%2A> oder <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> aufrufen), sollten Sie immer mit dem Metadatentyp, der von der ursprünglichen Registrierung verwendet überschreiben.  
  
 Wenn Sie erstellen eine <xref:System.Windows.FrameworkPropertyMetadata> Instanz ist, es gibt zwei Möglichkeiten, die Metadaten mit Werten für die speziellen Eigenschaften aufzufüllen, die die Merkmale der Framework-Eigenschaft zu kommunizieren:  
  
1.  Verwenden der <xref:System.Windows.FrameworkPropertyMetadata> Signatur des Konstruktors, die ermöglicht eine `flags` Parameter. Dieser Parameter sollte mit allen gewünschten kombinierten Werten der ausgefüllt werden die <xref:System.Windows.FrameworkPropertyMetadataOptions> Enumerationsflags.  
  
2.  Verwenden einer der Signaturen ohne eine `flags` Parameter, und legen Sie dann jeweils die boolesche Eigenschaft auf reporting <xref:System.Windows.FrameworkPropertyMetadata> auf `true` für jedes Merkmal Änderung gewünscht. Wenn Sie dies tun, müssen Sie diese Eigenschaften festlegen, bevor Elemente mit dieser Abhängigkeitseigenschaft erstellt werden. Die booleschen Eigenschaften verfügen über Lese-/Schreibzugriff, um dieses Verhalten zur Vermeidung des `flags`-Parameters zu ermöglichen und trotzdem die Metadaten zu füllen, aber die Metadaten müssen vor der Verwendung der Eigenschaft effektiv versiegelt werden. Daher wird der Versuch, Eigenschaften nach der Anforderung von Metadaten festzulegen, ein ungültiger Vorgang sein.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Zusammenführungsverhalten von Framework-Eigenschaftenmetadaten  
 Wenn Sie Framework-Eigenschaftenmetadaten überschreiben, werden die verschiedenen Metadaten-Eigenschaften entweder zusammengeführt oder ersetzt.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> zusammengeführt wird. Wenn Sie ein neues hinzufügen <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, dieser Rückruf in den Metadaten gespeichert ist. Wenn Sie keinen angeben einer <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in Override "," den Wert des <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> wird höher gestuft, als Verweis aus den nächsten Vorgänger, der diesen in den Metadaten angegeben.  
  
-   Das Verhalten des tatsächlichen Eigenschaftstyp für <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> ist, dass Implementierungen mit der Reihenfolge der Ausführung von Eigenschaftenwerten, die Rückrufe der höchsten Schachtelungstiefe abgeleiteten Klasse wird für alle Metadaten-Besitzer in der Hierarchie werden beibehalten und eine Tabelle hinzugefügt werden zuerst aufgerufen. Geerbte Rückrufe werden nur einmal ausgeführt und gelten als im Besitz der Klasse, die sie in den Metadaten gespeichert hat.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A> wird ersetzt. Wenn Sie keinen angeben einer <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in Override "," den Wert des <xref:System.Windows.PropertyMetadata.DefaultValue%2A> stammen aus den nächsten Vorgänger, der diesen in den Metadaten angegeben.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> Implementierungen werden ersetzt. Wenn Sie ein neues hinzufügen <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, dieser Rückruf in den Metadaten gespeichert ist. Wenn Sie keinen angeben einer <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in Override "," den Wert des <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> wird höher gestuft, als Verweis aus den nächsten Vorgänger, der diesen in den Metadaten angegeben.  
  
-   Das Systemverhalten für die Eigenschaft ist, dass nur die <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in den unmittelbaren Metadaten aufgerufen wird. Keine Verweise auf andere <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> Implementierungen in der Hierarchie werden beibehalten.  
  
-   Die Flags <xref:System.Windows.FrameworkPropertyMetadataOptions> -Enumeration als eine bitweise OR-Operation kombiniert werden.  Bei Angabe von <xref:System.Windows.FrameworkPropertyMetadataOptions>, die ursprünglichen Optionen werden nicht überschrieben.  Um eine Option zu ändern, legen Sie die entsprechende Eigenschaft auf <xref:System.Windows.FrameworkPropertyMetadata>. Beispielsweise wenn die ursprüngliche <xref:System.Windows.FrameworkPropertyMetadata> -Objekt legt die <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> Flag, Sie können ändern, indem Sie festlegen <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> auf `false`.  
  
 Dieses Verhalten wird durch implementiert <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>, und kann für abgeleiteten Metadatenklassen überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>  
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
