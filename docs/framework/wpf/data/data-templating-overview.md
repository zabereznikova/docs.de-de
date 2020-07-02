---
title: Übersicht über Datenvorlagen
description: Untersuchen Sie die Datenvorlagen Modell-Flexibilität, die die Darstellung Ihrer Daten in Windows Presentation Foundation (WPF) definieren.
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
ms.openlocfilehash: 0226085a82cf97ea799a5a2d38e879b239d9b52a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619649"
---
# <a name="data-templating-overview"></a>Übersicht über Datenvorlagen
Mithilfe des WPF-Datenvorlagenmodells können Sie die Darstellung Ihrer Daten flexibel definieren. WPF-Steuerelemente verfügen über integrierte Funktionen, die die Anpassung der Datendarstellung unterstützen. In diesem Thema wird zunächst veranschaulicht, wie Sie einen definieren <xref:System.Windows.DataTemplate> und dann weitere Datenvorlagen Features einführen, wie z. b. die Auswahl von Vorlagen auf der Grundlage von benutzerdefinierter Logik und die Unterstützung für die Anzeige hierarchischer Daten.

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen
 Der Schwerpunkt dieses Themas liegt auf Datenvorlagenfeatures. Es bietet keine Einführung in Datenbindungskonzepte. Informationen zu grundlegende Datenbindungskonzepten finden Sie in der [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

 <xref:System.Windows.DataTemplate>dient zur Darstellung von Daten und ist eines der zahlreichen Features, die vom WPF-Format und-Vorlagen Modell bereitgestellt werden. Eine Einführung in das WPF-Format und das Vorlagen Modell, wie z. b <xref:System.Windows.Style> . das Verwenden eines zum Festlegen von Eigenschaften für Steuerelemente, finden Sie im Thema [formatieren und](../../../desktop-wpf/fundamentals/styles-templates-overview.md) Vorlagen.

 Außerdem ist es wichtig zu verstehen, was `Resources` im Wesentlichen die Möglichkeit zur <xref:System.Windows.Style> wiederverwendbaren Aktivierung von Objekten wie und ist <xref:System.Windows.DataTemplate> . Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>Grundlegendes zu Datenvorlagen

 Um zu veranschaulichen <xref:System.Windows.DataTemplate> , warum wichtig ist, sehen wir uns ein Beispiel für eine Datenbindung an. In diesem Beispiel gibt es eine <xref:System.Windows.Controls.ListBox> , die an eine Liste von-Objekten gebunden ist `Task` . Jedes `Task`-Objekt verfügt über `TaskName` (string), `Description` (string), `Priority` (int) und eine Eigenschaft des Typs `TaskType`, wobei es sich um ein `Enum` mit dem mit den Werten `Home` und `Work` handelt.

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>Ohne „DataTemplate“
 Ohne eine <xref:System.Windows.DataTemplate> sieht unser <xref:System.Windows.Controls.ListBox> aktuell wie folgt aus:

 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 Dies geschieht, wenn Sie ohne bestimmte Anweisungen <xref:System.Windows.Controls.ListBox> standardmäßig aufrufen, `ToString` Wenn Sie versuchen, die Objekte in der Auflistung anzuzeigen. Wenn das- `Task` Objekt die-Methode überschreibt `ToString` , wird daher die Zeichen folgen <xref:System.Windows.Controls.ListBox> Darstellung der einzelnen Quell Objekte in der zugrunde liegenden Auflistung angezeigt.

 Wenn z. B. die `Task`-Klasse auf diese Weise die `ToString`-Methode überschreibt, wobei `name` das Feld für die `TaskName`-Eigenschaft darstellt:

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 Das <xref:System.Windows.Controls.ListBox> sieht dann wie folgt aus:

 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 Das ist jedoch einschränkend und unflexibel. Außerdem können Sie, wenn Sie an XML-Daten binden, nicht überschreiben `ToString` .

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>Definieren einer einfachen Datenvorlage
 Die Lösung besteht darin, eine zu definieren <xref:System.Windows.DataTemplate> . Eine Möglichkeit besteht darin, die- <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft von <xref:System.Windows.Controls.ListBox> auf einen festzulegen <xref:System.Windows.DataTemplate> . Das, was Sie in <xref:System.Windows.DataTemplate> der angeben, wird zur visuellen Struktur des Datenobjekts. Folgendes <xref:System.Windows.DataTemplate> ist ziemlich einfach. Wir geben Ihnen Anweisungen, dass jedes Element als drei <xref:System.Windows.Controls.TextBlock> Elemente innerhalb einer angezeigt wird <xref:System.Windows.Controls.StackPanel> . Jedes- <xref:System.Windows.Controls.TextBlock> Element ist an eine Eigenschaft der- `Task` Klasse gebunden.

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 Die zugrunde liegenden Daten für die Beispiele in diesem Thema sind eine Auflistung von CLR-Objekten. Wenn Sie an XML-Daten binden, sind die grundlegenden Konzepte identisch, aber es gibt einen geringfügigen syntaktischen Unterschied. Beispielsweise würden Sie anstelle von `Path=TaskName` <xref:System.Windows.Data.Binding.XPath%2A> auf festlegen `@TaskName` (wenn `TaskName` ein Attribut des XML-Knotens ist).

 Nun <xref:System.Windows.Controls.ListBox> sieht das wie folgt aus:

 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>Erstellen der Datenvorlage als Ressource
 Im obigen Beispiel haben wir den Inline definiert <xref:System.Windows.DataTemplate> . Es ist jedoch üblicher, diese im Ressourcenabschnitt zu definieren, damit sie wiederverwendet werden kann, wie im folgenden Beispiel veranschaulicht:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Sie können `myTaskTemplate` nun als Ressource verwenden, wie im folgenden Beispiel veranschaulicht:

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 Da `myTaskTemplate` eine Ressource ist, können Sie Sie jetzt für andere Steuerelemente verwenden, die über eine Eigenschaft verfügen, die einen <xref:System.Windows.DataTemplate> Typ annimmt. Wie oben gezeigt, <xref:System.Windows.Controls.ItemsControl> ist es für-Objekte, wie z <xref:System.Windows.Controls.ListBox> . b., die- <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft. Für- <xref:System.Windows.Controls.ContentControl> Objekte ist es die- <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft.

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>Die DataType-Eigenschaft
 Die- <xref:System.Windows.DataTemplate> Klasse verfügt über eine- <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft, die der-Eigenschaft der-Klasse sehr ähnlich ist <xref:System.Windows.Style.TargetType%2A> <xref:System.Windows.Style> . Daher `x:Key` können Sie wie folgt vorgehen, anstatt ein für die <xref:System.Windows.DataTemplate> im obigen Beispiel anzugeben:

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 Dies <xref:System.Windows.DataTemplate> wird automatisch auf alle `Task` Objekte angewendet. Beachten Sie, dass die `x:Key` in diesem Fall implizit festgelegt wird. Wenn Sie diesem also einen- <xref:System.Windows.DataTemplate> Wert zuweisen, überschreiben `x:Key` Sie den impliziten, `x:Key` und der <xref:System.Windows.DataTemplate> wird nicht automatisch angewendet.

 Wenn Sie ein <xref:System.Windows.Controls.ContentControl> an eine Auflistung von- `Task` Objekten binden, <xref:System.Windows.Controls.ContentControl> verwendet die oben nicht <xref:System.Windows.DataTemplate> automatisch. Dies liegt daran, dass die Bindung für eine <xref:System.Windows.Controls.ContentControl> Weitere Informationen erfordert, um zu unterscheiden, ob Sie eine Bindung an eine gesamte Auflistung oder die einzelnen Objekte vornehmen möchten. Wenn Sie <xref:System.Windows.Controls.ContentControl> die Auswahl eines <xref:System.Windows.Controls.ItemsControl> Typs nachverfolgen, können Sie die- <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft der <xref:System.Windows.Controls.ContentControl> Bindung auf "" festlegen, `/` um anzugeben, dass Sie am aktuellen Element interessiert sind. Ein Beispiel finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). Andernfalls müssen Sie explizit angeben, <xref:System.Windows.DataTemplate> indem Sie die- <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft festlegen.

 Die- <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft ist besonders nützlich, wenn Sie über eine <xref:System.Windows.Data.CompositeCollection> von unterschiedlichen Typen von Datenobjekten verfügen. Ein Beispiel finden Sie unter [Implementieren von CompositeCollection](how-to-implement-a-compositecollection.md).

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>Hinzufügen weiterer Elemente zu DataTemplate
 Im Moment werden die Daten mit den notwendigen Informationen angezeigt, es sind aber definitiv noch Verbesserungen möglich. Lassen Sie uns die Präsentation verbessern, indem Sie ein- <xref:System.Windows.Controls.Border> , ein- <xref:System.Windows.Controls.Grid> Element und einige Elemente hinzufügen, die <xref:System.Windows.Controls.TextBlock> die angezeigten Daten beschreiben.

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 Der folgende Screenshot zeigt den, der <xref:System.Windows.Controls.ListBox> geändert wurde <xref:System.Windows.DataTemplate> :

 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 Wir können auf festlegen, <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> <xref:System.Windows.Controls.ListBox> um sicherzustellen, dass die Breite der Elemente den gesamten Speicherplatz einnimmt:

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 Wenn die- <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> Eigenschaft auf festgelegt <xref:System.Windows.HorizontalAlignment.Stretch> ist, <xref:System.Windows.Controls.ListBox> sieht nun wie folgt aus:

 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>Anwenden von Eigenschaftswerten mit DataTrigger
 Aus der aktuellen Darstellung geht nicht hervor, ob es sich bei einer `Task` um eine private oder um eine arbeitsbezogene Aufgabe handelt. Beachten Sie, dass das `Task`-Objekt über eine `TaskType`-Eigenschaft des Typs `TaskType` verfügt, die eine Enumeration mit den Werten `Home` und `Work` ist.

 Im folgenden Beispiel <xref:System.Windows.DataTrigger> legt den <xref:System.Windows.Controls.Border.BorderBrush%2A> des Elements mit dem Namen auf fest `border` , `Yellow` Wenn die- `TaskType` Eigenschaft ist `TaskType.Home` .

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 Die Anwendung sieht jetzt folgendermaßen aus. Private Aufgaben werden mit einem gelben Rahmen und Office-Aufgaben mit einem hellblauen Rahmen angezeigt:

 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 In diesem Beispiel <xref:System.Windows.DataTrigger> verwendet einen <xref:System.Windows.Setter> , um einen Eigenschafts Wert festzulegen. Die auslöserklassen verfügen auch über die <xref:System.Windows.TriggerBase.EnterActions%2A> <xref:System.Windows.TriggerBase.ExitActions%2A> Eigenschaften und, mit denen Sie eine Reihe von Aktionen starten können, z. b. Animationen. Außerdem gibt es eine-Klasse, <xref:System.Windows.MultiDataTrigger> mit der Sie Änderungen auf der Grundlage mehrerer Daten gebundener Eigenschaftswerte anwenden können.

 Eine alternative Möglichkeit, denselben Effekt zu erzielen, besteht darin, die <xref:System.Windows.Controls.Border.BorderBrush%2A> Eigenschaft an die Eigenschaft zu binden `TaskType` und einen Wert Konverter zu verwenden, um die Farbe auf Grundlage des Werts zurückzugeben `TaskType` . Mit Blick auf die Leistung ist es etwas effizienter, für diesen Effekt einen Konverter zu verwenden. Darüber hinaus bietet die Erstellung eines eigenen Konverters eine höhere Flexibilität, da Sie eine eigene Logik verwenden. Für welches Verfahren Sie sich entscheiden, hängt letztlich vom entsprechenden Szenario und Ihren Vorlieben ab. Weitere Informationen zum Schreiben eines Konverters finden Sie unter <xref:System.Windows.Data.IValueConverter> .

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>Was gehört in eine DataTemplate?

