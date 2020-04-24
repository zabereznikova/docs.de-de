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
ms.openlocfilehash: e4117d7add2a34d6d989d9222e7688361cf6b379
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646358"
---
# <a name="custom-dependency-properties"></a>Benutzerdefinierte Abhängigkeitseigenschaften

Dieses Thema beschreibt die Gründe, warum Anwendungsentwickler und Komponentenautoren in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] benutzerdefinierte Abhängigkeitseigenschaften erstellen möchten, und beschreibt die Implementierungsmaßnahmen und -optionen, die die Leistung, Verwendbarkeit oder Vielseitigkeit der Eigenschaft verbessern können.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Voraussetzungen

In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen auskennen, und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] vertraut sein und wissen, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen geschrieben werden.

<a name="whatis"></a>

## <a name="what-is-a-dependency-property"></a>Was ist eine Abhängigkeitseigenschaft?

Sie können eine andernfalls CLR-Eigenschaft (Common Language Runtime) aktivieren, um Styling, Datenbindung, Vererbung, Animationen und Standardwerte zu unterstützen, indem Sie sie als Abhängigkeitseigenschaft implementieren. Abhängigkeitseigenschaften sind Eigenschaften, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beim Eigenschaftensystem durch Aufrufen der <xref:System.Windows.DependencyProperty.Register%2A> Methode (oder <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>) registriert werden und die durch ein <xref:System.Windows.DependencyProperty> Bezeichnerfeld unterstützt werden. Abhängigkeitseigenschaften können nur <xref:System.Windows.DependencyObject> von <xref:System.Windows.DependencyObject> Typen verwendet werden, sind jedoch in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassenhierarchie recht hoch, sodass die meisten in verfügbaren Klassen Abhängigkeitseigenschaften unterstützen können. Weitere Informationen zu Abhängigkeitseigenschaften und einigen der Terminologie und Konventionen, die für deren Beschreibung in diesem SDK verwendet werden, finden Sie unter Übersicht über [Abhängigkeitseigenschaften](dependency-properties-overview.md).

<a name="example_dp"></a>

## <a name="examples-of-dependency-properties"></a>Beispiele für Abhängigkeitseigenschaften

Beispiele für Abhängigkeitseigenschaften, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die <xref:System.Windows.Controls.Control.Background%2A> für Klassen <xref:System.Windows.FrameworkElement.Width%2A> implementiert werden, sind unter anderem die Eigenschaft, die Eigenschaft und die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft. Jede Abhängigkeitseigenschaft, die von einer Klasse <xref:System.Windows.DependencyProperty> verfügbar gemacht wird, verfügt über ein entsprechendes öffentliches statisches Feld vom Typ, das für dieselbe Klasse verfügbar gemacht wird. Es handelt sich um den Bezeichner für die Abhängigkeitseigenschaft. Der Name des Bezeichners wird nach einer Konvention gewählt: Der Name der Abhängigkeitseigenschaft mit der angefügten Zeichenfolge `Property`. Das entsprechende <xref:System.Windows.DependencyProperty> Bezeichnerfeld <xref:System.Windows.Controls.Control.Background%2A> für <xref:System.Windows.Controls.Control.BackgroundProperty>die Eigenschaft lautet z. B. . Der Bezeichner speichert die Informationen über die Abhängigkeitseigenschaft, wie sie registriert wurde, und <xref:System.Windows.DependencyObject.SetValue%2A>der Bezeichner wird später für andere Vorgänge verwendet, die die Abhängigkeitseigenschaft betreffen, z. B. aufrufen .

