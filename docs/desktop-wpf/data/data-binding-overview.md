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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433253"
---
# <a name="data-binding-overview-in-wpf"></a>Datenbindungsübersicht in WPF

Die Datenbindung in Windows Presentation Foundation (WPF) bietet Apps eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können in Form von .NET-Objekten und XML an Daten aus einer Vielzahl von Datenquellen gebunden werden. <xref:System.Windows.Controls.ContentControl> Alle, <xref:System.Windows.Controls.Button> z. <xref:System.Windows.Controls.ItemsControl>B. <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView>und , verfügen über integrierte Funktionen, um ein flexibles Styling einzelner Datenelemente oder Sammlungen von Datenelementen zu ermöglichen. Sortier-, Filter- und Gruppenansichten können übergreifend für die Daten generiert werden.

Die Datenbindungsfunktionalität in WPF hat mehrere Vorteile gegenüber herkömmlichen Modellen, einschließlich der inhärenten Unterstützung für die Datenbindung durch eine breite Palette von Eigenschaften, eine flexible UI-Darstellung von Daten und eine saubere Trennung der Geschäftslogik von der Benutzeroberfläche.

In diesem Artikel werden zunächst Konzepte erläutert, die für <xref:System.Windows.Data.Binding> die WPF-Datenbindung von grundlegender Bedeutung sind, und dann die Verwendung der Klasse und anderer Features der Datenbindung behandelt.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>Was ist Datenbindung?

Die Datenbindung ist der Prozess, der eine Verbindung zwischen der App-Benutzeroberfläche und den angezeigten Daten herstellt. Wenn die Bindungseinstellungen korrekt sind und bei einer Änderung des Werts ordnungsgemäße Benachrichtigungen ausgegeben werden, werden die Elemente, die an die Daten gebunden sind, automatisch aktualisiert. Datenbindung kann auch bedeuten, dass bei einer Änderung der äußeren Darstellung von Daten in einem Element die zugrunde liegenden Daten automatisch aktualisiert werden können, um die Änderung wiederzugeben. Wenn der Benutzer beispielsweise den Wert `TextBox` in einem Element ändert, wird der zugrunde liegende Datenwert automatisch aktualisiert, um diese Änderung widerzuspiegeln.

Eine typische Verwendung der Datenbindung besteht darin, Server- oder lokale Konfigurationsdaten in Formularen oder anderen UI-Steuerelementen zu platzieren. In WPF wird dieses Konzept erweitert, um eine breite Palette von Eigenschaften an eine Vielzahl von Datenquellen zu binden. In WPF können Abhängigkeitseigenschaften von Elementen an .NET-Objekte (einschließlich ADO.NET Objekte oder Objekte gebunden werden, die Webdiensten und Webeigenschaften zugeordnet sind) und XML-Daten.

Sehen Sie sich ein Beispiel für die Datenbindung an, und sehen Sie sich die folgende App-Benutzeroberfläche aus der [Datenbindungsdemo][data-binding-demo]an, in der eine Liste der Auktionselemente angezeigt wird.