Im vorherigen Beispiel haben wir den-Typ mithilfe der-Eigenschaft in die eingefügt <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType> . Der <xref:System.Windows.Setter> des Auslösers legt den Wert einer Eigenschaft eines Elements (das- <xref:System.Windows.Controls.Border> Element) fest, das sich innerhalb von befindet <xref:System.Windows.DataTemplate> . Wenn die Eigenschaften, `Setters` mit denen Sie sich beschäftigen, keine Eigenschaften von Elementen sind, die sich innerhalb des aktuellen befinden <xref:System.Windows.DataTemplate> , ist es möglicherweise besser, die Eigenschaften mithilfe eines-Objekts festzulegen, <xref:System.Windows.Style> das für die- <xref:System.Windows.Controls.ListBoxItem> Klasse gilt (wenn das Steuerelement, das Sie binden, ein ist <xref:System.Windows.Controls.ListBox> ). Wenn Sie z. b. <xref:System.Windows.Trigger> den <xref:System.Windows.UIElement.Opacity%2A> Wert des Elements animieren möchten, wenn ein Mauszeiger auf ein Element zeigt, definieren Sie Trigger innerhalb eines <xref:System.Windows.Controls.ListBoxItem> Stils. Ein Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

 Im Allgemeinen sollten Sie Bedenken, dass die <xref:System.Windows.DataTemplate> auf die einzelnen generierten angewendet wird <xref:System.Windows.Controls.ListBoxItem> (Weitere Informationen dazu, wie und wo Sie tatsächlich angewendet werden, finden Sie auf der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Seite.) Ihr <xref:System.Windows.DataTemplate> betrifft nur die Darstellung und Darstellung der Datenobjekte. In den meisten Fällen gehören alle anderen Aspekte der Präsentation, wie z. b. das Aussehen eines Elements, wenn es ausgewählt wird, oder die Art und Weise, <xref:System.Windows.Controls.ListBox> in der die Elemente angeordnet werden, nicht zur Definition einer <xref:System.Windows.DataTemplate> . Ein Beispiel finden Sie im Abschnitt [Formatieren und Erstellen von Vorlagen für ItemsControl](#DataTemplating_ItemsControl).

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Auswählen einer DataTemplate anhand von Eigenschaften des Datenobjekts
 Im Abschnitt [Die DataType-Eigenschaft](#Styling_DataType) wurde erläutert, dass Sie verschiedene Datenvorlagen für verschiedene Datenobjekte definieren können. Dies ist besonders nützlich, wenn Sie über eine <xref:System.Windows.Data.CompositeCollection> von unterschiedlichen Typen oder Sammlungen mit Elementen verschiedener Typen verfügen. Im Abschnitt [Verwenden von DataTriggers zum Anwenden von Eigenschafts Werten](#DataTrigger_to_Apply_Property_Values) wird gezeigt, dass Sie eine Auflistung desselben Typs von Datenobjekten erstellen <xref:System.Windows.DataTemplate> und dann mithilfe von Triggern Änderungen auf der Grundlage der Eigenschaftswerte jedes Datenobjekts anwenden können. Mit Triggern können Sie Eigenschaftswerte anwenden oder Animationen starten, sie verfügen jedoch nicht über die nötige Flexibilität, um die Struktur der Datenobjekte zu rekonstruieren. In einigen Szenarien ist es möglicherweise erforderlich, dass Sie eine andere <xref:System.Windows.DataTemplate> für Datenobjekte erstellen, die denselben Typ aufweisen, aber über unterschiedliche Eigenschaften verfügen.

 Wenn z. B. ein `Task`-Objekt den `Priority`-Wert `1` hat, kann es sinnvoll sein, ihm ein völlig anderes Erscheinungsbild zuzuweisen, um als Warnung zu dienen. In diesem Fall erstellen Sie ein <xref:System.Windows.DataTemplate> -Objekt für die Anzeige der Objekte mit hoher Priorität `Task` . Fügen Sie dem <xref:System.Windows.DataTemplate> Ressourcenabschnitt Folgendes hinzu:

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

In diesem Beispiel wird die [DataTemplate. Resources](xref:System.Windows.FrameworkTemplate.Resources%2A) -Eigenschaft verwendet. Die in diesem Abschnitt definierten Ressourcen werden von den Elementen in der gemeinsam genutzt <xref:System.Windows.DataTemplate> .

 <xref:System.Windows.DataTemplate> `Priority` Erstellen Sie eine Unterklasse von, <xref:System.Windows.Controls.DataTemplateSelector> und überschreiben Sie die-Methode, um zu bestimmen, welche Logik basierend auf dem Wert des Datenobjekts verwendet werden soll <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> . Im folgenden Beispiel stellt die- <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode Logik bereit, um die entsprechende Vorlage basierend auf dem Wert der- `Priority` Eigenschaft zurückzugeben. Die zurück zugebende Vorlage befindet sich in den Ressourcen des umschließenden- <xref:System.Windows.Window> Elements.

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 Wir können dann den `TaskListDataTemplateSelector` als Ressource deklarieren:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Wenn Sie die Vorlagen Auswahl Ressource verwenden möchten, weisen Sie Sie der- <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> Eigenschaft von zu <xref:System.Windows.Controls.ListBox> . Die <xref:System.Windows.Controls.ListBox> Ruft die- <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode der `TaskListDataTemplateSelector` für jedes der Elemente in der zugrunde liegenden Auflistung auf. Beim Aufruf wird das Datenobjekt als Elementparameter übergeben. Der <xref:System.Windows.DataTemplate> , der von der-Methode zurückgegeben wird, wird dann auf das Datenobjekt angewendet.

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 Wenn die Vorlagen Auswahl vorhanden ist, wird <xref:System.Windows.Controls.ListBox> nun wie folgt angezeigt:

 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

Damit ist die Erläuterung unseres Beispiels abgeschlossen. Das vollständige Beispiel finden Sie unter [Einführung in das Datenvorlagenbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>Formatierung und Vorlagen für ItemsControl
 Obwohl der <xref:System.Windows.Controls.ItemsControl> nicht der einzige Steuerelement Typ ist, mit dem Sie einen <xref:System.Windows.DataTemplate> mit verwenden können, ist es ein gängiges Szenario, ein an <xref:System.Windows.Controls.ItemsControl> eine Auflistung zu binden. Im Abschnitt [Was gehört zu einem DataTemplate](#what_belongs_in_datatemplate) -Abschnitt wurde erläutert, dass die Definition von <xref:System.Windows.DataTemplate> nur die Darstellung von Daten betreffen sollte. Um zu wissen, wann es nicht für die Verwendung von geeignet ist, <xref:System.Windows.DataTemplate> ist es wichtig, die unterschiedlichen Stil-und Vorlagen Eigenschaften von zu verstehen <xref:System.Windows.Controls.ItemsControl> . Anhand des folgenden Beispiels soll die jeweilige Funktion dieser Eigenschaften veranschaulicht werden. Der <xref:System.Windows.Controls.ItemsControl> in diesem Beispiel ist an dieselbe Auflistung gebunden `Tasks` wie im vorherigen Beispiel. Zu Demonstrationszwecken werden die Formate und die Vorlagen in diesem Beispiel inline deklariert.

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 Im Folgenden sehen Sie ein Bildschirmfoto des Beispiels nach dem Rendern:

 ![Screenshot für ein ItemsControl-Beispiel](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 Beachten Sie, dass Sie anstelle von den <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> verwenden können <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> . Ein Beispiel finden Sie im vorherigen Abschnitt. Ebenso haben Sie die Möglichkeit, anstelle von <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> zu verwenden <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A> .

 Zwei weitere Stil bezogene Eigenschaften von, die <xref:System.Windows.Controls.ItemsControl> hier nicht angezeigt werden, sind <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> und <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A> .

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>Unterstützung für hierarchische Daten
 Bisher haben wir nur erläutert, wie eine einzelne Auflistung gebunden und angezeigt wird. Mitunter kann eine Auflistung auch andere Auflistungen enthalten. Die- <xref:System.Windows.HierarchicalDataTemplate> Klasse ist so konzipiert, dass Sie mit-Typen verwendet wird <xref:System.Windows.Controls.HeaderedItemsControl> , um solche Daten anzuzeigen. Im folgenden Beispiel ist `ListLeagueList` eine Liste von `League`-Objekten. Jedes `League`-Objekt verfügt über einen `Name` und eine Auflistung von `Division`-Objekten. Jede `Division` verfügt über einen `Name` und eine Auflistung von `Team`-Objekten, und `Team`Team-Objekt verfügt über einen `Name`.

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 Das Beispiel zeigt, dass Sie bei Verwendung von <xref:System.Windows.HierarchicalDataTemplate> problemlos Listen Daten anzeigen können, die andere Listen enthalten. Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.

 ![Hierarchcaldatatemplate-Beispiel Bildschirmfoto](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>Weitere Informationen

- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [Suchen von Elementen, die mit einer DataTemplate generiert wurden](how-to-find-datatemplate-generated-elements.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../controls/gridview-column-header-styles-and-templates-overview.md)
