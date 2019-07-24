---
title: Übersicht über die Datenbindung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data conversion for binding [WPF]
- binding data [WPF], about data binding
- data binding [WPF], about data binding
- conversion for data binding [WPF]
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
ms.openlocfilehash: e1fbb46c76fbc729818b6ff24b55c0d18f6b05df
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400699"
---
# <a name="data-binding-overview"></a>Übersicht über die Datenbindung
Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können an Daten aus einer Vielzahl von Datenquellen in Form von Common Language Runtime (CLR)-Objekten und [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]gebunden werden. <xref:System.Windows.Controls.ContentControl>z <xref:System.Windows.Controls.Button> . b. <xref:System.Windows.Controls.ItemsControl>und s, <xref:System.Windows.Controls.ListBox> wie <xref:System.Windows.Controls.ListView> z. b. und, verfügen über integrierte Funktionen, die eine flexible Formatierung einzelner Datenelemente oder Auflistungen von Datenelementen ermöglichen. Sortier-, Filter- und Gruppenansichten können übergreifend für die Daten generiert werden.  
  
 Die Datenbindungsfunktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten gegenüber herkömmlichen Modellen einige Vorteile. Dazu zählen eine Reihe von Eigenschaften, die Datenbindung grundsätzlich unterstützen, eine flexible Darstellung von Daten auf einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sowie die klare Trennung zwischen Geschäftslogik und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 In diesem Thema werden zunächst die Grund [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Legenden Konzepte für die Datenbindung erläutert. Anschließend wird <xref:System.Windows.Data.Binding> die Verwendung der-Klasse und anderer Funktionen der Datenbindung erläutert.  

<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>Was ist Datenbindung?  
 Durch Datenbindung wird eine Verbindung zwischen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung und der Geschäftslogik hergestellt. Wenn die Bindung die ordnungsgemäßen Einstellungen aufweist und die Daten die richtigen Benachrichtigungen bereitstellen, ändern sich die an die Daten gebundenen Elemente automatisch bei jeder Änderung des Werts der Daten, sodass die Änderungen entsprechend wiedergegeben werden. Datenbindung kann auch bedeuten, dass bei einer Änderung der äußeren Darstellung von Daten in einem Element die zugrunde liegenden Daten automatisch aktualisiert werden können, um die Änderung wiederzugeben. Wenn der Benutzer z. b. den Wert in einem <xref:System.Windows.Controls.TextBox> -Element bearbeitet, wird der zugrunde liegende Datenwert automatisch aktualisiert, um die Änderung widerzuspiegeln.  
  
 Eine typische Verwendung der Datenbindung wäre, die auf einem Server oder lokal gespeicherten Konfigurationsdaten in Formulare oder andere Steuerelemente der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] einzufügen. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird dieses Konzept dahingehend erweitert, dass auch eine Vielzahl von Eigenschaften an die unterschiedlichsten Datenquellen gebunden werden können. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]können Abhängigkeits Eigenschaften von Elementen an CLR-Objekte (einschließlich ADO.NET-Objekten oder-Objekten, die Webdiensten und Webeigenschaften zugeordnet sind) und [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten gebunden werden.  
  
 Ein Beispiel für eine Datenbindung finden Sie auf der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der folgenden Anwendung in der [Demo für die Datenbindung](https://go.microsoft.com/fwlink/?LinkID=163703):  
  
 ![Screenshot: Beispiel für Datenbindung](./media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 Oben sehen Sie die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] einer Anwendung, die eine Liste von Auktionselementen anzeigt. Die Anwendung veranschaulicht die folgenden Datenbindungsfunktionen:  
  
- Der Inhalt von <xref:System.Windows.Controls.ListBox> ist an eine Auflistung von *AuctionItem* -Objekten gebunden. Ein *AuctionItem*-Objekt verfügt über Eigenschaften wie *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* usw.  
  
- Die in der <xref:System.Windows.Controls.ListBox> angezeigten Daten (*Auktions Element* Objekte) werden Vorlagen Weise angezeigt, sodass die Beschreibung und der aktuelle Preis für jedes Element angezeigt werden. Dies erfolgt mithilfe einer <xref:System.Windows.DataTemplate>. Darüber hinaus hängt die Darstellung jedes Elements vom *SpecialFeatures*-Wert des angezeigten *AuctionItem* ab. Wenn der *SpecialFeatures*-Wert von *AuctionItem* auf *Color* festgelegt ist, hat das Element einen blauen Rahmen. Wenn der Wert *Highlight* ist, hat das Element einen orangefarbenen Rahmen und einen Stern. Im Abschnitt [Datenvorlagen](#data_templating) erhalten Sie weitere Informationen zu Datenvorlagen.  
  
- Der Benutzer kann die Daten mithilfe der <xref:System.Windows.Controls.CheckBox>angegebenen es gruppieren, Filtern oder sortieren. In der obigen Abbildung sind die Elemente "Gruppieren nach Kategorie" und "nach Kategorie und Datum <xref:System.Windows.Controls.CheckBox>sortieren" ausgewählt. Möglicherweise haben Sie bereits bemerkt, dass die Daten nach der Kategorie des Produkts gruppiert sind und der Name der Kategorie in alphabetischer Reihenfolge aufgeführt ist. In der Abbildung ist nicht so gut zu erkennen, dass auch die Elemente innerhalb der einzelnen Kategorien nach Startdatum sortiert sind. Dazu wird eine *Auflistungsansicht* verwendet. Im Abschnitt [Binden an Auflistungen](#binding_to_collections) werden Auflistungsansichten erläutert.  
  
- Wenn der Benutzer ein Element auswählt, <xref:System.Windows.Controls.ContentControl> zeigt die Details des ausgewählten Elements an. Dies wird als *Master/Detail-Szenario* bezeichnet. Im Abschnitt [Master/Detail-Szenario](#master_detail_scenario) erhalten Sie Informationen zu diesem Typ von Bindungsszenario.  
  
- Der Typ der *StartDate* -Eigenschaft ist <xref:System.DateTime>. dieser gibt ein Datum zurück, das die Zeit bis zur Millisekunde enthält. In dieser Anwendung wurde ein benutzerdefinierter Konverter verwendet, damit eine kürzere Datumszeichenfolge angezeigt wird. Weitere Informationen zu Konvertern finden Sie im Abschnitt [Datenkonvertierung](#data_conversion).  
  
 Wenn der Benutzer auf die Schaltfläche *Add Product* klickt, wird das folgende Formular aufgerufen:  
  
 ![Seite „Produktliste hinzufügen“](./media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 Der Benutzer kann die Felder im Formular bearbeiten, die Produktauflistung in der Kurzvorschau und in den detaillierteren Vorschaufenstern anzeigen und dann auf *submit* klicken, um die neue Produktauflistung hinzuzufügen. Alle vorhandenen Gruppierungs-, Filter- und Sortierfunktionen werden auf den neuen Eintrag angewendet. In diesem speziellen Fall wird das im obigen Bild eingegebene Element in der Kategorie *Computer* an zweiter Stelle angezeigt.  
  
 Nicht in diesem Bild angezeigt wird, ist die Validierungs Logik, die im *Start Datum* <xref:System.Windows.Controls.TextBox>bereitgestellt wird. Wenn der Benutzer ein ungültiges Datum eingibt (ungültige Formatierung oder letztes Datum), wird der Benutzer mit einem <xref:System.Windows.Controls.ToolTip> und einem roten Ausrufezeichen neben dem <xref:System.Windows.Controls.TextBox>benachrichtigt. Im Abschnitt [Datenvalidierung](#data_validation) wird näher auf das Erstellen von Validierungslogik eingegangen.  
  
 Bevor die oben genannten unterschiedlichen Datenbindungsfunktionen näher erläutert werden, werden im nächsten Abschnitt die grundlegenden Konzepte erläutert, die für ein Verständnis der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Datenbindung unerlässlich sind.  
  
## <a name="basic-data-binding-concepts"></a>Grundlegende Konzepte zur Datenbindung  
  
 Unabhängig davon, welches Element Sie binden und welcher Art die Datenquelle ist, erfolgt die Bindung stets gemäß dem in der folgenden Abbildung gezeigten Modell:  
  
 ![Diagramm, das das grundlegende Daten Bindungs Modell zeigt.](./media/data-binding-overview/basic-data-binding-diagram.png)  
  
 Wie in der Abbildung dargestellt, ist Datenbindung die Brücke zwischen dem Bindungsziel und der Bindungsquelle. Die Abbildung veranschaulicht die folgenden grundlegenden Konzepte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Datenbindung:  
  
- Eine Bindung besteht in der Regel aus diesen vier Komponenten: einem Bindungszielobjekt, einer Zieleigenschaft, einer Bindungsquelle sowie einem Pfad zum Wert in der Bindungsquelle, die verwendet werden soll. Wenn Sie z. b. den Inhalt <xref:System.Windows.Controls.TextBox> einer an die *Name* -Eigenschaft eines *Employee* -Objekts binden möchten, ist das Zielobjekt das <xref:System.Windows.Controls.TextBox>. die Ziel Eigenschaft ist die <xref:System.Windows.Controls.TextBox.Text%2A> -Eigenschaft, der zu verwendende Wert ist *Name*und die das Quell Objekt ist das *Employee* -Objekt.  
  
- Die Zieleigenschaft muss eine Abhängigkeitseigenschaft sein. Die <xref:System.Windows.UIElement> meisten Eigenschaften sind Abhängigkeits Eigenschaften und die meisten Abhängigkeits Eigenschaften, mit Ausnahme der schreibgeschützten Eigenschaften, unterstützen standardmäßig die Datenbindung. (Nur <xref:System.Windows.DependencyObject> -Typen können Abhängigkeits Eigenschaften definieren <xref:System.Windows.UIElement>, und alle <xref:System.Windows.DependencyObject>s werden von abgeleitet.)  
  
- Obwohl nicht in der Abbildung angegeben, sollte beachtet werden, dass das Bindungs Quell Objekt nicht auf ein benutzerdefiniertes CLR-Objekt beschränkt ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]die Datenbindung unterstützt Daten in Form von CLR- [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]Objekten und. Um einige Beispiele anzugeben, kann die Bindungs Quelle ein <xref:System.Windows.UIElement>, ein beliebiges Listen Objekt, ein CLR-Objekt, das ADO.NET-Daten oder Webdiensten zugeordnet ist, oder ein XmlNode-Objekt sein, das Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten enthält. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).  
  
 Beim Lesen anderer [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]-Themen sollten Sie daran denken, dass Sie beim Einrichten einer Bindung ein Bindungsziel *an* eine Bindungsquelle binden. Wenn Sie z. b. einige zugrunde liegende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in einem <xref:System.Windows.Controls.ListBox> mithilfe der Datenbindung anzeigen, binden Sie <xref:System.Windows.Controls.ListBox> ihre an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] die Daten.  
  
 Zum Einrichten einer Bindung verwenden Sie das <xref:System.Windows.Data.Binding> -Objekt. Im restlichen Teil dieses Themas werden viele der mit und einigen der Eigenschaften und der Verwendung des <xref:System.Windows.Data.Binding> Objekts verknüpften Konzepte erläutert.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>Richtung des Datenflusses  
 Wie bereits erwähnt, und wie durch den Pfeil in der obigen Abbildung ersichtlich, kann der Datenfluss einer Bindung vom Bindungs Ziel zur Bindungs Quelle wechseln (z. b. ändert sich der Quellwert, wenn ein Benutzer den Wert eines <xref:System.Windows.Controls.TextBox>bearbeitet) und/oder aus der Bindungs Quelle. zum Bindungs Ziel (z <xref:System.Windows.Controls.TextBox> . b. wird der Inhalt mit Änderungen in der Bindungs Quelle aktualisiert), wenn die Bindungs Quelle die richtigen Benachrichtigungen bereitstellt.  
  
 Sie können die Anwendung so einrichten, dass Benutzer die Daten ändern und zurück an das Quellobjekt übertragen können. Sie können auch das Aktualisieren von Quelldaten durch Benutzer unterbinden. Sie können dies steuern, indem Sie <xref:System.Windows.Data.Binding.Mode%2A> die-Eigenschaft <xref:System.Windows.Data.Binding> des-Objekts festlegen. In der folgenden Abbildung werden die unterschiedlichen Datenflusstypen veranschaulicht:  
  
 ![Datenfluss bei der Datenbindung](./media/databinding-dataflow.png "DataBinding_DataFlow")  
  
- <xref:System.Windows.Data.BindingMode.OneWay>die Bindung bewirkt, dass Änderungen an der Quell Eigenschaft die Ziel Eigenschaft automatisch aktualisieren, aber Änderungen an der Ziel Eigenschaft werden nicht an die Quell Eigenschaft zurückgegeben. Dieser Bindungstyp empfiehlt sich, wenn das gebundene Steuerelement implizit als schreibgeschützt festgelegt wurde. Sie können beispielsweise eine Bindung an eine Quelle wie einen Börsenticker erstellen, oder möglicherweise ist für die Zieleigenschaft keine Steuerungsoberfläche verfügbar, um Änderungen vorzunehmen, z. B. an der datengebundenen Hintergrundfarbe einer Tabelle. Wenn die Änderungen der Zieleigenschaft nicht überwacht werden müssen, vermeiden Sie mit dem <xref:System.Windows.Data.BindingMode.OneWay>-Bindungsmodus den Mehraufwand des <xref:System.Windows.Data.BindingMode.TwoWay>-Bindungsmodus.  
  
- <xref:System.Windows.Data.BindingMode.TwoWay>die Bindung bewirkt, dass bei Änderungen an der Quell-oder der Ziel Eigenschaft die andere automatisch aktualisiert wird. Dieser Typ von Bindung ist für bearbeitbare Formulare und sonstige vollständig interaktive [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarien geeignet. Die meisten Eigenschaften werden <xref:System.Windows.Data.BindingMode.OneWay> standardmäßig gebunden, aber einige Abhängigkeits Eigenschaften (in der Regel Eigenschaften Benutzer bearbeitbarer <xref:System.Windows.Controls.TextBox.Text%2A> Steuerelemente <xref:System.Windows.Controls.TextBox> wie die-Eigenschaft <xref:System.Windows.Controls.CheckBox>von und die <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> -Eigenschaft von) werden standardmäßig auf <xref:System.Windows.Data.BindingMode.TwoWay> Bindung. Eine programmgesteuerte Methode zum Bestimmen, ob eine Abhängigkeitseigenschaft standardmäßig uni- oder bidirektional bindet, besteht darin, die Metadaten der Eigenschaft mit <xref:System.Windows.DependencyProperty.GetMetadata%2A> abzurufen und dann den booleschen Wert der <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>-Eigenschaft zu überprüfen.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource>ist die Umkehrung <xref:System.Windows.Data.BindingMode.OneWay> der Bindung; Sie aktualisiert die Quell Eigenschaft, wenn die Ziel Eigenschaft geändert wird. Ein Beispielszenario besteht darin, einfach den Quellwert von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] neu zu bewerten.  
  
- In der Abbildung ist <xref:System.Windows.Data.BindingMode.OneTime> die Bindung nicht dargestellt, was bewirkt, dass die Quell Eigenschaft die Ziel Eigenschaft initialisiert. nachfolgende Änderungen werden jedoch nicht weitergegeben. Wenn sich also der Datenkontext oder das Objekt im Datenkontext ändert, wird die Änderung in der Zieleigenschaft nicht angezeigt. Dieser Bindungstyp empfiehlt sich, wenn Sie Daten verwenden, bei denen eine Momentaufnahme des aktuellen Zustands verwendet werden kann oder die Daten tatsächlich statisch sind. Dieser Bindungstyp ist auch hilfreich, wenn die Zieleigenschaft mit einem bestimmten Wert der Quelleigenschaft initialisiert werden soll und der Datenkontext vorab nicht bekannt ist. Dies ist eine wesentlich einfachere Form der <xref:System.Windows.Data.BindingMode.OneWay>-Bindung, die eine bessere Leistung in Situationen bietet, in denen sich der Quellwert nicht ändert.  
  
 Beachten Sie, dass die Quelle zum Erkennen von <xref:System.Windows.Data.BindingMode.OneWay> Quell <xref:System.Windows.Data.BindingMode.TwoWay> Änderungen (anwendbar auf-und-Bindungen) einen geeigneten Benachrichtigungs Mechanismus für <xref:System.ComponentModel.INotifyPropertyChanged>die Eigenschafts Änderung implementieren muss, z.b. Ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> -Implementierung finden Sie unter Implementieren von Benachrichtigungen über [Eigenschafts Änderungen](how-to-implement-property-change-notification.md) .  
  
 Die <xref:System.Windows.Data.Binding.Mode%2A> Eigenschaften Seite enthält weitere Informationen zu Bindungs Modi und ein Beispiel für die Angabe der Richtung einer Bindung.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>Wodurch werden Quellaktualisierungen ausgelöst?  
 Bindungen, die <xref:System.Windows.Data.BindingMode.TwoWay> auf <xref:System.Windows.Data.BindingMode.OneWayToSource> Änderungen in der Ziel Eigenschaft warten oder diese überwachen und an die Quelle zurückgeben. Dies wird als Aktualisieren der Quelle bezeichnet. Sie können beispielsweise den Text eines TextBox-Elements bearbeiten, um den zugrunde liegenden Quellwert zu ändern. Wie im letzten Abschnitt beschrieben, wird die Richtung des Datenflusses durch den Wert der <xref:System.Windows.Data.Binding.Mode%2A> -Eigenschaft der-Bindung bestimmt.  
  
 Wird der Quellwert aktualisiert, während Sie den Text bearbeiten oder nachdem Sie die Bearbeitung abgeschlossen haben und den Mauszeiger aus dem TextBox-Steuerelement bewegen? Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft der Bindung bestimmt, wodurch das Update der Quelle ausgelöst wird. Die Punkte der nach rechts weisenden Pfeile in der folgenden Abbildung veranschaulichen die Rolle <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> der-Eigenschaft:  
  
 ![Diagramm, das die Rolle der updatesourceauslösereigenschaft anzeigt.](./media/data-binding-overview/data-binding-updatesource-trigger.png)  
  
 Wenn der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert ist, wird der Wert, auf den der nach-rechts <xref:System.Windows.Data.BindingMode.TwoWay> -Pfeil <xref:System.Windows.Data.BindingMode.OneWayToSource> von oder den Bindungen zeigt, aktualisiert, sobald die Ziel Eigenschaft geändert wird <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Wenn der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert jedoch ist <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, wird dieser Wert nur mit dem neuen Wert aktualisiert, wenn die Ziel Eigenschaft den Fokus verliert.  
  
 Ähnlich wie bei <xref:System.Windows.Data.Binding.Mode%2A> der-Eigenschaft haben verschiedene Abhängigkeits Eigenschaften <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> unterschiedliche Standardwerte. Der Standardwert für die meisten Abhängigkeitseigenschaften ist <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, während die <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> aufweist. Dies bedeutet, dass Quell Aktualisierungen in der Regel auftreten, wenn sich die Ziel Eigenschaft ändert <xref:System.Windows.Controls.CheckBox>, was für es und andere einfache Steuerelemente in Ordnung ist. Bei Textfeldern kann eine Aktualisierung nach jeder Tastatureingabe die Leistung mindern und führt außerdem dazu, dass der Benutzer nicht wie gewohnt durch Drücken der Rücktaste Tippfehler beheben kann, bevor der neue Wert übergeben wird. Daher hat die- <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft den Standard <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> Wert anstelle von <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 Informationen dazu <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> , wie Sie den Standard <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert einer Abhängigkeits Eigenschaft suchen, finden Sie auf der Eigenschaften Seite.  
  
 Die folgende Tabelle enthält ein Beispielszenario für jeden <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert, der <xref:System.Windows.Controls.TextBox> als Beispiel verwendet wird:  
  
|UpdateSourceTrigger-Wert|Wenn der Quellwert aktualisiert wird|Beispielszenario für TextBox|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (Standard für <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>)|Wenn das TextBox-Steuerelement den Fokus verliert|Ein <xref:System.Windows.Controls.TextBox> , der Validierungs Logik zugeordnet ist (siehe Abschnitt zur Datenvalidierung).|  
|PropertyChanged|Beim eingeben in das<xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox>Steuerelemente in einem Chatraum Fenster|  
|Explicit|Wenn die Anwendung aufruft<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox>Steuerelemente in einem bearbeitbaren Formular (aktualisiert die Quell Werte nur, wenn der Benutzer auf die Schaltfläche "Senden" klickt)|  
  
 Ein Beispiel finden Sie unter [Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>Erstellen einer Bindung  
  
 Zum erneuten erfassen einiger der in den vorherigen Abschnitten erläuterten Konzepte richten Sie mithilfe des <xref:System.Windows.Data.Binding> -Objekts eine Bindung ein, und jede Bindung hat normalerweise vier Komponenten: Bindungs Ziel, Ziel Eigenschaft, Bindungs Quelle und einen Pfad zum zu verwendenden Quellwert. In diesem Abschnitt wird das Einrichten einer Bindung erläutert.  
  
 Im folgenden Beispiel ist das Bindungsquellobjekt eine Klasse namens *MyData*, die im Namespace *SDKSample* definiert ist. Zu Demonstrationszwecken hat die *MyData*-Klasse eine Zeichenfolgeneigenschaft namens *ColorName*, deren Wert auf „Red“ festgelegt ist. In diesem Beispiel wird also eine Schaltfläche mit einem roten Hintergrund erstellt.  
  
 [!code-xaml[BindNonTextProperty#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Weitere Informationen zur Syntax der Bindungsdeklaration und Beispiele zum Einrichten einer Bindung im Code finden Sie unter [Übersicht über Bindungsdeklarationen](binding-declarations-overview.md).  
  
 Wenn dieses Beispiel auf das einfache Diagramm angewendet wird, sieht die resultierend Abbildung wie die folgende aus. Dies ist eine <xref:System.Windows.Data.BindingMode.OneWay> Bindung, da die Background- <xref:System.Windows.Data.BindingMode.OneWay> Eigenschaft die Bindung standardmäßig unterstützt.  
  
 ![Diagramm, das die Eigenschaft für die Daten Bindungs Hintergrund anzeigt.](./media/data-binding-overview/data-binding-button-background-example.png)  
  
 Sie Fragen sich vielleicht, warum dies funktioniert, auch wenn die *ColorName* -Eigenschaft vom <xref:System.Windows.Controls.Control.Background%2A> Typ "String" <xref:System.Windows.Media.Brush>ist, während die-Eigenschaft vom Typ ist. Der Grund dafür ist die Standardtypkonvertierung, die im Abschnitt [Datenkonvertierung](#data_conversion) näher erläutert wird.  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>Angeben der Bindungsquelle  
 Beachten Sie, dass im vorherigen Beispiel die Bindungs Quelle durch Festlegen der <xref:System.Windows.FrameworkElement.DataContext%2A> -Eigenschaft für das <xref:System.Windows.Controls.DockPanel> -Element angegeben wird. Der <xref:System.Windows.Controls.Button> erbt dann den <xref:System.Windows.FrameworkElement.DataContext%2A> Wert aus der <xref:System.Windows.Controls.DockPanel>, die sein übergeordnetes Element ist. Das Bindungsquellobjekt stellt, wie bereits erwähnt, eine der vier erforderlichen Komponenten einer Bindung dar. Wäre das Bindungsquellobjekt nicht angegeben, hätte die Bindung keine Auswirkungen.  
  
 Es gibt mehrere Möglichkeiten, das Bindungsquellobjekt anzugeben. Die Verwendung <xref:System.Windows.FrameworkElement.DataContext%2A> der-Eigenschaft für ein übergeordnetes Element ist nützlich, wenn Sie mehrere Eigenschaften an dieselbe Quelle binden. Es kann aber auch zweckmäßiger sein, die Bindungsquelle in einzelnen Bindungsdeklarationen anzugeben. Im vorherigen Beispiel können Sie anstelle der <xref:System.Windows.FrameworkElement.DataContext%2A> -Eigenschaft die Bindungs Quelle angeben, indem Sie die <xref:System.Windows.Data.Binding.Source%2A> -Eigenschaft direkt auf die Bindungs Deklaration der Schaltfläche festlegen, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Abgesehen von der direkten <xref:System.Windows.FrameworkElement.DataContext%2A> Festlegung der-Eigenschaft für ein Element, <xref:System.Windows.FrameworkElement.DataContext%2A> das den Wert von einem Vorgänger (z. b. die Schaltfläche im ersten Beispiel) erbt, und das explizite <xref:System.Windows.Data.Binding.Source%2A> angeben der Bindungs Quelle durch Festlegen der-Eigenschaft auf der <xref:System.Windows.Data.Binding> (z. b. die Schaltfläche im letzten Beispiel), können Sie <xref:System.Windows.Data.Binding.ElementName%2A> auch die- <xref:System.Windows.Data.Binding.RelativeSource%2A> Eigenschaft oder die-Eigenschaft verwenden, um die Bindungs Quelle anzugeben. Die <xref:System.Windows.Data.Binding.ElementName%2A> -Eigenschaft ist nützlich, wenn Sie an andere Elemente in der Anwendung binden, z. b. Wenn Sie einen Schieberegler zum Anpassen der Breite einer Schaltfläche verwenden. Die <xref:System.Windows.Data.Binding.RelativeSource%2A> -Eigenschaft ist nützlich, wenn die Bindung in einem <xref:System.Windows.Controls.ControlTemplate> oder einem <xref:System.Windows.Style>angegeben wird. Weitere Informationen finden Sie unter [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>Angeben des Pfads zum Wert  
 Wenn die Bindungs Quelle ein Objekt ist, verwenden Sie die <xref:System.Windows.Data.Binding.Path%2A> -Eigenschaft, um den Wert anzugeben, der für die Bindung verwendet werden soll. Wenn Sie Daten an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten binden, verwenden Sie die <xref:System.Windows.Data.Binding.XPath%2A> -Eigenschaft, um den Wert anzugeben. In einigen Fällen kann es auch dann auf die Verwendung der <xref:System.Windows.Data.Binding.Path%2A> -Eigenschaft angewendet werden, wenn [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]es sich um die Daten handelt. Wenn Sie z. b. auf die Name-Eigenschaft eines zurückgegebenen XmlNode (als Ergebnis einer XPath-Abfrage) zugreifen möchten, sollten Sie die <xref:System.Windows.Data.Binding.Path%2A> -Eigenschaft zusätzlich <xref:System.Windows.Data.Binding.XPath%2A> zur-Eigenschaft verwenden.  
  
 Syntax Informationen und Beispiele finden Sie auf den <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften <xref:System.Windows.Data.Binding.XPath%2A> Seiten und.  
  
 Beachten Sie, dass der <xref:System.Windows.Data.Binding.Path%2A> zu verwendende Wert zwar eine der vier erforderlichen Komponenten einer Bindung ist, aber in den Szenarien, die Sie an ein gesamtes Objekt binden möchten, der zu verwendende Wert mit dem Bindungs Quell Objekt identisch ist. In diesen Fällen ist es zutreffend, keine anzugeben <xref:System.Windows.Data.Binding.Path%2A>. Betrachten Sie das folgende Beispiel:  
  
 [!code-xaml[MasterDetail#EmptyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 Im obigen Beispiel wird die leere Bindungssyntax verwendet: {Binding}. In diesem Fall <xref:System.Windows.Controls.ListBox> erbt der DataContext von einem übergeordneten DockPanel-Element (in diesem Beispiel nicht dargestellt). Wenn der Pfad nicht angegeben wurde, erfolgt die Bindung standardmäßig an das gesamte Objekt. Anders ausgedrückt: in diesem Beispiel wurde der Pfad ausgelassen, da die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft an das gesamte Objekt gebunden wird. (Im Abschnitt [Binden an Auflistungen](#binding_to_collections) wird ausführlich darauf eingegangen.)  
  
 Dieses Szenario ist nicht nur zum Binden an eine Auflistung hilfreich, sondern auch zum Binden an ein vollständiges Objekt statt nur an eine einzelne Eigenschaft eines Objekts. Wenn es sich beim Quellobjekt beispielsweise um einen Zeichenfolgentyp handelt und Sie lediglich an die Zeichenfolge binden möchten. Ein anderes allgemeines Szenario besteht darin, ein Element an ein Objekt mit mehreren Eigenschaften zu binden.  
  
 Beachten Sie, dass Sie ggf. benutzerdefinierte Logik anwenden müssen, damit die Daten für die gebundene Zieleigenschaft sinnvoll sind. Bei der benutzerdefinierten Logik kann es sich z. B. um einen benutzerdefinierten Konverter handeln (falls keine Standardtypkonvertierung vorhanden ist). Weitere Informationen über Konverter finden Sie unter [Datenkonvertierung](#data_conversion).  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Die „Binding“-Klasse und „BindingExpression“  
 Vor dem Einstieg in andere Features und Verwendungszwecke der Datenbindung wäre es sinnvoll, die <xref:System.Windows.Data.BindingExpression> Klasse einzuführen. Wie in den vorherigen Abschnitten gezeigt, ist die <xref:System.Windows.Data.Binding> -Klasse die Klasse auf hoher Ebene für die Deklaration einer Bindung. die <xref:System.Windows.Data.Binding> -Klasse stellt viele Eigenschaften bereit, mit denen Sie die Eigenschaften einer Bindung angeben können. Eine verwandte Klasse, <xref:System.Windows.Data.BindingExpression>, ist das zugrunde liegende Objekt, das die Verbindung zwischen der Quelle und dem Ziel beibehält. Ein Bindung enthält sämtliche Informationen, die von mehreren Bindungsausdrücken gemeinsam genutzt werden können. Ein <xref:System.Windows.Data.BindingExpression> ist ein Instanzausdruck, <xref:System.Windows.Data.Binding>der nicht freigegeben werden kann und alle Instanzinformationen von enthält.  
  
 Beachten Sie z. b. Folgendes: *myDataObject* ist eine Instanz der *MyData* -Klasse, *myBinding* ist das <xref:System.Windows.Data.Binding> Quell Objekt, und die *MyData* -Klasse ist eine definierte Klasse, die eine Zeichen folgen Eigenschaft namens  *MyDataProperty*. In diesem Beispiel wird der Text Inhalt von *MyText*, einer Instanz <xref:System.Windows.Controls.TextBlock>von, an *MyDataProperty*gebunden.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Mit demselben *myBinding*-Objekt können Sie auch andere Bindungen erstellen. Sie können beispielsweise mit dem *myBinding*-Objekt eine Bindung des Textinhalts eines Kontrollkästchens an *MyDataProperty* herstellen. In diesem Szenario gibt es zwei Instanzen <xref:System.Windows.Data.BindingExpression> , die das *myBinding* -Objekt gemeinsam nutzen.  
  
 Ein <xref:System.Windows.Data.BindingExpression> -Objekt kann über den Rückgabewert von abgerufen werden <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> , wenn für ein Daten gebundenes Objekt aufgerufen wird. Die folgenden Themen veranschaulichen einige Verwendungsmöglichkeiten der <xref:System.Windows.Data.BindingExpression> -Klasse:  
  
- [Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft](how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
- [Steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>Datenkonvertierung  
 Im vorherigen Beispiel ist die Schaltfläche rot, weil <xref:System.Windows.Controls.Control.Background%2A> die zugehörige Eigenschaft an eine Zeichen folgen Eigenschaft mit dem Wert "Red" gebunden ist. Dies funktioniert, weil ein Typkonverter für den <xref:System.Windows.Media.Brush> Typ vorhanden ist, um den Zeichen folgen Wert in einen <xref:System.Windows.Media.Brush>zu konvertieren.  
  
 Wenn diese Informationen der Abbildung im Abschnitt [Erstellen einer Bindung](#creating_a_binding) hinzugefügt werden, sieht das Diagramm folgendermaßen aus:  
  
 ![Diagramm, das die Standard Eigenschaft für die Datenbindung anzeigt.](./media/data-binding-overview/data-binding-button-default-conversion.png)  
  
 Wenn Sie jedoch nicht über eine Eigenschaft vom Typ "String" verfügen, hat das Bindungs Quell Objekt eine *Color* - <xref:System.Windows.Media.Color>Eigenschaft vom Typ? Damit die Bindung funktioniert, müssen Sie in diesem Fall zuerst den Wert der *Color* -Eigenschaft in einen Wert umwandeln, den die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft akzeptiert. Sie müssen einen benutzerdefinierten Konverter erstellen, indem Sie die <xref:System.Windows.Data.IValueConverter> -Schnittstelle implementieren, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[ColorPicker_snip#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 Auf <xref:System.Windows.Data.IValueConverter> der Seite "Referenz" finden Sie weitere Informationen.  
  
 Jetzt wird anstelle der Standardkonvertierung der benutzerdefinierte Konverter verwendet, und unser Diagramm sieht wie folgt aus:  
  
 ![Diagramm, das den benutzerdefinierten Konverter der Datenbindung anzeigt.](./media/data-binding-overview/data-binding-converter-color-example.png)  
  
 Wie bereits ausgeführt, können aufgrund von Typkonvertern, die im Typ vorhanden sind, an den gebunden wird, Standardkonvertierungen verfügbar sein. Dieses Verhalten hängt von den im Ziel vorhandenen Typkonvertern ab. Erstellen Sie im Zweifelsfall einen eigenen Konverter.  
  
 Es folgen einige typische Szenarien, in denen die Implementierung eines Datenkonverters sinnvoll ist:  
  
- Die Daten sollen je nach Kultur unterschiedlich angezeigt werden. Sie können z. B. einen Währungskonverter oder einen Datum-/Uhrzeitkonverter implementieren, der auf den Werten oder Standards basiert, die in einer bestimmten Kultur verwendet werden.  
  
- Die verwendeten Daten müssen nicht unbedingt dazu dienen, den Textwert einer Eigenschaft zu ändern. Sie können auch den Zweck haben, andere Werte zu ändern, beispielsweise die Quelle für ein Bild oder die Farbe bzw. das Format des Anzeigetexts. Konverter können in dieser Instanz verwendet werden, indem die Bindung einer Eigenschaft konvertiert wird, die ungeeignet zu sein scheint, z. B. wenn ein Textfeld an die Background-Eigenschaft einer Tabellenzelle gebunden wird.  
  
- Mehrere Steuerelemente oder mehrere Steuerelementeigenschaften sind an dieselben Daten gebunden. In diesem Fall wird durch die primäre Bindung möglicherweise nur der Text angezeigt, wohingegen andere Bindungen bestimmte Anzeigeprobleme behandeln, aber dieselben Bindungen als Quellinformationen verwenden.  
  
- Bisher haben wir noch nicht erörtert <xref:System.Windows.Data.MultiBinding>, wobei eine Ziel Eigenschaft über eine Auflistung von Bindungen verfügt. Im Fall <xref:System.Windows.Data.MultiBinding>eines verwenden Sie einen benutzerdefinierten <xref:System.Windows.Data.IMultiValueConverter> , um einen endgültigen Wert aus den Werten der Bindungen zu erhalten. So kann die Farbe beispielsweise aus roten, blauen und grünen Werten berechnet werden, die aus denselben oder anderen Bindungsquellobjekten stammen können. Beispiele und <xref:System.Windows.Data.MultiBinding> Informationen finden Sie auf der Seite "Klasse".  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>Binden an Auflistungen  
  
 Ein Bindungsquellobjekt kann als einzelnes Objekt behandelt werden, dessen Eigenschaften Daten enthalten, oder als eine Datenauflistung von polymorphen Objekten, die häufig zusammen gruppiert werden (beispielsweise als Ergebnis einer Datenbankabfrage). Bisher wurde nur das Binden an einzelne Objekte behandelt, aber auch das Binden an eine Datenauflistung ist ein gängiges Szenario. Ein häufiges Szenario ist Beispiels <xref:System.Windows.Controls.ItemsControl> Weise die Verwendung <xref:System.Windows.Controls.ListBox>einer, <xref:System.Windows.Controls.ListView>, oder <xref:System.Windows.Controls.TreeView> zum Anzeigen einer Datensammlung, z. b. in der im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) gezeigten Anwendung.  
  
 Das bisherige einfache Diagramm ist praktischerweise immer noch gültig. Wenn Sie ein <xref:System.Windows.Controls.ItemsControl> an eine Sammlung binden, sieht das Diagramm wie folgt aus:  
  
 ![Diagramm, das das ItemsControl-Objekt der Datenbindung anzeigt.](./media/data-binding-overview/data-binding-itemscontrol.png)  
  
 Wie in diesem Diagramm gezeigt, ist die Eigenschaft <xref:System.Windows.Controls.ItemsControl> die Eigenschaft, die verwendet <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> werden soll, um ein an ein Auflistungs Objekt zu binden. Sie können sich die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft als Inhalt <xref:System.Windows.Controls.ItemsControl>von vorstellen. Beachten Sie, dass die <xref:System.Windows.Data.BindingMode.OneWay> Bindung ist <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> , da <xref:System.Windows.Data.BindingMode.OneWay> die-Eigenschaft die Bindung standardmäßig unterstützt.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>Implementieren von Auflistungen  
 Sie können jede Auflistung auflisten, die die <xref:System.Collections.IEnumerable> -Schnittstelle implementiert. Wenn Sie jedoch dynamische Bindungen einrichten möchten, damit die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Einfügungen oder Löschungen in der Auflistung automatisch aktualisieren, muss die-Auflistung die <xref:System.Collections.Specialized.INotifyCollectionChanged> -Schnittstelle implementieren. Diese Schnittstelle macht ein Ereignis verfügbar, das bei jeder Änderung der zugrunde liegenden Auflistung ausgelöst werden sollte.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt die <xref:System.Collections.ObjectModel.ObservableCollection%601> -Klasse bereit, bei der es sich um eine integrierte Implementierung einer Datensammlung handelt <xref:System.Collections.Specialized.INotifyCollectionChanged> , die die-Schnittstelle verfügbar macht. Beachten Sie, dass jedes Objekt in der Auflistung, das bindbare Eigenschaften unterstützt, auch die-Schnittstelle implementieren muss, um die <xref:System.ComponentModel.INotifyPropertyChanged> Übertragung von Datenwerten von Quell Objekten an Ziele vollständig zu Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).  
  
 Bevor Sie eine eigene Auflistung implementieren, erwägen Sie <xref:System.Collections.ObjectModel.ObservableCollection%601> oder einer vorhandenen Sammlung Klassen, z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, und <xref:System.ComponentModel.BindingList%601>, a. Wenn Sie ein erweitertes Szenario haben und eine eigene Auflistung implementieren möchten, sollten Sie ggf. verwenden <xref:System.Collections.IList>, das eine nicht generische Auflistung von Objekten bereitstellt, auf die einzeln über einen Index zugegriffen werden kann, und somit die beste Leistung.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>Auflistungsansichten  
 Wenn Ihr <xref:System.Windows.Controls.ItemsControl> an eine Datensammlung gebunden ist, können Sie die Daten sortieren, Filtern oder gruppieren. Zu diesem Zweck verwenden Sie Auflistungs Sichten, bei denen es sich um <xref:System.ComponentModel.ICollectionView> Klassen handelt, die die Schnittstelle implementieren.  

#### <a name="what-are-collection-views"></a>Was sind Auflistungsansichten?  
 Eine Auflistungsansicht fungiert als Ebene über der Bindungsquellauflistung, in der Sie mit Sortier-, Filter- und Gruppierungsabfragen navigieren und die jeweilige Quellauflistung anzeigen können, ohne die zugrunde liegende Quellauflistung selbst ändern zu müssen. Eine Auflistungsansicht stellt außerdem einen Zeiger auf das aktuelle Element in der Auflistung zur Verfügung. Wenn die Quell Auflistung die <xref:System.Collections.Specialized.INotifyCollectionChanged> -Schnittstelle implementiert, werden die Änderungen, die <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> vom-Ereignis ausgelöst werden, an die Sichten weitergegeben.  
  
 Da in Ansichten die zugrunde liegenden Quellauflistungen nicht geändert werden, können einer Quellauflistung mehrere Ansichten zugeordnet sein. Angenommen, Sie verfügen über eine Auflistung von *Task*-Objekten. Mithilfe von Ansichten können Sie dieselben Daten auf verschiedene Weise anzeigen. Beispielsweise können Sie links auf der Seite Aufgaben nach Priorität und rechts nach Bereich sortieren.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>Erstellen einer Ansicht  
 Eine Möglichkeit, eine Ansicht zu erstellen und zu verwenden, besteht darin, das Ansichtsobjekt direkt zu instanziieren und dann als Bindungsquelle zu verwenden. Betrachten Sie z. B. die Anwendung [Demo für die Datenbindung](https://go.microsoft.com/fwlink/?LinkID=163703), die im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) gezeigt wird. Die Anwendung wird so implementiert, dass <xref:System.Windows.Controls.ListBox> die an eine Ansicht über die Datensammlung anstatt direkt an die Daten Auflistung bindet. Das folgende Beispiel wird aus der [Demo für die Datenbindung-Anwendung](https://go.microsoft.com/fwlink/?LinkID=163703) extrahiert. Die <xref:System.Windows.Data.CollectionViewSource> -Klasse ist [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] der Proxy einer Klasse, die von <xref:System.Windows.Data.CollectionView>erbt. In diesem speziellen Beispiel ist der <xref:System.Windows.Data.CollectionViewSource.Source%2A> der Ansicht an die Auflistung der *Auktions Elemente* (vom Typ <xref:System.Collections.ObjectModel.ObservableCollection%601>) des aktuellen Anwendungs Objekts gebunden.  
  
 [!code-xaml[DataBindingLab#WindowResources1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 Die Ressource *listingDataView* dient dann als Bindungs Quelle für Elemente in der Anwendung, z <xref:System.Windows.Controls.ListBox>. b.:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Um eine weitere Ansicht für dieselbe Auflistung zu erstellen, können Sie eine <xref:System.Windows.Data.CollectionViewSource> andere-Instanz erstellen und Ihr `x:Key` einen anderen Namen zuordnen.  
  
 In der folgenden Tabelle wird gezeigt, welche Sicht Datentypen als Standard Auflistungs <xref:System.Windows.Data.CollectionViewSource> Ansicht erstellt werden, oder basierend auf dem Quell Sammlungstyp.  
  
|Quellauflistungstyp|Auflistungsansichtstyp|Hinweise|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|Ein interner Typ, der auf basiert.<xref:System.Windows.Data.CollectionView>|Kann Elemente nicht gruppieren.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Am schnellsten.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>Verwenden einer Standardansicht  
 Die Angabe einer Auflistungsansicht als Bindungsquelle ist eine Möglichkeit, eine Auflistungsansicht zu erstellen und zu verwenden. WPF erstellt außerdem eine Standardauflistungsansicht für jede als Bindungsquelle verwendete Auflistung. Bei der direkten Bindung an eine Auflistung bindet WPF an die Standardansicht der Auflistung. Diese Standardansicht wird von allen Bindungen an diese Auflistung gemeinsam verwendet, sodass eine Änderung an der Standardansicht durch ein gebundenes Steuerelement oder Code, z. B. Sortierung oder eine Änderung des aktuellen Elementzeigers (dies wird zu einem späteren Zeitpunkt erläutert), sich auf alle anderen Bindungen an dieselbe Auflistung auswirkt.  
  
 Um die Standardansicht zu erhalten, verwenden Sie <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> die-Methode. Ein Beispiel finden Sie unter [Abrufen der Standardansicht einer Datenauflistung](how-to-get-the-default-view-of-a-data-collection.md).  
  
##### <a name="collection-views-with-adonet-datatables"></a>Auflistungsansichten mit ADO.NET-Datentabellen  
 Um die Leistung zu verbessern, delegieren <xref:System.Data.DataTable> Auflistungs Ansichten für ADO.net oder <xref:System.Data.DataView> Objekte <xref:System.Data.DataView>das Sortieren und Filtern an den. So wird die Sortierung und Filterung von allen Auflistungsansichten der Datenquelle gemeinsam verwendet. Damit jede Auflistungs Ansicht unabhängig sortiert und gefiltert werden kann, initialisieren Sie jede Sammlungsansicht <xref:System.Data.DataView> mit Ihrem eigenen-Objekt.  
  
#### <a name="sorting"></a>Sortieren  
 Wie bereits erwähnt, können mit Ansichten Sortierreihenfolgen auf Auflistungen angewendet werden. Da sie in der zugrunde liegenden Auflistung vorhanden sind, haben die Daten möglicherweise eine relevante inhärente Reihenfolge oder nicht. Die Ansicht der Auflistung ermöglicht Ihnen das Festlegen einer Reihenfolge oder das Ändern der Standardreihenfolge, je nachdem, welche Vergleichskriterien Sie angeben. Da es sich um eine clientbasierte Ansicht der Daten handelt, besteht ein übliches Szenario darin, dass der Benutzer Spalten mit Tabellendaten nach dem Wert sortiert, dem die Spalte entspricht. Mithilfe von Ansichten kann diese benutzerdefinierte Sortierung angewendet werden, ohne die zugrunde liegende Auflistung ändern oder den Auflistungsinhalt erneut abfragen zu müssen. Ein Beispiel finden Sie unter [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 Das folgende Beispiel zeigt die Sortier Logik von "Sort by category and date" <xref:System.Windows.Controls.CheckBox> der Anwendung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) :  
  
 [!code-csharp[DataBindingLab#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>Filtern  
 Ansichten können auch einen Filter auf eine Auflistung anwenden. Dies bedeutet, dass in der Auflistung zwar ein Element vorhanden sein kann, in dieser bestimmten Ansicht jedoch nur eine bestimmte Teilmenge der gesamten Auflistung angezeigt werden soll. Sie können die Daten nach einer Bedingung filtern. Beispielsweise <xref:System.Windows.Controls.CheckBox> enthält die Anwendung im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) die Logik zum Herausfiltern von Elementen, die $25 oder Mehrkosten. Der folgende Code wird ausgeführt, um *ShowOnlyBargainsFilter* als <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignishandler festzulegen, <xref:System.Windows.Controls.CheckBox> wenn dieser ausgewählt wird:  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Die *ShowOnlyBargainsFilter*-Ereignishandler hat folgende Implementierung:  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Wenn Sie eine der <xref:System.Windows.Data.CollectionView> -Klassen direkt anstelle von <xref:System.Windows.Data.CollectionViewSource>verwenden, verwenden Sie die <xref:System.Windows.Data.CollectionView.Filter%2A> -Eigenschaft, um einen Rückruf anzugeben. Ein Beispiel finden Sie unter [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md).  
  
#### <a name="grouping"></a>Gruppieren  
 Mit Ausnahme der internen Klasse, in der <xref:System.Collections.IEnumerable> eine Auflistung angezeigt wird, unterstützen alle Auflistungs Ansichten die Funktionalität der Gruppierung, die es dem Benutzer ermöglicht, die Auflistung in der Auflistungs Ansicht in logische Gruppen zu partitionieren. Die Gruppen können explizit sein, wobei Benutzer eine Liste von Gruppen angeben. Sie können auch implizit sein, wobei die Gruppen dynamisch in Abhängigkeit von den Daten generiert werden.  
  
 Das folgende Beispiel zeigt die Logik der Kategorie "Gruppieren nach" <xref:System.Windows.Controls.CheckBox>:  
  
 [!code-csharp[DataBindingLab#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 Ein weiteres Beispiel zu Gruppierungen finden Sie unter [Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist](../controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).  
  
#### <a name="current-item-pointers"></a>Zeiger auf aktuelle Elemente  
 Ansichten unterstützen ebenfalls das Konzept eines aktuellen Elements. Sie können durch die Objekte in einer Auflistungsansicht navigieren. Beim Navigieren verschieben Sie einen Elementzeiger, mit dem Sie das Objekt abrufen können, das sich an einer bestimmten Position in der Auflistung befindet. Ein Beispiel finden Sie unter [Navigieren durch die Objekte in einer Datenauflistungsansicht](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
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
  
<a name="master_detail_scenario"></a>   
#### <a name="master-detail-binding-scenario"></a>Szenario für Master-Detail-Bindung  
 Das Konzept eines aktuellen Elements ist nicht nur hilfreich, um durch Elemente in einer Auflistung zu navigieren, sondern auch für das Szenario einer Master-Detail-Bindung. Betrachten Sie wieder die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung, die im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) verwendet wird. In dieser Anwendung <xref:System.Windows.Controls.ListBox> bestimmt die Auswahl in den Inhalt, der in der <xref:System.Windows.Controls.ContentControl>angezeigt wird. Wenn ein Element ausgewählt wird, werden die Details <xref:System.Windows.Controls.ListBox> des ausgewählten Elements <xref:System.Windows.Controls.ContentControl> angezeigt, wenn ein Element ausgewählt wird.  
  
 Sie können das Master-Detail-Szenario auch einfach dadurch implementieren, dass mindestens zwei Steuerelemente an dieselbe Ansicht gebunden sind. Das folgende Beispiel aus der [Daten Bindungs Demo](https://go.microsoft.com/fwlink/?LinkID=163703) zeigt das Markup <xref:System.Windows.Controls.ListBox> von und die, <xref:System.Windows.Controls.ContentControl> die Sie im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) für die Anwendung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sehen:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Beachten Sie, dass beide Steuerelemente an dieselbe Quelle gebunden sind, und zwar die statische *listingDataView*-Ressource (siehe die Definition dieser Ressource im Abschnitt [Erstellen einer Ansicht](#how_to_create_a_view)). Dies funktioniert, denn wenn ein Singleton-Objekt <xref:System.Windows.Controls.ContentControl> (in diesem Fall) an eine Auflistungs Ansicht gebunden ist, bindet es <xref:System.Windows.Data.CollectionView.CurrentItem%2A> automatisch an die der Ansicht. Beachten Sie <xref:System.Windows.Data.CollectionViewSource> , dass-Objekte die Währung und die Auswahl automatisch synchronisieren. Wenn das Listen Steuerelement nicht wie in diesem <xref:System.Windows.Data.CollectionViewSource> Beispiel an ein-Objekt gebunden ist, müssen Sie seine <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> -Eigenschaft auf `true` festlegen, damit dies funktioniert.  
  
 Weitere Beispiele finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) und [Verwenden des Master/Detail-Musters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Ihnen ist vielleicht aufgefallen, dass im vorherigen Beispiel eine Vorlage verwendet wird. Tatsächlich werden die Daten nicht wie gewünscht angezeigt, ohne dass Vorlagen verwendet werden (der explizit von <xref:System.Windows.Controls.ContentControl> verwendete und der implizit <xref:System.Windows.Controls.ListBox>von verwendete). Im nächsten Abschnitt beschäftigen wir uns mit Datenvorlagen.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>Datenvorlagen  
 Ohne Datenvorlagen würde die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) wie folgt aussehen:  
  
 ![Demobeispiel für Datenbindung ohne Datenvorlagen](./media/data-binding-overview/data-binding-demo-templates.png)  
  
 Wie im Beispiel im vorherigen Abschnitt gezeigt, werden sowohl das <xref:System.Windows.Controls.ListBox> -Steuerelement als auch das <xref:System.Windows.Controls.ContentControl> -Objekt an das gesamte Auflistungs Objekt (oder genauer gesagt die Ansicht über das Auflistungs Objekt) von " *AuctionItem*s" gebunden. Ohne spezifische Anweisungen zum Anzeigen der Datensammlung zeigt das <xref:System.Windows.Controls.ListBox> eine Zeichen folgen Darstellung der einzelnen Objekte in der zugrunde liegenden Auflistung an <xref:System.Windows.Controls.ContentControl> und zeigt eine Zeichen folgen Darstellung des Objekts an, an das es gebunden ist.  
  
 Um dieses Problem zu beheben, definiert <xref:System.Windows.DataTemplate>die Anwendung s. Wie im Beispiel im vorherigen Abschnitt gezeigt, <xref:System.Windows.Controls.ContentControl> verwendet explizit das *detailsProductListingTemplate*<xref:System.Windows.DataTemplate>-Objekt. Das <xref:System.Windows.Controls.ListBox> -Steuerelement verwendet beim <xref:System.Windows.DataTemplate> Anzeigen der *Auktions Element* -Objekte in der-Auflistung implizit Folgendes:  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 Durch die Verwendung dieser beiden <xref:System.Windows.DataTemplate>s wird die resultierende Benutzeroberfläche im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) angezeigt. Wie Sie in diesem Screenshot sehen können, können Sie mit s nicht nur Daten in Ihren Steuerelementen <xref:System.Windows.DataTemplate>platzieren, sondern auch überzeugende Visualisierungen für Ihre Daten definieren. Beispielsweise werden <xref:System.Windows.DataTrigger>im obigen <xref:System.Windows.DataTemplate> Beispiel s verwendet, sodass der Wert von " *AuctionItem*s" mit dem *SpecialFeatures* -Wert " *Hervorhebung* " mit einem orangefarbenen Rahmen und einem Stern angezeigt wird.  
  
 Weitere Informationen zu Datenvorlagen finden Sie in der [Übersicht über Datenvorlagen](data-templating-overview.md).  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>Datenvalidierung  
  
 Die meisten Anwendungen, bei denen Benutzereingaben erfolgen, benötigen Validierungslogik, um sicherzustellen, dass der Benutzer die erwarteten Informationen eingegeben hat. Die Validierungsprüfungen können auf Typ, Bereich, Format oder anderen anwendungsspezifischen Anforderungen basieren. In diesem Abschnitt wird erklärt, wie Datenvalidierung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funktioniert.  
  
### <a name="associating-validation-rules-with-a-binding"></a>Zuordnen von Validierungsregeln zu einer Bindung  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Daten Bindungs Modell ermöglicht es Ihnen, <xref:System.Windows.Data.Binding.ValidationRules%2A> dem- <xref:System.Windows.Data.Binding> Objekt zuzuordnen. Im folgenden <xref:System.Windows.Controls.TextBox> Beispiel wird ein-Objekt an eine Eigenschaft mit dem Namen `StartPrice` gebunden und <xref:System.Windows.Controls.ExceptionValidationRule> der <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> -Eigenschaft ein-Objekt hinzugefügt.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 Ein <xref:System.Windows.Controls.ValidationRule> -Objekt überprüft, ob der Wert einer Eigenschaft gültig ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verfügt über die folgenden beiden Typen von integrierten <xref:System.Windows.Controls.ValidationRule> Objekten:  
  
- Eine <xref:System.Windows.Controls.ExceptionValidationRule> prüft auf Ausnahmen, die während der Aktualisierung der Bindungs Quell Eigenschaft ausgelöst wurden. Im vorherigen Beispiel ist `StartPrice` eine ganze Zahl. Wenn der Benutzer einen Wert eingibt, der nicht in eine ganze Zahl konvertiert werden kann, wird eine Ausnahme ausgelöst, wodurch die Bindung als ungültig markiert wird. Eine Alternative <xref:System.Windows.Controls.ExceptionValidationRule> Syntax zum expliziten Festlegen von ist das Festlegen der-Eigenschaft <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> `true` <xref:System.Windows.Data.Binding> für das <xref:System.Windows.Data.MultiBinding> -Objekt oder das-Objekt.  
  
- Ein <xref:System.Windows.Controls.DataErrorValidationRule> -Objekt überprüft auf Fehler, die von-Objekten ausgelöst werden <xref:System.ComponentModel.IDataErrorInfo> , die die-Schnittstelle implementieren. Ein Beispiel für die Verwendung dieser Validierungs Regel finden <xref:System.Windows.Controls.DataErrorValidationRule>Sie unter. Eine Alternative <xref:System.Windows.Controls.DataErrorValidationRule> Syntax zum expliziten Festlegen von ist das Festlegen der-Eigenschaft <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> `true` <xref:System.Windows.Data.Binding> für das <xref:System.Windows.Data.MultiBinding> -Objekt oder das-Objekt.  
  
 Sie können auch eine eigene Validierungs Regel erstellen, indem Sie von <xref:System.Windows.Controls.ValidationRule> der-Klasse ableiten <xref:System.Windows.Controls.ValidationRule.Validate%2A> und die-Methode implementieren. Das folgende Beispiel zeigt die Regel, die im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) zum <xref:System.Windows.Controls.TextBox> *Hinzufügen der Produkt Auflistung* "Start Datum" verwendet wird:  
  
 [!code-csharp[DataBindingLab#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> verwendet dieses *FutureDateRule*, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[DataBindingLab#CustomValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Beachten Sie, dass <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> die Bindungs <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>-Engine den Quellwert bei jedem Tastatur Strich aktualisiert, da der Wert ist, was bedeutet, dass jede Regel <xref:System.Windows.Data.Binding.ValidationRules%2A> in der Auflistung auf jedem Tastatur Strich überprüft wird. Dies wird im Abschnitt zum Validierungsprozess näher erläutert.  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>Bereitstellen von visuellem Feedback  
 Wenn der Benutzer einen ungültigen Wert eingibt, kann es sinnvoll sein, Feedback zum Fehler auf der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung zu geben. Eine Möglichkeit zum Bereitstellen eines solchen Feedbacks besteht <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> darin, die angefügte <xref:System.Windows.Controls.ControlTemplate>-Eigenschaft auf eine benutzerdefinierte festzulegen Wie im vorherigen unter Abschnitt gezeigt, verwendet *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> einen <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> mit dem Namen " *validationTemplate*". Im folgenden Beispiel sehen Sie die Definition von *validationTemplate*:  
  
 [!code-xaml[DataBindingLab#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 Das <xref:System.Windows.Controls.AdornedElementPlaceholder> -Element gibt an, wo das zu erstellende Steuerelement platziert werden soll.  
  
 Zusätzlich können Sie auch einen <xref:System.Windows.Controls.ToolTip> verwenden, um die Fehlermeldung anzuzeigen. Sowohl *StartDateEntryForm* als auch *startpreientryform*<xref:System.Windows.Controls.TextBox>verwenden das <xref:System.Windows.Controls.ToolTip> *textStyleTextBox*-Format, das eine erstellt, die die Fehlermeldung anzeigt. Im folgenden Beispiel wird die Definition von *textStyleTextBox* dargestellt. Die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> - `true` Eigenschaft ist, wenn eine oder mehrere der Bindungen in den Eigenschaften des gebundenen Elements fehlerhaft sind.  
  
 [!code-xaml[DataBindingLab#14](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 Beim benutzerdefinierten <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> <xref:System.Windows.Controls.ToolTip>und dem sieht *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> bei einem Validierungs Fehler wie folgt aus:  
  
 ![Fehler bei der Datenbindungsvalidierung](./media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 Wenn Sie <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> über zugeordnete Validierungsregeln verfügen, aber keinen für das gebundene Steuerelement angeben, wird <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> ein Standardwert verwendet, um Benutzer zu benachrichtigen, wenn ein Validierungs Fehler vorliegt. <xref:System.Windows.Data.Binding> Der Standard <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> Wert ist eine Steuerelement Vorlage, die einen roten Rahmen in der Adornerebene definiert. Mit dem Standard <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> -und <xref:System.Windows.Controls.ToolTip>dem [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Wert sieht *startpreientryform* <xref:System.Windows.Controls.TextBox> bei einem Validierungs Fehler wie folgt aus:  
  
 ![Fehler bei der Datenbindungsvalidierung](./media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 Ein Beispiel zum Bereitstellen von Logik zum Validieren aller Steuerelemente in einem Dialogfeld finden Sie im Abschnitt zu benutzerdefinierten Dialogfeldern in der [Übersicht über Dialogfelder](../app-development/dialog-boxes-overview.md).  
  
### <a name="validation-process"></a>Validierungsprozess  
 Eine Validierung erfolgt normalerweise, wenn der Wert eines Ziels an die Bindungsquelleigenschaft übergeben wird. Dies tritt bei <xref:System.Windows.Data.BindingMode.TwoWay> - <xref:System.Windows.Data.BindingMode.OneWayToSource> und-Bindungen auf. Um dies zu wiederholen, hängt das Quell Update von dem Wert der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft ab, wie im Abschnitt [was löst Quell Updates](#what_triggers_source_updates) beschrieben wird.  
  
 Im Folgenden wird der Prozess der *Validierung* beschrieben. Beachten Sie, dass der Prozess beim Auftreten eines Validierungs- oder anderen Fehlers in seinem Verlauf angehalten wird.  
  
1. Die Bindungs- <xref:System.Windows.Controls.ValidationRule> Engine überprüft <xref:System.Windows.Data.Binding>, ob benutzerdefinierte-Objekte definiert <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> sind, deren <xref:System.Windows.Controls.ValidationStep.RawProposedValue> auf festgelegt ist. in diesem Fall wird <xref:System.Windows.Controls.ValidationRule.Validate%2A> die-Methode <xref:System.Windows.Controls.ValidationRule> für jedes-Objekt aufgerufen, bis eines von Ihnen in einen Fehler auftritt. oder bis alle diese bestanden haben.  
  
2. Anschließend ruft die Bindungs-Engine den Konverter auf, sofern vorhanden.  
  
3. Wenn der Konverter erfolgreich ist, überprüft die Bindungs-Engine, ob Benutzer <xref:System.Windows.Controls.ValidationRule> definierte-Objekte <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> definiert sind <xref:System.Windows.Data.Binding>, <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> deren auf festgelegt ist. in diesem Fall <xref:System.Windows.Controls.ValidationRule.Validate%2A> wird die- <xref:System.Windows.Controls.ValidationRule> Methode für jedes-Objekt aufgerufen, das Legen Sie <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> auf fest, bis eines von Ihnen in einen Fehler oder bis zu allen Läufen ausgeführt wird. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>  
  
4. Die Bindungs-Engine legt die Quelleigenschaft fest.  
  
5. Die <xref:System.Windows.Controls.ValidationRule> Bindungs-Engine überprüft <xref:System.Windows.Data.Binding>, ob benutzerdefinierte-Objekte definiert <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> sind, deren <xref:System.Windows.Controls.ValidationStep.UpdatedValue> auf festgelegt ist. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> in diesem Fall wird <xref:System.Windows.Controls.ValidationRule.Validate%2A> die-Methode <xref:System.Windows.Controls.ValidationRule> für jeden aufgerufen, der auf festgelegt ist. <xref:System.Windows.Controls.ValidationStep.UpdatedValue> , bis einer von Ihnen in einen Fehler auftritt oder bis alle davon bestanden werden. Wenn eine <xref:System.Windows.Controls.DataErrorValidationRule> einer Bindung zugeordnet ist und deren <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf den Standard <xref:System.Windows.Controls.ValidationStep.UpdatedValue>Wert festgelegt ist, wird <xref:System.Windows.Controls.DataErrorValidationRule> der an dieser Stelle geprüft. Dies ist auch der Zeitpunkt, an dem Bindungen aktiviert <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> werden, `true` für die auf festgelegt ist.  
  
6. Die <xref:System.Windows.Controls.ValidationRule> Bindungs-Engine überprüft <xref:System.Windows.Data.Binding>, ob benutzerdefinierte-Objekte definiert <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> sind, deren <xref:System.Windows.Controls.ValidationStep.CommittedValue> auf festgelegt ist. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> in diesem Fall wird <xref:System.Windows.Controls.ValidationRule.Validate%2A> die-Methode <xref:System.Windows.Controls.ValidationRule> für jeden aufgerufen, der auf festgelegt ist. <xref:System.Windows.Controls.ValidationStep.CommittedValue> , bis einer von Ihnen in einen Fehler auftritt oder bis alle davon bestanden werden.  
  
 Wenn eine <xref:System.Windows.Controls.ValidationRule> während des gesamten Vorgangs nicht übergeben wird, erstellt die Bindungs-Engine ein <xref:System.Windows.Controls.ValidationError> -Objekt und fügt es der <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> -Auflistung des gebundenen Elements hinzu. Bevor die Bindungs-Engine die <xref:System.Windows.Controls.ValidationRule> Objekte in einem beliebigen Schritt ausführt, werden alle <xref:System.Windows.Controls.ValidationError> Elemente entfernt, die während <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> dieses Schritts der angefügten-Eigenschaft des gebundenen Elements hinzugefügt wurden. Wenn z. b. <xref:System.Windows.Controls.ValidationRule> ein <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> Fehler festgelegt ist, entfernt die Bindungs-Engine beim nächsten Auftreten des Überprüfungs Vorgangs <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> diese <xref:System.Windows.Controls.ValidationError> sofort, bevor Sie einen <xref:System.Windows.Controls.ValidationRule> aufruft, der auf festgelegt ist. <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 Wenn <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> nicht leer ist, wird <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> die angefügte-Eigenschaft des-Elements `true`auf festgelegt. Auch wenn die <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> -Eigenschaft <xref:System.Windows.Data.Binding> von auf `true`festgelegt ist, löst die Bindungs-Engine das <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> angefügte-Ereignis für das-Element aus.  
  
 Beachten Sie außerdem, dass die <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> angefügte Eigenschaft durch eine gültige Wertübertragung in beide Richtungen (Ziel an Quelle oder Ziel Quelle) gelöscht wird.  
  
 Wenn der Bindung entweder <xref:System.Windows.Controls.ExceptionValidationRule> ein zugeordnet ist oder die <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> -Eigenschaft auf `true` festgelegt ist und eine Ausnahme ausgelöst wird, wenn die Bindungs-Engine die Quelle festlegt, prüft die Bindungs-Engine, ob eine <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>vorhanden ist. Sie haben die Möglichkeit, den Rückruf <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> zum Bereitstellen eines benutzerdefinierten Handlers für die Behandlung von Ausnahmen zu verwenden. Wenn ein <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> <xref:System.Windows.Data.Binding>nicht in angegeben ist, erstellt die Bindungs-Engine eine <xref:System.Windows.Controls.ValidationError> mit der-Ausnahme und fügt Sie der <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> -Auflistung des gebundenen Elements hinzu.  
  
## <a name="debugging-mechanism"></a>Debugverfahren  
 Sie können die angefügte- <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> Eigenschaft für ein Bindungs bezogenes Objekt so festlegen, dass Informationen über den Status einer bestimmten Bindung empfangen werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Neues in WPF Version 4.5](../getting-started/whats-new.md)
- [Binden an die Ergebnisse einer LINQ-Abfrage](how-to-bind-to-the-results-of-a-linq-query.md)
- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [Demo für die Datenbindung](https://go.microsoft.com/fwlink/?LinkID=163703)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
- [Binden an eine ADO.NET-Datenquelle](how-to-bind-to-an-ado-net-data-source.md)
