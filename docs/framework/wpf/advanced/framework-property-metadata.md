---
title: Framework-Eigenschaftenmetadaten
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: b6bacf6f0c27b123d36f17510d84e5ef5e2cf122
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108705"
---
# <a name="framework-property-metadata"></a>Framework-Eigenschaftenmetadaten
Die Optionen für Framework-Eigenschaftenmetadaten werden für die Eigenschaften von Objektelementen gemeldet, die in der WPF-Frameworkebene in der Architektur [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vorhanden sein sollen. Im Allgemeinen bedeutet die Bezeichnung WPF-Frameworkebene, dass Funktionen wie das Rendering, die Datenbindung und die Verbesserungen des Eigenschaftensystems von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Präsentations-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] und von ausführbaren Dateien behandelt werden. Framework-Eigenschaftenmetadaten werden von diesen Systemen zur Ermittlung funktionsspezifischer Merkmale von bestimmten Elementeigenschaften abgefragt.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen verstehen und die [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Folgenden Artikel sollten Sie auch gelesen haben: [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Was wird von Framework-Eigenschaftenmetadaten übermittelt?  
 Framework-Eigenschaftenmetadaten können in folgende Kategorien unterteilt werden:  
  
-   Berichte zu Layouteigenschaften, die ein Element auswirken (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). Sie können diese Flags in Metadaten festlegen, wenn die Eigenschaft wirkt sich auf die jeweiligen Aspekte, und Sie auch implementieren die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden in Ihrer Klasse spezifisches Renderingverhalten und Informationen, die das Layout angeben. System. In der Regel würde eine solche Implementierung nach Eigenschafteninvalidierungen in Abhängigkeitseigenschaften suchen, wo die Layouteigenschaften in den Eigenschaftenmetadaten wahr waren. Nur diese Validierungen würde einen neuen Layoutdurchlauf erforderlich machen.  
  
-   Berichte zu Layouteigenschaften, die sich auf das übergeordnete Element eines Elements (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). Einige Beispiele, in denen diese Flags werden standardmäßig festgelegt, sind <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> und <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>sein. Standardmäßig erben Abhängigkeitseigenschaften keine Werte. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> ermöglicht dem Vererbungspfad auch in einer visuellen Struktur übertragen der für einige Szenarien für das Steuerelement Zusammensetzung erforderlich ist.  
  
    > [!NOTE]
    >  Im Kontext mit Eigenschaftswerten bedeutet der Begriff „erbt“ für Abhängigkeitseigenschaften etwas Bestimmtes. Das bedeutet, dass untergeordnete Elemente den tatsächlichen Abhängigkeitseigenschaftswert von übergeordneten Elementen erben können, aufgrund einer Funktion der WPF-Frameworkebene des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems. Dies hat nichts mit verwaltetem Codetypen und Vererbung der Member über abgeleitete Typen zu tun. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).  
  
-   Eigenschaften der Datenbindung Reporting (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). Standardmäßig unterstützen Abhängigkeitseigenschaften im Framework die Datenbindung mit einem unidirektionalen Bindungsverhalten. Sie können möglicherweise die Datenbindung deaktivieren, wenn es dafür überhaupt kein Szenario gäbe (da sie flexibel und erweiterbar vorgesehen sind, sind nicht viele Beispiele für solche Eigenschaften in den standardmäßigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]). Legen Sie möglicherweise die Bindung an einen bidirektionalen Standard für Eigenschaften verfügen, die zusammen Verhalten eines Steuerelements seiner Komponententeile verknüpfen (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> ist ein Beispiel) oder dass die bidirektionale Bindung das allgemeine und erwartete Szenario für Benutzer (<xref:System.Windows.Controls.TextBox.Text%2A> ist ein Beispiel). Das Ändern der auf die Datenbindung bezogenen Metadaten beeinflusst nur den Standardwert. Bei einer Basis pro Bindung kann dieser Standardwert immer geändert werden. Weitere Informationen zu den Bindungsmodi und zur Bindung im Allgemeinen finden Sie unter [Übersicht zur Datenbindung](../data/data-binding-overview.md).  
  