![Beispiel-Screenshot zur Datenbindung](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

Die App veranschaulicht die folgenden Funktionen der Datenbindung:

- Der Inhalt der ListBox ist an eine Auflistung von *AuctionItem-Objekten* gebunden. Ein *AuctionItem-Objekt* verfügt über Eigenschaften wie *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures*usw.

- Die im AuctionItem angezeigten `ListBox` Daten *(AuctionItem-Objekte)* werden so erstellt, dass die Beschreibung und der aktuelle Preis für jeden Artikel angezeigt werden. Die Vorlage wird mithilfe <xref:System.Windows.DataTemplate>einer erstellt. Darüber hinaus hängt die Darstellung jedes Elements vom *SpecialFeatures*-Wert des angezeigten *AuctionItem* ab. Wenn der *SpecialFeatures*-Wert von *AuctionItem* auf *Color* festgelegt ist, hat das Element einen blauen Rahmen. Wenn der Wert *Highlight* ist, hat das Element einen orangefarbenen Rahmen und einen Stern. Im Abschnitt [Datenvorlagen](#data-templating) erhalten Sie weitere Informationen zu Datenvorlagen.

- Der Benutzer kann die Daten mithilfe der `CheckBoxes` bereitgestellten Daten gruppieren, filtern oder sortieren. In der Abbildung oben werden die **Gruppe nach Kategorie** und Sortieren nach Kategorie und **Datum** `CheckBoxes` ausgewählt. Möglicherweise haben Sie bereits bemerkt, dass die Daten nach der Kategorie des Produkts gruppiert sind und der Name der Kategorie in alphabetischer Reihenfolge aufgeführt ist. In der Abbildung ist nicht so gut zu erkennen, dass auch die Elemente innerhalb der einzelnen Kategorien nach Startdatum sortiert sind. Die Sortierung erfolgt über eine *Auflistungsansicht*. Im Abschnitt [Bindung an Sammlungen](#binding-to-collections) werden Auflistungsansichten erläutert.

- Wenn der Benutzer ein Element <xref:System.Windows.Controls.ContentControl> auswählt, werden die Details des ausgewählten Elements angezeigt. Diese Erfahrung wird als *Master-Detail-Szenario*bezeichnet. Der Abschnitt ["Master-Detail-Szenario"](#master-detail-binding-scenario) enthält Informationen zu diesem Bindungstyp.

- Der Typ der *StartDate-Eigenschaft* ist <xref:System.DateTime>, die ein Datum zurückgibt, das die Zeit bis zur Millisekunde enthält. In dieser App wurde ein benutzerdefinierter Konverter verwendet, sodass eine kürzere Datumszeichenfolge angezeigt wird. Der Abschnitt [Datenkonvertierung](#data-conversion) enthält Informationen zu Konvertern.

Wenn der Benutzer die Schaltfläche *Produkt hinzufügen* auswählt, erscheint das folgende Formular.

![Seite Produktliste hinzufügen](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

Der Benutzer kann die Felder im Formular bearbeiten, eine Vorschau der Produktliste `Submit` mithilfe der kurzen oder detaillierten Vorschaubereiche anzeigen und die neue Produktliste hinzufügen. Alle vorhandenen Gruppierungs-, Filter- und Sortiereinstellungen gelten für den neuen Eintrag. In diesem speziellen Fall wird das im obigen Bild eingegebene Element in der Kategorie *Computer* an zweiter Stelle angezeigt.

In diesem Bild wird die Validierungslogik im *Startdatum* <xref:System.Windows.Controls.TextBox>nicht angezeigt. Wenn der Benutzer ein ungültiges Datum (ungültige Formatierung oder ein <xref:System.Windows.Controls.ToolTip> vergangenes Datum) eingibt, wird <xref:System.Windows.Controls.TextBox>der Benutzer mit einem und einem roten Ausrufezeichen neben dem benachrichtigt. Im Abschnitt [Datenvalidierung](#data-validation) wird näher auf das Erstellen von Validierungslogik eingegangen.

Bevor wir auf die verschiedenen oben beschriebenen Features der Datenbindung eingehen, werden wir zunächst die grundlegenden Konzepte besprechen, die für das Verständnis der WPF-Datenbindung von entscheidender Bedeutung sind.

## <a name="basic-data-binding-concepts"></a>Grundlegende Datenbindungskonzepte

Unabhängig davon, welches Element Sie binden und wie artlos Ihre Datenquelle ist, folgt jede Bindung immer dem Modell, das in der folgenden Abbildung dargestellt wird.

![Diagramm, das das grundlegende Datenbindungsmodell zeigt.](./media/data-binding-overview/basic-data-binding-diagram.png)

Wie die Abbildung zeigt, ist die Datenbindung im Wesentlichen die Brücke zwischen Ihrem Bindungsziel und Ihrer Bindungsquelle. Die Abbildung zeigt die folgenden grundlegenden WPF-Datenbindungskonzepte:

- In der Regel besteht jede Bindung aus vier Komponenten:

  - Ein Bindungszielobjekt.
  - Eine Zieleigenschaft.
  - Eine Bindungsquelle:
  - Ein Pfad zum Wert in der zu verwendenden Bindungsquelle.
  
  > Wenn Sie z. B. den `TextBox` Inhalt `Employee.Name` von a an die `TextBox`Eigenschaft binden möchten, lautet das Zielobjekt die , die Zieleigenschaft ist die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft, der zu verwendende Wert ist *Name*, und das Quellobjekt ist das *Employee-Objekt.*

- Die Zieleigenschaft muss eine Abhängigkeitseigenschaft sein. Die <xref:System.Windows.UIElement> meisten Eigenschaften sind Abhängigkeitseigenschaften, und die meisten Abhängigkeitseigenschaften, mit Ausnahme schreibgeschützter Eigenschaften, unterstützen standardmäßig die Datenbindung. (Nur typen, <xref:System.Windows.DependencyObject> die von abgeleitet <xref:System.Windows.UIElement> werden, können `DependencyObject`Abhängigkeitseigenschaften definieren; und alle Typen leiten sich von ab .)

- Obwohl in der Abbildung nicht dargestellt, sollte beachtet werden, dass das Bindungsquellobjekt nicht darauf beschränkt ist, ein benutzerdefiniertes .NET-Objekt zu sein. Die WPF-Datenbindung unterstützt Daten in Form von .NET-Objekten und XML. Um einige Beispiele zu geben, <xref:System.Windows.UIElement>kann ihre Bindungsquelle ein , ein beliebiges Listenobjekt, ein ADO.NET oder Web Services-Objekt oder ein XmlNode sein, der Ihre XML-Daten enthält. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../../framework/wpf/data/binding-sources-overview.md).

Beachten Sie, dass Sie beim Einrichten einer Bindung ein Bindungsziel *an* eine Bindungsquelle binden. Wenn Sie z. B. einige zugrunde <xref:System.Windows.Controls.ListBox> liegende XML-Daten in `ListBox` einer verwendenden Datenbindung anzeigen, binden Sie Ihre an die XML-Daten.

Um eine Bindung einzurichten, <xref:System.Windows.Data.Binding> verwenden Sie das Objekt. Im weiteren Verlauf dieses Artikels werden viele der konzepte und einige `Binding` der Eigenschaften und die Verwendung des Objekts erläutert.

### <a name="direction-of-the-data-flow"></a>Richtung des Datenflusses

Wie durch den Pfeil in der vorherigen Abbildung angegeben, kann der Datenfluss einer Bindung vom Bindungsziel zur Bindungsquelle gehen `TextBox`(z. B. ändert sich der Quellwert, `TextBox` wenn ein Benutzer den Wert einer ändert) und/oder von der Bindungsquelle zum Bindungsziel (z. B. wird Ihr Inhalt mit Änderungen in der Bindungsquelle aktualisiert), wenn die Bindungsquelle die richtigen Benachrichtigungen bereitstellt.

Möglicherweise möchten Sie, dass Ihre App Benutzern ermöglicht, die Daten zu ändern und wieder an das Quellobjekt weiterzuleiten. Sie können auch das Aktualisieren von Quelldaten durch Benutzer unterbinden. Sie können den Datenfluss steuern, indem Sie die <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>festlegen.

Diese Abbildung veranschaulicht die verschiedenen Arten des Datenflusses:

![Datenbindungsdatenfluss](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- <xref:System.Windows.Data.BindingMode.OneWay>Die Bindung bewirkt, dass Änderungen an der Quelleigenschaft die Zieleigenschaft automatisch aktualisieren, Änderungen an der Zieleigenschaft jedoch nicht an die Quelleigenschaft weitergegeben werden. Dieser Bindungstyp empfiehlt sich, wenn das gebundene Steuerelement implizit als schreibgeschützt festgelegt wurde. Sie können z. B. eine Bindung an eine Quelle binden, z. B. an einen Aktienticker, oder Ihre Zieleigenschaft verfügt über keine Kontrollschnittstelle, die für Änderungen bereitgestellt wird, z. B. eine datengebundene Hintergrundfarbe einer Tabelle. Wenn die Änderungen der Zieleigenschaft nicht überwacht werden müssen, vermeiden Sie mit dem <xref:System.Windows.Data.BindingMode.OneWay>-Bindungsmodus den Mehraufwand des <xref:System.Windows.Data.BindingMode.TwoWay>-Bindungsmodus.

- <xref:System.Windows.Data.BindingMode.TwoWay>Bindung bewirkt, dass Änderungen an der Quelleigenschaft oder der Zieleigenschaft die andere automatisch aktualisieren. Dieser Bindungstyp eignet sich für bearbeitbare Formulare oder andere vollständig interaktive UI-Szenarien. Die meisten <xref:System.Windows.Data.BindingMode.OneWay> Eigenschaften sind standardmäßig für die Bindung, aber einige Abhängigkeitseigenschaften (in der Regel Eigenschaften von benutzereditierbaren Steuerelementen wie dem <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> und [CheckBox.IsChecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked) default to <xref:System.Windows.Data.BindingMode.TwoWay> binding. Eine programmgesteuerte Möglichkeit, zu bestimmen, ob eine Abhängigkeitseigenschaft standardmäßig eine einseitige <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType> oder zweiseitige Eigenschaft <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType> bindet, besteht darin, die Eigenschaftenmetadaten mit den Eigenschaftenmetadaten abzurufen und dann den booleschen Wert der Eigenschaft zu überprüfen.

- <xref:System.Windows.Data.BindingMode.OneWayToSource>ist die <xref:System.Windows.Data.BindingMode.OneWay> Rückseite der Bindung; Es wird die Quelleigenschaft aktualisiert, wenn sich die Zieleigenschaft ändert. Ein Beispielszenario ist, wenn Sie nur den Quellwert aus der Benutzeroberfläche neu bewerten müssen.

- Nicht in der <xref:System.Windows.Data.BindingMode.OneTime> Abbildung dargestellt ist bindungsbedingt, wodurch die quell-Eigenschaft die Zieleigenschaft initialisiert, aber keine nachfolgenden Änderungen weitergibt. Wenn sich der Datenkontext ändert oder sich das Objekt im Datenkontext ändert, wird die Änderung *nicht* in der Zieleigenschaft widergespiegelt. Dieser Bindungstyp ist geeignet, wenn entweder eine Momentaufnahme des aktuellen Status oder die Daten wirklich statisch sind. Dieser Bindungstyp ist auch hilfreich, wenn die Zieleigenschaft mit einem bestimmten Wert der Quelleigenschaft initialisiert werden soll und der Datenkontext vorab nicht bekannt ist. Dieser Modus ist im <xref:System.Windows.Data.BindingMode.OneWay> Wesentlichen eine einfachere Form der Bindung, die eine bessere Leistung in Fällen bietet, in denen sich der Quellwert nicht ändert.

Um Quelländerungen (gilt <xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay> für und Bindungen) zu erkennen, muss die <xref:System.ComponentModel.INotifyPropertyChanged>Quelle einen geeigneten Benachrichtigungsmechanismus für Eigenschaftenänderungen implementieren, z. B. . Weitere Informationen finden [Sie unter Gewusst wie: Implementieren der Eigenschaftsänderungsbenachrichtigung](../../framework/wpf/data/how-to-implement-property-change-notification.md) für ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> Implementierung.

Die <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType> Eigenschaft enthält weitere Informationen zu Bindungsmodi und ein Beispiel für das Angeben der Richtung einer Bindung.

### <a name="what-triggers-source-updates"></a>Was Quellaktualisierungen auslöst

Bindungen, die <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> Änderungen in der Zieleigenschaft sind oder darauf lauschen, und sie an die Quelle zurückgeben, die als Aktualisierung der Quelle bezeichnet wird. Sie können beispielsweise den Text eines TextBox-Elements bearbeiten, um den zugrunde liegenden Quellwert zu ändern.

Wird der Quellwert jedoch aktualisiert, während Sie den Text bearbeiten oder nachdem Sie den Text bearbeitet haben und das Steuerelement den Fokus verliert? Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> Eigenschaft bestimmt, was die Aktualisierung der Quelle auslöst. Die Punkte der rechten Pfeile in der folgenden <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> Abbildung veranschaulichen die Rolle der Eigenschaft.

![Diagramm, das die Rolle der UpdateSourceTrigger-Eigenschaft anzeigt.](./media/data-binding-overview/data-binding-updatesource-trigger.png)

Wenn `UpdateSourceTrigger` der <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>Wert ist , wird der Wert, auf den der rechte Pfeil oder <xref:System.Windows.Data.BindingMode.TwoWay> die <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen zeigt, aktualisiert, sobald sich die Zieleigenschaft ändert. Wenn der `UpdateSourceTrigger` Wert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>jedoch ist , wird dieser Wert nur mit dem neuen Wert aktualisiert, wenn die Zieleigenschaft den Fokus verliert.

Ähnlich wie <xref:System.Windows.Data.Binding.Mode%2A> die Eigenschaft weisen verschiedene <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Abhängigkeitseigenschaften unterschiedliche Standardwerte auf. Der Standardwert für die meisten Abhängigkeitseigenschaften ist <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, während die `TextBox.Text`-Eigenschaft den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> aufweist. `PropertyChanged`bedeutet, dass die Quellaktualisierungen in der Regel immer dann erfolgen, wenn sich die Zieleigenschaft ändert. Sofortige Änderungen sind für CheckBoxen und andere einfache Steuerelemente in Ordnung. Bei Textfeldern kann die Aktualisierung nach jedem Tastenanschlag jedoch die Leistung beeinträchtigen und dem Benutzer die übliche Möglichkeit zum Zurückräumen und Beheben von Tippfehlern verwehren, bevor der neue Wert übertragen wird.

Informationen <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> zum Suchen des Standardwerts einer Abhängigkeitseigenschaft finden Sie auf der Eigenschaftenseite.

Die folgende Tabelle enthält ein <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Beispielszenario <xref:System.Windows.Controls.TextBox> für jeden Wert, der als Beispiel verwendet wird.

| UpdateSourceTrigger-Wert | Wenn der Quellwert aktualisiert wird | Beispielszenario für TextBox |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus`(Standard <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>für ) | Wenn das TextBox-Steuerelement den Fokus verliert. | Eine TextBox, die der Validierungslogik zugeordnet ist (siehe [Datenvalidierung](#data-validation) unten). |
| `PropertyChanged` | Wenn Sie in <xref:System.Windows.Controls.TextBox>die eingeben, | TextBox-Steuerelemente in einem Chatroomfenster. |
| `Explicit` | Wenn die <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>App anruft . | TextBox-Steuerelemente in einem bearbeitbaren Formular (aktualisiert die Quellwerte nur, wenn der Benutzer auf die Schaltfläche Senden klickt). |

Ein Beispiel finden Sie [unter Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert.](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="creating-a-binding"></a>Erstellen einer Bindung

Um einige der in den vorherigen Abschnitten beschriebenen Konzepte <xref:System.Windows.Data.Binding> zu wiederholen, richten Sie eine Bindung mithilfe des Objekts ein, und jede Bindung hat in der Regel vier Komponenten: ein Bindungsziel, eine Zieleigenschaft, eine Bindungsquelle und einen Pfad zum zu verwendenden Quellwert. In diesem Abschnitt wird das Einrichten einer Bindung erläutert.

Im folgenden Beispiel ist das Bindungsquellobjekt eine Klasse namens *MyData*, die im Namespace *SDKSample* definiert ist. Zu Demonstrationszwecken verfügt *MyData* über eine Zeichenfolgeneigenschaft namens *ColorName,* deren Wert auf "Rot" festgelegt ist. In diesem Beispiel wird also eine Schaltfläche mit einem roten Hintergrund erstellt.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

Weitere Informationen zur Syntax der Bindungsdeklaration und Beispiele zum Einrichten einer Bindung im Code finden Sie unter Übersicht über [Bindungsdeklarationen](../../framework/wpf/data/binding-declarations-overview.md).

Wenn dieses Beispiel auf das einfache Diagramm angewendet wird, sieht die resultierend Abbildung wie die folgende aus. Diese Abbildung <xref:System.Windows.Data.BindingMode.OneWay> beschreibt eine Bindung, <xref:System.Windows.Data.BindingMode.OneWay> da die Background-Eigenschaft standardmäßig die Bindung unterstützt.

![Diagramm, das die DatenbindungS-Hintergrundeigenschaft anzeigt.](./media/data-binding-overview/data-binding-button-background-example.png)

Sie fragen sich vielleicht, warum diese Bindung funktioniert, obwohl die *ColorName-Eigenschaft* vom Typ string ist, während die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft vom Typ <xref:System.Windows.Media.Brush>ist. Diese Bindung verwendet die Standardtypkonvertierung, die im Abschnitt [Datenkonvertierung](#data-conversion) erläutert wird.

### <a name="specifying-the-binding-source"></a>Angeben der Bindungsquelle

Beachten Sie, dass im vorherigen Beispiel die Bindungsquelle durch Festlegen der [DockPanel.DataContext-Eigenschaft](xref:System.Windows.FrameworkElement.DataContext) angegeben wird. Der <xref:System.Windows.Controls.Button> erbt dann <xref:System.Windows.FrameworkElement.DataContext%2A> den <xref:System.Windows.Controls.DockPanel>Wert vom , das übergeordnete Element ist. Das Bindungsquellobjekt stellt, wie bereits erwähnt, eine der vier erforderlichen Komponenten einer Bindung dar. Wäre das Bindungsquellobjekt nicht angegeben, hätte die Bindung keine Auswirkungen.

Es gibt mehrere Möglichkeiten, das Bindungsquellobjekt anzugeben. Die <xref:System.Windows.FrameworkElement.DataContext%2A> Verwendung der Eigenschaft für ein übergeordnetes Element ist nützlich, wenn Sie mehrere Eigenschaften an dieselbe Quelle binden. Es kann aber auch zweckmäßiger sein, die Bindungsquelle in einzelnen Bindungsdeklarationen anzugeben. Im vorherigen Beispiel können Sie <xref:System.Windows.FrameworkElement.DataContext%2A> anstelle der Eigenschaft die Bindungsquelle angeben, indem Sie die <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> Eigenschaft direkt auf der Bindungsdeklaration der Schaltfläche festlegen, wie im folgenden Beispiel.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

Abgesehen davon, <xref:System.Windows.FrameworkElement.DataContext%2A> dass Sie die Eigenschaft direkt <xref:System.Windows.FrameworkElement.DataContext%2A> für ein Element festlegen, den Wert von einem Vorgänger erben (z. <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> B. die Schaltfläche im ersten Beispiel), und die <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType> Bindungsquelle explizit angeben, indem Sie die Eigenschaft für die Bindung festlegen (z. B. die Schaltfläche im letzten Beispiel), können Sie auch die Eigenschaft oder die <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType> Eigenschaft verwenden, um die Bindungsquelle anzugeben. Die <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft ist nützlich, wenn Sie an andere Elemente in Ihrer App binden, z. B. wenn Sie einen Schieberegler zum Anpassen der Breite einer Schaltfläche verwenden. Die <xref:System.Windows.Data.Binding.RelativeSource%2A> Eigenschaft ist nützlich, wenn <xref:System.Windows.Controls.ControlTemplate> die <xref:System.Windows.Style>Bindung in einer oder einem angegeben ist. Weitere Informationen finden Sie unter [Gewusst wie: Angeben der Bindungsquelle](../../framework/wpf/data/how-to-specify-the-binding-source.md).

### <a name="specifying-the-path-to-the-value"></a>Angeben des Pfads zum Wert

Wenn ihre Bindungsquelle ein Objekt <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType> ist, verwenden Sie die Eigenschaft, um den Wert anzugeben, der für Ihre Bindung verwendet werden soll. Wenn Sie an XML-Daten binden, verwenden Sie die <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType> Eigenschaft, um den Wert anzugeben. In einigen Fällen kann es anwendbar <xref:System.Windows.Data.Binding.Path%2A> sein, die Eigenschaft auch dann zu verwenden, wenn es sich bei Ihren Daten um XML handelt. Wenn Sie beispielsweise auf die Name-Eigenschaft eines zurückgegebenen XmlNode (als Ergebnis einer XPath-Abfrage) zugreifen möchten, sollten Sie die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft zusätzlich zur <xref:System.Windows.Data.Binding.XPath%2A> Eigenschaft verwenden.

Weitere Informationen finden <xref:System.Windows.Data.Binding.Path%2A> Sie <xref:System.Windows.Data.Binding.XPath%2A> unter und eigenschaften.

Obwohl wir betont haben, dass der <xref:System.Windows.Data.Binding.Path%2A> zu verwendende Wert eine der vier erforderlichen Komponenten einer Bindung ist, ist der zu verwendende Wert in den Szenarien, die Sie an ein gesamtes Objekt binden möchten, derselbe wie das Bindungsquellobjekt. In diesen Fällen gilt es, <xref:System.Windows.Data.Binding.Path%2A>keine anzugeben. Betrachten Sie das folgende Beispiel.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

Im obigen Beispiel wird die leere Bindungssyntax verwendet: {Binding}. In diesem Fall <xref:System.Windows.Controls.ListBox> erbt der DataContext von einem übergeordneten DockPanel-Element (in diesem Beispiel nicht gezeigt). Wenn der Pfad nicht angegeben wurde, erfolgt die Bindung standardmäßig an das gesamte Objekt. Mit anderen Worten, in diesem Beispiel wurde der Pfad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> weggelassen, da wir die Eigenschaft an das gesamte Objekt binden. (Eine ausführliche Diskussion finden Sie im Abschnitt [Bindung an Sammlungen.)](#binding-to-collections)

Dieses Szenario ist nicht nur zum Binden an eine Auflistung hilfreich, sondern auch zum Binden an ein vollständiges Objekt statt nur an eine einzelne Eigenschaft eines Objekts. Wenn das Quellobjekt beispielsweise vom <xref:System.String>Typ ist, können Sie einfach an die Zeichenfolge selbst binden. Ein anderes allgemeines Szenario besteht darin, ein Element an ein Objekt mit mehreren Eigenschaften zu binden.

Möglicherweise müssen Sie benutzerdefinierte Logik anwenden, damit die Daten für Ihre gebundene Zieleigenschaft sinnvoll sind. Die benutzerdefinierte Logik kann in Form eines benutzerdefinierten Konverters vorliegen, wenn keine Standardtypkonvertierung vorhanden ist. Informationen zu Konvertern finden Sie unter [Datenkonvertierung.](#data-conversion)

### <a name="binding-and-bindingexpression"></a>Die „Binding“-Klasse und „BindingExpression“

Bevor Sie auf andere Funktionen und Verwendungen der Datenbindung eingehen, ist es sinnvoll, die <xref:System.Windows.Data.BindingExpression> Klasse einzuführen. Wie Sie in den vorherigen <xref:System.Windows.Data.Binding> Abschnitten gesehen haben, ist die Klasse die übergeordnete Klasse für die Deklaration einer Bindung. Es bietet viele Eigenschaften, mit denen Sie die Eigenschaften einer Bindung angeben können. Eine verwandte <xref:System.Windows.Data.BindingExpression>Klasse, , ist das zugrunde liegende Objekt, das die Verbindung zwischen der Quelle und dem Ziel aufrechterhält. Ein Bindung enthält sämtliche Informationen, die von mehreren Bindungsausdrücken gemeinsam genutzt werden können. A <xref:System.Windows.Data.BindingExpression> ist ein Instanzausdruck, der nicht freigegeben werden <xref:System.Windows.Data.Binding>kann und alle Instanzinformationen der enthält.

Betrachten Sie das `myDataObject` folgende Beispiel, `MyData` wobei `myBinding` es sich <xref:System.Windows.Data.Binding> um `MyData` eine Instanz der Klasse handelt, `MyDataProperty`das Quellobjekt ist und eine definierte Klasse ist, die eine Zeichenfolgeneigenschaft mit dem Namen enthält. In diesem Beispiel wird `myText`der Textinhalt <xref:System.Windows.Controls.TextBlock>von `MyDataProperty`gebunden, eine Instanz von an .

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

Mit demselben *myBinding*-Objekt können Sie auch andere Bindungen erstellen. Sie können z. B. das *myBinding-Objekt* verwenden, um den Textinhalt eines Kontrollkästchens an *MyDataProperty*zu binden. In diesem Szenario gibt es <xref:System.Windows.Data.BindingExpression> zwei Instanzen, in denen das *myBinding-Objekt* gemeinsam freiwird.

Ein <xref:System.Windows.Data.BindingExpression> Objekt wird <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> zurückgegeben, indem ein datengebundenes Objekt aufgerufen wird. Die folgenden Artikel veranschaulichen einige <xref:System.Windows.Data.BindingExpression> der Verwendungen der Klasse:

- [Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [Steuern, wenn der TextBox-Text die Quelle aktualisiert](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>Datenkonvertierung

Im [Abschnitt Erstellen eines](#creating-a-binding) Bindungsabschnitts <xref:System.Windows.Controls.Control.Background%2A> ist die Schaltfläche rot, da ihre Eigenschaft an eine Zeichenfolgeneigenschaft mit dem Wert "Rot" gebunden ist. Dieser Zeichenfolgenwert funktioniert, da ein <xref:System.Windows.Media.Brush> Typkonverter für den <xref:System.Windows.Media.Brush>Typ vorhanden ist, um den Zeichenfolgenwert in eine zu konvertieren.

Wenn Sie diese Informationen zur Abbildung hinzufügen, sieht der Abschnitt [Erstellen einer Bindung](#creating-a-binding) wie folgt aus.

![Diagramm, das die Standardeigenschaft der Datenbindung anzeigt.](./media/data-binding-overview/data-binding-button-default-conversion.png)

Was ist jedoch, wenn das Bindungsquellobjekt anstelle einer Eigenschaft <xref:System.Windows.Media.Color>vom Typ string über eine *Color-Eigenschaft* vom Typ verfügt? In diesem Fall müssen Sie den Color-Eigenschaftswert *Color* zunächst in etwas umwandeln, das die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft akzeptiert, damit die Bindung funktioniert. Sie müssten einen benutzerdefinierten Konverter <xref:System.Windows.Data.IValueConverter> erstellen, indem Sie die Schnittstelle implementieren, wie im folgenden Beispiel.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

Weitere Informationen finden Sie unter <xref:System.Windows.Data.IValueConverter>.

Jetzt wird der benutzerdefinierte Konverter anstelle der Standardkonvertierung verwendet, und unser Diagramm sieht wie folgt aus.

![Diagramm, das den benutzerdefinierten Konverter für die Datenbindung anzeigt.](./media/data-binding-overview/data-binding-converter-color-example.png)

Wie bereits ausgeführt, können aufgrund von Typkonvertern, die im Typ vorhanden sind, an den gebunden wird, Standardkonvertierungen verfügbar sein. Dieses Verhalten hängt von den im Ziel vorhandenen Typkonvertern ab. Erstellen Sie im Zweifelsfall einen eigenen Konverter.

Im Folgenden finden Sie einige typische Szenarien, in denen es sinnvoll ist, einen Datenkonverter zu implementieren:

- Die Daten sollen je nach Kultur unterschiedlich angezeigt werden. Sie können z. B. einen Währungskonverter oder einen Kalenderdatums-/Zeitkonverter basierend auf den Konventionen implementieren, die in einer bestimmten Kultur verwendet werden.

- Die verwendeten Daten müssen nicht unbedingt dazu dienen, den Textwert einer Eigenschaft zu ändern. Sie können auch den Zweck haben, andere Werte zu ändern, beispielsweise die Quelle für ein Bild oder die Farbe bzw. das Format des Anzeigetexts. Konverter können in dieser Instanz verwendet werden, indem die Bindung einer Eigenschaft konvertiert wird, die ungeeignet zu sein scheint, z. B. wenn ein Textfeld an die Background-Eigenschaft einer Tabellenzelle gebunden wird.

- Mehr als ein Steuerelement oder mehrere Eigenschaften von Steuerelementen sind an dieselben Daten gebunden. In diesem Fall wird durch die primäre Bindung möglicherweise nur der Text angezeigt, wohingegen andere Bindungen bestimmte Anzeigeprobleme behandeln, aber dieselben Bindungen als Quellinformationen verwenden.

- Eine zieleigenschaft verfügt über eine Auflistung von <xref:System.Windows.Data.MultiBinding>Bindungen, die als bezeichnet wird. Für <xref:System.Windows.Data.MultiBinding>verwenden Sie <xref:System.Windows.Data.IMultiValueConverter> eine benutzerdefinierte, um einen endgültigen Wert aus den Werten der Bindungen zu erzeugen. So kann die Farbe beispielsweise aus roten, blauen und grünen Werten berechnet werden, die aus denselben oder anderen Bindungsquellobjekten stammen können. Beispiele <xref:System.Windows.Data.MultiBinding> und Informationen finden Sie unter .

## <a name="binding-to-collections"></a>Bindung an Sammlungen

Ein Bindungsquellobjekt kann entweder als einzelnes Objekt behandelt werden, dessen Eigenschaften Daten enthalten, oder als Datensammlung polymorpher Objekte, die häufig gruppiert sind (z. B. das Ergebnis einer Abfrage in einer Datenbank). Bisher haben wir nur die Bindung an einzelne Objekte diskutiert. Das Binden an eine Datensammlung ist jedoch ein häufiges Szenario. Ein gängiges Szenario besteht z. B. darin, <xref:System.Windows.Controls.ItemsControl> eine , <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView>oder <xref:System.Windows.Controls.TreeView> eine Datensammlung anzuzeigen, z. B. in der App, die im Abschnitt Was ist [Datenbindung](#what-is-data-binding) angezeigt wird.

Das bisherige einfache Diagramm ist praktischerweise immer noch gültig. Wenn Sie eine <xref:System.Windows.Controls.ItemsControl> an eine Auflistung binden, sieht das Diagramm wie folgt aus.

![Diagramm, das das Data Binding ItemsControl-Objekt zeigt.](./media/data-binding-overview/data-binding-itemscontrol.png)

Wie in diesem Diagramm gezeigt, ist die Eigenschaft, um eine <xref:System.Windows.Controls.ItemsControl> an ein Auflistungsobjekt zu binden, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType> die zu verwendende Eigenschaft. Sie können `ItemsSource` sich den Inhalt <xref:System.Windows.Controls.ItemsControl>der vorstellen. Die Bindung <xref:System.Windows.Data.BindingMode.OneWay> ist, weil die `ItemsSource` Eigenschaft standardmäßig die Bindung unterstützt. `OneWay`

### <a name="how-to-implement-collections"></a>So implementieren Sie Sammlungen

Sie können über jede Auflistung aufzählen, <xref:System.Collections.IEnumerable> die die Schnittstelle implementiert. Um jedoch dynamische Bindungen einzurichten, sodass Einfügungen oder Löschungen in der <xref:System.Collections.Specialized.INotifyCollectionChanged> Auflistung die Benutzeroberfläche automatisch aktualisieren, muss die Auflistung die Schnittstelle implementieren. Diese Schnittstelle macht ein Ereignis verfügbar, das bei jeder Änderung der zugrunde liegenden Auflistung ausgelöst werden sollte.

WPF stellt <xref:System.Collections.ObjectModel.ObservableCollection%601> die Klasse bereit, bei der es sich um <xref:System.Collections.Specialized.INotifyCollectionChanged> eine integrierte Implementierung einer Datensammlung handelt, die die Schnittstelle verfügbar macht. Um das Übertragen von Datenwerten von Quellobjekten auf Ziele vollständig zu unterstützen, <xref:System.ComponentModel.INotifyPropertyChanged> muss jedes Objekt in Ihrer Auflistung, das bindbare Eigenschaften unterstützt, auch die Schnittstelle implementieren. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](../../framework/wpf/data/binding-sources-overview.md).

Bevor Sie eine eigene Auflistung implementieren, erwägen Sie <xref:System.Collections.ObjectModel.ObservableCollection%601> oder einer vorhandenen Sammlung Klassen, z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, und <xref:System.ComponentModel.BindingList%601>, a. Wenn Sie über ein erweitertes Szenario verfügen und <xref:System.Collections.IList>eine eigene Auflistung implementieren möchten, sollten Sie verwenden, die eine nicht generische Auflistung von Objekten bereitstellt, auf die der Index individuell zugreifen kann und somit die beste Leistung bietet.

### <a name="collection-views"></a>Sammlungsansichten

Sobald <xref:System.Windows.Controls.ItemsControl> Sie an eine Datensammlung gebunden sind, können Sie die Daten sortieren, filtern oder gruppieren. Dazu verwenden Sie Auflistungsansichten, d. h. Klassen, die die <xref:System.ComponentModel.ICollectionView> Schnittstelle implementieren.

#### <a name="what-are-collection-views"></a>Was sind Auflistungsansichten?

Eine Auflistungsansicht fungiert als Ebene über der Bindungsquellauflistung, in der Sie mit Sortier-, Filter- und Gruppierungsabfragen navigieren und die jeweilige Quellauflistung anzeigen können, ohne die zugrunde liegende Quellauflistung selbst ändern zu müssen. Eine Auflistungsansicht stellt außerdem einen Zeiger auf das aktuelle Element in der Auflistung zur Verfügung. Wenn die Quellauflistung <xref:System.Collections.Specialized.INotifyCollectionChanged> die Schnittstelle implementiert, <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> werden die vom Ereignis ausgelösten Änderungen an die Ansichten weitergegeben.

Da in Ansichten die zugrunde liegenden Quellauflistungen nicht geändert werden, können einer Quellauflistung mehrere Ansichten zugeordnet sein. Angenommen, Sie verfügen über eine Auflistung von *Task*-Objekten. Mithilfe von Ansichten können Sie dieselben Daten auf verschiedene Weise anzeigen. Beispielsweise können Sie links auf der Seite Aufgaben nach Priorität und rechts nach Bereich sortieren.

#### <a name="how-to-create-a-view"></a>Erstellen einer Ansicht

Eine Möglichkeit, eine Ansicht zu erstellen und zu verwenden, besteht darin, das Ansichtsobjekt direkt zu instanziieren und dann als Bindungsquelle zu verwenden. Betrachten Sie beispielsweise die [Datenbindungsdemo-App,][data-binding-demo] die im Abschnitt [Was ist Datenbindung](#what-is-data-binding) angezeigt wird. Die App ist so <xref:System.Windows.Controls.ListBox> implementiert, dass die an eine Ansicht über die Datensammlung anstelle der Datensammlung direkt gebunden ist. Das folgende Beispiel wird aus der [Datenbindungsdemo-App][data-binding-demo] extrahiert. Die <xref:System.Windows.Data.CollectionViewSource> Klasse ist der XAML-Proxy einer <xref:System.Windows.Data.CollectionView>Klasse, die von erbt. In diesem speziellen <xref:System.Windows.Data.CollectionViewSource.Source%2A> Beispiel ist die ansicht an die *AuctionItems-Auflistung* (vom Typ <xref:System.Collections.ObjectModel.ObservableCollection%601>) des aktuellen App-Objekts gebunden.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

Die *RessourcenauflistungDataView* dient dann als Bindungsquelle für Elemente <xref:System.Windows.Controls.ListBox>in der App, z. B. die .

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

Um eine andere Ansicht für dieselbe Auflistung <xref:System.Windows.Data.CollectionViewSource> zu erstellen, `x:Key` können Sie eine andere Instanz erstellen und ihr einen anderen Namen geben.

Die folgende Tabelle zeigt, welche Ansichtsdatentypen als <xref:System.Windows.Data.CollectionViewSource> Standardsammlungsansicht oder basierend auf dem Quellauflistungstyp erstellt werden.

| Quellauflistungstyp                    | Auflistungsansichtstyp | Notizen |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | Ein interner Typ, der auf<xref:System.Windows.Data.CollectionView> | Kann Elemente nicht gruppieren. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | Am schnellsten. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>Verwenden einer Standardansicht

Die Angabe einer Auflistungsansicht als Bindungsquelle ist eine Möglichkeit, eine Auflistungsansicht zu erstellen und zu verwenden. WPF erstellt außerdem eine Standardauflistungsansicht für jede als Bindungsquelle verwendete Auflistung. Bei der direkten Bindung an eine Auflistung bindet WPF an die Standardansicht der Auflistung. Diese Standardansicht wird von allen Bindungen für dieselbe Auflistung gemeinsam genutzt, sodass eine Änderung, die an einer Standardansicht durch ein gebundenes Steuerelement oder einen Code vorgenommen wurde (z. B. Sortieren oder eine Änderung am aktuellen Elementzeiger, weiter unten erläutert), in allen anderen Bindungen für dieselbe Auflistung widergespiegelt wird.

Um die Standardansicht abzubekommen, verwenden Sie die <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> Methode. Ein Beispiel finden Sie unter [Abrufen der Standardansicht einer Datensammlung](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).

#### <a name="collection-views-with-adonet-datatables"></a>Sammlungsansichten mit ADO.NET DataTables

Um die Leistung zu <xref:System.Data.DataTable> verbessern, delegieren Auflistungsansichten für ADO.NET oder <xref:System.Data.DataView> Objekte die Sortierung und Filterung an die <xref:System.Data.DataView>, wodurch das Sortieren und Filtern in allen Auflistungsansichten der Datenquelle freigegeben wird. Damit jede Auflistungsansicht unabhängig sortiert und gefiltert werden kann, initialisieren Sie jede Auflistungsansicht mit einem eigenen <xref:System.Data.DataView> Objekt.

#### <a name="sorting"></a>Sortierung

Wie bereits erwähnt, können mit Ansichten Sortierreihenfolgen auf Auflistungen angewendet werden. Da sie in der zugrunde liegenden Auflistung vorhanden sind, haben die Daten möglicherweise eine relevante inhärente Reihenfolge oder nicht. Die Ansicht der Auflistung ermöglicht Ihnen das Festlegen einer Reihenfolge oder das Ändern der Standardreihenfolge, je nachdem, welche Vergleichskriterien Sie angeben. Da es sich um eine clientbasierte Ansicht der Daten handelt, besteht ein übliches Szenario darin, dass der Benutzer Spalten mit Tabellendaten nach dem Wert sortiert, dem die Spalte entspricht. Mithilfe von Ansichten kann diese benutzerdefinierte Sortierung angewendet werden, ohne die zugrunde liegende Auflistung ändern oder den Auflistungsinhalt erneut abfragen zu müssen. Ein Beispiel finden Sie unter [Sortieren einer GridView-Spalte, wenn auf eine Kopfzeile geklickt wird.](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)

Das folgende Beispiel zeigt die Sortierlogik der <xref:System.Windows.Controls.CheckBox> "Sortierung nach Kategorie und Datum" der App-Benutzeroberfläche im Abschnitt [Was ist Datenbindung.](#what-is-data-binding)

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>Filtern

Ansichten können auch einen Filter auf eine Auflistung anwenden, sodass in der Ansicht nur eine bestimmte Teilmenge der vollständigen Auflistung angezeigt wird. Sie können die Daten nach einer Bedingung filtern. Zum Beispiel, wie von der App im Abschnitt [Was ist Datenbindung](#what-is-data-binding) <xref:System.Windows.Controls.CheckBox> tut, enthält das "Nur Schnäppchen anzeigen" Logik, um Artikel herauszufiltern, die 25 $ oder mehr kosten. Der folgende Code wird ausgeführt, um *ShowOnlyBargainsFilter* als <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignishandler festzulegen, wenn dieser <xref:System.Windows.Controls.CheckBox> ausgewählt ist.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

Der *ShowOnlyBargainsFilter-Ereignishandler* verfügt über die folgende Implementierung.

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

Wenn Sie eine der <xref:System.Windows.Data.CollectionView> Klassen direkt <xref:System.Windows.Data.CollectionViewSource>anstelle von <xref:System.Windows.Data.CollectionView.Filter%2A> verwenden, verwenden Sie die Eigenschaft, um einen Rückruf anzugeben. Ein Beispiel finden Sie unter [Filtern von Daten in einer Ansicht](../../framework/wpf/data/how-to-filter-data-in-a-view.md).

#### <a name="grouping"></a>Gruppierung

Mit Ausnahme der internen <xref:System.Collections.IEnumerable> Klasse, die eine Auflistung anzeigt, unterstützen alle Auflistungsansichten die *Gruppierung*, die es dem Benutzer ermöglicht, die Auflistung in der Auflistungsansicht in logische Gruppen zu partitionieren. Die Gruppen können explizit sein, wobei Benutzer eine Liste von Gruppen angeben. Sie können auch implizit sein, wobei die Gruppen dynamisch in Abhängigkeit von den Daten generiert werden.

Das folgende Beispiel zeigt die Logik der <xref:System.Windows.Controls.CheckBox>"Gruppe nach Kategorie" .

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

Ein weiteres Beispiel zu Gruppierungen finden Sie unter [Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).

#### <a name="current-item-pointers"></a>Aktuelle Elementzeiger

Ansichten unterstützen ebenfalls das Konzept eines aktuellen Elements. Sie können durch die Objekte in einer Auflistungsansicht navigieren. Beim Navigieren verschieben Sie einen Elementzeiger, mit dem Sie das Objekt abrufen können, das sich an einer bestimmten Position in der Auflistung befindet. Ein Beispiel finden Sie unter [Navigieren durch die Objekte in einer Daten-CollectionView](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).

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

Der Zeiger auf das aktuelle Element kann durch eine Sortierung oder Filterung beeinflusst werden, die auf die Auflistung angewendet wird. Beim Sortieren verbleibt der Zeiger für das aktuelle Element auf dem zuletzt ausgewählten Element, die Auflistungsansicht wird jedoch nun um den Zeiger herum neu angeordnet. (Vielleicht war das ausgewählte Element am Anfang der Liste vor, aber jetzt könnte das ausgewählte Element irgendwo in der Mitte sein.) Durch das Filtern wird das ausgewählte Element beibehalten, wenn diese Auswahl nach der Filterung sichtbar bleibt. Andernfalls wird der Zeiger für das aktuelle Element auf das erste Element der gefilterten Auflistungsansicht festgelegt.

#### <a name="master-detail-binding-scenario"></a>Master-Detail-Bindungsszenario

Das Konzept eines aktuellen Elements ist nicht nur hilfreich, um durch Elemente in einer Auflistung zu navigieren, sondern auch für das Szenario einer Master-Detail-Bindung. Betrachten Sie die App-Benutzeroberfläche im Abschnitt [Was ist Datenbindung,](#what-is-data-binding) erneut. In dieser App bestimmt <xref:System.Windows.Controls.ListBox> die Auswahl innerhalb <xref:System.Windows.Controls.ContentControl>der den Inhalt, der im angezeigt wird. Um es auf eine andere <xref:System.Windows.Controls.ListBox> Weise zu <xref:System.Windows.Controls.ContentControl> setzen, wenn ein Element ausgewählt ist, zeigt der die Details des ausgewählten Elements an.

Sie können das Master-Detail-Szenario auch einfach dadurch implementieren, dass mindestens zwei Steuerelemente an dieselbe Ansicht gebunden sind. Das folgende Beispiel aus der [Datenbindungsdemo][data-binding-demo] zeigt das Markup der <xref:System.Windows.Controls.ListBox> und die, die Sie auf der <xref:System.Windows.Controls.ContentControl> App-Benutzeroberfläche im Abschnitt Was ist [Datenbindung](#what-is-data-binding) sehen.

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

Beachten Sie, dass beide Steuerelemente an dieselbe Quelle, die statische *Ressource listingDataView,* gebunden sind (siehe die Definition dieser Ressource im [Abschnitt Erstellen eines Ansichtsabschnitts](#how-to-create-a-view)). Diese Bindung funktioniert, da ein Singleton-Objekt (in <xref:System.Windows.Controls.ContentControl> diesem Fall) automatisch an <xref:System.Windows.Data.CollectionView.CurrentItem%2A> die Ansicht gebunden ist. Die <xref:System.Windows.Data.CollectionViewSource> Objekte synchronisieren automatisch Währung und Auswahl. Wenn das Listensteuerelement nicht <xref:System.Windows.Data.CollectionViewSource> wie in diesem Beispiel an ein Objekt <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> gebunden `true` ist, müssen Sie seine Eigenschaft festlegen, damit dies funktioniert.

Weitere Beispiele finden Sie unter [Binden an eine Sammlung und Anzeige von Informationen basierend auf der Auswahl](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) und Verwenden des [Master-Detailmusters mit hierarchischen Daten](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).

Ihnen ist vielleicht aufgefallen, dass im vorherigen Beispiel eine Vorlage verwendet wird. In der Tat würden die Daten nicht so angezeigt, wie wir es uns <xref:System.Windows.Controls.ContentControl> wünschen, ohne die <xref:System.Windows.Controls.ListBox>Verwendung von Vorlagen (die, die explizit von der verwendet wird, und die, die implizit von der verwendet wird). Im nächsten Abschnitt beschäftigen wir uns mit Datenvorlagen.

## <a name="data-templating"></a>Datenvorlagen

Ohne die Verwendung von Datenvorlagen würde unsere App-Benutzeroberfläche im Abschnitt [Was ist Datenbindung](#what-is-data-binding) wie folgt aussehen.

![Demobeispiel für Datenbindung ohne Datenvorlagen](./media/data-binding-overview/demo-no-template.png)

Wie im Beispiel im vorherigen Abschnitt <xref:System.Windows.Controls.ListBox> gezeigt, <xref:System.Windows.Controls.ContentControl> sind sowohl das Steuerelement als auch der an das gesamte Auflistungsobjekt (oder genauer gesagt die Ansicht über das Auflistungsobjekt) von *AuctionItem*s gebunden. Ohne spezifische Anweisungen zum Anzeigen der <xref:System.Windows.Controls.ListBox> Datensammlung zeigt der die Zeichenfolgendarstellung jedes <xref:System.Windows.Controls.ContentControl> Objekts in der zugrunde liegenden Auflistung und die Zeichenfolgendarstellung des Objekts an, an das es gebunden ist.

Um dieses Problem zu lösen, definiert die App <xref:System.Windows.DataTemplate?text=DataTemplates>. Wie im Beispiel im vorherigen Abschnitt <xref:System.Windows.Controls.ContentControl> gezeigt, verwendet der explizit die *Datenvorlage detailsProductListingTemplate.* Das <xref:System.Windows.Controls.ListBox> Steuerelement verwendet implizit die folgende Datenvorlage, wenn die *AuctionItem-Objekte* in der Auflistung angezeigt werden.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

Bei Verwendung dieser beiden DataTemplates ist die resultierende Benutzeroberfläche diejenige, die im Abschnitt [Was ist Datenbindung](#what-is-data-binding) gezeigt wird. Wie Sie aus diesem Screenshot sehen können, können Sie nicht nur Daten in Ihren Steuerelementen platzieren, sondern auch überzeugende Visualisierungen für Ihre Daten definieren. Beispielsweise werden <xref:System.Windows.DataTrigger>s in den <xref:System.Windows.DataTemplate> obigen Werten verwendet, sodass *AuctionItem*s mit *dem SpecialFeatures-Wert* von *HighLight* mit einem orangefarbenen Rand und einem Stern angezeigt werden.

Weitere Informationen zu Datenvorlagen finden Sie in der Übersicht über die [Datenbearbeitung](../../framework/wpf/data/data-templating-overview.md).

## <a name="data-validation"></a>Datenüberprüfung

Die meisten Apps, die Benutzereingaben benötigen, benötigen Validierungslogik, um sicherzustellen, dass der Benutzer die erwarteten Informationen eingegeben hat. Die Validierungsprüfungen können auf Typ, Bereich, Format oder anderen app-spezifischen Anforderungen basieren. In diesem Abschnitt wird erläutert, wie die Datenvalidierung in WPF funktioniert.

### <a name="associating-validation-rules-with-a-binding"></a>Zuordnen von Validierungsregeln zu einer Bindung

Mit dem WPF-Datenbindungsmodell <xref:System.Windows.Data.Binding> können Sie Ihrem Objekt zuordnen. <xref:System.Windows.Data.Binding.ValidationRules%2A> Im folgenden Beispiel wird z. <xref:System.Windows.Controls.TextBox> B. `StartPrice` eine <xref:System.Windows.Controls.ExceptionValidationRule> an eine <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> benannte Eigenschaft gebunden und der Eigenschaft ein Objekt hinzugefügt.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

Ein <xref:System.Windows.Controls.ValidationRule> Objekt überprüft, ob der Wert einer Eigenschaft gültig ist. WPF verfügt über zwei <xref:System.Windows.Controls.ValidationRule> Arten von integrierten Objekten:

- Eine <xref:System.Windows.Controls.ExceptionValidationRule> Überprüfung auf Ausnahmen, die während der Aktualisierung der Bindungsquelleigenschaft ausgelöst wurden. Im vorherigen Beispiel ist `StartPrice` eine ganze Zahl. Wenn der Benutzer einen Wert eingibt, der nicht in eine ganze Zahl konvertiert werden kann, wird eine Ausnahme ausgelöst, wodurch die Bindung als ungültig markiert wird. Eine alternative Syntax <xref:System.Windows.Controls.ExceptionValidationRule> zum Festlegen der <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> explizit `true` ist, die Eigenschaft auf Ihr <xref:System.Windows.Data.Binding> oder <xref:System.Windows.Data.MultiBinding> Objekt festzulegen.

- Ein <xref:System.Windows.Controls.DataErrorValidationRule> Objekt überprüft, ob Fehler von <xref:System.ComponentModel.IDataErrorInfo> Objekten ausgelöst werden, die die Schnittstelle implementieren. Ein Beispiel für die Verwendung <xref:System.Windows.Controls.DataErrorValidationRule>dieser Validierungsregel finden Sie unter . Eine alternative Syntax <xref:System.Windows.Controls.DataErrorValidationRule> zum Festlegen der <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> explizit `true` ist, die Eigenschaft auf Ihr <xref:System.Windows.Data.Binding> oder <xref:System.Windows.Data.MultiBinding> Objekt festzulegen.

Sie können auch eine eigene Validierungsregel <xref:System.Windows.Controls.ValidationRule> erstellen, indem <xref:System.Windows.Controls.ValidationRule.Validate%2A> Sie von der Klasse ableiten und die Methode implementieren. Das folgende Beispiel zeigt die Regel, die vom <xref:System.Windows.Controls.TextBox> *Produkteintrag* "Startdatum" hinzufügen aus dem Abschnitt [Was ist Datenbindung](#what-is-data-binding) ist.

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

Das *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> verwendet diese *FutureDateRule*, wie im folgenden Beispiel gezeigt.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

Da <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> der <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>Wert ist , aktualisiert das Bindungsmodul den Quellwert bei jedem <xref:System.Windows.Data.Binding.ValidationRules%2A> Tastenanschlag, was bedeutet, dass es auch jede Regel in der Auflistung bei jedem Tastenanschlag überprüft. Dies wird im Abschnitt zum Validierungsprozess näher erläutert.

### <a name="providing-visual-feedback"></a>Visuelles Feedback

Wenn der Benutzer einen ungültigen Wert eingibt, können Sie Feedback zu dem Fehler auf der App-Benutzeroberfläche geben. Eine Möglichkeit, ein solches Feedback <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> bereitzustellen, besteht <xref:System.Windows.Controls.ControlTemplate>darin, die angefügte Eigenschaft auf eine benutzerdefinierte festzulegen. Wie im vorherigen Unterabschnitt gezeigt, verwendet das <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> eine aufgerufene *validationTemplate*. Das folgende Beispiel zeigt die Definition von *validationTemplate*.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

Das <xref:System.Windows.Controls.AdornedElementPlaceholder> Element gibt an, wo das zu schmückende Steuerelement platziert werden soll.

Darüber hinaus können Sie <xref:System.Windows.Controls.ToolTip> auch eine verwenden, um die Fehlermeldung anzuzeigen. Sowohl das *StartDateEntryForm als* auch das *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es verwenden <xref:System.Windows.Controls.ToolTip> die Formatvorlage *textStyleTextBox*, die eine erstellt, die die Fehlermeldung anzeigt. Im folgenden Beispiel wird die Definition von *textStyleTextBox* dargestellt. Die angefügte Eigenschaft <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> ist, `true` wenn eine oder mehrere Bindungen für die Eigenschaften des gebundenen Elements fehlerhaft sind.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

Bei <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> benutzerdefiniertem <xref:System.Windows.Controls.ToolTip>und dem sieht das *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> wie folgt aus, wenn ein Validierungsfehler auftritt.

![Datenbindungs-Validierungsfehler](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

Wenn <xref:System.Windows.Data.Binding> Sie über zugeordnete Validierungsregeln <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> verfügen, aber kein <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> für das gebundene Steuerelement angeben, wird ein Standardverwendet, um Benutzer zu benachrichtigen, wenn ein Validierungsfehler auftritt. Der <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> Standardwert ist eine Steuerelementvorlage, die einen roten Rahmen im Adorner-Layer definiert. Mit dem <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> Standard <xref:System.Windows.Controls.ToolTip>und dem sieht die Benutzeroberfläche des *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> wie folgt aus, wenn ein Validierungsfehler auftritt.

![Datenbindungs-Validierungsfehler](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

Ein Beispiel für die Bereitstellung von Logik zum Überprüfen aller Steuerelemente in einem Dialogfeld finden Sie im Abschnitt Benutzerdefinierte Dialogfelder in der [Dialogfeldübersicht](../../framework/wpf/app-development/dialog-boxes-overview.md).

### <a name="validation-process"></a>Validierungsprozess

Eine Validierung erfolgt normalerweise, wenn der Wert eines Ziels an die Bindungsquelleigenschaft übergeben wird. Diese Übertragung <xref:System.Windows.Data.BindingMode.TwoWay> erfolgt <xref:System.Windows.Data.BindingMode.OneWayToSource> auf und Bindungen. Was eine Quellaktualisierung verursacht, hängt vom <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert der Eigenschaft ab, wie im Abschnitt [Was Quellaktualisierungen auslöst,](#what-triggers-source-updates) beschrieben.

Die folgenden Elemente beschreiben den *Validierungsprozess.* Wenn während dieses Vorgangs zu einem Validierungsfehler oder einem anderen Fehlertyp auftritt, wird der Prozess angehalten:

1. Das Bindungsmodul überprüft, <xref:System.Windows.Controls.ValidationRule> ob benutzerdefinierte Objekte <xref:System.Windows.Controls.ValidationStep.RawProposedValue> definiert <xref:System.Windows.Data.Binding>sind, auf die <xref:System.Windows.Controls.ValidationRule.Validate%2A> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt <xref:System.Windows.Controls.ValidationRule> ist, in diesem Fall ruft es die Methode für jedes objektisch auf, bis eines von ihnen in einen Fehler läuft oder bis alle von ihnen übergeben werden.

2. Anschließend ruft die Bindungs-Engine den Konverter auf, sofern vorhanden.

3. Wenn der Konverter erfolgreich ist, prüft das <xref:System.Windows.Controls.ValidationRule> Bindungsmodul, ob benutzerdefinierte Objekte definiert sind, auf <xref:System.Windows.Controls.ValidationRule> die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> <xref:System.Windows.Data.Binding>ist, in diesem Fall ruft es die <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode auf, die auf <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> jedes von ihnen festgelegt hat, bis einer von ihnen in einen Fehler läuft oder bis alle von ihnen übergeben werden.

4. Die Bindungs-Engine legt die Quelleigenschaft fest.

5. Das Bindungsmodul überprüft, <xref:System.Windows.Controls.ValidationRule> ob benutzerdefinierte Objekte <xref:System.Windows.Controls.ValidationStep.UpdatedValue> definiert <xref:System.Windows.Data.Binding>sind, auf die <xref:System.Windows.Controls.ValidationRule.Validate%2A> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt ist, <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> in <xref:System.Windows.Controls.ValidationStep.UpdatedValue> diesem Fall ruft es die Methode auf, auf die festgelegt <xref:System.Windows.Controls.ValidationRule> wurde, bis eines von ihnen in einen Fehler läuft oder bis alle von ihnen übergeben werden. Wenn <xref:System.Windows.Controls.DataErrorValidationRule> a einer Bindung zugeordnet <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> ist und sie <xref:System.Windows.Controls.ValidationStep.UpdatedValue>auf <xref:System.Windows.Controls.DataErrorValidationRule> den Standardwert gesetzt ist, wird der an dieser Stelle überprüft. An dieser Stelle <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> `true` wird jede Bindung, auf der die Einstellung gesetzt ist, überprüft.

6. Das Bindungsmodul überprüft, <xref:System.Windows.Controls.ValidationRule> ob benutzerdefinierte Objekte <xref:System.Windows.Controls.ValidationStep.CommittedValue> definiert <xref:System.Windows.Data.Binding>sind, auf die <xref:System.Windows.Controls.ValidationRule.Validate%2A> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt ist, <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> in <xref:System.Windows.Controls.ValidationStep.CommittedValue> diesem Fall ruft es die Methode auf, auf die festgelegt <xref:System.Windows.Controls.ValidationRule> wurde, bis eines von ihnen in einen Fehler läuft oder bis alle von ihnen übergeben werden.

Wenn <xref:System.Windows.Controls.ValidationRule> a während dieses Vorgangs zu keinem Zeitpunkt <xref:System.Windows.Controls.ValidationError> vergeht, erstellt <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> das Bindungsmodul ein Objekt und fügt es der Auflistung des gebundenen Elements hinzu. Bevor das Bindungsmodul die <xref:System.Windows.Controls.ValidationRule> Objekte in einem <xref:System.Windows.Controls.ValidationError> bestimmten Schritt ausführt, werden alle Objekte entfernt, die der <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> angefügten Eigenschaft des gebundenen Elements während dieses Schritts hinzugefügt wurden. Wenn z. <xref:System.Windows.Controls.ValidationRule> B. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> ein, dessen Einstellung auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> "Fehlgeschlagen" festgelegt ist, <xref:System.Windows.Controls.ValidationError> entfernt das <xref:System.Windows.Controls.ValidationRule> Bindungsmodul das, das unmittelbar vor dem Aufrufen eines auf <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> . <xref:System.Windows.Controls.ValidationStep.UpdatedValue>

Wenn <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> nicht leer, <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> wird die angefügte `true`Eigenschaft des Elements auf festgelegt. <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> Wenn die Eigenschaft des <xref:System.Windows.Data.Binding> auf `true`festgelegt ist, löst <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> das Bindungsmodul das angefügte Ereignis für das Element aus.

Beachten Sie außerdem, dass eine gültige Wertübertragung in beide Richtungen <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> (Ziel an Quelle an Quelle zu Ziel) die angefügte Eigenschaft löscht.

Wenn der Bindung <xref:System.Windows.Controls.ExceptionValidationRule> entweder eine zugeordnet ist <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> oder die `true` Eigenschaft auf festgelegt ist und eine Ausnahme ausgelöst wird, wenn das <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>Bindungsmodul die Quelle festlegt, überprüft das Bindungsmodul, ob eine vorhanden ist. Sie haben die Möglichkeit, den <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> Rückruf zu verwenden, um einen benutzerdefinierten Handler für die Behandlung von Ausnahmen bereitzustellen. Wenn <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> auf der <xref:System.Windows.Data.Binding>nicht angegeben ist, <xref:System.Windows.Controls.ValidationError> erstellt das Bindungsmodul <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> eine mit der Ausnahme und fügt sie der Auflistung des gebundenen Elements hinzu.

## <a name="debugging-mechanism"></a>Debugging-Mechanismus

Sie können die <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> angehängte Eigenschaft für ein bindungsbezogenes Objekt festlegen, um Informationen über den Status einer bestimmten Bindung zu erhalten.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Binden an die Ergebnisse einer LINQ-Abfrage](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [Datenbindung](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Datenbindungsdemo][data-binding-demo]
- [How-to-Artikel](../../framework/wpf/data/data-binding-how-to-topics.md)
- [Binden an eine ADO.NET-Datenquelle](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "Datenbindungsdemo-App"
