---
title: Framework-Eigenschaftenmetadaten
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 8fb6e1b4cf6aed9454e9e9f1a77277d2f3611ca8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186653"
---
# <a name="framework-property-metadata"></a>Framework-Eigenschaftenmetadaten
Die Optionen für Framework-Eigenschaftenmetadaten werden für die Eigenschaften von Objektelementen gemeldet, die in der WPF-Frameworkebene in der Architektur [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vorhanden sein sollen. Im Allgemeinen beinhaltet die WPF-Framework-Ebene, dass Features wie Rendering, Datenbindung und Verfeinerungen des Eigenschaftensystems von den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Präsentations-APIs und ausführbaren Dateien behandelt werden. Framework-Eigenschaftenmetadaten werden von diesen Systemen zur Ermittlung funktionsspezifischer Merkmale von bestimmten Elementeigenschaften abgefragt.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klassen verstehen und die [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Folgenden Artikel sollten Sie auch gelesen haben: [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>
## <a name="what-is-communicated-by-framework-property-metadata"></a>Was wird von Framework-Eigenschaftenmetadaten übermittelt?  
 Framework-Eigenschaftenmetadaten können in folgende Kategorien unterteilt werden:  
  
- Melden von Layouteigenschaften,<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>die <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>sich auf ein Element ( , , ) auswirken. Sie können diese Flags in Metadaten festlegen, wenn sich die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Eigenschaft auf diese jeweiligen Aspekte auswirkt, und Sie implementieren auch die Methoden in Ihrer Klasse, um dem Layoutsystem ein bestimmtes Renderingverhalten und bestimmte Informationen zur Verfügung zu stellen. In der Regel würde eine solche Implementierung nach Eigenschafteninvalidierungen in Abhängigkeitseigenschaften suchen, wo die Layouteigenschaften in den Eigenschaftenmetadaten wahr waren. Nur diese Validierungen würde einen neuen Layoutdurchlauf erforderlich machen.  
  
- Melden von Layouteigenschaften, die sich<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>auf <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>das übergeordnete Element eines Elements auswirken ( , ). Einige Beispiele, in denen diese <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>Flags standardmäßig festgelegt sind, sind und .  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. Standardmäßig erben Abhängigkeitseigenschaften keine Werte. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>ermöglicht es, den Weg der Vererbung auch in einen visuellen Baum zu übertragen, was für einige Kontroll-Compositing-Szenarien erforderlich ist.  
  
    > [!NOTE]
    > Im Kontext mit Eigenschaftswerten bedeutet der Begriff „erbt“ für Abhängigkeitseigenschaften etwas Bestimmtes. Das bedeutet, dass untergeordnete Elemente den tatsächlichen Abhängigkeitseigenschaftswert von übergeordneten Elementen erben können, aufgrund einer Funktion der WPF-Frameworkebene des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems. Dies hat nichts mit verwaltetem Codetypen und Vererbung der Member über abgeleitete Typen zu tun. Weitere Informationen finden Sie unter [Eigenschaftenwertvererbung](property-value-inheritance.md).  
  
- Bindungsmerkmale für<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A> <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>Berichtsdaten ( , ). Standardmäßig unterstützen Abhängigkeitseigenschaften im Framework die Datenbindung mit einem unidirektionalen Bindungsverhalten. Sie können die Datenbindung deaktivieren, wenn es überhaupt kein Szenario dafür gibt (da sie flexibel und erweiterbar sein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sollen, gibt es nicht viele Beispiele für solche Eigenschaften in den Standard-APIs). Sie können die Bindung so festlegen, dass eine bidirektionale Standardeinstellung für Eigenschaften<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> gilt, die das Verhalten eines Steuerelements zwischen seinen<xref:System.Windows.Controls.TextBox.Text%2A> Komponententeilen verbinden (ein Beispiel ist) oder bei denen die bidirektionale Bindung das allgemeine und erwartete Szenario für Benutzer ist (ein Beispiel). Das Ändern der auf die Datenbindung bezogenen Metadaten beeinflusst nur den Standardwert. Bei einer Basis pro Bindung kann dieser Standardwert immer geändert werden. Weitere Informationen zu den Bindungsmodi und zur Bindung im Allgemeinen finden Sie unter [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Melden, ob Eigenschaften von Anwendungen oder Diensten erfasst<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>werden sollen, die Journaling unterstützen ( ). Für allgemeine Elemente ist Journaling nicht standardmäßig aktiviert, aber es ist selektiv für bestimmte Benutzereingabe-Steuerelemente aktiviert. Diese Eigenschaft soll von Journaling-Diensten gelesen werden, einschließlich der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung von Journaling, und wird in der Regel auf Benutzersteuerelemente festgelegt, z.B. Auswahlmöglichkeiten des Benutzers in Listen, die über Navigationsschritte hinweg beibehalten werden soll. Informationen zur Erfassung finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>
## <a name="reading-frameworkpropertymetadata"></a>Lesen von FrameworkPropertyMetadata  
 Jede der oben verknüpften Eigenschaften sind <xref:System.Windows.FrameworkPropertyMetadata> die spezifischen Eigenschaften, die der der unmittelbaren Basisklasse <xref:System.Windows.UIPropertyMetadata>hinzufügt. Jede dieser Eigenschaften wird standardmäßig `false` sein. Eine Metadatenanforderung für eine Eigenschaft, bei der der Wert dieser Eigenschaften <xref:System.Windows.FrameworkPropertyMetadata>wichtig ist, sollte versuchen, die zurückgegebenen Metadaten in zu umlegen, und dann die Werte der einzelnen Eigenschaften nach Bedarf überprüfen.  
  
<a name="Specifying_Metadata"></a>
## <a name="specifying-metadata"></a>Angeben von Metadaten  
 Wenn Sie eine neue Metadateninstanz zum Anwenden von Metadaten auf eine neue Abhängigkeitseigenschaftsregistrierung erstellen, haben Sie die Wahl zwischen der zu verwendenden Metadatenklasse: der Basis <xref:System.Windows.PropertyMetadata> oder einer abgeleiteten Klasse, z. <xref:System.Windows.FrameworkPropertyMetadata>B. . Im Allgemeinen sollten <xref:System.Windows.FrameworkPropertyMetadata>Sie verwenden, insbesondere wenn Ihre Eigenschaft [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Interaktion mit dem Eigenschaftensystem und Funktionen wie Layout und Datenbindung hat. Eine weitere Option für komplexere <xref:System.Windows.FrameworkPropertyMetadata> Szenarien besteht darin, eine eigene Metadatenberichtsklasse mit zusätzlichen Informationen zu erstellen, die in ihren Membern übertragen werden. Oder Sie <xref:System.Windows.PropertyMetadata> können <xref:System.Windows.UIPropertyMetadata> den Grad der Unterstützung für Funktionen Ihrer Implementierung verwenden oder kommunizieren.  
  
 Bei vorhandenen<xref:System.Windows.DependencyProperty.AddOwner%2A> Eigenschaften <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> (oder Aufrufen) sollten Sie immer mit dem Metadatentyp überschreiben, der von der ursprünglichen Registrierung verwendet wird.  
  
 Wenn Sie eine <xref:System.Windows.FrameworkPropertyMetadata> Instanz erstellen, gibt es zwei Möglichkeiten, diese Metadaten mit Werten für die spezifischen Eigenschaften aufzufüllen, die die Frameworkeigenschaften kommunizieren:  
  
1. Verwenden <xref:System.Windows.FrameworkPropertyMetadata> Sie die Konstruktorsignatur, die einen `flags` Parameter zulässt. Dieser Parameter sollte mit allen gewünschten <xref:System.Windows.FrameworkPropertyMetadataOptions> kombinierten Werten der Enumerationsflags gefüllt werden.  
  
2. Verwenden Sie eine der `flags` Signaturen ohne Parameter, und <xref:System.Windows.FrameworkPropertyMetadata> legen `true` Sie dann jede berichtsboolele Eigenschaft für jede gewünschte Merkmalsänderung fest. Wenn Sie dies tun, müssen Sie diese Eigenschaften festlegen, bevor Elemente mit dieser Abhängigkeitseigenschaft erstellt werden. Die booleschen Eigenschaften verfügen über Lese-/Schreibzugriff, um dieses Verhalten zur Vermeidung des `flags`-Parameters zu ermöglichen und trotzdem die Metadaten zu füllen, aber die Metadaten müssen vor der Verwendung der Eigenschaft effektiv versiegelt werden. Daher wird der Versuch, Eigenschaften nach der Anforderung von Metadaten festzulegen, ein ungültiger Vorgang sein.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>
## <a name="framework-property-metadata-merge-behavior"></a>Zusammenführungsverhalten von Framework-Eigenschaftenmetadaten  
 Wenn Sie Framework-Eigenschaftenmetadaten überschreiben, werden die verschiedenen Metadaten-Eigenschaften entweder zusammengeführt oder ersetzt.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>wird zusammengeführt. Wenn Sie eine <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>neue hinzufügen, wird dieser Rückruf in den Metadaten gespeichert. Wenn Sie in <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> der Außerkraftsetzung keine <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> angeben, wird der Wert von als Verweis vom nächstgelegenen Vorgänger heraufgestuft, der ihn in Metadaten angegeben hat.  
  
- Das tatsächliche Eigenschaftensystemverhalten für <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> ist, dass Implementierungen für alle Metadatenbesitzer in der Hierarchie beibehalten und einer Tabelle hinzugefügt werden, wobei die Ausführungsreihenfolge durch das Eigenschaftensystem darin besteht, dass zuerst die Rückrufe der am tiefsten abgeleiteten Klasse aufgerufen werden. Geerbte Rückrufe werden nur einmal ausgeführt und gelten als im Besitz der Klasse, die sie in den Metadaten gespeichert hat.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>wird ersetzt. Wenn Sie in <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> der Außerkraftsetzung keine <xref:System.Windows.PropertyMetadata.DefaultValue%2A> angeben, stammt der Wert von vom nächsten Vorgänger, der ihn in Metadaten angegeben hat.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>Implementierungen werden ersetzt. Wenn Sie eine <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>neue hinzufügen, wird dieser Rückruf in den Metadaten gespeichert. Wenn Sie in <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> der Außerkraftsetzung keine <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> angeben, wird der Wert von als Verweis vom nächstgelegenen Vorgänger heraufgestuft, der ihn in Metadaten angegeben hat.  
  
- Das Verhalten des Eigenschaftensystems <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> besteht darin, dass nur die in den unmittelbaren Metadaten aufgerufen werden. Es werden <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> keine Verweise auf andere Implementierungen in der Hierarchie beibehalten.  
  
- Die Flags <xref:System.Windows.FrameworkPropertyMetadataOptions> der Enumeration werden als bitweiser ODER-Vorgang kombiniert.  Wenn Sie <xref:System.Windows.FrameworkPropertyMetadataOptions>angeben, werden die ursprünglichen Optionen nicht überschrieben.  Um eine Option zu ändern, <xref:System.Windows.FrameworkPropertyMetadata>legen Sie die entsprechende Eigenschaft auf fest. Wenn das <xref:System.Windows.FrameworkPropertyMetadata> ursprüngliche Objekt z. B. das Flag festlegt, können Sie dies <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> ändern, indem Sie die Einstellung <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> auf `false`festlegen.  
  
 Dieses Verhalten wird <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>von implementiert und kann für abgeleitete Metadatenklassen überschrieben werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
