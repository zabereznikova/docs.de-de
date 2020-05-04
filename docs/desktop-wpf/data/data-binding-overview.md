---
title: Übersicht über Datenbindung
description: Erfahren Sie mehr über die verschiedenen Datenquellen, die Sie Ihrem Projekt in Windows Presentation Foundation für .NET Core hinzufügen können. Datenquellen können an XAML-Elemente gebunden werden, um dynamische Apps zu erstellen.
author: thraka
ms.date: 09/19/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7f17ff094a35c04ba880c87c6966d7d249817516
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433253"
---
# <a name="data-binding-overview-in-wpf"></a>Übersicht über die Datenbindung in WPF

Die Datenbindung in Windows Presentation Foundation (WPF) bietet für Apps eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können in Form von .NET-Objekten und XML an Daten aus einer Vielzahl von Datenquellen gebunden werden. <xref:System.Windows.Controls.ContentControl> wie <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.ItemsControl> wie <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ListView> verfügen über integrierte Funktionen, die eine flexible Formatierung von einzelnen Datenelementen oder Auflistungen von Datenelementen ermöglichen. Sortier-, Filter- und Gruppenansichten können übergreifend für die Daten generiert werden.

Die Datenbindungsfunktionen in WPF bieten gegenüber herkömmlichen Modellen einige Vorteile. Dazu zählen die grundsätzliche Unterstützung der Datenbindung durch eine breite Palette von Eigenschaften, eine flexible Darstellung von Daten auf der Benutzeroberfläche sowie die klare Trennung zwischen Geschäftslogik und Benutzeroberfläche.

In diesem Artikel werden zunächst die grundlegenden Konzepte der WPF-Datenbindung erläutert und anschließend die Verwendung der <xref:System.Windows.Data.Binding>-Klasse und anderer Datenbindungsfunktionen beschrieben.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>Was ist Datenbindung?

Durch Datenbindung wird eine Verbindung zwischen der Benutzeroberfläche der App und den dort angezeigten Daten hergestellt. Wenn die Bindungseinstellungen korrekt sind und bei einer Änderung des Werts ordnungsgemäße Benachrichtigungen ausgegeben werden, werden die Elemente, die an die Daten gebunden sind, automatisch aktualisiert. Datenbindung kann auch bedeuten, dass bei einer Änderung der äußeren Darstellung von Daten in einem Element die zugrunde liegenden Daten automatisch aktualisiert werden können, um die Änderung wiederzugeben. Wenn der Benutzer beispielsweise den Wert in einem `TextBox`-Element bearbeitet, wird der zugrunde liegende Datenwert automatisch aktualisiert, um diese Änderung anzuzeigen.

Eine typische Verwendung der Datenbindung wäre, die auf einem Server oder lokal gespeicherten Konfigurationsdaten in Formulare oder andere Steuerelemente der Benutzeroberfläche einzufügen. In WPF wird dieses Konzept dahingehend erweitert, dass auch eine Vielzahl von Eigenschaften an die unterschiedlichsten Datenquellen gebunden werden können. In WPF können Abhängigkeitseigenschaften von Elementen an .NET-Objekte (einschließlich ADO.NET-Objekte oder Objekte, die Webdiensten und Webeigenschaften zugeordnet sind) und XML-Daten gebunden werden.

Ein Beispiel für eine Datenbindung sehen Sie auf der folgenden App-Benutzeroberfläche aus der [Demo für die Datenbindung][data-binding-demo], die eine Liste von Auktionselementen zeigt.

