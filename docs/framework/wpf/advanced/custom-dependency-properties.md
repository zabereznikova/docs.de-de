---
title: Benutzerdefinierte Abhängigkeitseigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- implementing [WPF], wrappers
- registering properties [WPF]
- properties [WPF], metadata
- metadata [WPF], for properties
- custom dependency properties [WPF]
- properties [WPF], registering
- wrappers [WPF], implementing
- dependency properties [WPF], custom
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
ms.openlocfilehash: 1352876b79e103d20d08382ab088f7777c6fe2ae
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401567"
---
# <a name="custom-dependency-properties"></a>Benutzerdefinierte Abhängigkeitseigenschaften

Dieses Thema beschreibt die Gründe, warum Anwendungsentwickler und Komponentenautoren in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] benutzerdefinierte Abhängigkeitseigenschaften erstellen möchten, und beschreibt die Implementierungsmaßnahmen und -optionen, die die Leistung, Verwendbarkeit oder Vielseitigkeit der Eigenschaft verbessern können.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Erforderliche Komponenten

In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen auskennen, und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] vertraut sein und wissen, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen geschrieben werden.

<a name="whatis"></a>

## <a name="what-is-a-dependency-property"></a>Was ist eine Abhängigkeitseigenschaft?

Sie können aktivieren, was andernfalls eine Common Language Runtime (CLR)-Eigenschaft wäre, um Formatierung, Datenbindung, Vererbung, Animationen und Standardwerte zu unterstützen, indem Sie Sie als Abhängigkeits Eigenschaft implementieren. Abhängigkeits Eigenschaften sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften, die beim-Eigenschaften System durch Aufrufen der <xref:System.Windows.DependencyProperty.Register%2A> -Methode (oder <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>) registriert sind und durch ein <xref:System.Windows.DependencyProperty> Bezeichnerfeld unterstützt werden. Abhängigkeits Eigenschaften können nur <xref:System.Windows.DependencyObject> von-Typen verwendet werden <xref:System.Windows.DependencyObject> , sind jedoch in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassenhierarchie sehr hoch, sodass die Mehrzahl der in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügbaren Klassen Abhängigkeits Eigenschaften unterstützen können. Weitere Informationen zu Abhängigkeitseigenschaften und zur Terminologie und den Konventionen für die Beschreibung in [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] finden Sie unter [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md).

<a name="example_dp"></a>

## <a name="examples-of-dependency-properties"></a>Beispiele für Abhängigkeitseigenschaften

Beispiele für Abhängigkeits Eigenschaften, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Klassen implementiert <xref:System.Windows.Controls.Control.Background%2A> werden, sind u. a. <xref:System.Windows.Controls.TextBox.Text%2A> die-Eigenschaft, die <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft und die-Eigenschaft. Jede Abhängigkeits Eigenschaft, die von einer Klasse verfügbar gemacht wird, verfügt über <xref:System.Windows.DependencyProperty> ein entsprechendes öffentliches statisches Feld vom Typ, das für die gleiche Klasse Es handelt sich um den Bezeichner für die Abhängigkeitseigenschaft. Der Name des Bezeichners wird nach einer Konvention gewählt: Der Name der Abhängigkeitseigenschaft mit der angefügten Zeichenfolge `Property`. Beispielsweise ist <xref:System.Windows.DependencyProperty> <xref:System.Windows.Controls.Control.Background%2A> dasentsprechendeBezeichnerfeldfür<xref:System.Windows.Controls.Control.BackgroundProperty>die-Eigenschaft. Der Bezeichner speichert die Informationen zur Abhängigkeits Eigenschaft, während er registriert wurde. der Bezeichner wird dann später für andere Vorgänge verwendet, die die Abhängigkeits Eigenschaft <xref:System.Windows.DependencyObject.SetValue%2A>betreffen, z. b. durch Aufrufen von.

