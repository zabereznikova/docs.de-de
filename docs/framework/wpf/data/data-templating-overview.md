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
ms.openlocfilehash: 98fff9ba84f386e93549fa94fe84f7b2b0fff5fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097550"
---
# <a name="data-templating-overview"></a>Übersicht über Datenvorlagen
Mithilfe des WPF-Datenvorlagenmodells können Sie die Darstellung Ihrer Daten flexibel definieren. WPF-Steuerelemente verfügen über integrierte Funktionen, die die Anpassung der Datendarstellung unterstützen. In diesem Thema veranschaulicht, wie definieren Sie zuerst eine <xref:System.Windows.DataTemplate> und anschließend werden weitere Datenvorlagenfeatures-vorgestellt, wie z. B. die Auswahl von Vorlagen anhand benutzerdefinierter Logik und die Unterstützung für die Anzeige hierarchischer Daten.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Der Schwerpunkt dieses Themas liegt auf Datenvorlagenfeatures. Es bietet keine Einführung in Datenbindungskonzepte. Informationen zu grundlegende Datenbindungskonzepten finden Sie in der [Übersicht über Datenbindung](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> geht es um die Darstellung von Daten und ist einer der vielen Features des WPF-Stile und Vorlagen-Modells. Eine Einführung in von WPF-Stile und Vorlagen Modells, z. B. wie Sie mit einem <xref:System.Windows.Style> um Eigenschaften für Steuerelemente festlegen zu können, finden Sie unter den [Stile und Vorlagen](../controls/styling-and-templating.md) Thema.  
  
 Darüber hinaus ist es wichtig zu verstehen, `Resources`, die sind im Wesentlichen das, was Objekte ermöglichen, z.B. <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> wiederverwendbarkeit. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Grundlegendes zu Datenvorlagen  
  
 Warum veranschaulicht <xref:System.Windows.DataTemplate> ist wichtig, betrachten wir eines Datenbindungsbeispiels veranschaulicht. In diesem Beispiel haben wir eine <xref:System.Windows.Controls.ListBox> , gebunden ist, um eine Liste der `Task` Objekte. Jedes `Task`-Objekt verfügt über `TaskName` (string), `Description` (string), `Priority` (int) und eine Eigenschaft des Typs `TaskType`, wobei es sich um ein `Enum` mit dem mit den Werten `Home` und `Work` handelt.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Ohne „DataTemplate“  
 Ohne eine <xref:System.Windows.DataTemplate>, unsere <xref:System.Windows.Controls.ListBox> derzeit sieht wie folgt aus:  
  
 ![Daten-beispielscreenshot: Vorlagen](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Was passiert ist, ohne bestimmten Anweisungen, die <xref:System.Windows.Controls.ListBox> durch Aufrufe der standardmäßigen `ToString` beim Versuch, die Objekte in der Auflistung anzuzeigen. Aus diesem Grund Wenn die `Task` -Objekt überschreibt die `ToString` -Methode, und klicken Sie dann die <xref:System.Windows.Controls.ListBox> eine Zeichenfolgendarstellung der einzelnen Quellobjekte in der zugrunde liegenden Auflistung angezeigt.  
  
 Wenn z. B. die `Task`-Klasse auf diese Weise die `ToString`-Methode überschreibt, wobei `name` das Feld für die `TaskName`-Eigenschaft darstellt:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Die <xref:System.Windows.Controls.ListBox> sieht wie folgt aus:  
  
 ![Daten-beispielscreenshot: Vorlagen](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Das ist jedoch einschränkend und unflexibel. Zudem können Sie beim Binden an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten den `ToString`-Wert nicht überschreiben.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definieren einer einfachen Datenvorlage  
 Die Lösung besteht darin, definieren Sie eine <xref:System.Windows.DataTemplate>. Eine Möglichkeit dafür festgelegt ist die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> auf eine <xref:System.Windows.DataTemplate>. Angeben Ihrer <xref:System.Windows.DataTemplate> bilden die visuelle Struktur des Datenobjekts. Die folgenden <xref:System.Windows.DataTemplate> ist recht einfach. Wird werden Anweisungen, die jedes Element als drei wird gewährt <xref:System.Windows.Controls.TextBlock> Elemente innerhalb einer <xref:System.Windows.Controls.StackPanel>. Jede <xref:System.Windows.Controls.TextBlock> Element an eine Eigenschaft gebunden ist die `Task` Klasse.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Bei den zugrunde liegenden Daten für die Beispiele in diesem Thema handelt es sich um eine Auflistung von [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekten. Wenn Sie eine Bindung an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten vornehmen, stimmen die grundsätzlichen Konzepte überein, es besteht jedoch ein kleiner syntaktischer Unterschied. Z. B. statt `Path=TaskName`, legen Sie <xref:System.Windows.Data.Binding.XPath%2A> zu `@TaskName` (Wenn `TaskName` ist ein Attribut des Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Knoten).  
  
 Jetzt unsere <xref:System.Windows.Controls.ListBox> sieht wie folgt aus:  
  
 ![Daten-beispielscreenshot: Vorlagen](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Erstellen der Datenvorlage als Ressource  
 Im obigen Beispiel definierten wir die <xref:System.Windows.DataTemplate> Inline. Es ist jedoch üblicher, diese im Ressourcenabschnitt zu definieren, damit sie wiederverwendet werden kann, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Sie können `myTaskTemplate` nun als Ressource verwenden, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Da `myTaskTemplate` ist eine Ressource, jetzt können Sie sie für andere Steuerelemente, die eine Eigenschaft zu verwenden, übernimmt ein <xref:System.Windows.DataTemplate> Typ. Wie oben gezeigt, für die <xref:System.Windows.Controls.ItemsControl> Objekte, z. B. die <xref:System.Windows.Controls.ListBox>, ist die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft. Für <xref:System.Windows.Controls.ContentControl> -Objekten ist es die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Die DataType-Eigenschaft  
 Die <xref:System.Windows.DataTemplate> -Klasse verfügt über eine <xref:System.Windows.DataTemplate.DataType%2A> -Eigenschaft, die sehr ähnlich ist die <xref:System.Windows.Style.TargetType%2A> Eigenschaft der <xref:System.Windows.Style> Klasse. Aus diesem Grund anstelle einer `x:Key` für die <xref:System.Windows.DataTemplate> im obigen Beispiel können Sie Folgendes tun:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Dies <xref:System.Windows.DataTemplate> wird automatisch auf alle angewendet `Task` Objekte. Beachten Sie, dass die `x:Key` in diesem Fall implizit festgelegt wird. Aus diesem Grund, wenn Sie dies zuweisen <xref:System.Windows.DataTemplate> ein `x:Key` Wert überschreiben Sie die implizite `x:Key` und <xref:System.Windows.DataTemplate> wird nicht automatisch angewendet werden.  
  
 Wenn Sie binden ein <xref:System.Windows.Controls.ContentControl> auf eine Auflistung von `Task` Objekte, die <xref:System.Windows.Controls.ContentControl> verwendet nicht den oben genannten <xref:System.Windows.DataTemplate> automatisch. Grund hierfür ist die Bindung für eine <xref:System.Windows.Controls.ContentControl> benötigt weitere Informationen zum unterscheiden, ob Sie eine vollständige Auflistung und die einzelnen Objekte binden möchten. Wenn Ihre <xref:System.Windows.Controls.ContentControl> besteht im Nachverfolgen der Auswahl der ein <xref:System.Windows.Controls.ItemsControl> geben, Sie können festlegen, die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft der <xref:System.Windows.Controls.ContentControl> Binden an "`/`", um anzugeben, dass Sie das aktuelle Element interessiert sind. Ein Beispiel finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). Andernfalls müssen Sie an der <xref:System.Windows.DataTemplate> explizit durch Festlegen der <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft.  
  
 Die <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft ist besonders nützlich, wenn Sie haben eine <xref:System.Windows.Data.CompositeCollection> verschiedener Typen von Datenobjekten. Ein Beispiel finden Sie unter [Implementieren von CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Hinzufügen weiterer Elemente zu DataTemplate  
 Im Moment werden die Daten mit den notwendigen Informationen angezeigt, es sind aber definitiv noch Verbesserungen möglich. Wir verbessern die Darstellung durch Hinzufügen einer <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>, und einige <xref:System.Windows.Controls.TextBlock> Elemente, die die Daten zu beschreiben, die angezeigt wird.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Der folgende Screenshot zeigt die <xref:System.Windows.Controls.ListBox> mit dieser Änderung <xref:System.Windows.DataTemplate>:  
  
 ![Daten-beispielscreenshot: Vorlagen](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Wir können festlegen, <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> zu <xref:System.Windows.HorizontalAlignment.Stretch> auf die <xref:System.Windows.Controls.ListBox> um sicherzustellen, dass die Breite der Elemente belegt den gesamten Speicherplatz:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Mit der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> -Eigenschaftensatz auf <xref:System.Windows.HorizontalAlignment.Stretch>, <xref:System.Windows.Controls.ListBox> jetzt wie folgt aussieht:  
  
 ![Daten-beispielscreenshot: Vorlagen](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Anwenden von Eigenschaftswerten mit DataTrigger  
 Aus der aktuellen Darstellung geht nicht hervor, ob es sich bei einer `Task` um eine private oder um eine arbeitsbezogene Aufgabe handelt. Beachten Sie, dass das `Task`-Objekt über eine `TaskType`-Eigenschaft des Typs `TaskType` verfügt, die eine Enumeration mit den Werten `Home` und `Work` ist.  
  
 Im folgenden Beispiel die <xref:System.Windows.DataTrigger> legt diese fest der <xref:System.Windows.Controls.Border.BorderBrush%2A> des Elements mit dem Namen `border` zu `Yellow` Wenn der `TaskType` Eigenschaft `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Die Anwendung sieht jetzt folgendermaßen aus. Private Aufgaben werden mit einem gelben Rahmen und Office-Aufgaben mit einem hellblauen Rahmen angezeigt:  
  
 ![Daten-beispielscreenshot: Vorlagen](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 In diesem Beispiel die <xref:System.Windows.DataTrigger> verwendet eine <xref:System.Windows.Setter> , einen Eigenschaftswert festzulegen. Die Triggerklassen verfügen auch über die <xref:System.Windows.TriggerBase.EnterActions%2A> und <xref:System.Windows.TriggerBase.ExitActions%2A> Eigenschaften, die Sie eine Reihe von Aktionen wie z. B. Animationen starten können. Darüber hinaus steht auch eine <xref:System.Windows.MultiDataTrigger> -Klasse, die Sie zum Anwenden von Änderungen kann auf der Grundlage von mehrere Werte der datengebundenen Eigenschaft.  
  
 Eine alternative Möglichkeit, den gleichen Effekt zu erreichen ist, binden die <xref:System.Windows.Controls.Border.BorderBrush%2A> Eigenschaft, um die `TaskType` -Eigenschaft und ein Wertkonverter zum Zurückgeben der Farbe auf Grundlage der `TaskType` Wert. Mit Blick auf die Leistung ist es etwas effizienter, für diesen Effekt einen Konverter zu verwenden. Darüber hinaus bietet die Erstellung eines eigenen Konverters eine höhere Flexibilität, da Sie eine eigene Logik verwenden. Für welches Verfahren Sie sich entscheiden, hängt letztlich vom entsprechenden Szenario und Ihren Vorlieben ab. Weitere Informationen zum Schreiben eines Konverters, finden Sie unter <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Was gehört in eine DataTemplate?  

Im vorherigen Beispiel haben wir den Trigger der <xref:System.Windows.DataTemplate> mithilfe der <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> -Eigenschaft veranschaulicht. Die <xref:System.Windows.Setter> des Triggers legt den Wert einer Eigenschaft eines Elements (die <xref:System.Windows.Controls.Border> Element), der sich im die <xref:System.Windows.DataTemplate>. Jedoch wenn die Eigenschaften, die Ihre `Setters` beziehen sind keine Eigenschaften von Elementen in der aktuellen <xref:System.Windows.DataTemplate>, es möglicherweise besser geeignet, zum Festlegen der Eigenschaften, die mit einer <xref:System.Windows.Style> das der <xref:System.Windows.Controls.ListBoxItem> Klasse (wenn die Steuerelement erfolgt die Bindung ist eine <xref:System.Windows.Controls.ListBox>). Angenommen, Sie möchten Ihre <xref:System.Windows.Trigger> zum Animieren der <xref:System.Windows.UIElement.Opacity%2A> Wert des Elements bei der Maus auf ein Element, verweist Sie definieren die Trigger innerhalb einer <xref:System.Windows.Controls.ListBoxItem> Stil. Ein Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 Im Allgemeinen, beachten Sie, dass die <xref:System.Windows.DataTemplate> angewendet wird jedes erstellte <xref:System.Windows.Controls.ListBoxItem> (Weitere Informationen dazu, wie und wo sie genau angewendet, wird, finden Sie unter der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Seite.). Ihre <xref:System.Windows.DataTemplate> wird nur die Darstellung und das Erscheinungsbild der Datenobjekte kümmern. In den meisten Fällen sieht alle anderen Aspekte der Darstellung, z. B. welche ein Element wie wenn es ausgewählt wird oder wie die <xref:System.Windows.Controls.ListBox> Anordnung der Elemente, gehören nicht in der Definition einer <xref:System.Windows.DataTemplate>. Ein Beispiel finden Sie im Abschnitt [Formatieren und Erstellen von Vorlagen für ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Auswählen einer DataTemplate anhand von Eigenschaften des Datenobjekts  
 Im Abschnitt [Die DataType-Eigenschaft](#Styling_DataType) wurde erläutert, dass Sie verschiedene Datenvorlagen für verschiedene Datenobjekte definieren können. Das ist besonders nützlich, wenn Sie haben eine <xref:System.Windows.Data.CompositeCollection> verschiedener Typen oder Auflistungen mit Elementen verschiedener Typen. In der [DataTrigger zum Anwenden von Eigenschaftswerten verwenden](#DataTrigger_to_Apply_Property_Values) Abschnitt wurde gezeigt, wenn Sie eine Sammlung von Datenobjekten desselben Typs erstellen kann eine <xref:System.Windows.DataTemplate> und dann mithilfe von Triggern zum Anwenden von Änderungen, die basierend auf den Eigenschaftswerten jedes Datenobjekt. Mit Triggern können Sie Eigenschaftswerte anwenden oder Animationen starten, sie verfügen jedoch nicht über die nötige Flexibilität, um die Struktur der Datenobjekte zu rekonstruieren. Einige Szenarien müssen Sie einen anderen erstellen möglicherweise <xref:System.Windows.DataTemplate> für Daten Objekte, die identisch sind, geben Sie jedoch verfügen über unterschiedliche Eigenschaften.  
  
 Wenn z. B. ein `Task`-Objekt den `Priority`-Wert `1` hat, kann es sinnvoll sein, ihm ein völlig anderes Erscheinungsbild zuzuweisen, um als Warnung zu dienen. In diesem Fall erstellen Sie eine <xref:System.Windows.DataTemplate> für die Anzeige von hoher Priorität `Task` Objekte. Fügen Sie die folgenden <xref:System.Windows.DataTemplate> im Ressourcenabschnitt:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Beachten Sie, dass dieses Beispiel verwendet die <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> -Eigenschaft veranschaulicht. Ressourcen, die definiert, Abschnitt werden freigegeben, durch die Elemente innerhalb der <xref:System.Windows.DataTemplate>.  
  
 Bereitstellen von Logik zum Auswählen der <xref:System.Windows.DataTemplate> auf der Grundlage der `Priority` Wert des Datenobjekts, erstellen Sie eine Unterklasse von <xref:System.Windows.Controls.DataTemplateSelector> und überschreiben die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode. Im folgenden Beispiel die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode stellt die Logik zum Zurückgeben der entsprechenden Vorlage basierend auf den Wert der `Priority` Eigenschaft. Die Vorlage, die zurückgegeben wurde gefunden, in den Ressourcen des umschließenden <xref:System.Windows.Window> Element.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Wir können dann den `TaskListDataTemplateSelector` als Ressource deklarieren:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Um die Vorlagenauswahlressource verwenden zu können, weisen Sie ihn der <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox>. Die <xref:System.Windows.Controls.ListBox> Aufrufe der <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode der `TaskListDataTemplateSelector` für jedes der Elemente in der zugrunde liegenden Auflistung. Beim Aufruf wird das Datenobjekt als Elementparameter übergeben. Die <xref:System.Windows.DataTemplate> das zurückgegeben wird, indem die Methode wird dann auf die betreffende Datenobjekt angewendet.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Mit der Vorlagenauswahl die <xref:System.Windows.Controls.ListBox> nun wie folgt angezeigt:  
  
 ![Daten-beispielscreenshot: Vorlagen](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Damit ist die Erläuterung unseres Beispiels abgeschlossen. Das vollständige Beispiel finden Sie unter [Einführung in das Datenvorlagenbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Formatierung und Vorlagen für ItemsControl  
 Obwohl die <xref:System.Windows.Controls.ItemsControl> ist nicht der einzige Steuerelementtyp, die Sie verwenden können, eine <xref:System.Windows.DataTemplate> , es ist ein sehr häufiges Szenario zum Binden einer <xref:System.Windows.Controls.ItemsControl> für eine Sammlung. In der [Was gehört in eine DataTemplate](#what_belongs_in_datatemplate) Abschnitt erläutert, die die Definition Ihrer <xref:System.Windows.DataTemplate> muss nur die Darstellung von Daten. Um zu ermitteln, wenn sie nicht geeignet ist, verwenden, wird eine <xref:System.Windows.DataTemplate> es ist wichtig zu verstehen, die anderen gebotenen Stil- und Vorlageneigenschaften der <xref:System.Windows.Controls.ItemsControl>. Anhand des folgenden Beispiels soll die jeweilige Funktion dieser Eigenschaften veranschaulicht werden. Die <xref:System.Windows.Controls.ItemsControl> in diesem Beispiel wird auf die gleiche gebunden `Tasks` Auflistung wie im vorherigen Beispiel. Zu Demonstrationszwecken werden die Formate und die Vorlagen in diesem Beispiel inline deklariert.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Im Folgenden sehen Sie ein Bildschirmfoto des Beispiels nach dem Rendern:  
  
 ![Bildschirmfoto des ItemsControl-Beispiels](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Beachten Sie, dass anstelle der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, können Sie die <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Ein Beispiel finden Sie im vorherigen Abschnitt. Auf ähnliche Weise, anstatt die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, Sie haben die Möglichkeit zum Verwenden der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Zwei weitere Formatvorlagen bezogenen Eigenschaften für die <xref:System.Windows.Controls.ItemsControl> , werden nicht angezeigt, hier sind <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> und <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Unterstützung für hierarchische Daten  
 Bisher haben wir nur erläutert, wie eine einzelne Auflistung gebunden und angezeigt wird. Mitunter kann eine Auflistung auch andere Auflistungen enthalten. Die <xref:System.Windows.HierarchicalDataTemplate> Klasse mit verwendet werden soll <xref:System.Windows.Controls.HeaderedItemsControl> Typen, um solche Daten anzuzeigen. Im folgenden Beispiel ist `ListLeagueList` eine Liste von `League`-Objekten. Jedes `League`-Objekt verfügt über einen `Name` und eine Auflistung von `Division`-Objekten. Jede `Division` verfügt über einen `Name` und eine Auflistung von `Team`-Objekten, und `Team`Team-Objekt verfügt über einen `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Das Beispiel zeigt, mit der Verwendung von <xref:System.Windows.HierarchicalDataTemplate>, ganz einfach Listendaten anzuzeigen,, die andere Listen enthalten. Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.  
  
 ![Bildschirmabbildung für HierarchicalDataTemplate-Beispiel](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Siehe auch

- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [Suchen von Elementen, die mit einer DataTemplate-Klasse generiert wurden](how-to-find-datatemplate-generated-elements.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht über die Datenbindung](data-binding-overview.md)
- [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../controls/gridview-column-header-styles-and-templates-overview.md)