Wie in der Übersicht über [Abhängigkeitseigenschaften](dependency-properties-overview.md)erwähnt, sind alle Abhängigkeitseigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (mit Ausnahme der meisten angefügten Eigenschaften) aufgrund der "wrapper"-Implementierung ebenfalls CLR-Eigenschaften. Daher können Sie aus Code Abhängigkeitseigenschaften abrufen oder festlegen, indem Sie CLR-Accessoren aufrufen, die die Wrapper auf die gleiche Weise definieren, wie Sie andere CLR-Eigenschaften verwenden würden. Als Consumer etablierter Abhängigkeitseigenschaften verwenden Sie <xref:System.Windows.DependencyObject> <xref:System.Windows.DependencyObject.GetValue%2A> in <xref:System.Windows.DependencyObject.SetValue%2A>der Regel nicht die Methoden und , die den Verbindungspunkt zum zugrunde liegenden Eigenschaftensystem darstellen. Vielmehr wird die vorhandene Implementierung der CLR-Eigenschaften <xref:System.Windows.DependencyObject.GetValue%2A> bereits aufgerufen haben und <xref:System.Windows.DependencyObject.SetValue%2A> innerhalb der `get` und `set` wrapper Implementierungen der Eigenschaft, mit dem Bezeichnerfeld entsprechend. Wenn Sie eine benutzerdefinierte Abhängigkeitseigenschaft selbst implementieren, definieren Sie den Wrapper auf ähnliche Weise.

<a name="backing_with_dp"></a>

## <a name="when-should-you-implement-a-dependency-property"></a>Wann sollten Sie eine Abhängigkeitseigenschaft implementieren?

Wenn Sie eine Eigenschaft für eine Klasse implementieren, haben <xref:System.Windows.DependencyObject>Sie die Möglichkeit, ihre Eigenschaft <xref:System.Windows.DependencyProperty> mit einem Bezeichner zu unterstützen und sie somit zu einer Abhängigkeitseigenschaft zu machen. Es ist nicht immer notwendig oder angemessen, Ihre Eigenschaft in eine Abhängigkeitseigenschaft umzuwandeln. Es hängt von den Anforderungen Ihres Szenarios ab. Manchmal ist die normale Technik des Sicherns der Eigenschaft mit einem privaten Feld ausreichend. Sie sollten Ihre Eigenschaft allerdings als Abhängigkeitseigenschaft implementieren, wenn Sie möchten, dass Ihre Eigenschaft eine oder mehrere der folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen unterstützt:

- Sie möchten, dass Ihre Eigenschaft in einem Stil festgelegt werden kann. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

- Sie möchten, dass die Eigenschaft Datenbindung unterstützt. Weitere Informationen zur Datenbindung mit Abhängigkeitseigenschaften finden Sie unter [Binden der Eigenschaften von zwei Steuerelementen](../data/how-to-bind-the-properties-of-two-controls.md).

- Sie möchten, dass die Eigenschaft mit einem dynamischen Ressourcenverweis festgelegt werden kann. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

- Sie möchten einen Eigenschaftswert automatisch von einem übergeordneten Element in der Elementstruktur erben. Registrieren Sie sich in <xref:System.Windows.DependencyProperty.RegisterAttached%2A> diesem Fall bei der Methode, auch wenn Sie auch einen Eigenschaftenwrapper für den CLR-Zugriff erstellen. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).

- Sie möchten, dass Ihre Eigenschaft animiert werden kann. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).

- Sie möchten, dass das Eigenschaftensystem berichtet, wenn der vorherige Wert der Eigenschaft durch Aktionen des Eigenschaftensystems, der Umgebung, des Benutzers oder durch Lesen und Verwenden von Stilen geändert wurde. Mithilfe von Eigenschaftenmetadaten kann Ihre Eigenschaft eine Rückrufmethode angeben, die jedes Mal aufgerufen wird, wenn das Eigenschaftensystem feststellt, dass der Eigenschaftswert eindeutig geändert wurde. Ein verwandtes Konzept ist die Koersion des Eigenschaftswerts. Weitere Informationen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](dependency-property-callbacks-and-validation.md).

- Sie möchten geltende Konventionen für Metadaten verwenden, die auch von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Vorgängen verwendet werden, z.B. der Bericht, ob das Layoutsystem aufgrund eines geänderten Eigenschaftswerts die visuellen Objekte für ein Element neu aufbauen soll. Oder Sie möchten Überschreibungen von Metadaten verwenden, sodass abgeleitete Klassen auf Metadaten basierende Eigenschaften, z.B. den Standardwert, ändern können.

- Eigenschaften eines benutzerdefinierten Steuerelements sollen Visual Studio WPF **Properties** Designer unterstützungserhalten, z. B. Eigenschaftenfensterbearbeitung. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).