Wie in der [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md)erwähnt, sind alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Abhängigkeits Eigenschaften in (außer den meisten angefügten Eigenschaften) aufgrund der "Wrapper"-Implementierung auch CLR-Eigenschaften. Aus dem Code können Sie daher Abhängigkeits Eigenschaften abrufen oder festlegen, indem Sie CLR-Accessoren aufrufen, die die Wrapper auf die gleiche Weise definieren, wie Sie andere CLR-Eigenschaften verwenden würden. Als Consumer von festgelegten Abhängigkeits Eigenschaften verwenden Sie in der Regel nicht <xref:System.Windows.DependencyObject> die <xref:System.Windows.DependencyObject.GetValue%2A> Methoden <xref:System.Windows.DependencyObject.SetValue%2A>und, die den Verbindungspunkt zum zugrunde liegenden Eigenschaften System sind. Stattdessen hat die vorhandene Implementierung der CLR-Eigenschaften bereits und <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> in den `get` -und-Wrapper `set` Implementierungen der-Eigenschaft aufgerufen, wobei das Bezeichnerfeld entsprechend verwendet wird. Wenn Sie eine benutzerdefinierte Abhängigkeitseigenschaft selbst implementieren, definieren Sie den Wrapper auf ähnliche Weise.

<a name="backing_with_dp"></a>

## <a name="when-should-you-implement-a-dependency-property"></a>Wann sollten Sie eine Abhängigkeitseigenschaft implementieren?

Wenn Sie eine Eigenschaft für eine Klasse implementieren, können Sie, solange die Klasse von <xref:System.Windows.DependencyObject>abgeleitet ist, die-Eigenschaft mit einem <xref:System.Windows.DependencyProperty> -Bezeichner sichern und so eine Abhängigkeits Eigenschaft erstellen. Es ist nicht immer notwendig oder angemessen, Ihre Eigenschaft in eine Abhängigkeitseigenschaft umzuwandeln. Es hängt von den Anforderungen Ihres Szenarios ab. Manchmal ist die normale Technik des Sicherns der Eigenschaft mit einem privaten Feld ausreichend. Sie sollten Ihre Eigenschaft allerdings als Abhängigkeitseigenschaft implementieren, wenn Sie möchten, dass Ihre Eigenschaft eine oder mehrere der folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen unterstützt:

- Sie möchten, dass Ihre Eigenschaft in einem Stil festgelegt werden kann. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).

- Sie möchten, dass die Eigenschaft Datenbindung unterstützt. Weitere Informationen zur Datenbindung mit Abhängigkeitseigenschaften finden Sie unter [Binden der Eigenschaften von zwei Steuerelementen](../data/how-to-bind-the-properties-of-two-controls.md).

- Sie möchten, dass die Eigenschaft mit einem dynamischen Ressourcenverweis festgelegt werden kann. Weitere Informationen finden Sie unter [XAML-Ressourcen](xaml-resources.md).

- Sie möchten einen Eigenschaftswert automatisch von einem übergeordneten Element in der Elementstruktur erben. Registrieren Sie in diesem Fall mit der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> -Methode, auch wenn Sie einen Eigenschafts Wrapper für den CLR-Zugriff erstellen. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).

- Sie möchten, dass Ihre Eigenschaft animiert werden kann. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).

- Sie möchten, dass das Eigenschaftensystem berichtet, wenn der vorherige Wert der Eigenschaft durch Aktionen des Eigenschaftensystems, der Umgebung, des Benutzers oder durch Lesen und Verwenden von Stilen geändert wurde. Mithilfe von Eigenschaftenmetadaten kann Ihre Eigenschaft eine Rückrufmethode angeben, die jedes Mal aufgerufen wird, wenn das Eigenschaftensystem feststellt, dass der Eigenschaftswert eindeutig geändert wurde. Ein verwandtes Konzept ist die Koersion des Eigenschaftswerts. Weitere Informationen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](dependency-property-callbacks-and-validation.md).

- Sie möchten geltende Konventionen für Metadaten verwenden, die auch von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Vorgängen verwendet werden, z.B. der Bericht, ob das Layoutsystem aufgrund eines geänderten Eigenschaftswerts die visuellen Objekte für ein Element neu aufbauen soll. Oder Sie möchten Überschreibungen von Metadaten verwenden, sodass abgeleitete Klassen auf Metadaten basierende Eigenschaften, z.B. den Standardwert, ändern können.

