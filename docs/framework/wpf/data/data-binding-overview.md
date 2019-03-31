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
ms.openlocfilehash: 9e55714db55168c95f744665165e333d7f2ca730
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634556"
---
# <a name="data-binding-overview"></a>Übersicht über die Datenbindung
Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können an Daten aus einer Vielzahl von Datenquellen in Form von [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Objekten und [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] gebunden werden. <xref:System.Windows.Controls.ContentControl>s wie z. B. <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.ItemsControl>s wie z. B. <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ListView> verfügen über integrierte Funktionen, um flexible Formatierung von einzelnen Datenelementen oder Auflistungen von Datenelementen zu aktivieren. Sortier-, Filter- und Gruppenansichten können übergreifend für die Daten generiert werden.  
  
 Die Datenbindungsfunktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten gegenüber herkömmlichen Modellen einige Vorteile. Dazu zählen eine Reihe von Eigenschaften, die Datenbindung grundsätzlich unterstützen, eine flexible Darstellung von Daten auf einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sowie die klare Trennung zwischen Geschäftslogik und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 In diesem Thema wird zunächst erläutert die grundlegenden Konzepte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Datenbindung und anschließend wird die Verwendung der <xref:System.Windows.Data.Binding> -Klasse und anderen Features der Datenbindung.  
  
  
<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>Was ist Datenbindung?  
 Durch Datenbindung wird eine Verbindung zwischen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung und der Geschäftslogik hergestellt. Wenn die Bindung die ordnungsgemäßen Einstellungen aufweist und die Daten die richtigen Benachrichtigungen bereitstellen, ändern sich die an die Daten gebundenen Elemente automatisch bei jeder Änderung des Werts der Daten, sodass die Änderungen entsprechend wiedergegeben werden. Datenbindung kann auch bedeuten, dass bei einer Änderung der äußeren Darstellung von Daten in einem Element die zugrunde liegenden Daten automatisch aktualisiert werden können, um die Änderung wiederzugeben. Z. B., wenn der Benutzer den Wert in bearbeitet ein <xref:System.Windows.Controls.TextBox> Element, das zugrunde liegende Datenwert wird automatisch aktualisiert, um diese Änderung zu übernehmen.  
  
 Eine typische Verwendung der Datenbindung wäre, die auf einem Server oder lokal gespeicherten Konfigurationsdaten in Formulare oder andere Steuerelemente der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] einzufügen. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird dieses Konzept dahingehend erweitert, dass auch eine Vielzahl von Eigenschaften an die unterschiedlichsten Datenquellen gebunden werden können. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Abhängigkeitseigenschaften von Elementen an [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekte (einschließlich [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)]-Objekte oder Objekte, die Webdiensten und Webeigenschaften zugeordnet sind) und [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten gebunden werden.  
  
 Ein Beispiel für eine Datenbindung finden Sie auf der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der folgenden Anwendung in der [Demo für die Datenbindung](https://go.microsoft.com/fwlink/?LinkID=163703):  
  
 ![Screenshot des Datenbindungsbeispiels](./media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 Oben sehen Sie die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] einer Anwendung, die eine Liste von Auktionselementen anzeigt. Die Anwendung veranschaulicht die folgenden Datenbindungsfunktionen:  
  
-   Den Inhalt der <xref:System.Windows.Controls.ListBox> gebunden ist, auf eine Auflistung von *AuctionItem* Objekte. Ein *AuctionItem*-Objekt verfügt über Eigenschaften wie *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* usw.  
  
-   Die Daten (*AuctionItem* Objekte) angezeigt, der <xref:System.Windows.Controls.ListBox> auf Vorlagen basierende ist, sodass die Beschreibung und den aktuellen Preis für jedes Element angezeigt werden. Dies erfolgt mithilfe einer <xref:System.Windows.DataTemplate>. Darüber hinaus hängt die Darstellung jedes Elements vom *SpecialFeatures*-Wert des angezeigten *AuctionItem* ab. Wenn der *SpecialFeatures*-Wert von *AuctionItem* auf *Color* festgelegt ist, hat das Element einen blauen Rahmen. Wenn der Wert *Highlight* ist, hat das Element einen orangefarbenen Rahmen und einen Stern. Im Abschnitt [Datenvorlagen](#data_templating) erhalten Sie weitere Informationen zu Datenvorlagen.  
  
-   Der Benutzer kann gruppieren, filtern oder Sortieren der Daten mithilfe der <xref:System.Windows.Controls.CheckBox>es bereitgestellt. In der Abbildung oben, die "Group by Category" und "Sort by Category and Date" <xref:System.Windows.Controls.CheckBox>es ausgewählt sind. Möglicherweise haben Sie bereits bemerkt, dass die Daten nach der Kategorie des Produkts gruppiert sind und der Name der Kategorie in alphabetischer Reihenfolge aufgeführt ist. In der Abbildung ist nicht so gut zu erkennen, dass auch die Elemente innerhalb der einzelnen Kategorien nach Startdatum sortiert sind. Dazu wird eine *Auflistungsansicht* verwendet. Im Abschnitt [Binden an Auflistungen](#binding_to_collections) werden Auflistungsansichten erläutert.  
  
-   Wenn der Benutzer ein Element markiert die <xref:System.Windows.Controls.ContentControl> zeigt die Details des ausgewählten Elements. Dies wird als *Master/Detail-Szenario* bezeichnet. Im Abschnitt [Master/Detail-Szenario](#master_detail_scenario) erhalten Sie Informationen zu diesem Typ von Bindungsszenario.  
  
-   Der Typ des der *"StartDate"* Eigenschaft <xref:System.DateTime>, ein Datum mit der Zeit auf die Millisekunde genau zurückgegeben. In dieser Anwendung wurde ein benutzerdefinierter Konverter verwendet, damit eine kürzere Datumszeichenfolge angezeigt wird. Weitere Informationen zu Konvertern finden Sie im Abschnitt [Datenkonvertierung](#data_conversion).  
  
 Wenn der Benutzer auf die Schaltfläche *Add Product* klickt, wird das folgende Formular aufgerufen:  
  
 ![Seite „Produktliste hinzufügen“](./media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 Der Benutzer kann die Felder im Formular bearbeiten, die Produktauflistung in der Kurzvorschau und in den detaillierteren Vorschaufenstern anzeigen und dann auf *submit* klicken, um die neue Produktauflistung hinzuzufügen. Alle vorhandenen Gruppierungs-, Filter- und Sortierfunktionen werden auf den neuen Eintrag angewendet. In diesem speziellen Fall wird das im obigen Bild eingegebene Element in der Kategorie *Computer* an zweiter Stelle angezeigt.  
  
 In dieser Abbildung nicht dargestellt, ist die Validierungslogik, die bereitgestellt werden, der *Startdatum* <xref:System.Windows.Controls.TextBox>. Wenn der Benutzer, ein ungültiges eingibt Datum (mit ungültiger Formatierung oder einem vergangenen Datum), mit der Benutzer benachrichtigt werden eine <xref:System.Windows.Controls.ToolTip> und ein rotes Ausrufezeichen neben der <xref:System.Windows.Controls.TextBox>. Im Abschnitt [Datenvalidierung](#data_validation) wird näher auf das Erstellen von Validierungslogik eingegangen.  
  
 Bevor die oben genannten unterschiedlichen Datenbindungsfunktionen näher erläutert werden, werden im nächsten Abschnitt die grundlegenden Konzepte erläutert, die für ein Verständnis der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Datenbindung unerlässlich sind.  
  
## <a name="basic-data-binding-concepts"></a>Grundlegende Konzepte zur Datenbindung  
  
 Unabhängig davon, welches Element Sie binden und welcher Art die Datenquelle ist, erfolgt die Bindung stets gemäß dem in der folgenden Abbildung gezeigten Modell:  
  
 ![Das Diagramm, die das einfache Datenbindungsmodell anzeigt.](./media/data-binding-overview/basic-data-binding-diagram.png)  
  
 Wie in der Abbildung dargestellt, ist Datenbindung die Brücke zwischen dem Bindungsziel und der Bindungsquelle. Die Abbildung veranschaulicht die folgenden grundlegenden Konzepte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Datenbindung:  
  
-   Eine Bindung besteht in der Regel aus diesen vier Komponenten: einem Bindungszielobjekt, einer Zieleigenschaft, einer Bindungsquelle sowie einem Pfad zum Wert in der Bindungsquelle, die verwendet werden soll. Z. B., wenn Sie den Inhalt einer binden möchten eine <xref:System.Windows.Controls.TextBox> auf die *Namen* Eigenschaft eine *Mitarbeiter* Objekt, das Zielobjekt der <xref:System.Windows.Controls.TextBox>, die Zieleigenschaft der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft, die zu verwendende Wert *Namen*, und das Quellobjekt ist die *Mitarbeiter* Objekt.  
  
-   Die Zieleigenschaft muss eine Abhängigkeitseigenschaft sein. Die meisten <xref:System.Windows.UIElement> -Eigenschaften sind Abhängigkeitseigenschaften und die meisten Abhängigkeitseigenschaften, außer schreibgeschützten, unterstützen die Datenbindung standardmäßig. (Nur <xref:System.Windows.DependencyObject> -Typen können Abhängigkeitseigenschaften und alle definieren <xref:System.Windows.UIElement>s abgeleitet <xref:System.Windows.DependencyObject>.)  
  
-   Obwohl nicht in der Abbildung angegeben, sollte beachtet werden, dass das Bindungsquellenobjekt nicht darauf beschränkt ist, als benutzerdefiniertes [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekt zu fungieren. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Datenbindung unterstützt Daten in Form von [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekten und [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Um Beispiele zu ermöglichen, die Bindungsquelle möglicherweise eine <xref:System.Windows.UIElement>, beliebiges Listenobjekt, ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Objekt, das zugeordnet ist [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] Daten oder Webdienste oder eine XmlNode-Klasse, die enthält Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).  
  
 Beim Lesen anderer [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]-Themen sollten Sie daran denken, dass Sie beim Einrichten einer Bindung ein Bindungsziel *an* eine Bindungsquelle binden. Angenommen, Sie einige zugrunde liegende anzeigen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in eine <xref:System.Windows.Controls.ListBox> mithilfe der Datenbindung, erfolgt die Bindung Ihrer <xref:System.Windows.Controls.ListBox> auf die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.  
  
 Um eine Bindung herzustellen, verwenden Sie die <xref:System.Windows.Data.Binding> Objekt. Im weiteren Verlauf dieses Themas erläutert viele der Konzepte und einige der Eigenschaften und die Nutzung der <xref:System.Windows.Data.Binding> Objekt.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>Richtung des Datenflusses  
 Wie bereits erwähnt, und wie durch den Pfeil in der Abbildung oben angezeigt, kann Datenfluss einer Bindung vom Bindungsziel zur Bindungsquelle wechseln (z. B. den Wert des ändert, wenn ein Benutzer den Wert des bearbeitet ein <xref:System.Windows.Controls.TextBox>) und/oder von der Bindungsquelle an das Bindungsziel (z. B. Ihre <xref:System.Windows.Controls.TextBox> Inhalt mit Änderungen in der Bindungsquelle aktualisiert wird), wenn die Bindungsquelle die entsprechenden Benachrichtigungen bereitstellt.  
  
 Sie können die Anwendung so einrichten, dass Benutzer die Daten ändern und zurück an das Quellobjekt übertragen können. Sie können auch das Aktualisieren von Quelldaten durch Benutzer unterbinden. Sie können dies steuern, durch Festlegen der <xref:System.Windows.Data.Binding.Mode%2A> Eigenschaft Ihre <xref:System.Windows.Data.Binding> Objekt. In der folgenden Abbildung werden die unterschiedlichen Datenflusstypen veranschaulicht:  
  
 ![Datenfluss bei der Datenbindung](./media/databinding-dataflow.png "DataBinding_DataFlow")  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> Bindung bewirkt, dass Änderungen an der Quelleigenschaft die Zieleigenschaft automatisch aktualisiert, aber Änderungen an der Zieleigenschaft nicht zurück an die Quelleigenschaft weitergegeben werden. Dieser Bindungstyp empfiehlt sich, wenn das gebundene Steuerelement implizit als schreibgeschützt festgelegt wurde. Sie können beispielsweise eine Bindung an eine Quelle wie einen Börsenticker erstellen, oder möglicherweise ist für die Zieleigenschaft keine Steuerungsoberfläche verfügbar, um Änderungen vorzunehmen, z. B. an der datengebundenen Hintergrundfarbe einer Tabelle. Wenn die Änderungen der Zieleigenschaft nicht überwacht werden müssen, vermeiden Sie mit dem <xref:System.Windows.Data.BindingMode.OneWay>-Bindungsmodus den Mehraufwand des <xref:System.Windows.Data.BindingMode.TwoWay>-Bindungsmodus.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> Bindung bewirkt, dass Änderungen auf die Quelleigenschaft oder der Zieleigenschaft die jeweils andere automatisch aktualisiert. Dieser Typ von Bindung ist für bearbeitbare Formulare und sonstige vollständig interaktive [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarien geeignet. Die meisten Eigenschaften standardmäßig <xref:System.Windows.Data.BindingMode.OneWay> Bindung, aber einige Abhängigkeitseigenschaften (meistens Eigenschaften von vom Benutzer bearbeitbare Steuerelemente wie z. B. die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> Eigenschaft <xref:System.Windows.Controls.CheckBox>) standardmäßig <xref:System.Windows.Data.BindingMode.TwoWay> Bindung. Eine programmgesteuerte Methode zum Bestimmen, ob eine Abhängigkeitseigenschaft standardmäßig uni- oder bidirektional bindet, besteht darin, die Metadaten der Eigenschaft mit <xref:System.Windows.DependencyProperty.GetMetadata%2A> abzurufen und dann den booleschen Wert der <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>-Eigenschaft zu überprüfen.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> Stellt die Umkehrung der <xref:System.Windows.Data.BindingMode.OneWay> Bindung; er aktualisiert die Quelleigenschaft, wenn die Zieleigenschaft ändert. Ein Beispielszenario besteht darin, einfach den Quellwert von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] neu zu bewerten.  
  
-   In der Abbildung nicht dargestellt ist <xref:System.Windows.Data.BindingMode.OneTime> Bindung, die bewirkt, dass der Quelleigenschaft die Zieleigenschaft initialisiert, aber nachfolgende Änderungen werden nicht weitergegeben. Wenn sich also der Datenkontext oder das Objekt im Datenkontext ändert, wird die Änderung in der Zieleigenschaft nicht angezeigt. Dieser Bindungstyp empfiehlt sich, wenn Sie Daten verwenden, bei denen eine Momentaufnahme des aktuellen Zustands verwendet werden kann oder die Daten tatsächlich statisch sind. Dieser Bindungstyp ist auch hilfreich, wenn die Zieleigenschaft mit einem bestimmten Wert der Quelleigenschaft initialisiert werden soll und der Datenkontext vorab nicht bekannt ist. Dies ist eine wesentlich einfachere Form der <xref:System.Windows.Data.BindingMode.OneWay>-Bindung, die eine bessere Leistung in Situationen bietet, in denen sich der Quellwert nicht ändert.  
  
 Beachten Sie, dass zum Erkennen von quelländerungen (gilt für <xref:System.Windows.Data.BindingMode.OneWay> und <xref:System.Windows.Data.BindingMode.TwoWay> Bindungen), muss die Quelle einen Änderungsbenachrichtigungsmechanismus von geeigneten wie z. B. implementieren <xref:System.ComponentModel.INotifyPropertyChanged>. Finden Sie unter [bei Eigenschaftenänderungen implementieren](how-to-implement-property-change-notification.md) ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> Implementierung.  
  
 Die <xref:System.Windows.Data.Binding.Mode%2A> -Eigenschaftenseite bietet weitere Informationen zu Bindungsmodi und ein Beispiel dafür, wie Sie die Richtung einer Bindung an.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>Wodurch werden Quellaktualisierungen ausgelöst?  
 Bindungen <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Lauschen auf Änderungen in der Zieleigenschaft und übertragen sie zurück an die Quelle. Dies wird als Aktualisieren der Quelle bezeichnet. Sie können beispielsweise den Text eines TextBox-Elements bearbeiten, um den zugrunde liegenden Quellwert zu ändern. Wie im vorherigen Abschnitt beschrieben wird, wird die Richtung des Datenflusses durch den Wert bestimmt die <xref:System.Windows.Data.Binding.Mode%2A> -Eigenschaft der Bindung.  
  
 Wird der Quellwert aktualisiert, während Sie den Text bearbeiten oder nachdem Sie die Bearbeitung abgeschlossen haben und den Mauszeiger aus dem TextBox-Steuerelement bewegen? Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft der Bindung bestimmt, wodurch die Aktualisierung der Quelle ausgelöst. Die Punkte der richtigen Pfeile in der folgenden Abbildung veranschaulichen die Rolle der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft:  
  
 ![Diagramm die Rolle von der UpdateSourceTrigger-Eigenschaft zeigt.](./media/data-binding-overview/data-binding-updatesource-trigger.png)  
  
 Wenn die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, klicken Sie dann der Wert verweist den Pfeil nach rechts von <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen aktualisiert wird, sobald die Zieleigenschaft ändert. Aber wenn die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, und klicken Sie dann diesen Wert nur durch den neuen Wert aktualisiert wird, wenn die Zieleigenschaft den Fokus verliert.  
  
 Ähnlich wie die <xref:System.Windows.Data.Binding.Mode%2A> -Eigenschaft haben verschiedene Abhängigkeitseigenschaften unterschiedliche <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Werte. Der Standardwert für die meisten Abhängigkeitseigenschaften ist <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, während die <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> aufweist. Dies bedeutet, dass quellaktualisierungen in der Regel bei jedem auftreten, die Zieleigenschaft ändert, handelt es sich gut für <xref:System.Windows.Controls.CheckBox>es und anderen einfachen Steuerelementen. Bei Textfeldern kann eine Aktualisierung nach jeder Tastatureingabe die Leistung mindern und führt außerdem dazu, dass der Benutzer nicht wie gewohnt durch Drücken der Rücktaste Tippfehler beheben kann, bevor der neue Wert übergeben wird. Deshalb die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft hat den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> anstelle von <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 Finden Sie unter den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaftenseite finden Sie Informationen zur Suche nach dem <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert einer Abhängigkeitseigenschaft.  
  
 Die folgende Tabelle enthält ein Beispielszenario für die einzelnen <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Wert mithilfe der <xref:System.Windows.Controls.TextBox> als Beispiel:  
  
|UpdateSourceTrigger-Wert|Wenn der Quellwert aktualisiert wird|Beispielszenario für TextBox|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (Standard für <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>)|Wenn das TextBox-Steuerelement den Fokus verliert|Ein <xref:System.Windows.Controls.TextBox> , Validierungslogik zugeordnet ist (siehe Abschnitt zur Datenvalidierung)|  
|PropertyChanged|Während der Eingabe in die <xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox> Steuerelemente in einem chatroomfenster|  
|Explicit|Wenn die Anwendung aufruft <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox> Steuerelemente in einem bearbeitbaren Formular (aktualisiert die Quellwerte nur klickt der Benutzer die Schaltfläche "Senden")|  
  
 Ein Beispiel finden Sie unter [Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>Erstellen einer Bindung  
  
 Um einige der in den vorherigen Abschnitten vorgestellten Konzepte einzugehen, Sie Einrichten einer Bindung mit der <xref:System.Windows.Data.Binding> -Objekt und jede Bindung in der Regel besteht aus vier Komponenten: Binden von Ziel, Zieleigenschaft, Bindungsquelle und einen Pfad an der, die zu verwendende Quellwert. In diesem Abschnitt wird das Einrichten einer Bindung erläutert.  
  
 Im folgenden Beispiel ist das Bindungsquellobjekt eine Klasse namens *MyData*, die im Namespace *SDKSample* definiert ist. Zu Demonstrationszwecken hat die *MyData*-Klasse eine Zeichenfolgeneigenschaft namens *ColorName*, deren Wert auf „Red“ festgelegt ist. In diesem Beispiel wird also eine Schaltfläche mit einem roten Hintergrund erstellt.  
  
 [!code-xaml[BindNonTextProperty#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Weitere Informationen zur Syntax der Bindungsdeklaration und Beispiele zum Einrichten einer Bindung im Code finden Sie unter [Übersicht über Bindungsdeklarationen](binding-declarations-overview.md).  
  
 Wenn dieses Beispiel auf das einfache Diagramm angewendet wird, sieht die resultierend Abbildung wie die folgende aus. Dies ist eine <xref:System.Windows.Data.BindingMode.OneWay> -Bindung, da die Background-Eigenschaft unterstützt <xref:System.Windows.Data.BindingMode.OneWay> standardmäßig binden.  
  
 ![Diagramm, das zeigt, die die Datenbindung Background-Eigenschaft.](./media/data-binding-overview/data-binding-button-background-example.png)  
  
 Sie Fragen sich vielleicht, warum dies funktioniert, obwohl die *ColorName* Eigenschaft ist vom Typ String, während die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft ist vom Typ <xref:System.Windows.Media.Brush>. Der Grund dafür ist die Standardtypkonvertierung, die im Abschnitt [Datenkonvertierung](#data_conversion) näher erläutert wird.  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>Angeben der Bindungsquelle  
 Beachten Sie, dass im vorherigen Beispiel die Bindungsquelle, durch Festlegen angegeben wird der <xref:System.Windows.FrameworkElement.DataContext%2A> Eigenschaft für die <xref:System.Windows.Controls.DockPanel> Element. Die <xref:System.Windows.Controls.Button> erbt dann die <xref:System.Windows.FrameworkElement.DataContext%2A> Wert aus der <xref:System.Windows.Controls.DockPanel>, die das übergeordnete Element ist. Das Bindungsquellobjekt stellt, wie bereits erwähnt, eine der vier erforderlichen Komponenten einer Bindung dar. Wäre das Bindungsquellobjekt nicht angegeben, hätte die Bindung keine Auswirkungen.  
  
 Es gibt mehrere Möglichkeiten, das Bindungsquellobjekt anzugeben. Mithilfe der <xref:System.Windows.FrameworkElement.DataContext%2A> Eigenschaft für ein übergeordnetes Element ist nützlich, wenn Sie mehrere Eigenschaften an dieselbe Quelle binden. Es kann aber auch zweckmäßiger sein, die Bindungsquelle in einzelnen Bindungsdeklarationen anzugeben. Für das vorherige Beispiel, anstatt die <xref:System.Windows.FrameworkElement.DataContext%2A> -Eigenschaft, können Sie angeben der Bindungsquelle durch Festlegen der <xref:System.Windows.Data.Binding.Source%2A> Eigenschaft direkt auf der Bindungsdeklaration der Schaltfläche wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Anders als das Festlegen der <xref:System.Windows.FrameworkElement.DataContext%2A> Eigenschaft für ein Element direkt, erben die <xref:System.Windows.FrameworkElement.DataContext%2A> aus einem Vorgänger (z. B. die Schaltfläche im ersten Beispiel), und das Angeben der Bindungsquelle explizit durch Festlegen der <xref:System.Windows.Data.Binding.Source%2A> Eigenschaft für die <xref:System.Windows.Data.Binding> (z. B. die Schaltfläche im letzten Beispiel), können Sie auch die <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft oder das <xref:System.Windows.Data.Binding.RelativeSource%2A> Eigenschaft, um die Bindungsquelle angeben. Die <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft ist nützlich, wenn Sie an andere Elemente in Ihrer Anwendung binden, z. B. Wenn Sie einen Schieberegler anpassen, die Breite einer Schaltfläche. Die <xref:System.Windows.Data.Binding.RelativeSource%2A> Eigenschaft ist nützlich, wenn die Bindung, in angegeben wird eine <xref:System.Windows.Controls.ControlTemplate> oder <xref:System.Windows.Style>. Weitere Informationen finden Sie unter [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>Angeben des Pfads zum Wert  
 Wenn die Bindungsquelle ein Objekt ist, verwenden Sie die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft zum Angeben des Werts, der für die Bindung verwendet. Wenn Sie eine Bindung [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten, die Sie verwenden die <xref:System.Windows.Data.Binding.XPath%2A> Eigenschaft zum Angeben des Werts. In einigen Fällen ist es möglicherweise gilt für die Verwendung der <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft selbst, wenn Ihre Daten sind [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Z. B. Wenn Sie die Name-Eigenschaft eines zurückgegebenen XmlNode (als Ergebnis einer XPath-Abfrage) zugreifen möchten, verwenden Sie die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft zusätzlich zu den <xref:System.Windows.Data.Binding.XPath%2A> Eigenschaft.  
  
 Weitere Informationen zur Syntax und Beispiele finden Sie unter den <xref:System.Windows.Data.Binding.Path%2A> und <xref:System.Windows.Data.Binding.XPath%2A> Eigenschaftenseiten.  
  
 Beachten Sie, dass, obwohl wir, die Ihr Interesse und haben die <xref:System.Windows.Data.Binding.Path%2A> für den zu verwendenden Wert ist eine der vier erforderlichen Komponenten einer Bindung, in Szenarien, in denen Sie an ein vollständiges Objekt binden möchten, die der zu verwendenden Wert wäre das Bindungsquellobjekt identisch. In diesen Fällen ist es gilt nicht für an eine <xref:System.Windows.Data.Binding.Path%2A>. Betrachten Sie das folgende Beispiel:  
  
 [!code-xaml[MasterDetail#EmptyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 Im obigen Beispiel wird die leere Bindungssyntax verwendet: {Binding}. In diesem Fall die <xref:System.Windows.Controls.ListBox> erbt den DataContext von einem übergeordneten DockPanel-Element (nicht in diesem Beispiel dargestellt). Wenn der Pfad nicht angegeben wurde, erfolgt die Bindung standardmäßig an das gesamte Objekt. Das heißt, in diesem Beispiel der Pfad wurde ausgelassen, da wir binden die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft, um das gesamte Objekt. (Im Abschnitt [Binden an Auflistungen](#binding_to_collections) wird ausführlich darauf eingegangen.)  
  
 Dieses Szenario ist nicht nur zum Binden an eine Auflistung hilfreich, sondern auch zum Binden an ein vollständiges Objekt statt nur an eine einzelne Eigenschaft eines Objekts. Wenn es sich beim Quellobjekt beispielsweise um einen Zeichenfolgentyp handelt und Sie lediglich an die Zeichenfolge binden möchten. Ein anderes allgemeines Szenario besteht darin, ein Element an ein Objekt mit mehreren Eigenschaften zu binden.  
  
 Beachten Sie, dass Sie ggf. benutzerdefinierte Logik anwenden müssen, damit die Daten für die gebundene Zieleigenschaft sinnvoll sind. Bei der benutzerdefinierten Logik kann es sich z. B. um einen benutzerdefinierten Konverter handeln (falls keine Standardtypkonvertierung vorhanden ist). Weitere Informationen über Konverter finden Sie unter [Datenkonvertierung](#data_conversion).  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Die „Binding“-Klasse und „BindingExpression“  
 Vor dem Abrufen auf andere Features und Verwendungsmöglichkeiten der Datenbindung, es wäre hilfreich, stellen Sie vor der <xref:System.Windows.Data.BindingExpression> Klasse. Wie Sie, in den vorherigen Abschnitten gesehen haben der <xref:System.Windows.Data.Binding> Klasse ist die allgemeine Klasse für die Deklaration einer Bindung; die <xref:System.Windows.Data.Binding> -Klasse bietet zahlreiche Eigenschaften, mit denen Sie die Merkmale einer Bindung angeben. Eine verwandte Klasse <xref:System.Windows.Data.BindingExpression>, ist das zugrunde liegende Objekt, das die Verbindung zwischen der Quelle und Ziel aufrechterhält. Ein Bindung enthält sämtliche Informationen, die von mehreren Bindungsausdrücken gemeinsam genutzt werden können. Ein <xref:System.Windows.Data.BindingExpression> ist ein Instanzenausdruck, der nicht gemeinsam genutzt werden kann und sämtliche Instanzeninformationen von enthält die <xref:System.Windows.Data.Binding>.  
  
 Betrachten Sie beispielsweise die folgenden, in denen *MyDataObject* ist eine Instanz der *MyData* -Klasse, *MyBinding* ist die Quelle <xref:System.Windows.Data.Binding> -Objekt und *MyData* Klasse ist eine definierte Klasse, die eine Zeichenfolgeneigenschaft namens enthält *MyDataProperty*. In diesem Beispiel bindet den Textinhalt von *"MyText"*, eine Instanz von <xref:System.Windows.Controls.TextBlock>zu *MyDataProperty*.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Mit demselben *myBinding*-Objekt können Sie auch andere Bindungen erstellen. Sie können beispielsweise mit dem *myBinding*-Objekt eine Bindung des Textinhalts eines Kontrollkästchens an *MyDataProperty* herstellen. In diesem Szenario werden zwei Instanzen von <xref:System.Windows.Data.BindingExpression> Freigabe der *MyBinding* Objekt.  
  
 Ein <xref:System.Windows.Data.BindingExpression> -Objekt abgerufen werden kann, durch den Rückgabewert des Aufrufs <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> auf einem datengebundenen Objekt. In den folgenden Themen veranschaulichen einige Verwendungsmöglichkeiten der der <xref:System.Windows.Data.BindingExpression> Klasse:  
  
-   [Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft](how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
-   [Steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>Datenkonvertierung  
 Im vorherigen Beispiel ist die Schaltfläche Rot da seine <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft an eine Zeichenfolgeneigenschaft mit dem Wert "Red" gebunden ist. Dies funktioniert, weil ein Typkonverter auf vorhanden ist, wird die <xref:System.Windows.Media.Brush> Typ, den Zeichenfolgenwert, konvertiert ein <xref:System.Windows.Media.Brush>.  
  
 Wenn diese Informationen der Abbildung im Abschnitt [Erstellen einer Bindung](#creating_a_binding) hinzugefügt werden, sieht das Diagramm folgendermaßen aus:  
  
 ![Das Diagramm, das die Standardeigenschaft für die Datenbindung anzeigt.](./media/data-binding-overview/data-binding-button-default-conversion.png)  
  
 Jedoch, was geschieht, wenn statt einer Eigenschaft vom Typzeichenfolge das Bindungsquellobjekt hat eine *Farbe* Eigenschaft vom Typ <xref:System.Windows.Media.Color>? In diesem Fall, in der Reihenfolge für die Bindung funktioniert Sie müssen zuerst die *Farbe* in einen Eigenschaftswert, der die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft akzeptiert. Sie müssen einen benutzerdefinierten Konverter erstellen, durch die Implementierung der <xref:System.Windows.Data.IValueConverter> -Schnittstelle, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[ColorPicker_snip#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 Die <xref:System.Windows.Data.IValueConverter> -Referenzseite finden Sie weitere Informationen.  
  
 Jetzt wird anstelle der Standardkonvertierung der benutzerdefinierte Konverter verwendet, und unser Diagramm sieht wie folgt aus:  
  
 ![Das Diagramm, das die benutzerdefinierte Bindung Datenkonverter anzeigt.](./media/data-binding-overview/data-binding-converter-color-example.png)  
  
 Wie bereits ausgeführt, können aufgrund von Typkonvertern, die im Typ vorhanden sind, an den gebunden wird, Standardkonvertierungen verfügbar sein. Dieses Verhalten hängt von den im Ziel vorhandenen Typkonvertern ab. Erstellen Sie im Zweifelsfall einen eigenen Konverter.  
  
 Es folgen einige typische Szenarien, in denen die Implementierung eines Datenkonverters sinnvoll ist:  
  
-   Die Daten sollen je nach Kultur unterschiedlich angezeigt werden. Sie können z. B. einen Währungskonverter oder einen Datum-/Uhrzeitkonverter implementieren, der auf den Werten oder Standards basiert, die in einer bestimmten Kultur verwendet werden.  
  
-   Die verwendeten Daten müssen nicht unbedingt dazu dienen, den Textwert einer Eigenschaft zu ändern. Sie können auch den Zweck haben, andere Werte zu ändern, beispielsweise die Quelle für ein Bild oder die Farbe bzw. das Format des Anzeigetexts. Konverter können in dieser Instanz verwendet werden, indem die Bindung einer Eigenschaft konvertiert wird, die ungeeignet zu sein scheint, z. B. wenn ein Textfeld an die Background-Eigenschaft einer Tabellenzelle gebunden wird.  
  
-   Mehrere Steuerelemente oder mehrere Steuerelementeigenschaften sind an dieselben Daten gebunden. In diesem Fall wird durch die primäre Bindung möglicherweise nur der Text angezeigt, wohingegen andere Bindungen bestimmte Anzeigeprobleme behandeln, aber dieselben Bindungen als Quellinformationen verwenden.  
  
-   Bisher haben nicht noch erörtert <xref:System.Windows.Data.MultiBinding>, wobei eine Zieleigenschaft eine Auflistung von Bindungen hat. Im Fall von einem <xref:System.Windows.Data.MultiBinding>, verwenden Sie eine benutzerdefinierte <xref:System.Windows.Data.IMultiValueConverter> um einen endgültigen Wert aus den Werten der Bindungen zu erstellen. So kann die Farbe beispielsweise aus roten, blauen und grünen Werten berechnet werden, die aus denselben oder anderen Bindungsquellobjekten stammen können. Finden Sie unter den <xref:System.Windows.Data.MultiBinding> -klassenseite Beispiele und Informationen.  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>Binden an Auflistungen  
  
 Ein Bindungsquellobjekt kann als einzelnes Objekt behandelt werden, dessen Eigenschaften Daten enthalten, oder als eine Datenauflistung von polymorphen Objekten, die häufig zusammen gruppiert werden (beispielsweise als Ergebnis einer Datenbankabfrage). Bisher wurde nur das Binden an einzelne Objekte behandelt, aber auch das Binden an eine Datenauflistung ist ein gängiges Szenario. Z. B. ein häufiges Szenario ist die Verwendung einer <xref:System.Windows.Controls.ItemsControl> wie z. B. eine <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>, oder <xref:System.Windows.Controls.TreeView> um eine datenauflistung anzuzeigen, wie gezeigt in der Anwendung in der [Was ist Datenbindung?](#what_is_data_binding) Abschnitt.  
  
 Das bisherige einfache Diagramm ist praktischerweise immer noch gültig. Wenn Sie binden ein <xref:System.Windows.Controls.ItemsControl> auf eine Auflistung, das Diagramm sieht wie folgt aus:  
  
 ![Diagramm, das zeigt, das die Datenbindung ItemsControl-Objekt.](./media/data-binding-overview/data-binding-itemscontrol.png)  
  
 Wie in diesem Diagramm dargestellt, zum Binden einer <xref:System.Windows.Controls.ItemsControl> an ein Auflistungsobjekt <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft ist die Eigenschaft zu verwenden. Sie können sich vorstellen <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft als Inhalt der <xref:System.Windows.Controls.ItemsControl>. Beachten Sie, dass die Bindung <xref:System.Windows.Data.BindingMode.OneWay> da die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft unterstützt <xref:System.Windows.Data.BindingMode.OneWay> standardmäßig binden.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>Implementieren von Auflistungen  
 Sie können jede Auflistung, die implementiert Auflisten der <xref:System.Collections.IEnumerable> Schnittstelle. Allerdings um dynamische Bindungen einzurichten, sodass einfügungen oder löschungen in der Sammlung aktualisieren die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automatisch die Sammlung implementieren muss die <xref:System.Collections.Specialized.INotifyCollectionChanged> Schnittstelle. Diese Schnittstelle macht ein Ereignis verfügbar, das bei jeder Änderung der zugrunde liegenden Auflistung ausgelöst werden sollte.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt die <xref:System.Collections.ObjectModel.ObservableCollection%601> -Klasse, die integrierte Implementierung einer datenauflistung, die verfügbar macht, ist die <xref:System.Collections.Specialized.INotifyCollectionChanged> Schnittstelle. Beachten Sie, um die Übertragung von Datenwerten von Quellobjekten zu Zielen vollständig zu unterstützen, jedes Objekt in der Auflistung, die bindbare Eigenschaften unterstützt auch implementieren muss, die <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle. Weitere Informationen finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).  
  
 Bevor Sie eine eigene Auflistung implementieren, erwägen Sie <xref:System.Collections.ObjectModel.ObservableCollection%601> oder einer vorhandenen Sammlung Klassen, z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, und <xref:System.ComponentModel.BindingList%601>, a. Wenn Sie ein erweitertes Szenario und Ihre eigene Auflistung implementieren möchten, erwägen Sie die Verwendung <xref:System.Collections.IList>, dem bietet es sich um einer nicht generische Auflistung von Objekten, die durch den Index und somit die beste Leistung einzeln zugegriffen werden kann.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>Auflistungsansichten  
 Sobald Ihre <xref:System.Windows.Controls.ItemsControl> gebunden an eine datenauflistung, Sie sollten zu sortieren, filtern oder Gruppieren der Daten ist. Zu diesem Zweck verwenden Sie Auflistungsansichten, bei denen Klassen handelt, implementieren die <xref:System.ComponentModel.ICollectionView> Schnittstelle.  
  
  
#### <a name="what-are-collection-views"></a>Was sind Auflistungsansichten?  
 Eine Auflistungsansicht fungiert als Ebene über der Bindungsquellauflistung, in der Sie mit Sortier-, Filter- und Gruppierungsabfragen navigieren und die jeweilige Quellauflistung anzeigen können, ohne die zugrunde liegende Quellauflistung selbst ändern zu müssen. Eine Auflistungsansicht stellt außerdem einen Zeiger auf das aktuelle Element in der Auflistung zur Verfügung. Wenn die quellauflistung implementiert die <xref:System.Collections.Specialized.INotifyCollectionChanged> Schnittstelle, die Änderungen, die ausgelöst wird, indem die <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> Ereignis an die Ansichten weitergegeben werden.  
  
 Da in Ansichten die zugrunde liegenden Quellauflistungen nicht geändert werden, können einer Quellauflistung mehrere Ansichten zugeordnet sein. Angenommen, Sie verfügen über eine Auflistung von *Task*-Objekten. Mithilfe von Ansichten können Sie dieselben Daten auf verschiedene Weise anzeigen. Beispielsweise können Sie links auf der Seite Aufgaben nach Priorität und rechts nach Bereich sortieren.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>Erstellen einer Ansicht  
 Eine Möglichkeit, eine Ansicht zu erstellen und zu verwenden, besteht darin, das Ansichtsobjekt direkt zu instanziieren und dann als Bindungsquelle zu verwenden. Betrachten Sie z. B. die Anwendung [Demo für die Datenbindung](https://go.microsoft.com/fwlink/?LinkID=163703), die im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) gezeigt wird. Die Anwendung implementiert wird, dass die <xref:System.Windows.Controls.ListBox> bindet an eine Ansicht über die Datensammlung anstelle der Erfassung direkt. Das folgende Beispiel wird aus der [Demo für die Datenbindung-Anwendung](https://go.microsoft.com/fwlink/?LinkID=163703) extrahiert. Die <xref:System.Windows.Data.CollectionViewSource> -Klasse ist die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Proxy einer Klasse, die von erbt <xref:System.Windows.Data.CollectionView>. In diesem Beispiel ist die <xref:System.Windows.Data.CollectionViewSource.Source%2A> der Ansicht gebunden ist die *AuctionItems* Auflistung (des Typs <xref:System.Collections.ObjectModel.ObservableCollection%601>) des aktuellen Anwendungsobjekts.  
  
 [!code-xaml[DataBindingLab#WindowResources1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 Die Ressource *ListingDataView* dient dann als Bindungsquelle für Elemente in der Anwendung, z. B. die <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Um eine andere Ansicht für dieselbe Sammlung zu erstellen, können Sie erstellen Sie eine weitere <xref:System.Windows.Data.CollectionViewSource> -Instanz, und weisen Sie ihm einen anderen `x:Key` Name.  
  
 Die folgende Tabelle zeigt, welche Ansichtsdatentypen als Standardauflistungsansicht an oder von erstellte <xref:System.Windows.Data.CollectionViewSource> basierend auf dem Quellauflistungstyp.  
  
|Quellauflistungstyp|Auflistungsansichtstyp|Hinweise|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|Ein interner Typ basierend auf <xref:System.Windows.Data.CollectionView>|Kann Elemente nicht gruppieren.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Am schnellsten.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>Verwenden einer Standardansicht  
 Die Angabe einer Auflistungsansicht als Bindungsquelle ist eine Möglichkeit, eine Auflistungsansicht zu erstellen und zu verwenden. WPF erstellt außerdem eine Standardauflistungsansicht für jede als Bindungsquelle verwendete Auflistung. Bei der direkten Bindung an eine Auflistung bindet WPF an die Standardansicht der Auflistung. Diese Standardansicht wird von allen Bindungen an diese Auflistung gemeinsam verwendet, sodass eine Änderung an der Standardansicht durch ein gebundenes Steuerelement oder Code, z. B. Sortierung oder eine Änderung des aktuellen Elementzeigers (dies wird zu einem späteren Zeitpunkt erläutert), sich auf alle anderen Bindungen an dieselbe Auflistung auswirkt.  
  
 Rufen Sie die Standardansicht, die Sie mit der <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> Methode. Ein Beispiel finden Sie unter [Abrufen der Standardansicht einer Datenauflistung](how-to-get-the-default-view-of-a-data-collection.md).  
  
##### <a name="collection-views-with-adonet-datatables"></a>Auflistungsansichten mit ADO.NET-Datentabellen  
 Zur Verbesserung der Leistung der Auflistung Ansichten für ADO.NET <xref:System.Data.DataTable> oder <xref:System.Data.DataView> Objekten delegieren, Sortierung und Filterung an die <xref:System.Data.DataView>. So wird die Sortierung und Filterung von allen Auflistungsansichten der Datenquelle gemeinsam verwendet. Um jede Auflistungsansicht, Sortierung und Filterung zu aktivieren, initialisieren Sie jede Auflistungsansicht mit eigenem <xref:System.Data.DataView> Objekt.  
  
#### <a name="sorting"></a>Sortieren  
 Wie bereits erwähnt, können mit Ansichten Sortierreihenfolgen auf Auflistungen angewendet werden. Da sie in der zugrunde liegenden Auflistung vorhanden sind, haben die Daten möglicherweise eine relevante inhärente Reihenfolge oder nicht. Die Ansicht der Auflistung ermöglicht Ihnen das Festlegen einer Reihenfolge oder das Ändern der Standardreihenfolge, je nachdem, welche Vergleichskriterien Sie angeben. Da es sich um eine clientbasierte Ansicht der Daten handelt, besteht ein übliches Szenario darin, dass der Benutzer Spalten mit Tabellendaten nach dem Wert sortiert, dem die Spalte entspricht. Mithilfe von Ansichten kann diese benutzerdefinierte Sortierung angewendet werden, ohne die zugrunde liegende Auflistung ändern oder den Auflistungsinhalt erneut abfragen zu müssen. Ein Beispiel finden Sie unter [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 Das folgende Beispiel zeigt die Sortierlogik des der "Sort by Category and Date" <xref:System.Windows.Controls.CheckBox> der Anwendung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in die [Was ist Datenbindung?](#what_is_data_binding) Abschnitt:  
  
 [!code-csharp[DataBindingLab#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>Filtern  
 Ansichten können auch einen Filter auf eine Auflistung anwenden. Dies bedeutet, dass in der Auflistung zwar ein Element vorhanden sein kann, in dieser bestimmten Ansicht jedoch nur eine bestimmte Teilmenge der gesamten Auflistung angezeigt werden soll. Sie können die Daten nach einer Bedingung filtern. Beispielsweise erfolgt wie von der Anwendung in der [Was ist Datenbindung?](#what_is_data_binding) im Abschnitt "Show only Bargains" <xref:System.Windows.Controls.CheckBox> enthält die Logik, um Elemente zu filtern, die $25 oder mehr Kosten. Der folgende Code wird ausgeführt, um *ShowOnlyBargainsFilter* als die <xref:System.Windows.Data.CollectionViewSource.Filter> Ereignishandler beim, <xref:System.Windows.Controls.CheckBox> ausgewählt ist:  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Die *ShowOnlyBargainsFilter*-Ereignishandler hat folgende Implementierung:  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Wenn Sie eine der verwenden die <xref:System.Windows.Data.CollectionView> direkt anstelle von Klassen <xref:System.Windows.Data.CollectionViewSource>, verwenden Sie die <xref:System.Windows.Data.CollectionView.Filter%2A> Eigenschaft zum Angeben eines Rückrufs. Ein Beispiel finden Sie unter [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md).  
  
#### <a name="grouping"></a>Gruppieren  
 Mit Ausnahme der internen Klasse zur Ansicht eine <xref:System.Collections.IEnumerable> Auflistung unterstützen alle Auflistungsansichten Gruppierungsfunktionen, die dem Benutzer ermöglicht, die die Auflistung in der Auflistungsansicht in logische Gruppen unterteilen. Die Gruppen können explizit sein, wobei Benutzer eine Liste von Gruppen angeben. Sie können auch implizit sein, wobei die Gruppen dynamisch in Abhängigkeit von den Daten generiert werden.  
  
 Das folgende Beispiel zeigt die Logik der "Group by Category" <xref:System.Windows.Controls.CheckBox>:  
  
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
 Das Konzept eines aktuellen Elements ist nicht nur hilfreich, um durch Elemente in einer Auflistung zu navigieren, sondern auch für das Szenario einer Master-Detail-Bindung. Betrachten Sie wieder die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung, die im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) verwendet wird. In dieser Anwendung wird die Auswahl in der <xref:System.Windows.Controls.ListBox> bestimmt den Inhalt, dargestellt der <xref:System.Windows.Controls.ContentControl>. Ausgedrückt in eine andere Möglichkeit, wenn eine <xref:System.Windows.Controls.ListBox> Element ausgewählt ist, die <xref:System.Windows.Controls.ContentControl> zeigt die Details des ausgewählten Elements.  
  
 Sie können das Master-Detail-Szenario auch einfach dadurch implementieren, dass mindestens zwei Steuerelemente an dieselbe Ansicht gebunden sind. Im folgenden Beispiel aus der [Demo für die Datenbindung](https://go.microsoft.com/fwlink/?LinkID=163703) zeigt das Markup der der <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.ContentControl> Sie in der Anwendung finden Sie unter [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in die [Was ist Datenbindung?](#what_is_data_binding) Abschnitt:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Beachten Sie, dass beide Steuerelemente an dieselbe Quelle gebunden sind, und zwar die statische *listingDataView*-Ressource (siehe die Definition dieser Ressource im Abschnitt [Erstellen einer Ansicht](#how_to_create_a_view)). Dies funktioniert, da bei der ein Singleton-Objekt (die <xref:System.Windows.Controls.ContentControl> in diesem Fall) gebunden ist, eine Auflistungsansicht automatisch bindet an die <xref:System.Windows.Data.CollectionView.CurrentItem%2A> der Ansicht. Beachten Sie, dass <xref:System.Windows.Data.CollectionViewSource> -Objekte Währung und Auswahl automatisch zu synchronisieren. Wenn Ihr Listensteuerelement, nicht gebunden ist eine <xref:System.Windows.Data.CollectionViewSource> Objekt wie in diesem Beispiel ist, dann Sie festlegen müssen seiner <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` damit dies funktioniert.  
  
 Weitere Beispiele finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) und [Verwenden des Master/Detail-Musters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Ihnen ist vielleicht aufgefallen, dass im vorherigen Beispiel eine Vorlage verwendet wird. In der Tat die Daten werden nicht angezeigt wie wir, ohne die Verwendung von Vorlagen möchten (explizit verwendet, durch die <xref:System.Windows.Controls.ContentControl> und die andere implizit von der <xref:System.Windows.Controls.ListBox>). Im nächsten Abschnitt beschäftigen wir uns mit Datenvorlagen.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>Datenvorlagen  
 Ohne Datenvorlagen würde die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung im Abschnitt [Was ist Datenbindung?](#what_is_data_binding) wie folgt aussehen:  
  
 ![Demobeispiel für Datenbindung ohne Datenvorlagen](./media/data-binding-overview/data-binding-demo-templates.png)  
  
 Wie im Beispiel im vorherigen Abschnitt gezeigt sowohl die <xref:System.Windows.Controls.ListBox> Steuerelement und die <xref:System.Windows.Controls.ContentControl> gebunden sind, um das gesamte Objekt (oder genauer gesagt: die Ansicht Auflistungsobjekts) von *AuctionItem*s. Ohne spezielle Vorgehensweise beim Anzeigen der Datensammlung, das die der <xref:System.Windows.Controls.ListBox> eine Zeichenfolgendarstellung der einzelnen Objekte in der zugrunde liegenden Auflistung anzeigt und die <xref:System.Windows.Controls.ContentControl> angezeigt, eine Zeichenfolgendarstellung für das Objekt, das es gebunden ist.  
  
 Um dieses Problem zu beheben, die Anwendung definiert <xref:System.Windows.DataTemplate>s. Wie im Beispiel im vorherigen Abschnitt gezeigt die <xref:System.Windows.Controls.ContentControl> verwendet explizit den *DetailsProductListingTemplate*<xref:System.Windows.DataTemplate>. Die <xref:System.Windows.Controls.ListBox> -Steuerelement verwendet implizit folgende <xref:System.Windows.DataTemplate> beim Anzeigen der *AuctionItem* Objekte in der Auflistung:  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 Mit der Verwendung dieser beiden <xref:System.Windows.DataTemplate>s, die resultierende Benutzeroberfläche ist dargestellt, der [Was ist Datenbindung?](#what_is_data_binding) Abschnitt. Wie Sie in dieser bildschirmabbildung sehen können, neben ermöglicht werden die Daten in die Steuerelemente <xref:System.Windows.DataTemplate>s können Sie ansprechende Visualisierungen für Ihre Daten zu definieren. Z. B. <xref:System.Windows.DataTrigger>s werden verwendet, in der obigen <xref:System.Windows.DataTemplate> , damit *AuctionItem*mit *SpecialFeatures* Wert *markieren* angezeigt werden sollen, mit einer orangefarbenen Rahmen und einen Stern.  
  
 Weitere Informationen zu Datenvorlagen finden Sie in der [Übersicht über Datenvorlagen](data-templating-overview.md).  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>Datenvalidierung  
  
 Die meisten Anwendungen, bei denen Benutzereingaben erfolgen, benötigen Validierungslogik, um sicherzustellen, dass der Benutzer die erwarteten Informationen eingegeben hat. Die Validierungsprüfungen können auf Typ, Bereich, Format oder anderen anwendungsspezifischen Anforderungen basieren. In diesem Abschnitt wird erklärt, wie Datenvalidierung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funktioniert.  
  
### <a name="associating-validation-rules-with-a-binding"></a>Zuordnen von Validierungsregeln zu einer Bindung  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Datenbindungsmodell ermöglicht Ihnen die Zuordnung <xref:System.Windows.Data.Binding.ValidationRules%2A> mit Ihrem <xref:System.Windows.Data.Binding> Objekt. Z. B. im folgenden Beispiel wird eine <xref:System.Windows.Controls.TextBox> auf eine Eigenschaft mit dem Namen `StartPrice` und fügt eine <xref:System.Windows.Controls.ExceptionValidationRule> -Objekt an die <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> Eigenschaft.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 Ein <xref:System.Windows.Controls.ValidationRule> -Objekt überprüft, ob der Wert einer Eigenschaft gültig ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hat die folgenden zwei Arten von integrierten <xref:System.Windows.Controls.ValidationRule> Objekte:  
  
-   Ein <xref:System.Windows.Controls.ExceptionValidationRule> überprüft, ob während der Aktualisierung der Bindungsquelleneigenschaft ausgelöste Ausnahmen. Im vorherigen Beispiel ist `StartPrice` eine ganze Zahl. Wenn der Benutzer einen Wert eingibt, der nicht in eine ganze Zahl konvertiert werden kann, wird eine Ausnahme ausgelöst, wodurch die Bindung als ungültig markiert wird. Eine alternative Syntax zum Festlegen der <xref:System.Windows.Controls.ExceptionValidationRule> explizit besteht darin, die <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> Eigenschaft, um `true` auf Ihre <xref:System.Windows.Data.Binding> oder <xref:System.Windows.Data.MultiBinding> Objekt.  
  
-   Ein <xref:System.Windows.Controls.DataErrorValidationRule> -Objekt überprüft, ob Fehler, die von Objekten ausgelöst werden, die implementieren die <xref:System.ComponentModel.IDataErrorInfo> Schnittstelle. Ein Beispiel für die Verwendung dieser Validierungsregel, finden Sie unter <xref:System.Windows.Controls.DataErrorValidationRule>. Eine alternative Syntax zum Festlegen der <xref:System.Windows.Controls.DataErrorValidationRule> explizit besteht darin, die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> Eigenschaft, um `true` auf Ihre <xref:System.Windows.Data.Binding> oder <xref:System.Windows.Data.MultiBinding> Objekt.  
  
 Sie können auch eigene Validierungsregeln erstellen, durch Ableiten von der <xref:System.Windows.Controls.ValidationRule> -Klasse und Implementieren der <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode. Das folgende Beispiel zeigt die Regel ein, die die *Add Product Listing* "Start Date" <xref:System.Windows.Controls.TextBox> aus der [Was ist Datenbindung?](#what_is_data_binding) Abschnitt:  
  
 [!code-csharp[DataBindingLab#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 Die *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> verwendet diese *FutureDateRule*, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[DataBindingLab#CustomValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Beachten Sie, dass die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, die Bindungs-Engine aktualisiert dem Quellwert bei jeder Tastatureingabe und überprüft auch daher alle Regeln in der <xref:System.Windows.Data.Binding.ValidationRules%2A> -Auflistung bei jeder Tastatureingabe. Dies wird im Abschnitt zum Validierungsprozess näher erläutert.  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>Bereitstellen von visuellem Feedback  
 Wenn der Benutzer einen ungültigen Wert eingibt, kann es sinnvoll sein, Feedback zum Fehler auf der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung zu geben. Eine Möglichkeit zum Bereitstellen von Feedback besteht darin, legen Sie die <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> angefügte Eigenschaft auf eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate>. Wie im vorherigen Unterabschnitt gezeigt die *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> verwendet eine <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> namens *ValidationTemplate*. Im folgenden Beispiel sehen Sie die Definition von *validationTemplate*:  
  
 [!code-xaml[DataBindingLab#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 Die <xref:System.Windows.Controls.AdornedElementPlaceholder> Element gibt an, in dem das Steuerelement platziert werden soll.  
  
 Darüber hinaus können Sie auch eine <xref:System.Windows.Controls.ToolTip> um die Fehlermeldung anzuzeigen. Sowohl die *StartDateEntryForm* und *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>verwenden das Format *TextStyleTextBox*, erstellt eine <xref:System.Windows.Controls.ToolTip> , Zeigt die Fehlermeldung an. Im folgenden Beispiel wird die Definition von *textStyleTextBox* dargestellt. Die angefügte Eigenschaft <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> ist `true` Wenn mindestens eine der Bindungen in den Eigenschaften des gebundenen Elements fehlerhaft sind.  
  
 [!code-xaml[DataBindingLab#14](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 Mit dem benutzerdefinierten <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und <xref:System.Windows.Controls.ToolTip>, *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> sieht wie folgt aus, wenn ein Überprüfungsfehler vorhanden ist:  
  
 ![Fehler bei der Datenbindungsvalidierung](./media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 Wenn Ihre <xref:System.Windows.Data.Binding> über zugeordnete Validierungsregeln, aber nicht angeben einer <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> für das gebundene Steuerelement ein, den Standardwert <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> wird verwendet, um Benutzer zu benachrichtigen, wenn ein Überprüfungsfehler vorliegt. Der Standardwert <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> ist eine Steuerelementvorlage, die einen roten Rahmen in der Adornerebene definiert. Mit der standardmäßigen <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und <xref:System.Windows.Controls.ToolTip>, wird die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von der *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> sieht wie folgt aus, wenn ein Überprüfungsfehler vorhanden ist:  
  
 ![Fehler bei der Datenbindungsvalidierung](./media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 Ein Beispiel zum Bereitstellen von Logik zum Validieren aller Steuerelemente in einem Dialogfeld finden Sie im Abschnitt zu benutzerdefinierten Dialogfeldern in der [Übersicht über Dialogfelder](../app-development/dialog-boxes-overview.md).  
  
### <a name="validation-process"></a>Validierungsprozess  
 Eine Validierung erfolgt normalerweise, wenn der Wert eines Ziels an die Bindungsquelleigenschaft übergeben wird. In diesem Fall auf <xref:System.Windows.Data.BindingMode.TwoWay> und <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen. Wie bereits ausgeführt, wodurch wird eine Aktualisierung einer Quelle hängt vom Wert von der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft, wie in beschrieben die [Quellaktualisierungen ausgelöst](#what_triggers_source_updates) Abschnitt.  
  
 Im Folgenden wird der Prozess der *Validierung* beschrieben. Beachten Sie, dass der Prozess beim Auftreten eines Validierungs- oder anderen Fehlers in seinem Verlauf angehalten wird.  
  
1.  Die Bindungs-Engine überprüft, ob alle benutzerdefinierten <xref:System.Windows.Controls.ValidationRule> Objekte definiert sind, dessen <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> nastaven NA hodnotu <xref:System.Windows.Controls.ValidationStep.RawProposedValue> , <xref:System.Windows.Data.Binding>, in diesem Fall ruft die <xref:System.Windows.Controls.ValidationRule.Validate%2A> -Methode für jede <xref:System.Windows.Controls.ValidationRule> erst beim Ausführen eines einen Fehler oder bis alle Regeln erfolgreich.  
  
2.  Anschließend ruft die Bindungs-Engine den Konverter auf, sofern vorhanden.  
  
3.  Wenn der Konverter erfolgreich ist, wird die Bindungs-Engine überprüft, ob benutzerdefinierte <xref:System.Windows.Controls.ValidationRule> Objekte definiert sind, dessen <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> nastaven NA hodnotu <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> , <xref:System.Windows.Data.Binding>, in diesem Fall ruft die <xref:System.Windows.Controls.ValidationRule.Validate%2A> -Methode für jede <xref:System.Windows.Controls.ValidationRule> , bei dem <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> bis einer davon ein Fehler ausgeführt wird oder alle Regeln erfolgreich.  
  
4.  Die Bindungs-Engine legt die Quelleigenschaft fest.  
  
5.  Die Bindungs-Engine überprüft, ob alle benutzerdefinierten <xref:System.Windows.Controls.ValidationRule> Objekte definiert sind, dessen <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> nastaven NA hodnotu <xref:System.Windows.Controls.ValidationStep.UpdatedValue> , <xref:System.Windows.Data.Binding>, in diesem Fall ruft die <xref:System.Windows.Controls.ValidationRule.Validate%2A> -Methode für jede <xref:System.Windows.Controls.ValidationRule> , bei dem <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt <xref:System.Windows.Controls.ValidationStep.UpdatedValue> bis einer davon ein Fehler ausgeführt wird oder alle Regeln erfolgreich. Wenn eine <xref:System.Windows.Controls.DataErrorValidationRule> bezieht sich auf einer Bindung und die zugehörige <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> auf den Standardwert festgelegt ist <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, <xref:System.Windows.Controls.DataErrorValidationRule> an diesem Punkt aktiviert ist. Dies ist auch der Punkt bei Bindungen, die die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> festgelegt `true` überprüft werden.  
  
6.  Die Bindungs-Engine überprüft, ob alle benutzerdefinierten <xref:System.Windows.Controls.ValidationRule> Objekte definiert sind, dessen <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> nastaven NA hodnotu <xref:System.Windows.Controls.ValidationStep.CommittedValue> , <xref:System.Windows.Data.Binding>, in diesem Fall ruft die <xref:System.Windows.Controls.ValidationRule.Validate%2A> -Methode für jede <xref:System.Windows.Controls.ValidationRule> , bei dem <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt <xref:System.Windows.Controls.ValidationStep.CommittedValue> bis einer davon ein Fehler ausgeführt wird oder alle Regeln erfolgreich.  
  
 Wenn eine <xref:System.Windows.Controls.ValidationRule> übergibt die nicht zu einem beliebigen Zeitpunkt während dieses Prozesses, erstellt die Bindungs-Engine eine <xref:System.Windows.Controls.ValidationError> -Objekt und fügt es der <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> -Auflistung des gebundenen Elements. Bevor Sie die Bindung-Engine ausgeführt wird die <xref:System.Windows.Controls.ValidationRule> Objekte im Rahmen eines Schritts entfernt alle <xref:System.Windows.Controls.ValidationError> , hinzugefügt wurde die <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> angefügte Eigenschaft des gebundenen Elements während dieses Schritts. Z. B. wenn ein <xref:System.Windows.Controls.ValidationRule> , deren <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> nastaven NA hodnotu <xref:System.Windows.Controls.ValidationStep.UpdatedValue> fehlgeschlagen ist, wird das nächste Mal den Prozess der Validierung auftritt, die Bindungs-Engine entfernt werden, die <xref:System.Windows.Controls.ValidationError> unmittelbar vor dem Aufruf <xref:System.Windows.Controls.ValidationRule> , bei dem <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> festgelegt <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 Wenn <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> ist nicht leer ist, die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft des Elements nastaven NA hodnotu `true`. Auch wenn die <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> Eigenschaft der <xref:System.Windows.Data.Binding> nastaven NA hodnotu `true`, löst die Bindungs-Engine die <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> angefügtes Ereignis für das Element.  
  
 Beachten Sie auch, die eine Übertragung gültigen Wert in beide Richtungen (Ziel zu Quelle oder Ziel) Löscht die <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> angefügte Eigenschaft.  
  
 Die Bindung verfügt entweder ein <xref:System.Windows.Controls.ExceptionValidationRule> zugeordnet, oder Sie haben die <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> -Eigenschaftensatz auf `true` und die Bindungs-Engine eine Ausnahme wird ausgelöst, wenn die Bindungs-Engine die Quelle festlegt, überprüft werden, um festzustellen, ob eine <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>. Sie haben die Möglichkeit zum Verwenden der <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> Rückruf, der einen benutzerdefinierten Handler zum Behandeln von Ausnahmen angeben. Wenn ein <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> nicht angegeben ist, auf die <xref:System.Windows.Data.Binding>, erstellt die Bindungs-Engine eine <xref:System.Windows.Controls.ValidationError> mit der Ausnahme und fügt es der <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> -Auflistung des gebundenen Elements.  
  
## <a name="debugging-mechanism"></a>Debugverfahren  
 Sie können die angefügte Eigenschaft festlegen <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> für ein Objekt Datenbindung, um Informationen über den Status einer bestimmten Bindung zu erhalten.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Neues in WPF Version 4.5](../getting-started/whats-new.md)
- [Binden an die Ergebnisse einer LINQ-Abfrage](how-to-bind-to-the-results-of-a-linq-query.md)
- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [Demo der Datenbindung](https://go.microsoft.com/fwlink/?LinkID=163703)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
- [Binden an eine ADO.NET-Datenquelle](how-to-bind-to-an-ado-net-data-source.md)
