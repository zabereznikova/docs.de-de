---
title: Übersicht über Datenvorlagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: 556ce7b42f13d7c5ba7fba36b09277cda9bcae5d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400656"
---
# <a name="data-templating-overview"></a>Übersicht über Datenvorlagen
Mithilfe des WPF-Datenvorlagenmodells können Sie die Darstellung Ihrer Daten flexibel definieren. WPF-Steuerelemente verfügen über integrierte Funktionen, die die Anpassung der Datendarstellung unterstützen. In diesem Thema wird zunächst veranschaulicht, wie <xref:System.Windows.DataTemplate> Sie einen definieren und dann weitere Datenvorlagen Features einführen, wie z. b. die Auswahl von Vorlagen auf der Grundlage von benutzerdefinierter Logik und die Unterstützung für die Anzeige hierarchischer Daten.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Der Schwerpunkt dieses Themas liegt auf Datenvorlagenfeatures. Es bietet keine Einführung in Datenbindungskonzepte. Informationen zu grundlegende Datenbindungskonzepten finden Sie in der [Übersicht über Datenbindung](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate>dient zur Darstellung von Daten und ist eines der zahlreichen Features, die vom WPF-Format und-Vorlagen Modell bereitgestellt werden. Eine Einführung in das WPF-Format und das Vorlagen Modell, wie z. b. das <xref:System.Windows.Style> verwenden eines zum Festlegen von Eigenschaften für Steuerelemente, finden Sie im Thema Formatieren [und](../controls/styling-and-templating.md) Vorlagen.  
  
 Außerdem ist es wichtig zu verstehen `Resources`, was im Wesentlichen die Möglichkeit zur wiederverwendbaren Aktivierung von Objekten <xref:System.Windows.Style> wie und <xref:System.Windows.DataTemplate> ist. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Grundlegendes zu Datenvorlagen  
  
 Um zu veranschaulichen <xref:System.Windows.DataTemplate> , warum wichtig ist, sehen wir uns ein Beispiel für eine Datenbindung an. In diesem Beispiel gibt es eine <xref:System.Windows.Controls.ListBox> , die an eine Liste von `Task` -Objekten gebunden ist. Jedes `Task`-Objekt verfügt über `TaskName` (string), `Description` (string), `Priority` (int) und eine Eigenschaft des Typs `TaskType`, wobei es sich um ein `Enum` mit dem mit den Werten `Home` und `Work` handelt.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Ohne „DataTemplate“  
 Ohne eine <xref:System.Windows.DataTemplate>sieht unser <xref:System.Windows.Controls.ListBox> aktuell wie folgt aus:  
  
 ![Screenshot: Beispiel für Daten] Vorlagen (./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Dies geschieht, wenn Sie ohne bestimmte Anweisungen standardmäßig aufrufen <xref:System.Windows.Controls.ListBox> `ToString` , wenn Sie versuchen, die Objekte in der Auflistung anzuzeigen. Wenn das `Task` -Objekt die `ToString` -Methode überschreibt, wird <xref:System.Windows.Controls.ListBox> daher die Zeichen folgen Darstellung der einzelnen Quell Objekte in der zugrunde liegenden Auflistung angezeigt.  
  
 Wenn z. B. die `Task`-Klasse auf diese Weise die `ToString`-Methode überschreibt, wobei `name` das Feld für die `TaskName`-Eigenschaft darstellt:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Das <xref:System.Windows.Controls.ListBox> sieht dann wie folgt aus:  
  
 ![Screenshot: Beispiel für Daten] Vorlagen (./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Das ist jedoch einschränkend und unflexibel. Zudem können Sie beim Binden an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten den `ToString`-Wert nicht überschreiben.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definieren einer einfachen Datenvorlage  
 Die Lösung besteht darin, eine <xref:System.Windows.DataTemplate>zu definieren. Eine Möglichkeit besteht darin, die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> -Eigenschaft <xref:System.Windows.Controls.ListBox> von auf einen <xref:System.Windows.DataTemplate>festzulegen. Das, was Sie in <xref:System.Windows.DataTemplate> der angeben, wird zur visuellen Struktur des Datenobjekts. Folgendes <xref:System.Windows.DataTemplate> ist ziemlich einfach. Wir geben Ihnen Anweisungen, dass jedes Element als drei <xref:System.Windows.Controls.TextBlock> Elemente innerhalb einer <xref:System.Windows.Controls.StackPanel>angezeigt wird. Jedes <xref:System.Windows.Controls.TextBlock> -Element ist an eine Eigenschaft `Task` der-Klasse gebunden.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Die zugrunde liegenden Daten für die Beispiele in diesem Thema sind eine Auflistung von CLR-Objekten. Wenn Sie eine Bindung an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten vornehmen, stimmen die grundsätzlichen Konzepte überein, es besteht jedoch ein kleiner syntaktischer Unterschied. Beispielsweise würden Sie anstelle von `Path=TaskName`auf `@TaskName` festlegen <xref:System.Windows.Data.Binding.XPath%2A> (wenn `TaskName` ein Attribut [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Ihres Knotens ist).  
  
 <xref:System.Windows.Controls.ListBox> Nun sieht das wie folgt aus:  
  
 ![Screenshot: Beispiel für Daten] Vorlagen (./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Erstellen der Datenvorlage als Ressource  
 Im obigen Beispiel haben wir den <xref:System.Windows.DataTemplate> Inline definiert. Es ist jedoch üblicher, diese im Ressourcenabschnitt zu definieren, damit sie wiederverwendet werden kann, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Sie können `myTaskTemplate` nun als Ressource verwenden, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Da `myTaskTemplate` eine Ressource ist, können Sie Sie jetzt für andere Steuerelemente verwenden, die über eine Eigenschaft verfügen <xref:System.Windows.DataTemplate> , die einen Typ annimmt. Wie oben gezeigt, ist <xref:System.Windows.Controls.ItemsControl> es für-Objekte, <xref:System.Windows.Controls.ListBox>wie z. b <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> ., die-Eigenschaft. Für <xref:System.Windows.Controls.ContentControl> -Objekte ist es die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> -Eigenschaft.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Die DataType-Eigenschaft  
 Die <xref:System.Windows.DataTemplate> -Klasse verfügt <xref:System.Windows.DataTemplate.DataType%2A> über eine-Eigenschaft, die der <xref:System.Windows.Style.TargetType%2A> -Eigenschaft der <xref:System.Windows.Style> -Klasse sehr ähnlich ist. Daher können Sie wie folgt vorgehen `x:Key` , anstatt <xref:System.Windows.DataTemplate> ein für die im obigen Beispiel anzugeben:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Dies <xref:System.Windows.DataTemplate> wird automatisch auf alle `Task` Objekte angewendet. Beachten Sie, dass die `x:Key` in diesem Fall implizit festgelegt wird. Wenn Sie diesem <xref:System.Windows.DataTemplate> also einen `x:Key` -Wert zuweisen, überschreiben Sie den impliziten `x:Key` , und <xref:System.Windows.DataTemplate> der wird nicht automatisch angewendet.  
  
 Wenn Sie ein <xref:System.Windows.Controls.ContentControl> an eine Auflistung von `Task` -Objekten binden, verwendet <xref:System.Windows.Controls.ContentControl> die oben <xref:System.Windows.DataTemplate> nicht automatisch. Dies liegt daran, dass die Bindung <xref:System.Windows.Controls.ContentControl> für eine weitere Informationen erfordert, um zu unterscheiden, ob Sie eine Bindung an eine gesamte Auflistung oder die einzelnen Objekte vornehmen möchten. <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Controls.ContentControl> `/`Wenn Sie die Auswahl <xref:System.Windows.Controls.ItemsControl> eines Typs nachverfolgen, können Sie die-Eigenschaft der Bindung auf "" festlegen, um anzugeben, dass Sie am aktuellen Element interessiert sind. <xref:System.Windows.Controls.ContentControl> Ein Beispiel finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). Andernfalls müssen Sie <xref:System.Windows.DataTemplate> explizit angeben, indem Sie die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> -Eigenschaft festlegen.  
  
 Die <xref:System.Windows.DataTemplate.DataType%2A> -Eigenschaft ist besonders nützlich, wenn Sie <xref:System.Windows.Data.CompositeCollection> über eine von unterschiedlichen Typen von Datenobjekten verfügen. Ein Beispiel finden Sie unter [Implementieren von CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Hinzufügen weiterer Elemente zu DataTemplate  
 Im Moment werden die Daten mit den notwendigen Informationen angezeigt, es sind aber definitiv noch Verbesserungen möglich. Lassen Sie uns die Präsentation verbessern, indem <xref:System.Windows.Controls.Border>Sie ein <xref:System.Windows.Controls.Grid>-, ein <xref:System.Windows.Controls.TextBlock> -Element und einige Elemente hinzufügen, die die angezeigten Daten beschreiben.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Der folgende Screenshot zeigt den <xref:System.Windows.Controls.ListBox> , der geändert <xref:System.Windows.DataTemplate>wurde:  
  
 ![Screenshot: Beispiel für Daten] Vorlagen (./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Wir können auf <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> festlegen <xref:System.Windows.HorizontalAlignment.Stretch> , um sicherzustellen, dass die Breite der Elemente den gesamten Speicherplatz einnimmt: <xref:System.Windows.Controls.ListBox>  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Wenn die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> -Eigenschaft auf <xref:System.Windows.HorizontalAlignment.Stretch>festgelegt <xref:System.Windows.Controls.ListBox> ist, sieht nun wie folgt aus:  
  
 ![Screenshot: Beispiel für Daten] Vorlagen (./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Anwenden von Eigenschaftswerten mit DataTrigger  
 Aus der aktuellen Darstellung geht nicht hervor, ob es sich bei einer `Task` um eine private oder um eine arbeitsbezogene Aufgabe handelt. Beachten Sie, dass das `Task`-Objekt über eine `TaskType`-Eigenschaft des Typs `TaskType` verfügt, die eine Enumeration mit den Werten `Home` und `Work` ist.  
  
 <xref:System.Windows.DataTrigger> Im folgenden Beispiel <xref:System.Windows.Controls.Border.BorderBrush%2A> legt den des Elements mit dem Namen `border` auf `Yellow` fest, wenn die `TaskType` -Eigenschaft `TaskType.Home`ist.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Die Anwendung sieht jetzt folgendermaßen aus. Private Aufgaben werden mit einem gelben Rahmen und Office-Aufgaben mit einem hellblauen Rahmen angezeigt:  
  
 ![Screenshot: Beispiel für Daten] Vorlagen (./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 In diesem Beispiel <xref:System.Windows.DataTrigger> verwendet einen <xref:System.Windows.Setter> , um einen Eigenschafts Wert festzulegen. Die auslöserklassen verfügen <xref:System.Windows.TriggerBase.EnterActions%2A> auch <xref:System.Windows.TriggerBase.ExitActions%2A> über die Eigenschaften und, mit denen Sie eine Reihe von Aktionen starten können, z. b. Animationen. Außerdem gibt es eine <xref:System.Windows.MultiDataTrigger> -Klasse, mit der Sie Änderungen auf der Grundlage mehrerer Daten gebundener Eigenschaftswerte anwenden können.  
  
 Eine alternative Möglichkeit, denselben Effekt zu erzielen, besteht darin, <xref:System.Windows.Controls.Border.BorderBrush%2A> die Eigenschaft an `TaskType` die Eigenschaft zu binden und einen Wert Konverter zu verwenden, um die `TaskType` Farbe auf Grundlage des Werts zurückzugeben. Mit Blick auf die Leistung ist es etwas effizienter, für diesen Effekt einen Konverter zu verwenden. Darüber hinaus bietet die Erstellung eines eigenen Konverters eine höhere Flexibilität, da Sie eine eigene Logik verwenden. Für welches Verfahren Sie sich entscheiden, hängt letztlich vom entsprechenden Szenario und Ihren Vorlieben ab. Weitere Informationen zum Schreiben eines Konverters finden <xref:System.Windows.Data.IValueConverter>Sie unter.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Was gehört in eine DataTemplate?  

Im vorherigen Beispiel haben wir <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate>den--------------<xref:System.Windows.DataTemplate.Triggers%2A> -Eigenschaft veranschaulicht. Der <xref:System.Windows.Setter> des Auslösers legt den Wert einer Eigenschaft eines Elements (das <xref:System.Windows.Controls.Border> -Element <xref:System.Windows.DataTemplate>) fest, das sich innerhalb von befindet. Wenn die Eigenschaften, mit denen Sie `Setters` sich beschäftigen, keine Eigenschaften von Elementen sind, die sich innerhalb des <xref:System.Windows.DataTemplate>aktuellen befinden, ist es möglicherweise besser, die Eigenschaften mithilfe <xref:System.Windows.Style> eines festzulegen, <xref:System.Windows.Controls.ListBoxItem> das für die Klasse gilt (wenn die das Steuerelement, das Sie <xref:System.Windows.Controls.ListBox>binden, ist ein). Wenn Sie z. b. den <xref:System.Windows.Trigger> <xref:System.Windows.UIElement.Opacity%2A> Wert des Elements animieren möchten, wenn ein Mauszeiger auf ein Element zeigt, definieren Sie Trigger innerhalb eines <xref:System.Windows.Controls.ListBoxItem> Stils. Ein Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 Im Allgemeinen sollten Sie Bedenken, dass die <xref:System.Windows.DataTemplate> auf die einzelnen generierten <xref:System.Windows.Controls.ListBoxItem> angewendet wird (Weitere Informationen dazu, wie und wo Sie tatsächlich angewendet werden, finden Sie auf der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Seite.) Ihr <xref:System.Windows.DataTemplate> betrifft nur die Darstellung und Darstellung der Datenobjekte. In den meisten Fällen gehören alle anderen Aspekte der Präsentation, wie z. b. das Aussehen eines Elements, wenn es ausgewählt <xref:System.Windows.Controls.ListBox> wird, oder die Art und Weise, in der die Elemente angeordnet <xref:System.Windows.DataTemplate>werden, nicht zur Definition einer. Ein Beispiel finden Sie im Abschnitt [Formatieren und Erstellen von Vorlagen für ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Auswählen einer DataTemplate anhand von Eigenschaften des Datenobjekts  
 Im Abschnitt [Die DataType-Eigenschaft](#Styling_DataType) wurde erläutert, dass Sie verschiedene Datenvorlagen für verschiedene Datenobjekte definieren können. Dies ist besonders nützlich, wenn Sie über <xref:System.Windows.Data.CompositeCollection> eine von unterschiedlichen Typen oder Sammlungen mit Elementen verschiedener Typen verfügen. Im Abschnitt [Verwenden von DataTriggers zum Anwenden von Eigenschafts Werten](#DataTrigger_to_Apply_Property_Values) wird gezeigt, dass Sie eine <xref:System.Windows.DataTemplate> Auflistung desselben Typs von Datenobjekten erstellen und dann mithilfe von Triggern Änderungen auf der Grundlage der Eigenschaftswerte jedes Datenobjekts anwenden können. Mit Triggern können Sie Eigenschaftswerte anwenden oder Animationen starten, sie verfügen jedoch nicht über die nötige Flexibilität, um die Struktur der Datenobjekte zu rekonstruieren. In einigen Szenarien ist es möglicherweise erforderlich, <xref:System.Windows.DataTemplate> dass Sie eine andere für Datenobjekte erstellen, die denselben Typ aufweisen, aber über unterschiedliche Eigenschaften verfügen.  
  
 Wenn z. B. ein `Task`-Objekt den `Priority`-Wert `1` hat, kann es sinnvoll sein, ihm ein völlig anderes Erscheinungsbild zuzuweisen, um als Warnung zu dienen. In diesem Fall erstellen Sie ein <xref:System.Windows.DataTemplate> -Objekt für die Anzeige der Objekte mit hoher Priorität. `Task` Fügen Sie dem Ressourcenabschnitt <xref:System.Windows.DataTemplate> Folgendes hinzu:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Beachten Sie, dass in <xref:System.Windows.DataTemplate>diesem Beispiel verwendet wird.<xref:System.Windows.FrameworkTemplate.Resources%2A> -Eigenschaft veranschaulicht. Die in diesem Abschnitt definierten Ressourcen werden von den Elementen in der <xref:System.Windows.DataTemplate>gemeinsam genutzt.  
  
 Erstellen Sie eine Unterklasse von <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.DataTemplateSelector> , und überschreiben Sie `Priority` die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> -Methode, um zu bestimmen, welche Logik basierend auf dem Wert des Datenobjekts verwendet werden soll. Im folgenden Beispiel stellt die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> -Methode Logik bereit, um die entsprechende Vorlage basierend auf dem Wert `Priority` der-Eigenschaft zurückzugeben. Die zurück zugebende Vorlage befindet sich in den Ressourcen des umschließenden <xref:System.Windows.Window> -Elements.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Wir können dann den `TaskListDataTemplateSelector` als Ressource deklarieren:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Wenn Sie die Vorlagen Auswahl Ressource verwenden möchten, weisen Sie <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> Sie der- <xref:System.Windows.Controls.ListBox>Eigenschaft von zu. Die <xref:System.Windows.Controls.ListBox> Ruft die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> -Methode der `TaskListDataTemplateSelector` für jedes der Elemente in der zugrunde liegenden Auflistung auf. Beim Aufruf wird das Datenobjekt als Elementparameter übergeben. Der <xref:System.Windows.DataTemplate> , der von der-Methode zurückgegeben wird, wird dann auf das Datenobjekt angewendet.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Wenn die Vorlagen Auswahl vorhanden ist, wird <xref:System.Windows.Controls.ListBox> nun wie folgt angezeigt:  
  
 ![Screenshot: Beispiel für Daten] Vorlagen (./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Damit ist die Erläuterung unseres Beispiels abgeschlossen. Das vollständige Beispiel finden Sie unter [Einführung in das Datenvorlagenbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Formatierung und Vorlagen für ItemsControl  
 Obwohl der <xref:System.Windows.Controls.ItemsControl> nicht der einzige Steuerelement Typ ist, mit dem Sie einen <xref:System.Windows.DataTemplate> mit verwenden können, ist es ein gängiges Szenario, <xref:System.Windows.Controls.ItemsControl> ein an eine Auflistung zu binden. Im Abschnitt [Was gehört zu einem DataTemplate](#what_belongs_in_datatemplate) -Abschnitt wurde erläutert, dass die Definition <xref:System.Windows.DataTemplate> von nur die Darstellung von Daten betreffen sollte. Um zu wissen, wann es nicht für die Verwendung <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ItemsControl>von geeignet ist, ist es wichtig, die unterschiedlichen Stil-und Vorlagen Eigenschaften von zu verstehen. Anhand des folgenden Beispiels soll die jeweilige Funktion dieser Eigenschaften veranschaulicht werden. Der <xref:System.Windows.Controls.ItemsControl> in diesem Beispiel ist an dieselbe `Tasks` Auflistung gebunden wie im vorherigen Beispiel. Zu Demonstrationszwecken werden die Formate und die Vorlagen in diesem Beispiel inline deklariert.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Im Folgenden sehen Sie ein Bildschirmfoto des Beispiels nach dem Rendern:  
  
 ![Bildschirmfoto des ItemsControl-Beispiels](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Beachten Sie, dass Sie anstelle <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>von den <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>verwenden können. Ein Beispiel finden Sie im vorherigen Abschnitt. Ebenso haben Sie die Möglichkeit, <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>anstelle von zu <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>verwenden.  
  
 Zwei weitere Stil bezogene Eigenschaften von, die <xref:System.Windows.Controls.ItemsControl> hier nicht angezeigt werden, sind <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> und <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Unterstützung für hierarchische Daten  
 Bisher haben wir nur erläutert, wie eine einzelne Auflistung gebunden und angezeigt wird. Mitunter kann eine Auflistung auch andere Auflistungen enthalten. Die <xref:System.Windows.HierarchicalDataTemplate> -Klasse ist so konzipiert, dass <xref:System.Windows.Controls.HeaderedItemsControl> Sie mit-Typen verwendet wird, um solche Daten anzuzeigen. Im folgenden Beispiel ist `ListLeagueList` eine Liste von `League`-Objekten. Jedes `League`-Objekt verfügt über einen `Name` und eine Auflistung von `Division`-Objekten. Jede `Division` verfügt über einen `Name` und eine Auflistung von `Team`-Objekten, und `Team`Team-Objekt verfügt über einen `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Das Beispiel zeigt, dass Sie bei Verwendung <xref:System.Windows.HierarchicalDataTemplate>von problemlos Listen Daten anzeigen können, die andere Listen enthalten. Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.  
  
 ![Hierarchcaldatatemplate-Beispiel Bildschirm] Foto (./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Siehe auch

- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [Suchen von Elementen, die mit einer DataTemplate generiert wurden](how-to-find-datatemplate-generated-elements.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../controls/gridview-column-header-styles-and-templates-overview.md)