![Screenshot des Datenbindungsbeispiels](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

Die App veranschaulicht die folgenden Datenbindungsfunktionen:

- Der Inhalt von „ListBox“ ist an eine Auflistung von *AuctionItem*-Objekten gebunden. Ein *AuctionItem*-Objekt verfügt über Eigenschaften wie *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* usw.

- Die Daten (*AuctionItem*-Objekte), die in `ListBox` angezeigt werden, sind vorlagenbasiert, sodass für jedes Element Beschreibung und aktueller Preis zu sehen sind. Die Vorlage wird mithilfe von <xref:System.Windows.DataTemplate> erstellt. Darüber hinaus hängt die Darstellung jedes Elements vom *SpecialFeatures*-Wert des angezeigten *AuctionItem* ab. Wenn der *SpecialFeatures*-Wert von *AuctionItem* auf *Color* festgelegt ist, hat das Element einen blauen Rahmen. Wenn der Wert *Highlight* ist, hat das Element einen orangefarbenen Rahmen und einen Stern. Im Abschnitt [Datenvorlagen](#data-templating) erhalten Sie weitere Informationen zu Datenvorlagen.

- Der Benutzer kann die Daten mithilfe der bereitgestellten Kontrollkästchen (`CheckBoxes`) gruppieren, filtern oder sortieren. Im oben gezeigten Bild sind die Kontrollkästchen (`CheckBoxes`) **Group by category** und **Sort by category and date** aktiviert. Möglicherweise haben Sie bereits bemerkt, dass die Daten nach der Kategorie des Produkts gruppiert sind und der Name der Kategorie in alphabetischer Reihenfolge aufgeführt ist. In der Abbildung ist nicht so gut zu erkennen, dass auch die Elemente innerhalb der einzelnen Kategorien nach Startdatum sortiert sind. Zur Sortierung wird eine *Auflistungsansicht* verwendet. Im Abschnitt [Binden an Auflistungen](#binding-to-collections) werden Auflistungsansichten erläutert.

- Wenn der Benutzer ein Element auswählt, werden in <xref:System.Windows.Controls.ContentControl> die Einzelheiten zum ausgewählten Element angezeigt. Dieses Verhalten wird als *Master/Detail-Szenario* bezeichnet. Im Abschnitt [Master/Detail-Szenario](#master-detail-binding-scenario) erhalten Sie Informationen zu diesem Bindungstyp.

- Der Typ der *StartDate*-Eigenschaft ist <xref:System.DateTime>, wodurch ein Datum mit der Zeit bis auf die Millisekunde genau zurückgegeben wird. In dieser App wurde ein benutzerdefinierter Konverter verwendet, damit eine kürzere Datumszeichenfolge angezeigt wird. Weitere Informationen zu Konvertern finden Sie im Abschnitt [Datenkonvertierung](#data-conversion).

Wenn der Benutzer die Schaltfläche *Add Product* auswählt, wird das folgende Formular aufgerufen.

![Seite „Add Product Listing“](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

Der Benutzer kann die Felder im Formular bearbeiten, die Produktauflistung in der Kurzvorschau oder der detaillierten Vorschau anzeigen und `Submit` auswählen, um die neue Produktauflistung hinzuzufügen. Alle vorhandenen Gruppierungs-, Filter- und Sortiereinstellungen werden auf den neuen Eintrag angewendet. In diesem speziellen Fall wird das im obigen Bild eingegebene Element in der Kategorie *Computer* an zweiter Stelle angezeigt.

Was in diesem Bild nicht angezeigt wird, ist die im <xref:System.Windows.Controls.TextBox>-Element *Start Date* bereitgestellte Validierungslogik. Wenn der Benutzer ein ungültiges Datum eingibt (mit ungültiger Formatierung oder ein Datum in der Vergangenheit), wird er durch einen <xref:System.Windows.Controls.ToolTip> und ein rotes Ausrufezeichen neben dem <xref:System.Windows.Controls.TextBox> benachrichtigt. Im Abschnitt [Datenvalidierung](#data-validation) wird näher auf das Erstellen von Validierungslogik eingegangen.

Bevor die oben genannten unterschiedlichen Datenbindungsfunktionen näher erläutert werden, wird zunächst auf die grundlegenden Konzepte eingegangen, die für ein Verständnis der WPF-Datenbindung unerlässlich sind.

## <a name="basic-data-binding-concepts"></a>Grundlegende Konzepte der Datenbindung

Unabhängig davon, welches Element Sie binden und welcher Art die Datenquelle ist, erfolgt die Bindung stets gemäß dem in der folgenden Abbildung gezeigten Modell.

![Diagramm zur Veranschaulichung des grundlegenden Datenbindungsmodells](./media/data-binding-overview/basic-data-binding-diagram.png)

Wie in der Abbildung gezeigt, ist die Datenbindung die Brücke zwischen dem Bindungsziel und der Bindungsquelle. Die Abbildung veranschaulicht die folgenden grundlegenden Konzepte der WPF-Datenbindung:

- Eine Bindung besteht in der Regel aus vier Komponenten:

  - Bindungszielobjekt
  - Zieleigenschaft
  - Bindungsquelle
  - Pfad zum Wert in der zu verwendenden Bindungsquelle
  
  > Angenommen, Sie möchten den Inhalt von `TextBox` an die `Employee.Name`-Eigenschaft binden. Dann ist Ihr Zielobjekt `TextBox`, die Zieleigenschaft die <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft, der zu verwendende Wert *Name* und das Quellobjekt das *Employee*-Objekt.

- Die Zieleigenschaft muss eine Abhängigkeitseigenschaft sein. Die meisten <xref:System.Windows.UIElement>-Eigenschaften sind Abhängigkeitseigenschaften, und die meisten Abhängigkeitseigenschaften, mit Ausnahme der schreibgeschützten, unterstützen standardmäßig die Datenbindung. (Nur Typen, die von <xref:System.Windows.DependencyObject> abgeleitet werden, können Abhängigkeitseigenschaften definieren, und alle <xref:System.Windows.UIElement>-Typen werden von `DependencyObject` abgeleitet.)

- Obwohl nicht in der Abbildung dargestellt, sollte beachtet werden, dass das Bindungsquellenobjekt nicht darauf beschränkt ist, als benutzerdefiniertes .NET-Objekt zu fungieren. Die WPF-Datenbindung unterstützt Daten in Form von .NET-Objekten und XML. So könnte es sich bei Ihrer Bindungsquelle beispielsweise um ein <xref:System.Windows.UIElement> handeln, ein beliebiges Listenobjekt, ein ADO.NET- oder Webdienste-Objekt oder um einen XmlNode, der Ihre XML-Daten enthält. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../../framework/wpf/data/binding-sources-overview.md).

Sie sollten daran denken, dass Sie beim Einrichten einer Bindung ein Bindungsziel *an* eine Bindungsquelle binden. Wenn Sie z. B. zugrunde liegende XML-Daten mithilfe der Datenbindung in <xref:System.Windows.Controls.ListBox> anzeigen, binden Sie `ListBox` an die XML-Daten.

Verwenden Sie zum Einrichten einer Bindung das <xref:System.Windows.Data.Binding>-Objekt. Im weiteren Verlauf dieses Artikels werden zahlreiche Konzepte zum `Binding`-Objekt, einige Eigenschaften und seine Verwendung erläutert.

### <a name="direction-of-the-data-flow"></a>Richtung des Datenflusses

Wie durch den Pfeil in der vorherigen Abbildung gezeigt, kann der Datenfluss einer Bindung vom Bindungsziel zur Bindungsquelle verlaufen (z. B. ändert sich der Quellwert, wenn ein Benutzer den Wert von `TextBox` bearbeitet) und/oder von der Bindungsquelle zum Bindungsziel (z. B. wenn der `TextBox`-Inhalt durch Änderungen in der Bindungsquelle aktualisiert wird), wenn die Bindungsquelle die entsprechenden Benachrichtigungen bereitstellt.

Sie können die App so einrichten, dass Benutzer die Daten ändern und zurück an das Quellobjekt übertragen können. Sie können auch das Aktualisieren von Quelldaten durch Benutzer unterbinden. Sie können den Datenfluss steuern, indem Sie <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>festlegen.

In dieser Abbildung werden die unterschiedlichen Datenflusstypen veranschaulicht:

![Datenfluss bei der Datenbindung](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- Die <xref:System.Windows.Data.BindingMode.OneWay>-Bindung bewirkt, dass bei Änderungen an der Quelleigenschaft die Zieleigenschaft automatisch aktualisiert wird, ohne dass Änderungen an der Zieleigenschaft an die Quelleigenschaft zurückübertragen werden. Dieser Bindungstyp empfiehlt sich, wenn das gebundene Steuerelement implizit als schreibgeschützt festgelegt wurde. Sie können beispielsweise eine Bindung an eine Quelle wie einen Börsenticker erstellen, oder möglicherweise ist für die Zieleigenschaft keine Steuerungsschnittstelle verfügbar, um Änderungen vorzunehmen, z. B. an der datengebundenen Hintergrundfarbe einer Tabelle. Wenn die Änderungen der Zieleigenschaft nicht überwacht werden müssen, vermeiden Sie mit dem <xref:System.Windows.Data.BindingMode.OneWay>-Bindungsmodus den Mehraufwand des <xref:System.Windows.Data.BindingMode.TwoWay>-Bindungsmodus.

- Die <xref:System.Windows.Data.BindingMode.TwoWay>-Bindung bewirkt, dass bei Änderungen an der Quell- bzw. der Zieleigenschaft die jeweils andere automatisch aktualisiert wird. Dieser Typ von Bindung ist für bearbeitbare Formulare und sonstige vollständig interaktive Benutzeroberflächenszenarien geeignet. Die meisten Eigenschaften sind standardmäßig auf die <xref:System.Windows.Data.BindingMode.OneWay>-Bindung festgelegt, aber einige Abhängigkeitseigenschaften (meistens Eigenschaften von Steuerelementen, die vom Benutzer bearbeitet werden können, z. B. <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> und [CheckBox.IsChecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked)) sind standardmäßig auf die <xref:System.Windows.Data.BindingMode.TwoWay>-Bindung festgelegt. Eine programmgesteuerte Methode zum Bestimmen, ob eine Abhängigkeitseigenschaft standardmäßig uni- oder bidirektional bindet, besteht darin, die Eigenschaftenmetadaten mit <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType> abzurufen und dann den booleschen Wert der <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType>-Eigenschaft zu überprüfen.

- Das Gegenteil von <xref:System.Windows.Data.BindingMode.OneWayToSource> ist die <xref:System.Windows.Data.BindingMode.OneWay>-Bindung, bei der die Quelleigenschaft aktualisiert wird, sobald die Zieleigenschaft geändert wird. Ein Beispielszenario dafür ist, wenn nur der Quellwert von der Benutzeroberfläche neu bewertet werden muss.

- In der Abbildung nicht gezeigt wird die <xref:System.Windows.Data.BindingMode.OneTime>-Bindung, die bewirkt, dass die Quelleigenschaft die Zieleigenschaft initialisiert, nachfolgende Änderungen jedoch nicht weitergegeben werden. Wenn sich der Datenkontext oder das Objekt im Datenkontext ändert, wird die Änderung in der Zieleigenschaft *nicht* angezeigt. Dieser Bindungstyp empfiehlt sich, wenn entweder eine Momentaufnahme des aktuellen Zustands verwendet werden kann oder die Daten tatsächlich statisch sind. Dieser Bindungstyp ist auch hilfreich, wenn die Zieleigenschaft mit einem bestimmten Wert der Quelleigenschaft initialisiert werden soll und der Datenkontext vorab nicht bekannt ist. Dieser Modus ist im Wesentlichen eine einfachere Form der <xref:System.Windows.Data.BindingMode.OneWay>-Bindung, die eine bessere Leistung in Situationen bietet, in denen sich der Quellwert nicht ändert.

Zum Erkennen von Quelländerungen (das gilt für die <xref:System.Windows.Data.BindingMode.OneWay>-Bindung und die <xref:System.Windows.Data.BindingMode.TwoWay>-Bindung) muss die Quelle einen geeigneten Mechanismus für Benachrichtigungen bei Eigenschaftenänderungen implementieren, z. B. <xref:System.ComponentModel.INotifyPropertyChanged>. Weitere Informationen finden Sie unter [Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../framework/wpf/data/how-to-implement-property-change-notification.md). Dort finden Sie auch ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged>-Implementierung.

Die <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>-Eigenschaft bietet weitere Informationen zu Bindungsmodi und ein Beispiel zum Angeben der Bindungsrichtung.

### <a name="what-triggers-source-updates"></a>Wodurch werden Quellaktualisierungen ausgelöst?

Bindungen vom Typ <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> überwachen die Zieleigenschaft auf Änderungen und übertragen sie zurück an die Quelle. Dies wird als Aktualisieren der Quelle bezeichnet. Sie können beispielsweise den Text eines TextBox-Elements bearbeiten, um den zugrunde liegenden Quellwert zu ändern.

Wird der Quellwert aktualisiert, während Sie den Text bearbeiten oder nachdem Sie die Bearbeitung abgeschlossen haben und das Steuerelement den Fokus verliert? Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType>-Eigenschaft bestimmt, wodurch die Aktualisierung der Quelle ausgelöst wird. Die Punkte der nach rechts weisenden Pfeile in der folgenden Abbildung veranschaulichen die Rolle der <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType>-Eigenschaft.

![Diagramm zur Veranschaulichung der Rolle der UpdateSourceTrigger-Eigenschaft](./media/data-binding-overview/data-binding-updatesource-trigger.png)

Ist der `UpdateSourceTrigger`-Wert auf <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType> festgelegt, wird der Wert, auf den mit dem nach rechts weisenden Pfeil der <xref:System.Windows.Data.BindingMode.TwoWay>-Bindung oder der <xref:System.Windows.Data.BindingMode.OneWayToSource>-Bindungen gezeigt wird, aktualisiert, sobald sich die Zieleigenschaft ändert. Ist der `UpdateSourceTrigger`-Wert hingegen auf <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> festgelegt, wird dieser Wert nur dann durch den neuen Wert aktualisiert, wenn die Zieleigenschaft den Fokus verliert.

Wie bei der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft haben verschiedene Abhängigkeitseigenschaften unterschiedliche <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Standardwerte. Der Standardwert für die meisten Abhängigkeitseigenschaften ist <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, während die `TextBox.Text`-Eigenschaft den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> aufweist. `PropertyChanged` bedeutet, dass Quellaktualisierungen in der Regel bei jeder Änderung der Zieleigenschaft erfolgen. Sofortige Änderungen sind bei Kontrollkästchen und anderen einfachen Steuerelementen unproblematisch. Bei Textfeldern kann eine Aktualisierung nach jeder Tastatureingabe jedoch die Leistung mindern und führt außerdem dazu, dass der Benutzer nicht wie gewohnt durch Drücken der Rücktaste Tippfehler beheben kann, bevor der neue Wert übergeben wird.

Auf der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Eigenschaftenseite erhalten Sie weitere Informationen zur Suche nach dem Standardwert einer Abhängigkeitseigenschaft.

In der folgenden Tabelle sehen Sie ein Beispielszenario für jeden <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Wert, wobei <xref:System.Windows.Controls.TextBox> als Beispiel verwendet wird.

| UpdateSourceTrigger-Wert | Wenn der Quellwert aktualisiert wird | Beispielszenario für TextBox |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus` (Standard für <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>) | Wenn das TextBox-Steuerelement den Fokus verliert. | Ein TextBox-Element, dem eine Validierungslogik zugeordnet ist (siehe Abschnitt [Datenvalidierung](#data-validation) weiter unten). |
| `PropertyChanged` | Während der Eingabe in <xref:System.Windows.Controls.TextBox>. | TextBox-Steuerelemente in einem Chatroomfenster. |
| `Explicit` | Wenn die App <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> aufruft. | TextBox-Steuerelemente in einem bearbeitbaren Formular (aktualisiert die Quellwerte nur dann, wenn der Benutzer auf die Schaltfläche zum Senden klickt). |

Ein Beispiel finden Sie unter [Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).

## <a name="creating-a-binding"></a>Erstellen einer Bindung

Hier noch einmal eine Wiederholung der in den vorherigen Abschnitten vorgestellten Konzepte: Sie richten eine Bindung mithilfe des <xref:System.Windows.Data.Binding>-Objekts ein. Jede Bindung besteht in der Regel aus vier Komponenten. Dies sind Bindungsziel, Zieleigenschaft, Bindungsquelle sowie ein Pfad zu dem zu verwendenden Quellwert. In diesem Abschnitt wird das Einrichten einer Bindung erläutert.

Im folgenden Beispiel ist das Bindungsquellobjekt eine Klasse namens *MyData*, die im Namespace *SDKSample* definiert ist. Zu Demonstrationszwecken weist *MyData* eine Zeichenfolgeneigenschaft namens *ColorName* auf, deren Wert auf „Red“ festgelegt ist. In diesem Beispiel wird also eine Schaltfläche mit einem roten Hintergrund erstellt.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

Weitere Informationen zur Syntax der Bindungsdeklaration und Beispiele zum Einrichten einer Bindung im Code finden Sie unter [Übersicht über Bindungsdeklarationen](../../framework/wpf/data/binding-declarations-overview.md).

Wenn dieses Beispiel auf das einfache Diagramm angewendet wird, sieht die resultierend Abbildung wie die folgende aus. Diese Abbildung zeigt eine <xref:System.Windows.Data.BindingMode.OneWay>-Bindung, da die Background-Eigenschaft standardmäßig <xref:System.Windows.Data.BindingMode.OneWay>-Bindungen unterstützt.

![Diagramm zur Veranschaulichung der Background-Eigenschaft einer Datenbindung](./media/data-binding-overview/data-binding-button-background-example.png)

Sie fragen sich vielleicht, warum diese Bindung funktioniert, obwohl die *ColorName*-Eigenschaft ein Zeichenfolgentyp ist, während die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft vom Typ <xref:System.Windows.Media.Brush> ist. Bei dieser Bindung wird die Standardtypkonvertierung verwendet, die im Abschnitt [Datenkonvertierung](#data-conversion) erläutert wird.

### <a name="specifying-the-binding-source"></a>Angeben der Bindungsquelle

Beachten Sie, dass im vorherigen Beispiel die Bindungsquelle durch Festlegen der [DockPanel.DataContext](xref:System.Windows.FrameworkElement.DataContext)-Eigenschaft angegeben wurde. <xref:System.Windows.Controls.Button> erbt dann den <xref:System.Windows.FrameworkElement.DataContext%2A>-Wert von <xref:System.Windows.Controls.DockPanel>, wobei es sich um das übergeordnete Element handelt. Das Bindungsquellobjekt stellt, wie bereits erwähnt, eine der vier erforderlichen Komponenten einer Bindung dar. Wäre das Bindungsquellobjekt nicht angegeben, hätte die Bindung keine Auswirkungen.

Es gibt mehrere Möglichkeiten, das Bindungsquellobjekt anzugeben. Die Verwendung der <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft für ein übergeordnetes Element ist hilfreich, wenn Sie mehrere Eigenschaften an dieselbe Quelle binden. Es kann aber auch zweckmäßiger sein, die Bindungsquelle in einzelnen Bindungsdeklarationen anzugeben. Im vorherigen Beispiel können Sie auch statt der <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft die Bindungsquelle angeben, indem Sie die <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>-Eigenschaft direkt in der Bindungsdeklaration der Schaltfläche festlegen. Dies wird im folgenden Beispiel gezeigt.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

Statt die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft direkt für ein Element festzulegen, den <xref:System.Windows.FrameworkElement.DataContext%2A>-Wert von einem übergeordneten Element zu erben (z. B. die Schaltfläche im ersten Beispiel) und die Bindungsquelle explizit durch Festlegen der <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>-Eigenschaft in der Bindung anzugeben (z. B. die Schaltfläche im letzten Beispiel), können Sie zum Angeben der Bindungsquelle auch die <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType>-Eigenschaft oder die <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType>-Eigenschaft verwenden. Die <xref:System.Windows.Data.Binding.ElementName%2A>-Eigenschaft ist hilfreich zum Binden an andere Elemente in der App, beispielsweise wenn Sie die Breite einer Schaltfläche mit einem Schieberegler anpassen. Die <xref:System.Windows.Data.Binding.RelativeSource%2A>-Eigenschaft bietet sich an, wenn die Bindung in <xref:System.Windows.Controls.ControlTemplate> oder <xref:System.Windows.Style> angegeben ist. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben der Bindungsquelle](../../framework/wpf/data/how-to-specify-the-binding-source.md).

### <a name="specifying-the-path-to-the-value"></a>Angeben des Pfads zum Wert

Wenn die Bindungsquelle ein Objekt ist, verwenden Sie die <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType>-Eigenschaft, um den für die Bindung zu verwendenden Wert anzugeben. Wenn Sie eine Bindung an XML-Daten vornehmen, geben Sie den Wert mithilfe der <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType>-Eigenschaft an. In einigen Fällen können Sie die <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft auch dann verwenden, wenn es sich bei den Daten um XML handelt. Angenommen, Sie möchten auf die Name-Eigenschaft eines zurückgegebenen XmlNode zugreifen (als Ergebnis einer XPath-Abfrage), dann sollten Sie die <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft zusätzlich zur <xref:System.Windows.Data.Binding.XPath%2A>-Eigenschaft verwenden.

Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft und zur <xref:System.Windows.Data.Binding.XPath%2A>-Eigenschaft.

Obwohl darauf hingewiesen wurde, dass der zu verwendende <xref:System.Windows.Data.Binding.Path%2A> zum Wert eine der vier erforderlichen Komponenten einer Bindung darstellt, ist der in den Szenarien zum Binden an ein vollständiges Objekt zu verwendende Wert mit dem Bindungsquellobjekt identisch. In einem solchen Fall muss kein <xref:System.Windows.Data.Binding.Path%2A> angegeben werden. Betrachten Sie das folgende Beispiel.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

Im obigen Beispiel wird die leere Bindungssyntax verwendet: {Binding}. In diesem Fall erbt <xref:System.Windows.Controls.ListBox> den DataContext von einem übergeordneten DockPanel-Element (was in diesem Beispiel nicht gezeigt wird). Wenn der Pfad nicht angegeben wurde, erfolgt die Bindung standardmäßig an das gesamte Objekt. Das heißt, dass der Pfad in diesem Beispiel ausgelassen wird, da die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>-Eigenschaft an das gesamte Objekt gebunden wird. (Im Abschnitt [Binden an Auflistungen](#binding-to-collections) wird ausführlich darauf eingegangen.)

Dieses Szenario ist nicht nur zum Binden an eine Auflistung hilfreich, sondern auch zum Binden an ein vollständiges Objekt statt nur an eine einzelne Eigenschaft eines Objekts. Wenn es sich beim Quellobjekt beispielsweise um den Typ <xref:System.String> handelt, möchten Sie vielleicht lediglich eine Bindung an die Zeichenfolge selbst vornehmen. Ein anderes allgemeines Szenario besteht darin, ein Element an ein Objekt mit mehreren Eigenschaften zu binden.

Möglicherweise müssen Sie benutzerdefinierte Logik anwenden, damit die Daten für die gebundene Zieleigenschaft sinnvoll sind. Bei der benutzerdefinierten Logik kann es sich z. B. um einen benutzerdefinierten Konverter handeln, falls keine Standardtypkonvertierung vorhanden ist. Weitere Informationen über Konverter finden Sie unter [Datenkonvertierung](#data-conversion).

### <a name="binding-and-bindingexpression"></a>Die „Binding“-Klasse und „BindingExpression“

Bevor auf weitere Features und Verwendungsmöglichkeiten der Datenbindung eingegangen wird, ist es sinnvoll, sich mit der <xref:System.Windows.Data.BindingExpression>-Klasse zu befassen. Wie die vorherigen Abschnitte gezeigt haben, handelt es sich bei der <xref:System.Windows.Data.Binding>-Klasse um die Klasse höherer Ebene für die Deklaration einer Bindung. Diese Klasse bietet zahlreiche Eigenschaften, mit denen Sie die Merkmale einer Bindung angeben können. Die verwandte <xref:System.Windows.Data.BindingExpression>-Klasse ist das zugrunde liegende Objekt, das die Verbindung zwischen Quelle und Ziel aufrechterhält. Ein Bindung enthält sämtliche Informationen, die von mehreren Bindungsausdrücken gemeinsam genutzt werden können. <xref:System.Windows.Data.BindingExpression> ist ein Instanzenausdruck, der nicht gemeinsam genutzt werden kann und sämtliche Instanzeninformationen von <xref:System.Windows.Data.Binding> enthält.

Sehen Sie sich das folgende Beispiel an, bei dem `myDataObject` eine Instanz der `MyData`-Klasse ist, `myBinding` das Quellobjekt von <xref:System.Windows.Data.Binding> ist und `MyData` eine definierte Klasse ist, die eine Zeichenfolgeneigenschaft namens `MyDataProperty` enthält. In diesem Beispiel wird der Textinhalt von `myText`, einer Instanz von <xref:System.Windows.Controls.TextBlock>, an `MyDataProperty` gebunden.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

Mit demselben *myBinding*-Objekt können Sie auch andere Bindungen erstellen. Sie können beispielsweise mit dem *myBinding*-Objekt eine Bindung des Textinhalts eines Kontrollkästchens an *MyDataProperty* herstellen. In diesem Szenario werden zwei Instanzen von <xref:System.Windows.Data.BindingExpression> verwendet, die das *myBinding*-Objekt gemeinsam nutzen.

Ein <xref:System.Windows.Data.BindingExpression>-Objekt wird durch Aufrufen von <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> für ein datengebundenes Objekt zurückgegeben. In den folgenden Artikeln werden einige Verwendungsmöglichkeiten der <xref:System.Windows.Data.BindingExpression>-Klasse veranschaulicht:

- [Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [Steuern, wann der TextBox-Text die Quelle aktualisiert](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>Datenkonvertierung

Im Abschnitt [Erstellen einer Bindung](#creating-a-binding) ist die Schaltfläche rot, da die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft an eine Zeichenfolgeneigenschaft mit dem Wert „Red“ gebunden ist. Dieser Zeichenfolgenwert funktioniert, weil ein Typkonverter für den <xref:System.Windows.Media.Brush>-Typ vorhanden ist, mit dem der Zeichenfolgenwert in <xref:System.Windows.Media.Brush> konvertiert wird.

Wenn diese Informationen der Abbildung im Abschnitt [Erstellen einer Bindung](#creating-a-binding) hinzugefügt werden, sieht das Ergebnis folgendermaßen aus.

![Diagramm zur Veranschaulichung der Default-Eigenschaft einer Datenbindung](./media/data-binding-overview/data-binding-button-default-conversion.png)

Was geschieht jedoch, wenn keine Eigenschaft mit einem Zeichenfolgentyp vorhanden ist, sondern das Bindungsquellobjekt eine <xref:System.Windows.Media.Color>-Eigenschaft mit dem Typ *Color* aufweist? Damit in diesem Fall die Bindung funktioniert, müssten Sie den *Color*-Eigenschaftswert zuerst in einen Wert ändern, der von der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft akzeptiert wird. Dazu müssten Sie einen benutzerdefinierten Konverter erstellen, indem Sie die <xref:System.Windows.Data.IValueConverter>-Schnittstelle implementieren, wie es im folgenden Beispiel gezeigt ist.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

Weitere Informationen finden Sie unter <xref:System.Windows.Data.IValueConverter>.

Jetzt wird anstelle der Standardkonvertierung der benutzerdefinierte Konverter verwendet, und das Diagramm sieht folgendermaßen aus.

![Diagramm zur Veranschaulichung des benutzerdefinierten Konverters einer Datenbindung](./media/data-binding-overview/data-binding-converter-color-example.png)

Wie bereits ausgeführt, können aufgrund von Typkonvertern, die im Typ vorhanden sind, an den gebunden wird, Standardkonvertierungen verfügbar sein. Dieses Verhalten hängt von den im Ziel vorhandenen Typkonvertern ab. Erstellen Sie im Zweifelsfall einen eigenen Konverter.

Es folgen einige typische Szenarien, in denen die Implementierung eines Datenkonverters sinnvoll ist:

- Die Daten sollen je nach Kultur unterschiedlich angezeigt werden. Sie können z. B. einen Währungskonverter oder einen Datum-/Uhrzeitkonverter implementieren, der auf den Konventionen in einer bestimmten Kultur basiert.

- Die verwendeten Daten müssen nicht unbedingt dazu dienen, den Textwert einer Eigenschaft zu ändern. Sie können auch den Zweck haben, andere Werte zu ändern, beispielsweise die Quelle für ein Bild oder die Farbe bzw. das Format des Anzeigetexts. Konverter können in dieser Instanz verwendet werden, indem die Bindung einer Eigenschaft konvertiert wird, die ungeeignet zu sein scheint, z. B. wenn ein Textfeld an die Background-Eigenschaft einer Tabellenzelle gebunden wird.

- Mehrere Steuerelemente oder mehrere Steuerelementeigenschaften sind an dieselben Daten gebunden. In diesem Fall wird durch die primäre Bindung möglicherweise nur der Text angezeigt, wohingegen andere Bindungen bestimmte Anzeigeprobleme behandeln, aber dieselben Bindungen als Quellinformationen verwenden.

- Eine Zieleigenschaft verfügt über eine Auflistung von Bindungen. Dies wird als <xref:System.Windows.Data.MultiBinding> bezeichnet. Bei <xref:System.Windows.Data.MultiBinding> verwenden Sie einen benutzerdefinierten <xref:System.Windows.Data.IMultiValueConverter>, um einen endgültigen Wert aus den Werten der Bindungen zu generieren. So kann die Farbe beispielsweise aus roten, blauen und grünen Werten berechnet werden, die aus denselben oder anderen Bindungsquellobjekten stammen können. Beispiele und weitere Informationen finden Sie unter <xref:System.Windows.Data.MultiBinding>.

## <a name="binding-to-collections"></a>Binden an Auflistungen

Ein Bindungsquellobjekt kann entweder als einzelnes Objekt behandelt werden, dessen Eigenschaften Daten enthalten, oder als eine Datenauflistung von polymorphen Objekten, die häufig zusammen gruppiert werden (beispielsweise als Ergebnis einer Datenbankabfrage). Bisher wurde nur das Binden an einzelne Objekte behandelt. Das Binden an eine Datenauflistung ist jedoch ebenfalls ein gängiges Szenario. So besteht ein häufiges Szenario darin, ein <xref:System.Windows.Controls.ItemsControl> wie <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView> oder <xref:System.Windows.Controls.TreeView> zu verwenden, um eine Datenauflistung anzuzeigen. Ein Beispiel finden Sie in der App, die im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) verwendet wird.

Das bisherige einfache Diagramm ist praktischerweise immer noch gültig. Wenn Sie <xref:System.Windows.Controls.ItemsControl> an eine Auflistung binden, sieht das Diagramm folgendermaßen aus.

![Diagramm zur Veranschaulichung des ItemsControl-Objekts einer Datenbindung](./media/data-binding-overview/data-binding-itemscontrol.png)

Wie in diesem Diagramm gezeigt, muss zum Binden von <xref:System.Windows.Controls.ItemsControl> an ein Auflistungsobjekt die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType>-Eigenschaft verwendet werden. Sie können sich die `ItemsSource`-Eigenschaft als Inhalt von <xref:System.Windows.Controls.ItemsControl> vorstellen. Die Bindung ist <xref:System.Windows.Data.BindingMode.OneWay>, da die `ItemsSource`-Eigenschaft standardmäßig die `OneWay`-Bindung unterstützt.

### <a name="how-to-implement-collections"></a>Implementieren von Auflistungen

Sie können jede Auflistung auflisten, die die <xref:System.Collections.IEnumerable>-Schnittstelle implementiert. Um dynamische Bindungen einzurichten, bei denen die Benutzeroberfläche automatisch nach Einfügungen oder Löschungen in der Auflistung aktualisiert wird, muss die Auflistung die <xref:System.Collections.Specialized.INotifyCollectionChanged>-Schnittstelle implementieren. Diese Schnittstelle macht ein Ereignis verfügbar, das bei jeder Änderung der zugrunde liegenden Auflistung ausgelöst werden sollte.

WPF stellt die <xref:System.Collections.ObjectModel.ObservableCollection%601>-Klasse bereit, bei der es sich um die integrierte Implementierung einer Datenauflistung handelt, die die <xref:System.Collections.Specialized.INotifyCollectionChanged>-Schnittstelle verfügbar macht. Um eine vollständige Unterstützung für die Übertragung von Datenwerten von Quellobjekten zu Zielen zu gewährleisten, muss jedes Objekt in der Auflistung, die bindbare Eigenschaften unterstützt, auch die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../../framework/wpf/data/binding-sources-overview.md).

Bevor Sie eine eigene Auflistung implementieren, erwägen Sie <xref:System.Collections.ObjectModel.ObservableCollection%601> oder einer vorhandenen Sammlung Klassen, z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, und <xref:System.ComponentModel.BindingList%601>, a. Falls Sie für ein erweitertes Szenario Ihre eigene Auflistung implementieren möchten, können Sie <xref:System.Collections.IList> und somit eine nicht generische Auflistung von Objekten verwenden, auf die einzeln über den Index zugegriffen werden kann. So lässt sich eine optimale Leistung erzielen.

### <a name="collection-views"></a>Auflistungsansichten

Nachdem <xref:System.Windows.Controls.ItemsControl> an eine Datenauflistung gebunden wurde, können Sie die Daten sortieren, filtern oder gruppieren. Hierzu verwenden Sie Auflistungsansichten, bei denen es sich um Klassen handelt, die die <xref:System.ComponentModel.ICollectionView>-Schnittstelle implementieren.

#### <a name="what-are-collection-views"></a>Was sind Auflistungsansichten?

Eine Auflistungsansicht fungiert als Ebene über der Bindungsquellauflistung, in der Sie mit Sortier-, Filter- und Gruppierungsabfragen navigieren und die jeweilige Quellauflistung anzeigen können, ohne die zugrunde liegende Quellauflistung selbst ändern zu müssen. Eine Auflistungsansicht stellt außerdem einen Zeiger auf das aktuelle Element in der Auflistung zur Verfügung. Wenn die Quellauflistung die <xref:System.Collections.Specialized.INotifyCollectionChanged>-Schnittstelle implementiert, werden die vom <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>-Ereignis ausgelösten Änderungen an die Ansichten weitergegeben.

Da in Ansichten die zugrunde liegenden Quellauflistungen nicht geändert werden, können einer Quellauflistung mehrere Ansichten zugeordnet sein. Angenommen, Sie verfügen über eine Auflistung von *Task*-Objekten. Mithilfe von Ansichten können Sie dieselben Daten auf verschiedene Weise anzeigen. Beispielsweise können Sie links auf der Seite Aufgaben nach Priorität und rechts nach Bereich sortieren.

#### <a name="how-to-create-a-view"></a>Erstellen einer Ansicht

Eine Möglichkeit, eine Ansicht zu erstellen und zu verwenden, besteht darin, das Ansichtsobjekt direkt zu instanziieren und dann als Bindungsquelle zu verwenden. Betrachten Sie z. B. die App [Demo für die Datenbindung][data-binding-demo], die im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) gezeigt wird. Die App wurde so implementiert, dass <xref:System.Windows.Controls.ListBox> an eine Ansicht über die Datenauflistung gebunden wird, anstatt direkt an die Datenauflistung. Das folgende Beispiel wird aus der App [Demo für die Datenbindung][data-binding-demo] extrahiert. Die <xref:System.Windows.Data.CollectionViewSource>-Klasse ist der XAML-Proxy einer Klasse, die von <xref:System.Windows.Data.CollectionView>erbt. In diesem speziellen Beispiel ist die <xref:System.Windows.Data.CollectionViewSource.Source%2A> der Ansicht an die *AuctionItems*-Auflistung (des Typs <xref:System.Collections.ObjectModel.ObservableCollection%601>) des aktuellen Anwendungsobjekts gebunden.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

Die Ressource *listingDataView* dient dann als Bindungsquelle für Elemente in der App, z. B. <xref:System.Windows.Controls.ListBox>.

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

Wenn Sie eine weitere Ansicht für dieselbe Auflistung erstellen möchten, können Sie eine weitere <xref:System.Windows.Data.CollectionViewSource>-Instanz erstellen und ihr einen anderen `x:Key`-Namen geben.

Die folgende Tabelle zeigt, welche Ansichtsdatentypen als Standardauflistungsansicht bzw. mit <xref:System.Windows.Data.CollectionViewSource> basierend auf dem Quellauflistungstyp erstellt werden.

| Quellauflistungstyp                    | Auflistungsansichtstyp | Hinweise |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | Ein interner auf <xref:System.Windows.Data.CollectionView> basierender Typ | Kann Elemente nicht gruppieren. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | Am schnellsten. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>Verwenden einer Standardansicht

Die Angabe einer Auflistungsansicht als Bindungsquelle ist eine Möglichkeit, eine Auflistungsansicht zu erstellen und zu verwenden. WPF erstellt außerdem eine Standardauflistungsansicht für jede als Bindungsquelle verwendete Auflistung. Bei der direkten Bindung an eine Auflistung bindet WPF an die Standardansicht der Auflistung. Diese Standardansicht wird von allen Bindungen an diese Auflistung gemeinsam verwendet, sodass eine Änderung an der Standardansicht durch ein gebundenes Steuerelement oder Code, z. B. Sortierung oder eine Änderung des aktuellen Elementzeigers (dies wird zu einem späteren Zeitpunkt erläutert), sich auf alle anderen Bindungen an dieselbe Auflistung auswirkt.

Zum Abrufen der Standardansicht verwenden Sie die <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>-Methode. Ein Beispiel finden Sie unter [Abrufen der Standardansicht einer Datenauflistung](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).

#### <a name="collection-views-with-adonet-datatables"></a>Auflistungsansichten mit ADO.NET-Datentabellen

Zur Leistungsoptimierung wird bei Auflistungsansichten für ADO.NET die Sortierung und Filterung von <xref:System.Data.DataTable>- oder <xref:System.Data.DataView>-Objekten an <xref:System.Data.DataView> delegiert. So wird die Sortierung und Filterung von allen Auflistungsansichten der Datenquelle gemeinsam verwendet. Um für die einzelnen Auflistungsansichten eine eigene Sortierung und Filterung zu ermöglichen, müssen Sie jede Auflistungsansicht mit einem eigenen <xref:System.Data.DataView>-Objekt initialisieren.

#### <a name="sorting"></a>Sortieren

Wie bereits erwähnt, können mit Ansichten Sortierreihenfolgen auf Auflistungen angewendet werden. Da sie in der zugrunde liegenden Auflistung vorhanden sind, haben die Daten möglicherweise eine relevante inhärente Reihenfolge oder nicht. Die Ansicht der Auflistung ermöglicht Ihnen das Festlegen einer Reihenfolge oder das Ändern der Standardreihenfolge, je nachdem, welche Vergleichskriterien Sie angeben. Da es sich um eine clientbasierte Ansicht der Daten handelt, besteht ein übliches Szenario darin, dass der Benutzer Spalten mit Tabellendaten nach dem Wert sortiert, dem die Spalte entspricht. Mithilfe von Ansichten kann diese benutzerdefinierte Sortierung angewendet werden, ohne die zugrunde liegende Auflistung ändern oder den Auflistungsinhalt erneut abfragen zu müssen. Ein Beispiel finden Sie unter [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).

Das folgende Beispiel zeigt die Sortierlogik des Kontrollkästchens (<xref:System.Windows.Controls.CheckBox>) „Sort by category and date“, das auf der Benutzeroberfläche der App im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) verwendet wird.

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>Filtern

Ansichten können auch einen Filter auf eine Auflistung anwenden, sodass in der Ansicht nur eine bestimmte Teilmenge der gesamten Auflistung angezeigt wird. Sie können die Daten nach einer Bedingung filtern. In der App im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) enthält das Kontrollkästchen (<xref:System.Windows.Controls.CheckBox>) „Show only bargains“ z. B. eine Logik, mit der Elemente herausgefiltert werden, die mehr als 25 Dollar kosten. Der folgende Code wird ausgeführt, um *ShowOnlyBargainsFilter* als den <xref:System.Windows.Data.CollectionViewSource.Filter>-Ereignishandler festzulegen, wenn <xref:System.Windows.Controls.CheckBox> aktiviert wird.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

Der *ShowOnlyBargainsFilter*-Ereignishandler hat die folgende Implementierung.

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

Wenn Sie direkt eine der <xref:System.Windows.Data.CollectionView>-Klassen anstelle von <xref:System.Windows.Data.CollectionViewSource> verwenden, verwenden Sie die <xref:System.Windows.Data.CollectionView.Filter%2A>-Eigenschaft zum Angeben eines Rückrufs. Ein Beispiel finden Sie unter [Filtern von Daten in einer Ansicht](../../framework/wpf/data/how-to-filter-data-in-a-view.md).

#### <a name="grouping"></a>Gruppierung

Mit Ausnahme der internen Klasse zur Ansicht einer <xref:System.Collections.IEnumerable>-Auflistung unterstützen alle Auflistungsansichten eine *Gruppierung*, wodurch der Benutzer die Auflistung in der Auflistungsansicht in logische Gruppen unterteilen kann. Die Gruppen können explizit sein, wobei Benutzer eine Liste von Gruppen angeben. Sie können auch implizit sein, wobei die Gruppen dynamisch in Abhängigkeit von den Daten generiert werden.

Das folgende Beispiel zeigt die Logik des Kontrollkästchens (<xref:System.Windows.Controls.CheckBox>) „Group by category“.

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

Ein weiteres Beispiel zu Gruppierungen finden Sie unter [Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).

#### <a name="current-item-pointers"></a>Zeiger auf aktuelle Elemente

Ansichten unterstützen ebenfalls das Konzept eines aktuellen Elements. Sie können durch die Objekte in einer Auflistungsansicht navigieren. Beim Navigieren verschieben Sie einen Elementzeiger, mit dem Sie das Objekt abrufen können, das sich an einer bestimmten Position in der Auflistung befindet. Ein Beispiel finden Sie unter [Navigieren durch die Objekte in einer Datenauflistungsansicht](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).

Da WPF Bindungen an Auflistungen immer über Ansichten herstellt (entweder über eine von Ihnen erstellte Ansicht oder über die Standardansicht der jeweiligen Auflistung), verfügen alle Bindungen an Auflistungen über einen Zeiger auf das aktuelle Element. Bei der Bindung an eine Ansicht gibt der Schrägstrich ("/") im `Path`-Wert das aktuelle Element der Ansicht an. Der Datenkontext im folgenden Beispiel ist eine Auflistungsansicht. Die erste Zeile wird an die Auflistung gebunden. Die zweite Zeile wird an das aktuelle Element in der Auflistung gebunden. Die dritte Zeile wird an die `Description`-Eigenschaft des aktuellen Elements in der Auflistung gebunden.

```xaml
<Button Content="{Binding }" />
<Button Content="{Binding Path=/}" />
<Button Content="{Binding Path=/Description}" />
```

Der Schrägstrich und die Eigenschaftensyntax können gestapelt werden, um eine Hierarchie von Auflistungen zu durchlaufen. Im folgenden Beispiel erfolgt die Bindung an das aktuelle Element einer Auflistung mit dem Namen `Offices`, wobei es sich um eine Eigenschaft des aktuellen Elements der Quellauflistung handelt.

```xaml
<Button Content="{Binding /Offices/}" />
```

Der Zeiger auf das aktuelle Element kann durch eine Sortierung oder Filterung beeinflusst werden, die auf die Auflistung angewendet wird. Beim Sortieren verbleibt der Zeiger für das aktuelle Element auf dem zuletzt ausgewählten Element, die Auflistungsansicht wird jedoch nun um den Zeiger herum neu angeordnet. (Möglicherweise befand sich das ausgewählte Element zuvor am Anfang der Liste, jetzt aber in der Mitte.) Beim Filtern wird das ausgewählte Element beibehalten, wenn diese Auswahl nach dem Filtern in der Ansicht verbleibt. Andernfalls wird der Zeiger für das aktuelle Element auf das erste Element der gefilterten Auflistungsansicht festgelegt.

#### <a name="master-detail-binding-scenario"></a>Szenario für Master-Detail-Bindung

Das Konzept eines aktuellen Elements ist nicht nur hilfreich, um durch Elemente in einer Auflistung zu navigieren, sondern auch für das Szenario einer Master-Detail-Bindung. Betrachten Sie wieder die Benutzeroberfläche der App, die im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) verwendet wird. In dieser App wird durch die Auswahl in <xref:System.Windows.Controls.ListBox> der in <xref:System.Windows.Controls.ContentControl> angezeigte Inhalt bestimmt. Anders ausgedrückt: Wenn ein <xref:System.Windows.Controls.ListBox>-Element ausgewählt wird, werden in <xref:System.Windows.Controls.ContentControl> die Details zum ausgewählten Element angezeigt.

Sie können das Master-Detail-Szenario auch einfach dadurch implementieren, dass mindestens zwei Steuerelemente an dieselbe Ansicht gebunden sind. Im folgenden Beispiel aus der [Demo für die Datenbindung][data-binding-demo] ist das Markup von <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ContentControl> dargestellt, das auf der Benutzeroberfläche der App im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) verwendet wird.

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

Beachten Sie, dass beide Steuerelemente an dieselbe Quelle gebunden sind, und zwar die statische *listingDataView*-Ressource (siehe die Definition dieser Ressource im Abschnitt [Erstellen einer Ansicht](#how-to-create-a-view)). Diese Bindung funktioniert deshalb, weil ein Singleton-Objekt (in diesem Fall <xref:System.Windows.Controls.ContentControl>) beim Binden an eine Auflistungsansicht automatisch an <xref:System.Windows.Data.CollectionView.CurrentItem%2A> in der Ansicht gebunden wird. Die <xref:System.Windows.Data.CollectionViewSource>-Objekte synchronisieren automatisch Währung und Auswahl. Ist Ihr Listensteuerelement, anders als in diesem Beispiel, nicht an ein <xref:System.Windows.Data.CollectionViewSource>-Objekt gebunden, müssen Sie dessen <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>-Eigenschaft auf `true` festlegen, damit dies erfolgt.

Weitere Beispiele finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) und [Verwenden des Master-/Detailmusters mit hierarchischen Daten](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).

Ihnen ist vielleicht aufgefallen, dass im vorherigen Beispiel eine Vorlage verwendet wird. Die Daten würden nicht wunschgemäß angezeigt, wenn keine Vorlagen verwendet würden (eine wird explizit von <xref:System.Windows.Controls.ContentControl> verwendet und die andere implizit von <xref:System.Windows.Controls.ListBox>). Im nächsten Abschnitt beschäftigen wir uns mit Datenvorlagen.

## <a name="data-templating"></a>Datenvorlagen

Ohne Datenvorlagen würde die Benutzeroberfläche der App im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) folgendermaßen aussehen.

![Demobeispiel für Datenbindung ohne Datenvorlagen](./media/data-binding-overview/demo-no-template.png)

Wie im Beispiel im vorherigen Abschnitt gezeigt, werden sowohl das <xref:System.Windows.Controls.ListBox>-Steuerelement als auch <xref:System.Windows.Controls.ContentControl> an das gesamte Auflistungsobjekt (oder genauer gesagt, die Ansicht des Auflistungsobjekts) von *AuctionItem* gebunden. Ohne spezielle Anzeigeanweisungen für die Datensammlung, wird <xref:System.Windows.Controls.ListBox> als Zeichenfolgendarstellung der Objekte in der zugrunde liegenden Auflistung angezeigt, und <xref:System.Windows.Controls.ContentControl> wird als Zeichenfolgendarstellung des Objekts angezeigt, an das es gebunden ist.

Um dieses Problem zu lösen, definiert die App <xref:System.Windows.DataTemplate?text=DataTemplates>. Wie im Beispiel im vorherigen Abschnitt gezeigt, verwendet <xref:System.Windows.Controls.ContentControl> explizit die *detailsProductListingTemplate*-Datenvorlage. Das <xref:System.Windows.Controls.ListBox>-Steuerelement verwendet implizit die folgende Datenvorlage, wenn die *AuctionItem*-Objekte in der Auflistung angezeigt werden.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

Bei Verwendung dieser beiden Datenvorlagen entspricht die resultierende Benutzeroberfläche der im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) dargestellten Benutzeroberfläche. Wie Sie in diesem Screenshot erkennen können, ermöglichen Datenvorlagen nicht nur das Einfügen von Daten in die Steuerelemente, sondern auch das Definieren überzeugender Grafiken für Ihre Daten. Beispielsweise werden <xref:System.Windows.DataTrigger> in der obigen <xref:System.Windows.DataTemplate> verwendet, sodass *AuctionItem*-Objekte mit *HighLight* als *SpecialFeatures*-Wert mit einem orangefarbenen Rahmen und einem Stern angezeigt werden.

Weitere Informationen zu Datenvorlagen finden Sie in der [Übersicht über Datenvorlagen](../../framework/wpf/data/data-templating-overview.md).

## <a name="data-validation"></a>Datenvalidierung

Die meisten Apps, bei denen Benutzereingaben erfolgen, benötigen Validierungslogik, um sicherzustellen, dass der Benutzer die erwarteten Informationen eingegeben hat. Die Validierungsprüfungen können auf Typ, Bereich, Format oder anderen App-spezifischen Anforderungen basieren. In diesem Abschnitt wird erklärt, wie Datenvalidierung in WPF funktioniert.

### <a name="associating-validation-rules-with-a-binding"></a>Zuordnen von Validierungsregeln zu einer Bindung

Das WPF-Datenbindungsmodell ermöglicht Ihnen die Zuordnung von <xref:System.Windows.Data.Binding.ValidationRules%2A> zum <xref:System.Windows.Data.Binding>-Objekt. Im folgenden Beispiel wird z. B. ein<xref:System.Windows.Controls.TextBox> -Element an eine Eigenschaft mit der Bezeichnung `StartPrice` gebunden, und ein <xref:System.Windows.Controls.ExceptionValidationRule>-Objekt wird der <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType>-Eigenschaft hinzugefügt.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

Ein <xref:System.Windows.Controls.ValidationRule>-Objekt überprüft, ob der Wert einer Eigenschaft gültig ist. WPF verfügt über zwei Typen integrierter <xref:System.Windows.Controls.ValidationRule>-Objekte:

- Eine <xref:System.Windows.Controls.ExceptionValidationRule> überprüft, ob während des Updates der Bindungsquelleigenschaft Ausnahmen ausgelöst wurden. Im vorherigen Beispiel ist `StartPrice` eine ganze Zahl. Wenn der Benutzer einen Wert eingibt, der nicht in eine ganze Zahl konvertiert werden kann, wird eine Ausnahme ausgelöst, wodurch die Bindung als ungültig markiert wird. Alternativ zum expliziten Festlegen der <xref:System.Windows.Controls.ExceptionValidationRule> können Sie die <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>-Eigenschaft des `true`- oder <xref:System.Windows.Data.Binding>-Objekts auf <xref:System.Windows.Data.MultiBinding> festlegen.

- Ein <xref:System.Windows.Controls.DataErrorValidationRule>-Objekt überprüft, ob Fehler vorliegen, die von Objekten ausgelöst werden, die die <xref:System.ComponentModel.IDataErrorInfo>-Schnittstelle implementieren. Ein Beispiel für die Verwendung dieser Validierungsregel finden Sie unter <xref:System.Windows.Controls.DataErrorValidationRule>. Alternativ zum expliziten Festlegen der <xref:System.Windows.Controls.DataErrorValidationRule> können Sie die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>-Eigenschaft des `true`- oder <xref:System.Windows.Data.Binding>-Objekts auf <xref:System.Windows.Data.MultiBinding> festlegen.

Sie können auch eigene Validierungsregeln erstellen, indem Sie von der <xref:System.Windows.Controls.ValidationRule>-Klasse ableiten und die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode implementieren. Das folgende Beispiel zeigt die Regel, die vom <xref:System.Windows.Controls.TextBox>-Element „Start Date“ in *Add Product Listing* im Abschnitt [Was ist Datenbindung?](#what-is-data-binding) verwendet wird.

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

Das <xref:System.Windows.Controls.TextBox>-Element *StartDateEntryForm* verwendet diese *FutureDateRule*, wie es im folgenden Beispiel gezeigt ist.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

Da der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Wert auf <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> festgelegt ist, aktualisiert die Bindungs-Engine den Quellwert bei jeder Tastatureingabe und überprüft daher auch alle Regeln in der <xref:System.Windows.Data.Binding.ValidationRules%2A>-Auflistung bei jeder Tastatureingabe. Dies wird im Abschnitt zum Validierungsprozess näher erläutert.

### <a name="providing-visual-feedback"></a>Bereitstellen von visuellem Feedback

Wenn der Benutzer einen ungültigen Wert eingibt, kann es sinnvoll sein, Feedback zum Fehler auf der Benutzeroberfläche der App zu geben. Eine Möglichkeit zum Bereitstellen von Feedback besteht darin, die angefügte Eigenschaft <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> auf eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> festzulegen. Wie im vorherigen Unterabschnitt gezeigt, verwendet das <xref:System.Windows.Controls.TextBox>-Element *StartDateEntryForm* eine <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> namens *validationTemplate*. Im folgenden Beispiel sehen Sie die Definition von *validationTemplate*.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

Das <xref:System.Windows.Controls.AdornedElementPlaceholder>-Element gibt an, wo das erweiterte Steuerelement platziert werden soll.

Darüber hinaus können Sie <xref:System.Windows.Controls.ToolTip> verwenden, um die Fehlermeldung anzuzeigen. Die beiden <xref:System.Windows.Controls.TextBox>-Elemente *StartDateEntryForm* und *StartPriceEntryForm* verwenden das Format *textStyleTextBox*, das einen <xref:System.Windows.Controls.ToolTip> erstellt, um die Fehlermeldung anzuzeigen. Im folgenden Beispiel wird die Definition von *textStyleTextBox* dargestellt. Die angefügte Eigenschaft <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> ist `true`, wenn mindestens eine der Bindungen an die Eigenschaften des gebundenen Elements fehlerhaft ist.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

Mit der benutzerdefinierten <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und dem <xref:System.Windows.Controls.ToolTip> sieht das <xref:System.Windows.Controls.TextBox>-Element *StartDateEntryForm* bei einem Validierungsfehler folgendermaßen aus.

![Datenbindungs-Validierungsfehler](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

Wenn Ihre <xref:System.Windows.Data.Binding> über zugeordnete Validierungsregeln verfügt, Sie aber keine <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> für das gebundene Steuerelement angeben, wird eine standardmäßige <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> verwendet, um Benutzer bei einem Validierungsfehler zu benachrichtigen. Die standardmäßige <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> ist eine Steuerelementvorlage, die einen roten Rahmen auf der Adornerebene definiert. Mit der standardmäßigen <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und dem <xref:System.Windows.Controls.ToolTip> sieht das <xref:System.Windows.Controls.TextBox>-Element *StartPriceEntryForm* bei einem Validierungsfehler folgendermaßen aus.

![Datenbindungs-Validierungsfehler](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

Ein Beispiel zum Bereitstellen von Logik zum Validieren aller Steuerelemente in einem Dialogfeld finden Sie im Abschnitt zu benutzerdefinierten Dialogfeldern in der [Übersicht über Dialogfelder](../../framework/wpf/app-development/dialog-boxes-overview.md).

### <a name="validation-process"></a>Validierungsprozess

Eine Validierung erfolgt normalerweise, wenn der Wert eines Ziels an die Bindungsquelleigenschaft übergeben wird. Diese Übergabe erfolgt bei <xref:System.Windows.Data.BindingMode.TwoWay>- und <xref:System.Windows.Data.BindingMode.OneWayToSource>-Bindungen. Wodurch die Aktualisierung einer Quelle verursacht wird, hängt also vom Wert der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Eigenschaft ab, wie im Abschnitt [Wodurch werden Quellaktualisierungen ausgelöst?](#what-triggers-source-updates) beschrieben.

Im Folgenden wird der Prozess der *Validierung* beschrieben. Der Prozess wird bei Auftreten eines Validierungs- oder anderen Fehlers in seinem Verlauf angehalten:

1. Die Bindungs-Engine überprüft, ob benutzerdefinierte <xref:System.Windows.Controls.ValidationRule>-Objekte definiert sind, deren <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.RawProposedValue> für die <xref:System.Windows.Data.Binding> festgelegt ist. In diesem Fall wird die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode für jede <xref:System.Windows.Controls.ValidationRule> aufgerufen, bis eine der Regeln einen Fehler zurückgibt oder alle Regeln erfolgreich überprüft wurden.

2. Anschließend ruft die Bindungs-Engine den Konverter auf, sofern vorhanden.

3. Bei erfolgreicher Ausführung des Konverters überprüft die Bindungs-Engine, ob benutzerdefinierte <xref:System.Windows.Controls.ValidationRule>-Objekte definiert sind, deren <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> für die <xref:System.Windows.Data.Binding> festgelegt ist. In diesem Fall wird die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode für jede <xref:System.Windows.Controls.ValidationRule> aufgerufen, für die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> festgelegt ist, bis eine der Regeln einen Fehler zurückgibt oder alle Regeln erfolgreich überprüft wurden.

4. Die Bindungs-Engine legt die Quelleigenschaft fest.

5. Die Bindungs-Engine überprüft, ob benutzerdefinierte <xref:System.Windows.Controls.ValidationRule>-Objekte definiert sind, deren <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> für die <xref:System.Windows.Data.Binding> festgelegt ist. In diesem Fall wird die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode für jede <xref:System.Windows.Controls.ValidationRule> aufgerufen, für die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> festgelegt ist, bis eine der Regeln einen Fehler zurückgibt oder alle Regeln erfolgreich überprüft wurden. Wenn ein <xref:System.Windows.Controls.DataErrorValidationRule>-Objekt einer Bindung zugeordnet und das <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>-Element des Objekts auf den Standardwert (<xref:System.Windows.Controls.ValidationStep.UpdatedValue>) festgelegt ist, wird an dieser Stelle das <xref:System.Windows.Controls.DataErrorValidationRule>-Objekt geprüft. An diesem Punkt wird jede Bindung, für die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> auf `true` festgelegt ist, geprüft.

6. Die Bindungs-Engine überprüft, ob benutzerdefinierte <xref:System.Windows.Controls.ValidationRule>-Objekte definiert sind, deren <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.CommittedValue> für die <xref:System.Windows.Data.Binding> festgelegt ist. In diesem Fall wird die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode für jede <xref:System.Windows.Controls.ValidationRule> aufgerufen, für die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.CommittedValue> festgelegt ist, bis eine der Regeln einen Fehler zurückgibt oder alle Regeln erfolgreich überprüft wurden.

Wenn während dieses Prozesses eine <xref:System.Windows.Controls.ValidationRule> nicht erfolgreich überprüft wird, erstellt die Bindungs-Engine ein <xref:System.Windows.Controls.ValidationError>-Objekt und fügt es der <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>-Auflistung des gebundenen Elements hinzu. Bevor die Bindungs-Engine die <xref:System.Windows.Controls.ValidationRule>-Objekte im Rahmen eines Schritts ausführt, werden alle <xref:System.Windows.Controls.ValidationError> entfernt, die der angefügten Eigenschaft <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> des gebundenen Elements während dieses Schritts hinzugefügt wurden. Wenn beispielsweise eine <xref:System.Windows.Controls.ValidationRule>, deren <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> festgelegt ist, fehlgeschlagen ist, entfernt die Bindungs-Engine bei der nächsten Ausführung des Validierungsprozesses diesen <xref:System.Windows.Controls.ValidationError> unmittelbar vor dem Aufruf einer <xref:System.Windows.Controls.ValidationRule>, für die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> festgelegt ist.

Wenn <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> nicht leer ist, wird die angefügte Eigenschaft <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> des Elements auf `true` festgelegt. Wenn außerdem die <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>-Eigenschaft der <xref:System.Windows.Data.Binding> auf `true` festgelegt ist, löst die Bindungs-Engine das angefügte Ereignis <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> des Elements aus.

Beachten Sie außerdem, dass durch eine gültige Wertübertragung (Ziel zu Quelle oder umgekehrt) die angefügte Eigenschaft <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> gelöscht wird.

Wenn der Bindung entweder ein <xref:System.Windows.Controls.ExceptionValidationRule>-Element zugeordnet ist oder die <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>-Eigenschaft der Bindung auf `true` festgelegt wurde und beim Festlegen der Quelle durch die Bindungs-Engine eine Ausnahme ausgelöst wird, überprüft die Bindungs-Engine, ob ein <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>-Element vorhanden ist. Sie können den <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>-Rückruf verwenden, um einen benutzerdefinierten Handler zum Behandeln von Ausnahmen bereitzustellen. Wenn kein <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> für die <xref:System.Windows.Data.Binding> angegeben ist, erstellt die Bindungs-Engine einen <xref:System.Windows.Controls.ValidationError> mit der Ausnahme und fügt ihn der <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>-Auflistung des gebundenen Elements hinzu.

## <a name="debugging-mechanism"></a>Debugverfahren

Sie können die angefügte Eigenschaft <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> auf ein für die Datenbindung relevantes Objekt festlegen, um Informationen über den Status einer bestimmten Bindung zu erhalten.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Binden an die Ergebnisse einer LINQ-Abfrage](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [Datenbindung](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Demo für die Datenbindung][data-binding-demo]
- [Gewusst-wie-Artikel](../../framework/wpf/data/data-binding-how-to-topics.md)
- [Binden an eine ADO.NET-Datenquelle](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "Demo-App für die Datenbindung"