-   Meldet, ob die Eigenschaften von Anwendungen oder Dienste, die Journaling unterstützen werden sollen (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>). Für allgemeine Elemente ist Journaling nicht standardmäßig aktiviert, aber es ist selektiv für bestimmte Benutzereingabe-Steuerelemente aktiviert. Diese Eigenschaft soll von Journaling-Diensten gelesen werden, einschließlich der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung von Journaling, und wird in der Regel auf Benutzersteuerelemente festgelegt, z.B. Auswahlmöglichkeiten des Benutzers in Listen, die über Navigationsschritte hinweg beibehalten werden soll. Informationen zur Erfassung finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Lesen von FrameworkPropertyMetadata  
 Jede der oben verknüpften Eigenschaften handelt es sich um die spezifischen Eigenschaften, die die <xref:System.Windows.FrameworkPropertyMetadata> hinzugefügt, den direkten Basisklassen <xref:System.Windows.UIPropertyMetadata>. Jede dieser Eigenschaften wird standardmäßig `false` sein. Eine Metadatenanforderung für eine Eigenschaft, in dem wichtig den Wert dieser Eigenschaften zu wissen ist, sollten die zurückgegebene Metadaten in umgewandelt versuchen <xref:System.Windows.FrameworkPropertyMetadata>, und überprüfen Sie dann die Werte der einzelnen Eigenschaften nach Bedarf.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Angeben von Metadaten  
 Wenn Sie eine neuen Metadateninstanz zum Zweck der Anwendung von Metadaten in einer neuen Registrierung der Abhängigkeitseigenschaft erstellen, haben Sie die Auswahl der Metadatenklasse verwenden: die Basis <xref:System.Windows.PropertyMetadata> oder eine abgeleitete Klasse wie z. B. <xref:System.Windows.FrameworkPropertyMetadata>. Sie sollten im Allgemeinen verwenden <xref:System.Windows.FrameworkPropertyMetadata>, insbesondere, wenn die Eigenschaft jegliche Interaktion mit dem Eigenschaftensystem hat und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionen, z. B. Layout und Datenbindung. Eine weitere Möglichkeit für anspruchsvollere Szenarios ist eine Ableitung <xref:System.Windows.FrameworkPropertyMetadata> berichterstellungsklasse mit zusätzlichen Informationen zum Erstellen Ihrer eigenen Metadaten in seinen Membern ausgeführt. Oder Sie können <xref:System.Windows.PropertyMetadata> oder <xref:System.Windows.UIPropertyMetadata> den Grad der Unterstützung für Funktionen Ihrer Implementierung zu kommunizieren.  
  
 Für vorhandene Eigenschaften (<xref:System.Windows.DependencyProperty.AddOwner%2A> oder <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> aufrufen), sollten Sie immer mit dem Metadatentyp, die von der ursprünglichen Registrierung verwendet überschreiben.  
  
 Bei der Erstellung einer <xref:System.Windows.FrameworkPropertyMetadata> Instanz ist, es gibt zwei Möglichkeiten, Metadaten mit den Werten für die einzelnen Eigenschaften aufzufüllen, die die Merkmale der Framework-Eigenschaft kommunizieren:  
  
1.  Verwenden der <xref:System.Windows.FrameworkPropertyMetadata> Konstruktorsignatur, die ermöglicht eine `flags` Parameter. Dieser Parameter sollte mit allen gewünschten kombinierten Werten der gefüllt werden die <xref:System.Windows.FrameworkPropertyMetadataOptions> Enumerationsflags.  
  
2.  Verwenden Sie eine der Signaturen ohne ein `flags` Parameter, und legen Sie anschließend jeden Bericht zur booleschen Eigenschaft für <xref:System.Windows.FrameworkPropertyMetadata> zu `true` für jede Änderung der Merkmale gewünschte. Wenn Sie dies tun, müssen Sie diese Eigenschaften festlegen, bevor Elemente mit dieser Abhängigkeitseigenschaft erstellt werden. Die booleschen Eigenschaften verfügen über Lese-/Schreibzugriff, um dieses Verhalten zur Vermeidung des `flags`-Parameters zu ermöglichen und trotzdem die Metadaten zu füllen, aber die Metadaten müssen vor der Verwendung der Eigenschaft effektiv versiegelt werden. Daher wird der Versuch, Eigenschaften nach der Anforderung von Metadaten festzulegen, ein ungültiger Vorgang sein.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Zusammenführungsverhalten von Framework-Eigenschaftenmetadaten  
 Wenn Sie Framework-Eigenschaftenmetadaten überschreiben, werden die verschiedenen Metadaten-Eigenschaften entweder zusammengeführt oder ersetzt.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> wird zusammengeführt. Wenn Sie ein neues hinzufügen <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, dieser Rückruf in den Metadaten gespeichert ist. Wenn Sie keinen angeben einer <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in der Überschreibung der Wert des <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> wird höher gestuft, als Verweis vom nächsten Vorgänger, der Metadaten angegeben.  
  
-   Das Verhalten des tatsächlichen Eigenschaftensystems für <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> besteht darin, dass die Implementierungen für alle Metadaten-Besitzer in der Hierarchie beibehalten und eine Tabelle hinzugefügt, mit der Reihenfolge der Ausführung durch das Eigenschaftensystem, die Rückrufe der tiefsten abgeleiteten Klasse sind zuerst aufgerufen. Geerbte Rückrufe werden nur einmal ausgeführt und gelten als im Besitz der Klasse, die sie in den Metadaten gespeichert hat.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A> wird ersetzt. Wenn Sie keinen angeben einer <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> in der Überschreibung der Wert des <xref:System.Windows.PropertyMetadata.DefaultValue%2A> stammt aus der unmittelbaren Vorgänger, der Metadaten angegeben.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> -Implementierungen werden ersetzt. Wenn Sie ein neues hinzufügen <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, dieser Rückruf in den Metadaten gespeichert ist. Wenn Sie keinen angeben einer <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in der Überschreibung der Wert des <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> wird höher gestuft, als Verweis vom nächsten Vorgänger, der Metadaten angegeben.  
  
-   Verhalten des Eigenschaftensystems ist, dass nur die <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> in den unmittelbaren Metadaten aufgerufen wird. Keine Verweise auf andere <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> Implementierungen in der Hierarchie werden beibehalten.  
  
-   Die Flags der <xref:System.Windows.FrameworkPropertyMetadataOptions> Enumeration, die als eine bitweise OR-Operation kombiniert werden.  Bei Angabe von <xref:System.Windows.FrameworkPropertyMetadataOptions>, die ursprünglichen Optionen nicht überschrieben.  Um eine Option zu ändern, legen Sie die entsprechende Eigenschaft für <xref:System.Windows.FrameworkPropertyMetadata>. Z. B. wenn die ursprüngliche <xref:System.Windows.FrameworkPropertyMetadata> -Objekt legt die <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> Flag können Sie Sie ändern, indem Sie die Einstellung <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> zu `false`.  
  
 Dieses Verhalten wird implementiert, indem <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>, und kann für abgeleitete Metadatenklassen überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
