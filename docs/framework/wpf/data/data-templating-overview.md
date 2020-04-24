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
ms.openlocfilehash: b9e55eac1c72cd3deec21754373da4364a7cfed2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646460"
---
# <a name="data-templating-overview"></a>Übersicht über Datenvorlagen
Mithilfe des WPF-Datenvorlagenmodells können Sie die Darstellung Ihrer Daten flexibel definieren. WPF-Steuerelemente verfügen über integrierte Funktionen, die die Anpassung der Datendarstellung unterstützen. In diesem Thema wird <xref:System.Windows.DataTemplate> zunächst veranschaulicht, wie Sie ein definieren und dann andere Datenvorlagenfeatures einführen, z. B. die Auswahl von Vorlagen basierend auf benutzerdefinierter Logik und die Unterstützung für die Anzeige hierarchischer Daten.

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen
 Der Schwerpunkt dieses Themas liegt auf Datenvorlagenfeatures. Es bietet keine Einführung in Datenbindungskonzepte. Informationen zu grundlegende Datenbindungskonzepten finden Sie in der [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

 <xref:System.Windows.DataTemplate>handelt von der Darstellung von Daten und ist eines der vielen Features, die vom WPF-Styling- und Vorlagenmodell bereitgestellt werden. Eine Einführung in das WPF-Styling- und Vorlagenmodell, <xref:System.Windows.Style> z. B. die Verwendung eines zum Festlegen von Eigenschaften für Steuerelemente, finden Sie im Thema [Styling und Templating.](../../../desktop-wpf/fundamentals/styles-templates-overview.md)

 Darüber hinaus ist es `Resources`wichtig zu verstehen , welche <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> im Wesentlichen Objekte wie und wiederverwendbar zu ermöglichen sind. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>Grundlegendes zu Datenvorlagen

 Um zu <xref:System.Windows.DataTemplate> veranschaulichen, warum wichtig ist, gehen wir durch ein Datenbindungsbeispiel. In diesem Beispiel haben <xref:System.Windows.Controls.ListBox> wir eine, die `Task` an eine Liste von Objekten gebunden ist. Jedes `Task`-Objekt verfügt über `TaskName` (string), `Description` (string), `Priority` (int) und eine Eigenschaft des Typs `TaskType`, wobei es sich um ein `Enum` mit dem mit den Werten `Home` und `Work` handelt.

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>Ohne „DataTemplate“
 Ohne <xref:System.Windows.DataTemplate>eine <xref:System.Windows.Controls.ListBox> , sieht unsere derzeit wie folgt aus:

 ![Beispiel-Screenshot für Datentemplatierung](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 Was passiert, ist, dass ohne <xref:System.Windows.Controls.ListBox> spezifische Anweisungen `ToString` die standardmäßigen Aufrufe, wenn Sie versuchen, die Objekte in der Auflistung anzuzeigen. Wenn das `Task` Objekt die `ToString` Methode überschreibt, zeigt die <xref:System.Windows.Controls.ListBox> daher die Zeichenfolgendarstellung jedes Quellobjekts in der zugrunde liegenden Auflistung an.

 Wenn z. B. die `Task`-Klasse auf diese Weise die `ToString`-Methode überschreibt, wobei `name` das Feld für die `TaskName`-Eigenschaft darstellt:

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 Dann <xref:System.Windows.Controls.ListBox> sieht die wie folgt aus:

 ![Beispiel-Screenshot für Datentemplatierung](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 Das ist jedoch einschränkend und unflexibel. Wenn Sie an XML-Daten binden, können Sie auch `ToString`nicht überschreiben.

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>Definieren einer einfachen Datenvorlage
 Die Lösung besteht <xref:System.Windows.DataTemplate>darin, eine zu definieren. Eine Möglichkeit, dies zu <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> tun, <xref:System.Windows.Controls.ListBox> besteht <xref:System.Windows.DataTemplate>darin, die Eigenschaft des auf eine festzulegen. Was Sie in <xref:System.Windows.DataTemplate> Ihrem datenobjekt angeben, wird zur visuellen Struktur des Datenobjekts. Das <xref:System.Windows.DataTemplate> Folgende ist ziemlich einfach. Wir geben Anweisungen, dass jedes <xref:System.Windows.Controls.TextBlock> Element <xref:System.Windows.Controls.StackPanel>als drei Elemente innerhalb einer angezeigt wird. Jedes <xref:System.Windows.Controls.TextBlock> Element ist an eine `Task` Eigenschaft der Klasse gebunden.

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 Die zugrunde liegenden Daten für die Beispiele in diesem Thema sind eine Sammlung von CLR-Objekten. Wenn Sie an XML-Daten binden, sind die grundlegenden Konzepte die gleichen, aber es gibt einen leichten syntaktischen Unterschied. `Path=TaskName`Anstatt beispielsweise auf zu verfügen, <xref:System.Windows.Data.Binding.XPath%2A> `@TaskName` werden `TaskName` Sie auf (wenn es sich um ein Attribut Ihres XML-Knotens handelt) festgelegt.

 Jetzt <xref:System.Windows.Controls.ListBox> sieht unser aussehen wie folgt aus:

 ![Beispiel-Screenshot für Datentemplatierung](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>Erstellen der Datenvorlage als Ressource
 Im obigen Beispiel haben <xref:System.Windows.DataTemplate> wir die Inline definiert. Es ist jedoch üblicher, diese im Ressourcenabschnitt zu definieren, damit sie wiederverwendet werden kann, wie im folgenden Beispiel veranschaulicht:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Sie können `myTaskTemplate` nun als Ressource verwenden, wie im folgenden Beispiel veranschaulicht:

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 Da `myTaskTemplate` es sich um eine Ressource handelt, können Sie sie <xref:System.Windows.DataTemplate> jetzt für andere Steuerelemente verwenden, die über eine Eigenschaft verfügen, die einen Typ annimmt. Wie oben gezeigt, ist es für <xref:System.Windows.Controls.ItemsControl> Objekte, wie z. B. die <xref:System.Windows.Controls.ListBox>, die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft. Bei <xref:System.Windows.Controls.ContentControl> Objekten handelt <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> es sich um die Eigenschaft.

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>Die DataType-Eigenschaft
 Die <xref:System.Windows.DataTemplate> Klasse <xref:System.Windows.DataTemplate.DataType%2A> verfügt über eine Eigenschaft, die der <xref:System.Windows.Style.TargetType%2A> Eigenschaft der <xref:System.Windows.Style> Klasse sehr ähnlich ist. Anstatt eine `x:Key` für die <xref:System.Windows.DataTemplate> im obigen Beispiel anzugeben, können Sie daher Folgendes tun:

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 Dies <xref:System.Windows.DataTemplate> wird automatisch `Task` auf alle Objekte angewendet. Beachten Sie, dass die `x:Key` in diesem Fall implizit festgelegt wird. Wenn Sie <xref:System.Windows.DataTemplate> diesem Wert `x:Key` also einen Wert zuweisen, überschreiben Sie das implizite `x:Key` und das <xref:System.Windows.DataTemplate> wird nicht automatisch angewendet.

 Wenn Sie eine <xref:System.Windows.Controls.ContentControl> an eine `Task` Auflistung <xref:System.Windows.Controls.ContentControl> von Objekten binden, verwendet der die oben genannten <xref:System.Windows.DataTemplate> Objekte nicht automatisch. Dies liegt daran, <xref:System.Windows.Controls.ContentControl> dass die Bindung an ein weitere Informationen benötigt, um zu unterscheiden, ob Sie an eine ganze Auflistung oder die einzelnen Objekte binden möchten. Wenn <xref:System.Windows.Controls.ContentControl> Sie die Auswahl <xref:System.Windows.Controls.ItemsControl> eines Typs nachverfolgen, <xref:System.Windows.Controls.ContentControl> können Sie`/`die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft der Bindung auf " festlegen, um anzugeben, dass Sie an dem aktuellen Element interessiert sind. Ein Beispiel finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). Andernfalls müssen Sie die <xref:System.Windows.DataTemplate> explizit angeben, indem Sie die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft festlegen.

 Die <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft ist besonders nützlich, wenn Sie über verschiedene <xref:System.Windows.Data.CompositeCollection> Arten von Datenobjekten verfügen. Ein Beispiel finden Sie unter [Implementieren von CompositeCollection](how-to-implement-a-compositecollection.md).

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>Hinzufügen weiterer Elemente zu DataTemplate
 Im Moment werden die Daten mit den notwendigen Informationen angezeigt, es sind aber definitiv noch Verbesserungen möglich. Verbessern wir die Präsentation, indem <xref:System.Windows.Controls.Border>wir <xref:System.Windows.Controls.Grid>eine <xref:System.Windows.Controls.TextBlock> , a und einige Elemente hinzufügen, die die angezeigten Daten beschreiben.

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 Der folgende Screenshot <xref:System.Windows.Controls.ListBox> zeigt <xref:System.Windows.DataTemplate>die mit diesem geänderten :

 ![Beispiel-Screenshot für Datentemplatierung](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 Wir können <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> auf <xref:System.Windows.Controls.ListBox> die setzen, um sicherzustellen, dass die Breite der Elemente den gesamten Raum einnimmt:

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 Wenn <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> die Eigenschaft <xref:System.Windows.HorizontalAlignment.Stretch>auf <xref:System.Windows.Controls.ListBox> gesetzt ist, sieht die jetzt wie folgt aus:

 ![Beispiel-Screenshot für Datentemplatierung](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>Anwenden von Eigenschaftswerten mit DataTrigger
 Aus der aktuellen Darstellung geht nicht hervor, ob es sich bei einer `Task` um eine private oder um eine arbeitsbezogene Aufgabe handelt. Beachten Sie, dass das `Task`-Objekt über eine `TaskType`-Eigenschaft des Typs `TaskType` verfügt, die eine Enumeration mit den Werten `Home` und `Work` ist.

 Im folgenden Beispiel <xref:System.Windows.DataTrigger> legt <xref:System.Windows.Controls.Border.BorderBrush%2A> der das `border` Element `Yellow` fest, auf das die `TaskType` Eigenschaft benannt ist. `TaskType.Home`

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 Die Anwendung sieht jetzt folgendermaßen aus. Private Aufgaben werden mit einem gelben Rahmen und Office-Aufgaben mit einem hellblauen Rahmen angezeigt:

 ![Beispiel-Screenshot für Datentemplatierung](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 In diesem <xref:System.Windows.DataTrigger> Beispiel <xref:System.Windows.Setter> verwendet die zum Festlegen eines Eigenschaftswerts. Die Triggerklassen verfügen <xref:System.Windows.TriggerBase.EnterActions%2A> <xref:System.Windows.TriggerBase.ExitActions%2A> auch über die und Eigenschaften, mit denen Sie eine Reihe von Aktionen wie Animationen starten können. Darüber hinaus gibt es <xref:System.Windows.MultiDataTrigger> eine Klasse, mit der Sie Änderungen basierend auf mehreren datengebundenen Eigenschaftswerten anwenden können.

 Eine alternative Möglichkeit, den gleichen Effekt <xref:System.Windows.Controls.Border.BorderBrush%2A> zu `TaskType` erzielen, besteht darin, die Eigenschaft an `TaskType` die Eigenschaft zu binden und einen Wertkonverter zu verwenden, um die Farbe basierend auf dem Wert zurückzugeben. Mit Blick auf die Leistung ist es etwas effizienter, für diesen Effekt einen Konverter zu verwenden. Darüber hinaus bietet die Erstellung eines eigenen Konverters eine höhere Flexibilität, da Sie eine eigene Logik verwenden. Für welches Verfahren Sie sich entscheiden, hängt letztlich vom entsprechenden Szenario und Ihren Vorlieben ab. Informationen zum Schreiben eines Konverters <xref:System.Windows.Data.IValueConverter>finden Sie unter .

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>Was gehört in eine DataTemplate?

Im vorherigen Beispiel haben wir den <xref:System.Windows.DataTemplate> Trigger <xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType> innerhalb der verwendungseigenschaft platziert. Der <xref:System.Windows.Setter> des Triggers legt den Wert einer <xref:System.Windows.Controls.Border> Eigenschaft eines Elements <xref:System.Windows.DataTemplate>(des Elements) fest, das sich innerhalb der befindet. Wenn die Eigenschaften, `Setters` mit denen Sie sich befassen, jedoch <xref:System.Windows.DataTemplate>keine Eigenschaften von Elementen sind, die <xref:System.Windows.Style> sich innerhalb <xref:System.Windows.Controls.ListBoxItem> des aktuellen befinden, kann <xref:System.Windows.Controls.ListBox>es besser sein, die Eigenschaften mit einem für die Klasse festzulegen (wenn das Steuerelement, das Sie binden, ein ist). Wenn Sie beispielsweise möchten, dass Sie <xref:System.Windows.Trigger> den <xref:System.Windows.UIElement.Opacity%2A> Wert des Elements animieren, wenn <xref:System.Windows.Controls.ListBoxItem> eine Maus auf ein Element zeigt, definieren Sie Trigger innerhalb eines Stils. Ein Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

 Im Allgemeinen sollten Sie <xref:System.Windows.DataTemplate> bedenken, dass die auf <xref:System.Windows.Controls.ListBoxItem> jeden der generierten angewendet wird (weitere <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Informationen darüber, wie und wo es tatsächlich angewendet wird, siehe Seite.). Ihr <xref:System.Windows.DataTemplate> geht es nur um die Darstellung und Darstellung der Datenobjekte. In den meisten Fällen gehören alle anderen Aspekte der Darstellung, z. <xref:System.Windows.Controls.ListBox> B. wie ein Element aussieht, wenn <xref:System.Windows.DataTemplate>es ausgewählt wird, oder wie die Layouts der Elemente nicht in die Definition einer gehören. Ein Beispiel finden Sie im Abschnitt [Formatieren und Erstellen von Vorlagen für ItemsControl](#DataTemplating_ItemsControl).

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Auswählen einer DataTemplate anhand von Eigenschaften des Datenobjekts
 Im Abschnitt [Die DataType-Eigenschaft](#Styling_DataType) wurde erläutert, dass Sie verschiedene Datenvorlagen für verschiedene Datenobjekte definieren können. Dies ist besonders nützlich, wenn Sie eine <xref:System.Windows.Data.CompositeCollection> von verschiedenen Typen oder Auflistungen mit Elementen unterschiedlicher Typen haben. Im Abschnitt Verwenden von [DataTriggers zum Anwenden von Eigenschaftswerten](#DataTrigger_to_Apply_Property_Values) haben wir gezeigt, dass Sie, wenn Sie über eine Auflistung desselben Datenobjekttyps verfügen, ein <xref:System.Windows.DataTemplate> erstellen und dann Trigger verwenden können, um Änderungen basierend auf den Eigenschaftswerten jedes Datenobjekts anzuwenden. Mit Triggern können Sie Eigenschaftswerte anwenden oder Animationen starten, sie verfügen jedoch nicht über die nötige Flexibilität, um die Struktur der Datenobjekte zu rekonstruieren. In einigen Szenarien müssen Sie <xref:System.Windows.DataTemplate> möglicherweise ein anderes für Datenobjekte erstellen, die vom gleichen Typ sind, aber unterschiedliche Eigenschaften aufweisen.

 Wenn z. B. ein `Task`-Objekt den `Priority`-Wert `1` hat, kann es sinnvoll sein, ihm ein völlig anderes Erscheinungsbild zuzuweisen, um als Warnung zu dienen. In diesem Fall erstellen <xref:System.Windows.DataTemplate> Sie eine für die `Task` Anzeige der Objekte mit hoher Priorität. Fügen wir dem <xref:System.Windows.DataTemplate> Ressourcenabschnitt Folgendes hinzu:

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

In diesem Beispiel wird die [DataTemplate.Resources-Eigenschaft](xref:System.Windows.FrameworkTemplate.Resources%2A) verwendet. Die in diesem Abschnitt definierten Ressourcen <xref:System.Windows.DataTemplate>werden von den Elementen im gemeinsam genutzt.

 Erstellen Sie eine <xref:System.Windows.DataTemplate> Unterklasse der `Priority` <xref:System.Windows.Controls.DataTemplateSelector> Methode, und überschreiben Sie die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode, um die zu verwendende Logik auszuwählen, die auf dem Wert des Datenobjekts basieren soll. Im folgenden Beispiel <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> stellt die Methode Logik bereit, um die `Priority` entsprechende Vorlage basierend auf dem Wert der Eigenschaft zurückzugeben. Die zurückzugebende Vorlage befindet sich in den <xref:System.Windows.Window> Ressourcen des umhüllenden Elements.

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 Wir können dann den `TaskListDataTemplateSelector` als Ressource deklarieren:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Um die Vorlagenselektorressource zu <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> verwenden, <xref:System.Windows.Controls.ListBox>weisen Sie sie der Eigenschaft der zu. Der <xref:System.Windows.Controls.ListBox> ruft <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> die `TaskListDataTemplateSelector` Methode der für jedes Element in der zugrunde liegenden Auflistung auf. Beim Aufruf wird das Datenobjekt als Elementparameter übergeben. Die, <xref:System.Windows.DataTemplate> die von der Methode zurückgegeben wird, wird dann auf dieses Datenobjekt angewendet.

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 Wenn der Vorlagenselektor <xref:System.Windows.Controls.ListBox> an Ort und Stelle ist, wird das jetzt wie folgt angezeigt:

 ![Beispiel-Screenshot für Datentemplatierung](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

Damit ist die Erläuterung unseres Beispiels abgeschlossen. Das vollständige Beispiel finden Sie unter [Einführung in das Datenvorlagenbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>Formatierung und Vorlagen für ItemsControl
 Auch wenn <xref:System.Windows.Controls.ItemsControl> der nicht der einzige Steuerelementtyp <xref:System.Windows.DataTemplate> ist, den Sie mit verwenden <xref:System.Windows.Controls.ItemsControl> können, ist es ein sehr häufiges Szenario, um eine an eine Auflistung zu binden. Im Abschnitt [Was gehört in einem DataTemplate](#what_belongs_in_datatemplate) Abschnitt <xref:System.Windows.DataTemplate> haben wir diskutiert, dass die Definition von Ihnen sollte nur mit der Darstellung von Daten betroffen sein. Um zu wissen, wann es nicht <xref:System.Windows.DataTemplate> geeignet ist, eine zu verwenden, ist <xref:System.Windows.Controls.ItemsControl>es wichtig, die verschiedenen Stil- und Vorlageneigenschaften zu verstehen, die von der bereitgestellt werden. Anhand des folgenden Beispiels soll die jeweilige Funktion dieser Eigenschaften veranschaulicht werden. Der <xref:System.Windows.Controls.ItemsControl> in diesem Beispiel ist `Tasks` an dieselbe Auflistung gebunden wie im vorherigen Beispiel. Zu Demonstrationszwecken werden die Formate und die Vorlagen in diesem Beispiel inline deklariert.

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 Im Folgenden sehen Sie ein Bildschirmfoto des Beispiels nach dem Rendern:

 ![Screenshot für ein ItemsControl-Beispiel](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 Beachten Sie, dass <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>Sie anstelle <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>der die verwenden können. Ein Beispiel finden Sie im vorherigen Abschnitt. Anstatt die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>zu verwenden, haben Sie die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>Möglichkeit, die zu verwenden.

 Zwei weitere stilbezogene Eigenschaften <xref:System.Windows.Controls.ItemsControl> der, die <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> hier <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>nicht angezeigt werden, sind und .

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>Unterstützung für hierarchische Daten
 Bisher haben wir nur erläutert, wie eine einzelne Auflistung gebunden und angezeigt wird. Mitunter kann eine Auflistung auch andere Auflistungen enthalten. Die <xref:System.Windows.HierarchicalDataTemplate> Klasse ist für <xref:System.Windows.Controls.HeaderedItemsControl> die Verwendung mit Typen zur Anzeige solcher Daten konzipiert. Im folgenden Beispiel ist `ListLeagueList` eine Liste von `League`-Objekten. Jedes `League`-Objekt verfügt über einen `Name` und eine Auflistung von `Division`-Objekten. Jede `Division` verfügt über einen `Name` und eine Auflistung von `Team`-Objekten, und `Team`Team-Objekt verfügt über einen `Name`.

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 Das Beispiel zeigt, dass <xref:System.Windows.HierarchicalDataTemplate>Sie mit der Verwendung von einfach Listendaten anzeigen können, die andere Listen enthalten. Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.

 ![HierarchicalDataTemplate-Beispiel-Screenshot](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>Siehe auch

- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [Suchen von DataTemplate-generierten Elementen](how-to-find-datatemplate-generated-elements.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../controls/gridview-column-header-styles-and-templates-overview.md)