Wenn Sie diese Szenarios untersuchen, sollten Sie auch bedenken, ob Sie Ihr Szenario erreichen können, indem Sie die Metadaten einer vorhandenen Abhängigkeitseigenschaft überschreiben, anstatt eine völlig neue Eigenschaft zu implementieren. Ob die Überschreibung von Metadaten sinnvoll ist hängt von Ihrem Szenario ab und wie sehr dieses Szenario der Implementierung vorhandener [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Abhängigkeitseigenschaften und -Klassen ähnelt. Weitere Informationen zum Überschreiben der Metadaten von vorhandenen Eigenschaften finden Sie unter [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).

<a name="checklist"></a>

## <a name="checklist-for-defining-a-dependency-property"></a>Prüfliste für die Definition einer Abhängigkeitseigenschaft

Das Definieren einer Abhängigkeitseigenschaft besteht aus vier unterschiedlichen Konzepten. Diese Konzepte sind nicht unbedingt aufeinanderfolgende Schritte, da einige von ihnen am Ende als einzelne Codezeilen in der Implementierung kombiniert werden:

- (Optional) Erstellen Sie Eigenschaftsmetadaten für die Abhängigkeitseigenschaft.

- Registrieren Sie den Eigenschaftennamen im Eigenschaftensystem, indem Sie einen Besitzertyp und den Typ des Eigenschaftswerts angeben. Geben Sie, falls verwendet, auch die Metadaten der Eigenschaft an.

- Definieren <xref:System.Windows.DependencyProperty> Sie einen `public` `static` `readonly` Bezeichner als Feld für den Besitzertyp.

- Definieren Sie eine CLR-Eigenschaft "wrapper", deren Name mit dem Namen der Abhängigkeitseigenschaft übereinstimmt. Implementieren Sie die CLR-Eigenschaft `get` "wrapper" und `set` Accessoren, um eine Verbindung mit der Abhängigkeitseigenschaft herzustellen, die sie unterstützt.

<a name="registering"></a>

### <a name="registering-the-property-with-the-property-system"></a>Registrieren der Eigenschaft im Eigenschaftensystem

Damit Ihre Eigenschaft zu einer Abhängigkeitseigenschaft wird, müssen Sie diese Eigenschaft in einer Tabelle im Eigenschaftensystem registrieren und einen eindeutigen Bezeichner angeben. Dieser wird als Qualifizierer für spätere Vorgänge im Eigenschaftensystem verwendet. Bei diesen Vorgängen kann es sich um interne Vorgänge oder eigene Codeaufrufeigenschaftensystem-APIs handelt. Um die Eigenschaft zu <xref:System.Windows.DependencyProperty.Register%2A> registrieren, rufen Sie die Methode innerhalb des Körpers Ihrer Klasse auf (innerhalb der Klasse, jedoch außerhalb von Memberdefinitionen). Das Bezeichnerfeld wird <xref:System.Windows.DependencyProperty.Register%2A> auch vom Methodenaufruf als Rückgabewert bereitgestellt. Der Grund <xref:System.Windows.DependencyProperty.Register%2A> dafür, dass der Aufruf außerhalb anderer Memberdefinitionen erfolgt, `public` `static` `readonly` liegt darin, dass Sie diesen Rückgabewert verwenden, um ein Feld vom Typ als Teil Ihrer Klasse zuzuweisen und zu <xref:System.Windows.DependencyProperty> erstellen. Das Feld wird zum Bezeichner für Ihre Abhängigkeitseigenschaft.

[!code-csharp[WPFAquariumSln#RegisterAG](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
[!code-vb[WPFAquariumSln#RegisterAG](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]

<a name="nameconventions"></a>

### <a name="dependency-property-name-conventions"></a>Namenskonventionen für Abhängigkeitseigenschaften

Es gibt Namenskonventionen für Abhängigkeitseigenschaften, die Sie bis auf bestimmte Ausnahmefälle befolgen müssen.

Die Abhängigkeitseigenschaft selbst hat einen grundlegenden Namen, "AquariumGraphic", wie in diesem <xref:System.Windows.DependencyProperty.Register%2A>Beispiel, der als erster Parameter von angegeben wird. Dieser Name muss innerhalb jedes Registrierungstyps eindeutig sein. Abhängigkeitseigenschaften, die über Basistypen geerbt werden, gelten bereits als teil des Registrierungstyps. Namen von geerbten Eigenschaften können nicht erneut registriert werden. Es gibt jedoch ein Verfahren zum Hinzufügen von Klassen als Besitzer einer Abhängigkeitseigenschaft, sogar wenn diese Abhängigkeitseigenschaft nicht geerbt ist. Weitere Informationen hierzu finden Sie unter [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).

Geben Sie einem Bezeichnerfeld beim Erstellen den Namen der Eigenschaft bei der Registrierung und das Suffix `Property`. Dieses Feld ist Ihr Bezeichner für die Abhängigkeitseigenschaft und <xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.DependencyObject.GetValue%2A> wird später als Eingabe für die und Aufrufe verwendet, die Sie in den Wrappern, durch jeden anderen Codezugriff auf die Eigenschaft durch Ihren eigenen Code, durch jeden externen Codezugriff, den Sie zulassen, durch das Eigenschaftensystem und möglicherweise durch [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessoren vornehmen.

> [!NOTE]
> Die übliche Implementierung ist das Definieren der Abhängigkeitseigenschaft im Text einer Klasse. Es ist aber auch möglich, eine Abhängigkeitseigenschaft im statischen Konstruktor der Klasse zu definieren. Diese Vorgehensweise kann sinnvoll sein, wenn Sie mehr als eine Codezeile benötigen, um die Abhängigkeitseigenschaft zu initialisieren.

<a name="wrapper1"></a>

### <a name="implementing-the-wrapper"></a>Implementieren des „Wrappers“

Ihre Wrapperimplementierung <xref:System.Windows.DependencyObject.GetValue%2A> sollte `get` in der <xref:System.Windows.DependencyObject.SetValue%2A> Implementierung `set` und in der Implementierung aufrufen (der ursprüngliche Registrierungsaufruf und das Feld werden auch hier zur Übersichtlichkeit angezeigt).

In allen außer außergewöhnlichen Umständen sollten Ihre <xref:System.Windows.DependencyObject.GetValue%2A> Wrapperimplementierungen nur die und <xref:System.Windows.DependencyObject.SetValue%2A> Aktionen ausführen. Der Grund hierfür wird im Thema [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md) erläutert.

Alle vorhandenen öffentlichen Abhängigkeitseigenschaften, die für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen zur Verfügung stehen, verwenden dieses einfache Modell der Wrapper-Implementierung. Ein Großteil der komplexen Funktionsweise von Abhängigkeitseigenschaften ist entweder ein grundsätzliches Verhalten des Eigenschaftensystems oder wird durch andere Konzepte wie Koersion oder Rückrufe für Eigenschaftenänderungen durch Eigenschaftenmetadaten implementiert.

[!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
[!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]

Auch hier muss der Name der Wrappereigenschaft konventionell mit dem gewählten Namen identisch <xref:System.Windows.DependencyProperty.Register%2A> sein und als erster Parameter des Aufrufs angegeben werden, der die Eigenschaft registriert hat. Wenn die Eigenschaft den Konventionen nicht folgt, werden dadurch nicht unbedingt alle möglichen Verwendungsarten deaktiviert, aber Sie werden mehrere deutliche Probleme bemerken:

- Bestimmte Aspekte von Stilen und Vorlagen funktionieren nicht.

- Die meisten Tools und Designer verlassen sich auf Benennungskonventionen, um [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ordnungsgemäß zu serialisieren oder um Unterstützung für eine Entwicklerumgebung auf Ebene einzelner Eigenschaften zu bieten.

- Die aktuelle Implementierung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] des Ladevorgangs umgeht die Wrapper vollständig und basiert bei der Verarbeitung von Attributwerten auf der Namenskonvention. Weitere Informationen finden Sie unter [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md).

<a name="metadata"></a>

### <a name="property-metadata-for-a-new-dependency-property"></a>Eigenschaftsmetadaten für eine neue Abhängigkeitseigenschaft

Wenn Sie eine Abhängigkeitseigenschaft registrieren, wird bei der Registrierung über das Eigenschaftensystem ein Metadatenobjekt erstellt, das Merkmale der Eigenschaft speichert. Viele dieser Merkmale weisen Standardwerte auf, die festgelegt sind, <xref:System.Windows.DependencyProperty.Register%2A>wenn die Eigenschaft mit den einfachen Signaturen von registriert ist. Mit <xref:System.Windows.DependencyProperty.Register%2A> anderen Signaturen können Sie die Metadaten angeben, die Sie beim Registrieren der Eigenschaft verwenden möchten. Die häufigste Art von Metadaten für Abhängigkeitseigenschaften ist ein Standardwert, der für jede neue Instanz angegeben wird, die diese Eigenschaft verwendet.

Wenn Sie eine Abhängigkeitseigenschaft erstellen, die <xref:System.Windows.FrameworkElement>für eine abgeleitete Klasse <xref:System.Windows.FrameworkPropertyMetadata> von vorhanden <xref:System.Windows.PropertyMetadata> ist, können Sie die spezialisiertere Metadatenklasse anstelle der Basisklasse verwenden. Der Konstruktor <xref:System.Windows.FrameworkPropertyMetadata> für die Klasse verfügt über mehrere Signaturen, in denen Sie verschiedene Metadatenmerkmale in Kombination angeben können. Wenn Sie nur den Standardwert angeben möchten, verwenden Sie <xref:System.Object>die Signatur, die einen einzelnen Parameter vom Typ annimmt. Übergeben Sie diesen Objektparameter als typspezifischen Standardwert für Ihre Eigenschaft (der angegebene `propertyType` Standardwert <xref:System.Windows.DependencyProperty.Register%2A> muss der Typ sein, den Sie als Parameter im Aufruf angegeben haben).

Für <xref:System.Windows.FrameworkPropertyMetadata>können Sie auch Metadatenoptionsflags für Ihre Eigenschaft angeben. Diese Flags werden nach der Registrierung in diskrete Eigenschaften auf den Eigenschaftenmetadaten konvertiert und werden verwendet, um bestimmte Bedingungen an andere Prozesse zu kommunizieren, z.B. an die Layout-Engine.

#### <a name="setting-appropriate-metadata-flags"></a>Festlegen von Flags für die entsprechenden Metadaten

- Wenn sich Ihre Eigenschaft (oder Änderungen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]ihres Wertes) auf die auswirkt und insbesondere die Größe des Layoutsystems anoder <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure> <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>das <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>Element auf einer Seite rendert, legen Sie eines oder mehrere der folgenden Flags fest: , , .

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>gibt an, dass eine Änderung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an dieser Eigenschaft eine Änderung des Renderns erfordert, bei der das enthaltende Objekt möglicherweise mehr oder weniger Speicherplatz innerhalb des übergeordneten Objekts benötigt. Für die Eigenschaft „Breite“ sollte beispielsweise dieses Flag festgelegt sein.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>gibt an, dass eine Änderung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an dieser Eigenschaft eine Änderung des Renderings erfordert, die normalerweise keine Änderung des dedizierten Bereichs erfordert, aber darauf hinweist, dass sich die Positionierung innerhalb des Raums geändert hat. Für die Eigenschaft „Ausrichtung“ sollte beispielsweise dieses Flag festgelegt sein.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>gibt an, dass eine andere Änderung aufgetreten ist, die sich nicht auf Layout und Kennzahl auswirkt, aber ein anderes Rendering erfordert. Ein Beispiel wäre eine Eigenschaft, die eine Farbe eines vorhandenen Elements ändert, z.B. „Hintergrund“.

  - Diese Flags werden in Metadaten häufig als ein Protokoll für Ihre eigenen Überschreibungsimplementierungen von Eigenschaftensystem oder Layoutrückrufen verwendet. Sie verfügen beispielsweise über <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> einen Rückruf, <xref:System.Windows.UIElement.InvalidateArrange%2A> der aufruft, wenn eine Eigenschaft <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> `true` der Instanz eine Wertänderung meldet und wie in ihren Metadaten vorhanden ist.

- Manche Eigenschaften können Auswirkungen auf die Merkmale des Renderings des übergeordneten Elements haben, sowohl über und unter den Änderungen der oben genannten benötigten Größe. Ein Beispiel <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> ist die Eigenschaft, die im Flow-Dokumentmodell verwendet wird, wobei Änderungen an dieser Eigenschaft die gesamter Rendering des Flussdokuments ändern können, das den Absatz enthält. Verwenden <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> oder identifizieren Sie ähnliche Fälle in Ihren eigenen Eigenschaften.

- Standardmäßig unterstützen Abhängigkeitseigenschaften die Datenbindung. Sie können die Datenbindung in Fällen bewusst deaktivieren, in denen kein realistisches Szenario für die Datenbindung besteht, oder in denen die Leistung der Datenbindung für ein großes Objekt als Problem erkannt wird.

- Standardmäßig ist die <xref:System.Windows.Data.Binding.Mode%2A> Datenbindung für <xref:System.Windows.Data.BindingMode.OneWay>Abhängigkeitseigenschaften standardmäßig auf . Sie können die Bindung <xref:System.Windows.Data.BindingMode.TwoWay> jederzeit so ändern, dass sie pro Bindungsinstanz angezeigt wird. Weitere Informationen finden Sie unter [Angeben der Richtung der Bindung](../data/how-to-specify-the-direction-of-the-binding.md). Als Autor der Abhängigkeitseigenschaft können Sie jedoch <xref:System.Windows.Data.BindingMode.TwoWay> festlegen, dass die Eigenschaft standardmäßig den Bindungsmodus verwendet. Ein Beispiel für eine <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>vorhandene Abhängigkeitseigenschaft ist ; Das Szenario für diese <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> Eigenschaft besteht darin, dass <xref:System.Windows.Controls.MenuItem> die Einstellungslogik und das Kompotieren von interagieren mit dem Standarddesignstil. Die <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> Eigenschaftenlogik verwendet die Datenbindung nativ, um den Status der Eigenschaft in Übereinstimmung mit anderen Statuseigenschaften und Methodenaufrufen beizubehalten. Eine weitere Beispieleigenschaft, die standardmäßig gebunden <xref:System.Windows.Data.BindingMode.TwoWay> wird, ist <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>.

- Sie können die Eigenschaftenvererbung in einer <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> benutzerdefinierten Abhängigkeitseigenschaft auch aktivieren, indem Sie das Flag festlegen. Eigenschaftenvererbung eignet sich für ein Szenario, in dem übergeordnete und untergeordnete Elemente über eine gemeinsame Eigenschaft verfügen und es sinnvoll ist, dass das untergeordnete Element diesen bestimmten Eigenschaftswert auf den gleichen Wert wie das übergeordnete Element festlegt. Eine vererbbare Beispieleigenschaft ist <xref:System.Windows.FrameworkElement.DataContext%2A>, die für Bindungsvorgänge verwendet wird, um das wichtige Masterdetailszenario für die Datenpräsentation zu aktivieren. Indem <xref:System.Windows.FrameworkElement.DataContext%2A> alle untergeordneten Elemente vererbbar werden, erben sie auch diesen Datenkontext. Aufgrund der Vererbung von Eigenschaftswerten können Sie einen Datenkontext am Seiten- oder Anwendungsstamm angeben, und müssen ihn nicht für Bindungen in allen möglichen untergeordneten Elementen neu angeben. <xref:System.Windows.FrameworkElement.DataContext%2A>ist auch ein gutes Beispiel, um zu veranschaulichen, dass die Vererbung den Standardwert überschreibt, aber er kann immer lokal für ein bestimmtes untergeordnetes Element festgelegt werden. Weitere Informationen finden Sie unter [Verwenden des Master-Detail-Musters mit hierarchischen Daten](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). Die Vererbung von Eigenschaftswerten kann zu Leistungseinbußen führen und sollte deswegen nur sparsam eingesetzt werden. Weitere Informationen hierzu finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).

- Legen <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> Sie das Flag fest, um anzugeben, ob Ihre Abhängigkeitseigenschaft von Navigationsjournaldiensten erkannt oder verwendet werden soll. Ein Beispiel <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> ist die Eigenschaft; Jedes Element, das in einem Auswahlsteuerelement ausgewählt wurde, sollte beibehalten werden, wenn der Journalverlauf navigiert wird.

<a name="RODP"></a>

## <a name="read-only-dependency-properties"></a>Schreibgeschützte Abhängigkeitseigenschaften

Sie können eine Abhängigkeitseigenschaft definieren, die schreibgeschützt ist. Allerdings unterscheiden sich die Szenarios, warum Sie eine Eigenschaft als schreibgeschützt definieren sollen. Dies ist auch beim Registrieren mit dem Eigenschaftensystem und Verfügbar machen des Bezeichners der Fall. Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](read-only-dependency-properties.md).

<a name="CTDP"></a>

## <a name="collection-type-dependency-properties"></a>Abhängigkeitseigenschaften vom Auflistungstyp

Bei Abhängigkeitseigenschaften vom Auflistungstyp gibt es zusätzliche Implementierungsprobleme, die man berücksichtigen sollte. Weitere Informationen finden Sie unter [Abhängigkeitseigenschaften vom Auflistungstyp](collection-type-dependency-properties.md).

<a name="SecurityC"></a>

## <a name="dependency-property-security-considerations"></a>Überlegungen zur Sicherheit von Abhängigkeitseigenschaften

Abhängigkeitseigenschaften sollten als öffentliche Eigenschaften deklariert werden. Bezeichnerfelder für Abhängigkeitseigenschaften sollten als öffentliche statische Felder deklariert werden. Auch wenn Sie versuchen, andere Zugriffsebenen (z. B. geschützt) zu deklarieren, kann immer über den Bezeichner in Kombination mit den Eigenschaftensystem-APIs auf eine Abhängigkeitseigenschaft zugegriffen werden. Sogar ein geschütztes Bezeichnerfeld ist aufgrund von Metadatenberichten oder Wertermittlungs-APIs, die Teil des Eigenschaftensystems sind, wie <xref:System.Windows.LocalValueEnumerator>z. B. zugänglich. Weitere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md).

<a name="DPCtor"></a>

## <a name="dependency-properties-and-class-constructors"></a>Abhängigkeitseigenschaften und Klassenkonstruktoren

Es ist ein allgemeines Prinzip für das Programmieren von verwaltetem Code (oft durch Codeanalysetools wie FxCop erzwungen), dass Klassenkonstruktoren keine virtuellen Methoden aufrufen dürfen. Der Grund hierfür ist, dass Konstruktoren als Basisinitialisierung eines abgeleiteten Klassenkonstruktors aufgerufen werden können. Außerdem erfolgt der Eintritt in die virtuelle Methode über den Konstruktor möglicherweise bei einem unvollständigen Initialisierungszustand der erstellten Objektinstanz. Wenn Sie von einer Klasse ableiten, <xref:System.Windows.DependencyObject>die bereits von ableitet, sollten Sie sich bewusst sein, dass das Eigenschaftensystem selbst virtuelle Methoden intern aufruft und verfügbar macht. Diese virtuellen Methoden sind Teil der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Dienste für das Eigenschaftensystem. Das Überschreiben der Methoden ermöglicht abgeleiteten Klassen,beim Festlegen von Werten teilzunehmen. Sie sollten die Werte der Abhängigkeitseigenschaft innerhalb von Klassenkonstruktoren nicht festlegen, solange Sie keinem sehr spezifischen Konstruktormuster folgen, um potentielle Probleme bei der Initialisierung der Runtime zu vermeiden. Weitere Informationen finden Sie unter [Sichere Konstruktormuster für DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md).

## <a name="see-also"></a>Siehe auch

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Abhängigkeitseigenschaften vom Auflistungstyp](collection-type-dependency-properties.md)
- [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md)
- [Laden von XAML und Abhängigkeitseigenschaften](xaml-loading-and-dependency-properties.md)
- [Sichere Konstruktormuster für DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md)