- Sie möchten, dass die Eigenschaften eines benutzerdefinierten Steuer Elements den Visual Studio WPF-Designer unterstützen, z. b. die Bearbeitung von **Eigenschaften** Fenstern Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).

Wenn Sie diese Szenarios untersuchen, sollten Sie auch bedenken, ob Sie Ihr Szenario erreichen können, indem Sie die Metadaten einer vorhandenen Abhängigkeitseigenschaft überschreiben, anstatt eine völlig neue Eigenschaft zu implementieren. Ob die Überschreibung von Metadaten sinnvoll ist hängt von Ihrem Szenario ab und wie sehr dieses Szenario der Implementierung vorhandener [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Abhängigkeitseigenschaften und -Klassen ähnelt. Weitere Informationen zum Überschreiben der Metadaten von vorhandenen Eigenschaften finden Sie unter [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).

<a name="checklist"></a>

## <a name="checklist-for-defining-a-dependency-property"></a>Prüfliste für die Definition einer Abhängigkeitseigenschaft

Das Definieren einer Abhängigkeitseigenschaft besteht aus vier unterschiedlichen Konzepten. Diese Konzepte sind nicht unbedingt aufeinanderfolgende Schritte, da einige von ihnen am Ende als einzelne Codezeilen in der Implementierung kombiniert werden:

- (Optional) Erstellen Sie Eigenschaftsmetadaten für die Abhängigkeitseigenschaft.

- Registrieren Sie den Eigenschaftennamen im Eigenschaftensystem, indem Sie einen Besitzertyp und den Typ des Eigenschaftswerts angeben. Geben Sie, falls verwendet, auch die Metadaten der Eigenschaft an.

- Definieren Sie <xref:System.Windows.DependencyProperty> einen Bezeichner `public` `static` als Feldfürden`readonly` Besitzertyp.

- Definieren Sie eine CLR-Wrapper Eigenschaft, deren Name mit dem Namen der Abhängigkeits Eigenschaft übereinstimmt. Implementieren Sie die-und `get` `set` -Accessoren der CLR "Wrapper"-Eigenschaft, um eine Verbindung mit der Abhängigkeits Eigenschaft herzustellen, die diese sichert

<a name="registering"></a>

### <a name="registering-the-property-with-the-property-system"></a>Registrieren der Eigenschaft im Eigenschaftensystem

Damit Ihre Eigenschaft zu einer Abhängigkeitseigenschaft wird, müssen Sie diese Eigenschaft in einer Tabelle im Eigenschaftensystem registrieren und einen eindeutigen Bezeichner angeben. Dieser wird als Qualifizierer für spätere Vorgänge im Eigenschaftensystem verwendet. Bei diesen Vorgängen kann es sich um interne Vorgänge oder ihren eigenen Code handeln, der die Eigenschaften System-APIs aufrufen Um die Eigenschaft zu registrieren, müssen Sie <xref:System.Windows.DependencyProperty.Register%2A> die-Methode im Textkörper der Klasse (innerhalb der-Klasse, aber außerhalb von Element Definitionen) aufzurufen. Das Bezeichnerfeld wird auch vom <xref:System.Windows.DependencyProperty.Register%2A> Methoden aufrufswert als Rückgabewert bereitgestellt. Der Grund für die <xref:System.Windows.DependencyProperty.Register%2A> Ausführung des Aufrufes außerhalb anderer Element Definitionen ist, dass Sie diesen Rückgabewert verwenden, um ein `public` `static` `readonly` Feld vom Typ <xref:System.Windows.DependencyProperty> als Teil der Klasse zuzuweisen und zu erstellen. Das Feld wird zum Bezeichner für Ihre Abhängigkeitseigenschaft.

[!code-csharp[WPFAquariumSln#RegisterAG](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
[!code-vb[WPFAquariumSln#RegisterAG](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]

<a name="nameconventions"></a>

### <a name="dependency-property-name-conventions"></a>Namenskonventionen für Abhängigkeitseigenschaften

Es gibt Namenskonventionen für Abhängigkeitseigenschaften, die Sie bis auf bestimmte Ausnahmefälle befolgen müssen.

Die Abhängigkeits Eigenschaft selbst hat einen einfachen Namen, "aquariengraphic", wie in diesem Beispiel, der als erster Parameter von <xref:System.Windows.DependencyProperty.Register%2A>angegeben wird. Dieser Name muss innerhalb jedes Registrierungstyps eindeutig sein. Abhängigkeitseigenschaften, die über Basistypen geerbt werden, gelten bereits als teil des Registrierungstyps. Namen von geerbten Eigenschaften können nicht erneut registriert werden. Es gibt jedoch ein Verfahren zum Hinzufügen von Klassen als Besitzer einer Abhängigkeitseigenschaft, sogar wenn diese Abhängigkeitseigenschaft nicht geerbt ist. Weitere Informationen hierzu finden Sie unter [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).

Geben Sie einem Bezeichnerfeld beim Erstellen den Namen der Eigenschaft bei der Registrierung und das Suffix `Property`. Dieses Feld ist der Bezeichner für die-Abhängigkeits Eigenschaft und wird später als Eingabe für den <xref:System.Windows.DependencyObject.SetValue%2A> -Aufruf und den- <xref:System.Windows.DependencyObject.GetValue%2A> Aufruf verwendet, den Sie in den Wrappern durch jeglichen anderen Code Zugriff auf die Eigenschaft durch ihren eigenen Code, durch jeglichen externen Code Zugriff, den Sie zulassen, vornehmen. , vom-Eigenschaften System und potenziell von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessoren.

> [!NOTE]
> Die übliche Implementierung ist das Definieren der Abhängigkeitseigenschaft im Text einer Klasse. Es ist aber auch möglich, eine Abhängigkeitseigenschaft im statischen Konstruktor der Klasse zu definieren. Diese Vorgehensweise kann sinnvoll sein, wenn Sie mehr als eine Codezeile benötigen, um die Abhängigkeitseigenschaft zu initialisieren.

<a name="wrapper1"></a>

### <a name="implementing-the-wrapper"></a>Implementieren des „Wrappers“

Die Wrapper Implementierung sollte in <xref:System.Windows.DependencyObject.GetValue%2A> der `get` -Implementierung und in <xref:System.Windows.DependencyObject.SetValue%2A> der `set` -Implementierung (der ursprüngliche Registrierungs Name und das-Feld werden ebenfalls zur Verdeutlichung angezeigt) aufgerufen werden.

In allen außer Ausnahmefällen sollten Ihre Wrapper Implementierungen nur die <xref:System.Windows.DependencyObject.GetValue%2A> Aktionen und <xref:System.Windows.DependencyObject.SetValue%2A> ausführen. Der Grund hierfür wird im Thema [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md) erläutert.

Alle vorhandenen öffentlichen Abhängigkeitseigenschaften, die für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen zur Verfügung stehen, verwenden dieses einfache Modell der Wrapper-Implementierung. Ein Großteil der komplexen Funktionsweise von Abhängigkeitseigenschaften ist entweder ein grundsätzliches Verhalten des Eigenschaftensystems oder wird durch andere Konzepte wie Koersion oder Rückrufe für Eigenschaftenänderungen durch Eigenschaftenmetadaten implementiert.

[!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
[!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]

Der Name der Wrapper Eigenschaft muss gemäß der Konvention mit dem ausgewählten Namen identisch sein und als erster Parameter des <xref:System.Windows.DependencyProperty.Register%2A> Aufrufes angegeben werden, der die Eigenschaft registriert hat. Wenn die Eigenschaft den Konventionen nicht folgt, werden dadurch nicht unbedingt alle möglichen Verwendungsarten deaktiviert, aber Sie werden mehrere deutliche Probleme bemerken:

- Bestimmte Aspekte von Stilen und Vorlagen funktionieren nicht.

- Die meisten Tools und Designer verlassen sich auf Benennungskonventionen, um [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ordnungsgemäß zu serialisieren oder um Unterstützung für eine Entwicklerumgebung auf Ebene einzelner Eigenschaften zu bieten.

- Die aktuelle Implementierung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ladeprogramms umgeht die Wrapper komplett und verlässt sich beim Verarbeiten von Attributwerten auf die Benennungskonvention. Weitere Informationen finden Sie unter [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md).

<a name="metadata"></a>

### <a name="property-metadata-for-a-new-dependency-property"></a>Eigenschaftsmetadaten für eine neue Abhängigkeitseigenschaft

Wenn Sie eine Abhängigkeitseigenschaft registrieren, wird bei der Registrierung über das Eigenschaftensystem ein Metadatenobjekt erstellt, das Merkmale der Eigenschaft speichert. Viele dieser Eigenschaften verfügen über Standardwerte, die festgelegt werden, wenn die-Eigenschaft mit den <xref:System.Windows.DependencyProperty.Register%2A>einfachen Signaturen von registriert wird. Andere Signaturen von <xref:System.Windows.DependencyProperty.Register%2A> ermöglichen es Ihnen, die Metadaten anzugeben, die Sie bei der Registrierung der Eigenschaft wünschen. Die häufigste Art von Metadaten für Abhängigkeitseigenschaften ist ein Standardwert, der für jede neue Instanz angegeben wird, die diese Eigenschaft verwendet.

Wenn Sie eine Abhängigkeits Eigenschaft erstellen, die auf einer abgeleiteten Klasse <xref:System.Windows.FrameworkElement>von vorhanden ist, können Sie anstelle der Basis <xref:System.Windows.FrameworkPropertyMetadata> <xref:System.Windows.PropertyMetadata> Klasse die speziellere Metadatenklasse verwenden. Der Konstruktor für die <xref:System.Windows.FrameworkPropertyMetadata> -Klasse verfügt über mehrere Signaturen, in denen Sie verschiedene Metadatenmerkmale in Kombination angeben können. Wenn Sie nur den Standardwert angeben möchten, verwenden Sie die Signatur, die einen einzelnen Parameter vom Typ <xref:System.Object>annimmt. Übergeben Sie diesen Objekt Parameter als typspezifischen Standardwert für die `propertyType` <xref:System.Windows.DependencyProperty.Register%2A> -Eigenschaft (der angegebene Standardwert muss der Typ sein, den Sie im-Befehl als Parameter angegeben haben).

Für <xref:System.Windows.FrameworkPropertyMetadata>können Sie auch metadatenoptionsflags für Ihre Eigenschaft angeben. Diese Flags werden nach der Registrierung in diskrete Eigenschaften auf den Eigenschaftenmetadaten konvertiert und werden verwendet, um bestimmte Bedingungen an andere Prozesse zu kommunizieren, z.B. an die Layout-Engine.

#### <a name="setting-appropriate-metadata-flags"></a>Festlegen von Flags für die entsprechenden Metadaten

- Wenn sich [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]die-Eigenschaft (oder Änderungen in ihrem Wert) auf auswirkt und sich insbesondere darauf auswirkt, wie das Layoutsystem das Element auf einer Seite anpassen oder darstellen soll, legen Sie mindestens eines der folgenden Flags <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>fest: <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>,.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>Gibt an, dass eine Änderung an dieser Eigenschaft eine Änderung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] am Rendering erfordert, bei der das enthaltende Objekt möglicherweise mehr oder weniger Platz innerhalb des übergeordneten Elements erfordert. Für die Eigenschaft „Breite“ sollte beispielsweise dieses Flag festgelegt sein.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>Gibt an, dass eine Änderung an dieser Eigenschaft eine Änderung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] am Rendering erfordert, die in der Regel keine Änderung des dedizierten Speicherplatzes erfordert, sondern angibt, dass sich die Positionierung innerhalb des Speicherplatzes geändert hat. Für die Eigenschaft „Ausrichtung“ sollte beispielsweise dieses Flag festgelegt sein.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>Gibt an, dass eine andere Änderung aufgetreten ist, die sich nicht auf Layout und Measure auswirkt, aber ein anderes Rendering erfordert. Ein Beispiel wäre eine Eigenschaft, die eine Farbe eines vorhandenen Elements ändert, z.B. „Hintergrund“.

  - Diese Flags werden in Metadaten häufig als ein Protokoll für Ihre eigenen Überschreibungsimplementierungen von Eigenschaftensystem oder Layoutrückrufen verwendet. Beispielsweise könnten <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> Sie über einen Rückruf verfügen, der aufruft <xref:System.Windows.UIElement.InvalidateArrange%2A> , wenn <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> eine Eigenschaft der-Instanz eine Änderung des Werts meldet und `true` wie in Ihren Metadaten.

- Manche Eigenschaften können Auswirkungen auf die Merkmale des Renderings des übergeordneten Elements haben, sowohl über und unter den Änderungen der oben genannten benötigten Größe. Ein Beispiel hierfür ist <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> die im Fluss Dokument Modell verwendete Eigenschaft, bei der Änderungen an dieser Eigenschaft das allgemeine Rendering des Fluss Dokuments ändern können, das den Absatz enthält. Verwenden <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> Sie <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> oder, um ähnliche Fälle in ihren eigenen Eigenschaften zu identifizieren.

- Standardmäßig unterstützen Abhängigkeitseigenschaften die Datenbindung. Sie können die Datenbindung in Fällen bewusst deaktivieren, in denen kein realistisches Szenario für die Datenbindung besteht, oder in denen die Leistung der Datenbindung für ein großes Objekt als Problem erkannt wird.

- Standardmäßig ist die Daten <xref:System.Windows.Data.Binding.Mode%2A> Bindung für Abhängigkeits Eigenschaften <xref:System.Windows.Data.BindingMode.OneWay>standardmäßig auf. Sie können die Bindung jederzeit in <xref:System.Windows.Data.BindingMode.TwoWay> eine einzelne Bindungs Instanz ändern. Ausführliche Informationen finden Sie unter [angeben der Bindungs Richtung](../data/how-to-specify-the-direction-of-the-binding.md). Als Autor der Abhängigkeits Eigenschaft können Sie jedoch festlegen, dass die Eigenschaft den <xref:System.Windows.Data.BindingMode.TwoWay> Bindungs Modus standardmäßig verwendet. Ein Beispiel für eine vorhandene Abhängigkeits Eigenschaft <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>ist. das Szenario für diese Eigenschaft besteht darin <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> , dass die Einstellungs Logik und die <xref:System.Windows.Controls.MenuItem> Zusammensetzung von mit dem Standarddesign Stil interagieren. Die <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> Eigenschafts Logik verwendet systemeigene Daten Bindungen, um den Status der Eigenschaft in Übereinstimmung mit anderen Zustands Eigenschaften und Methoden aufrufen beizubehalten. Eine andere Beispiel Eigenschaft, <xref:System.Windows.Data.BindingMode.TwoWay> die standardmäßig <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>gebunden wird, ist.

- Sie können die Eigenschaften Vererbung auch in einer benutzerdefinierten Abhängigkeits Eigenschaft <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> aktivieren, indem Sie das-Flag festlegen. Eigenschaftenvererbung eignet sich für ein Szenario, in dem übergeordnete und untergeordnete Elemente über eine gemeinsame Eigenschaft verfügen und es sinnvoll ist, dass das untergeordnete Element diesen bestimmten Eigenschaftswert auf den gleichen Wert wie das übergeordnete Element festlegt. Ein Beispiel für eine Vererb <xref:System.Windows.FrameworkElement.DataContext%2A>Bare Eigenschaft ist, die für Bindungs Vorgänge verwendet wird, um das wichtige Master/Detail-Szenario für die Datendarstellung zu aktivieren. <xref:System.Windows.FrameworkElement.DataContext%2A> Durch Vererbung erbt jedes untergeordnete Element ebenfalls diesen Datenkontext. Aufgrund der Vererbung von Eigenschaftswerten können Sie einen Datenkontext am Seiten- oder Anwendungsstamm angeben, und müssen ihn nicht für Bindungen in allen möglichen untergeordneten Elementen neu angeben. <xref:System.Windows.FrameworkElement.DataContext%2A>ist auch ein gutes Beispiel, um zu veranschaulichen, dass die Vererbung den Standardwert überschreibt, aber immer lokal auf ein bestimmtes untergeordnetes Element festgelegt werden kann. Weitere Informationen finden Sie unter [Verwenden des Master/Detail-Musters mit hierarchischen Daten](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). Die Vererbung von Eigenschaftswerten kann zu Leistungseinbußen führen und sollte deswegen nur sparsam eingesetzt werden. Weitere Informationen hierzu finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).

- Legen Sie <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> das-Flag fest, um anzugeben, ob die Abhängigkeits Eigenschaft von Navigations Journal Diensten erkannt oder verwendet werden soll. Ein Beispiel ist die <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> -Eigenschaft. jedes Element, das in einem Auswahl Steuerelement ausgewählt wurde, sollte beibehalten werden, wenn der Journal Verlauf navigiert wird.

<a name="RODP"></a>

## <a name="read-only-dependency-properties"></a>Schreibgeschützte Abhängigkeitseigenschaften

Sie können eine Abhängigkeitseigenschaft definieren, die schreibgeschützt ist. Allerdings unterscheiden sich die Szenarios, warum Sie eine Eigenschaft als schreibgeschützt definieren sollen. Dies ist auch beim Registrieren mit dem Eigenschaftensystem und Verfügbar machen des Bezeichners der Fall. Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](read-only-dependency-properties.md).

<a name="CTDP"></a>

## <a name="collection-type-dependency-properties"></a>Abhängigkeitseigenschaften vom Auflistungstyp

Bei Abhängigkeitseigenschaften vom Auflistungstyp gibt es zusätzliche Implementierungsprobleme, die man berücksichtigen sollte. Weitere Informationen finden Sie unter [Abhängigkeitseigenschaften vom Auflistungstyp](collection-type-dependency-properties.md).

<a name="SecurityC"></a>

## <a name="dependency-property-security-considerations"></a>Überlegungen zur Sicherheit von Abhängigkeitseigenschaften

Abhängigkeitseigenschaften sollten als öffentliche Eigenschaften deklariert werden. Bezeichnerfelder für Abhängigkeitseigenschaften sollten als öffentliche statische Felder deklariert werden. Auch wenn Sie versuchen, andere Zugriffsebenen zu deklarieren (z. b. geschützt), kann auf eine Abhängigkeits Eigenschaft immer über den Bezeichner in Kombination mit den Eigenschaften System-APIs zugegriffen werden. Der Zugriff auf ein geschütztes Bezeichnerfeld ist möglicherweise möglich, weil Metadatenberichte oder Wert Erstellungs-APIs, die Teil <xref:System.Windows.LocalValueEnumerator>des Eigenschaften Systems sind, wie z. b. Weitere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md).

<a name="DPCtor"></a>

## <a name="dependency-properties-and-class-constructors"></a>Abhängigkeitseigenschaften und Klassenkonstruktoren

Es ist ein allgemeines Prinzip für das Programmieren von verwaltetem Code (oft durch Codeanalysetools wie FxCop erzwungen), dass Klassenkonstruktoren keine virtuellen Methoden aufrufen dürfen. Der Grund hierfür ist, dass Konstruktoren als Basisinitialisierung eines abgeleiteten Klassenkonstruktors aufgerufen werden können. Außerdem erfolgt der Eintritt in die virtuelle Methode über den Konstruktor möglicherweise bei einem unvollständigen Initialisierungszustand der erstellten Objektinstanz. Wenn Sie von einer Klasse ableiten, die bereits von <xref:System.Windows.DependencyObject>abgeleitet ist, sollten Sie beachten, dass das Eigenschaften System selbst aufruft und virtuelle Methoden intern verfügbar macht. Diese virtuellen Methoden sind Teil der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Dienste für das Eigenschaftensystem. Das Überschreiben der Methoden ermöglicht abgeleiteten Klassen,beim Festlegen von Werten teilzunehmen. Sie sollten die Werte der Abhängigkeitseigenschaft innerhalb von Klassenkonstruktoren nicht festlegen, solange Sie keinem sehr spezifischen Konstruktormuster folgen, um potentielle Probleme bei der Initialisierung der Runtime zu vermeiden. Weitere Informationen finden Sie unter [Sichere Konstruktormuster für DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md).

## <a name="see-also"></a>Siehe auch

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Abhängigkeitseigenschaften vom Auflistungstyp](collection-type-dependency-properties.md)
- [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md)
- [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md)
- [Sichere Konstruktormuster für DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md)
