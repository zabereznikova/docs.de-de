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
ms.openlocfilehash: 377ee76e7e3537e9cae010189306611a503acbed
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740623"
---
# <a name="data-templating-overview"></a>Übersicht über Datenvorlagen
Mithilfe des WPF-Datenvorlagenmodells können Sie die Darstellung Ihrer Daten flexibel definieren. WPF-Steuerelemente verfügen über integrierte Funktionen, die die Anpassung der Datendarstellung unterstützen. In diesem Thema wird zunächst veranschaulicht, wie Sie eine <xref:System.Windows.DataTemplate> definieren und anschließend weitere Datenvorlagen Features, wie z. b. die Auswahl von Vorlagen, die auf benutzerdefinierter Logik basieren, und die Unterstützung für die Anzeige hierarchischer Daten.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Voraussetzungen  
 Der Schwerpunkt dieses Themas liegt auf Datenvorlagenfeatures. Es bietet keine Einführung in Datenbindungskonzepte. Informationen zu grundlegende Datenbindungskonzepten finden Sie in der [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> ist die Darstellung von Daten und ist eines der zahlreichen Features, die vom WPF-Modell für Stile und Vorlagen bereitgestellt werden. Eine Einführung in das WPF-Format und das Vorlagen Modell, z. b. die Verwendung einer <xref:System.Windows.Style> zum Festlegen von Eigenschaften für Steuerelemente, finden Sie im Thema [formatieren und](../controls/styling-and-templating.md) Vorlagen.  
  
 Darüber hinaus ist es wichtig, `Resources`zu verstehen, was im wesentlichen ermöglicht, dass Objekte wie <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> wiederverwendbar sind. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Grundlegendes zu Datenvorlagen  
  
 Um zu veranschaulichen, warum <xref:System.Windows.DataTemplate> wichtig ist, sehen wir uns ein Beispiel für eine Datenbindung an. In diesem Beispiel verfügen wir über eine <xref:System.Windows.Controls.ListBox>, die an eine Liste von `Task` Objekten gebunden ist. Jedes `Task`-Objekt verfügt über `TaskName` (string), `Description` (string), `Priority` (int) und eine Eigenschaft des Typs `TaskType`, wobei es sich um ein `Enum` mit dem mit den Werten `Home` und `Work` handelt.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Ohne „DataTemplate“  
 Ohne <xref:System.Windows.DataTemplate>sieht unser <xref:System.Windows.Controls.ListBox> derzeit wie folgt aus:  
  
 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Es geschieht, dass die <xref:System.Windows.Controls.ListBox> standardmäßig `ToString` aufruft, wenn versucht wird, die Objekte in der Auflistung anzuzeigen. Wenn das `Task` Objekt die `ToString`-Methode überschreibt, zeigt der <xref:System.Windows.Controls.ListBox> daher die Zeichen folgen Darstellung der einzelnen Quell Objekte in der zugrunde liegenden Auflistung an.  
  
 Wenn z. B. die `Task`-Klasse auf diese Weise die `ToString`-Methode überschreibt, wobei `name` das Feld für die `TaskName`-Eigenschaft darstellt:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Die <xref:System.Windows.Controls.ListBox> sieht dann wie folgt aus:  
  
 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Das ist jedoch einschränkend und unflexibel. Außerdem können Sie, wenn Sie an XML-Daten binden, `ToString`nicht überschreiben.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definieren einer einfachen Datenvorlage  
 Die Lösung besteht darin, eine <xref:System.Windows.DataTemplate>zu definieren. Eine Möglichkeit besteht darin, die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox> auf eine <xref:System.Windows.DataTemplate>festzulegen. Das, was Sie in Ihrem <xref:System.Windows.DataTemplate> angeben, wird zur visuellen Struktur des Datenobjekts. Der folgende <xref:System.Windows.DataTemplate> ist recht einfach. Wir geben Ihnen Anweisungen, dass jedes Element als drei <xref:System.Windows.Controls.TextBlock> Elemente innerhalb einer <xref:System.Windows.Controls.StackPanel>angezeigt wird. Jedes <xref:System.Windows.Controls.TextBlock> Element ist an eine Eigenschaft der `Task` Klasse gebunden.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Die zugrunde liegenden Daten für die Beispiele in diesem Thema sind eine Auflistung von CLR-Objekten. Wenn Sie an XML-Daten binden, sind die grundlegenden Konzepte identisch, aber es gibt einen geringfügigen syntaktischen Unterschied. Anstatt `Path=TaskName`zu haben, würden Sie z. b. <xref:System.Windows.Data.Binding.XPath%2A> auf `@TaskName` festlegen (wenn `TaskName` ein Attribut des XML-Knotens ist).  
  
 Unsere <xref:System.Windows.Controls.ListBox> sieht nun wie folgt aus:  
  
 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Erstellen der Datenvorlage als Ressource  
 Im obigen Beispiel haben wir den <xref:System.Windows.DataTemplate> Inline definiert. Es ist jedoch üblicher, diese im Ressourcenabschnitt zu definieren, damit sie wiederverwendet werden kann, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Sie können `myTaskTemplate` nun als Ressource verwenden, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Da `myTaskTemplate` eine Ressource ist, können Sie Sie jetzt für andere Steuerelemente verwenden, die über eine Eigenschaft verfügen, die einen <xref:System.Windows.DataTemplate>-Typ annimmt. Wie oben gezeigt, ist es für <xref:System.Windows.Controls.ItemsControl>-Objekte, z. b. die <xref:System.Windows.Controls.ListBox>, die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>-Eigenschaft. Bei <xref:System.Windows.Controls.ContentControl>-Objekten ist dies die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>-Eigenschaft.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Die DataType-Eigenschaft  
 Die <xref:System.Windows.DataTemplate>-Klasse verfügt über eine <xref:System.Windows.DataTemplate.DataType%2A>-Eigenschaft, die der <xref:System.Windows.Style.TargetType%2A>-Eigenschaft der <xref:System.Windows.Style>-Klasse sehr ähnlich ist. Daher können Sie anstelle eines `x:Key` für die <xref:System.Windows.DataTemplate> im obigen Beispiel folgende Aktionen ausführen:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Diese <xref:System.Windows.DataTemplate> wird automatisch auf alle `Task` Objekte angewendet. Beachten Sie, dass die `x:Key` in diesem Fall implizit festgelegt wird. Wenn Sie diese <xref:System.Windows.DataTemplate> einem `x:Key` Wert zuweisen, überschreiben Sie daher die impliziten `x:Key`, und der <xref:System.Windows.DataTemplate> wird nicht automatisch angewendet.  
  
 Wenn Sie eine <xref:System.Windows.Controls.ContentControl> an eine Auflistung von `Task` Objekten binden, verwendet der <xref:System.Windows.Controls.ContentControl> den oben genannten <xref:System.Windows.DataTemplate> nicht automatisch. Dies liegt daran, dass die Bindung einer <xref:System.Windows.Controls.ContentControl> mehr Informationen erfordert, um zu unterscheiden, ob Sie eine Bindung an eine gesamte Auflistung oder die einzelnen Objekte vornehmen möchten. Wenn Ihr <xref:System.Windows.Controls.ContentControl> die Auswahl eines <xref:System.Windows.Controls.ItemsControl> Typs nachverfolgt, können Sie die <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft der <xref:System.Windows.Controls.ContentControl> Bindung auf "`/`" festlegen, um anzugeben, dass Sie am aktuellen Element interessiert sind. Ein Beispiel finden Sie unter [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). Andernfalls müssen Sie den <xref:System.Windows.DataTemplate> explizit angeben, indem Sie die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>-Eigenschaft festlegen.  
  
 Die <xref:System.Windows.DataTemplate.DataType%2A>-Eigenschaft ist besonders nützlich, wenn Sie über eine <xref:System.Windows.Data.CompositeCollection> unterschiedlicher Typen von Datenobjekten verfügen. Ein Beispiel finden Sie unter [Implementieren von CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Hinzufügen weiterer Elemente zu DataTemplate  
 Im Moment werden die Daten mit den notwendigen Informationen angezeigt, es sind aber definitiv noch Verbesserungen möglich. Lassen Sie uns die Präsentation verbessern, indem Sie eine <xref:System.Windows.Controls.Border>, eine <xref:System.Windows.Controls.Grid>und einige <xref:System.Windows.Controls.TextBlock> Elemente hinzufügen, die die angezeigten Daten beschreiben.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Der folgende Screenshot zeigt die <xref:System.Windows.Controls.ListBox> mit diesem geänderten <xref:System.Windows.DataTemplate>:  
  
 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Wir können <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> auf die <xref:System.Windows.Controls.ListBox> <xref:System.Windows.HorizontalAlignment.Stretch> festlegen, um sicherzustellen, dass die Breite der Elemente den gesamten Speicherplatz einnimmt:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Wenn die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>-Eigenschaft auf <xref:System.Windows.HorizontalAlignment.Stretch>festgelegt ist, sieht die <xref:System.Windows.Controls.ListBox> nun wie folgt aus:  
  
 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Anwenden von Eigenschaftswerten mit DataTrigger  
 Aus der aktuellen Darstellung geht nicht hervor, ob es sich bei einer `Task` um eine private oder um eine arbeitsbezogene Aufgabe handelt. Beachten Sie, dass das `Task`-Objekt über eine `TaskType`-Eigenschaft des Typs `TaskType` verfügt, die eine Enumeration mit den Werten `Home` und `Work` ist.  
  
 Im folgenden Beispiel legt der <xref:System.Windows.DataTrigger> die <xref:System.Windows.Controls.Border.BorderBrush%2A> des-Elements mit dem Namen `border` auf `Yellow` fest, wenn die `TaskType`-Eigenschaft `TaskType.Home`ist.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Die Anwendung sieht jetzt folgendermaßen aus. Private Aufgaben werden mit einem gelben Rahmen und Office-Aufgaben mit einem hellblauen Rahmen angezeigt:  
  
 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 In diesem Beispiel verwendet die <xref:System.Windows.DataTrigger> eine <xref:System.Windows.Setter>, um einen Eigenschafts Wert festzulegen. Die auslöserklassen verfügen auch über die Eigenschaften <xref:System.Windows.TriggerBase.EnterActions%2A> und <xref:System.Windows.TriggerBase.ExitActions%2A>, mit denen Sie eine Reihe von Aktionen starten können, z. b. Animationen. Außerdem gibt es eine <xref:System.Windows.MultiDataTrigger> Klasse, mit der Sie Änderungen auf der Grundlage mehrerer Daten gebundener Eigenschaftswerte anwenden können.  
  
 Eine alternative Möglichkeit zum Erreichen desselben Effekts besteht darin, die <xref:System.Windows.Controls.Border.BorderBrush%2A>-Eigenschaft an die `TaskType`-Eigenschaft zu binden und einen Wert Konverter zu verwenden, um die Farbe auf der Grundlage des `TaskType` Werts zurückzugeben. Mit Blick auf die Leistung ist es etwas effizienter, für diesen Effekt einen Konverter zu verwenden. Darüber hinaus bietet die Erstellung eines eigenen Konverters eine höhere Flexibilität, da Sie eine eigene Logik verwenden. Für welches Verfahren Sie sich entscheiden, hängt letztlich vom entsprechenden Szenario und Ihren Vorlieben ab. Weitere Informationen zum Schreiben eines Konverters finden Sie unter <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Was gehört in eine DataTemplate?  

Im vorherigen Beispiel wurde der-<xref:System.Windows.DataTemplate> mithilfe des <xref:System.Windows.DataTemplate>in die eingefügt.<xref:System.Windows.DataTemplate.Triggers%2A> -Eigenschaft veranschaulicht. Der <xref:System.Windows.Setter> des Auslösers legt den Wert einer Eigenschaft eines Elements (das <xref:System.Windows.Controls.Border>-Element) fest, das sich innerhalb des <xref:System.Windows.DataTemplate>befindet. Wenn die Eigenschaften, mit denen Ihr `Setters` beschäftigt ist, jedoch keine Eigenschaften von Elementen sind, die sich innerhalb der aktuellen <xref:System.Windows.DataTemplate>befinden, ist es möglicherweise besser, die Eigenschaften mithilfe eines <xref:System.Windows.Style> festzulegen, das für die <xref:System.Windows.Controls.ListBoxItem> Klasse gilt (wenn das Steuerelement, das Sie binden, ein <xref:System.Windows.Controls.ListBox>). Wenn Sie z. b. möchten, dass Ihr <xref:System.Windows.Trigger> den <xref:System.Windows.UIElement.Opacity%2A> Wert des Elements animieren soll, wenn ein Mauszeiger auf ein Element zeigt, definieren Sie Trigger innerhalb eines <xref:System.Windows.Controls.ListBoxItem> Stils. Ein Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 Im Allgemeinen sollten Sie Bedenken, dass die <xref:System.Windows.DataTemplate> auf die einzelnen generierten <xref:System.Windows.Controls.ListBoxItem> angewendet wird (Weitere Informationen dazu, wie und wo Sie tatsächlich angewendet werden, finden Sie auf der Seite <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.) Ihr <xref:System.Windows.DataTemplate> betrifft nur die Darstellung und Darstellung der Datenobjekte. In den meisten Fällen gehören alle anderen Aspekte der Präsentation, wie z. b. das Aussehen eines Elements, wenn es ausgewählt ist, oder das <xref:System.Windows.Controls.ListBox>, das die Elemente festlegt, nicht zur Definition einer <xref:System.Windows.DataTemplate>. Ein Beispiel finden Sie im Abschnitt [Formatieren und Erstellen von Vorlagen für ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Auswählen einer DataTemplate anhand von Eigenschaften des Datenobjekts  
 Im Abschnitt [Die DataType-Eigenschaft](#Styling_DataType) wurde erläutert, dass Sie verschiedene Datenvorlagen für verschiedene Datenobjekte definieren können. Dies ist besonders nützlich, wenn Sie über eine <xref:System.Windows.Data.CompositeCollection> verschiedener Typen oder Sammlungen mit Elementen verschiedener Typen verfügen. Im Abschnitt [Verwenden von DataTriggers zum Anwenden von Eigenschafts Werten](#DataTrigger_to_Apply_Property_Values) haben wir gezeigt, dass Sie, wenn Sie über eine Auflistung desselben Typs von Datenobjekten verfügen, eine <xref:System.Windows.DataTemplate> erstellen und dann mithilfe von Triggern Änderungen auf der Grundlage der Eigenschaftswerte jedes Datenobjekts anwenden können. Mit Triggern können Sie Eigenschaftswerte anwenden oder Animationen starten, sie verfügen jedoch nicht über die nötige Flexibilität, um die Struktur der Datenobjekte zu rekonstruieren. In einigen Szenarien ist es möglicherweise erforderlich, dass Sie eine andere <xref:System.Windows.DataTemplate> für Datenobjekte erstellen, die denselben Typ aufweisen, aber über unterschiedliche Eigenschaften verfügen.  
  
 Wenn z. B. ein `Task`-Objekt den `Priority`-Wert `1` hat, kann es sinnvoll sein, ihm ein völlig anderes Erscheinungsbild zuzuweisen, um als Warnung zu dienen. In diesem Fall erstellen Sie eine <xref:System.Windows.DataTemplate> für die Anzeige der `Task` Objekte mit hoher Priorität. Fügen Sie dem Ressourcenabschnitt folgende <xref:System.Windows.DataTemplate> hinzu:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Beachten Sie, dass in diesem Beispiel die <xref:System.Windows.DataTemplate>verwendet wird.<xref:System.Windows.FrameworkTemplate.Resources%2A> -Eigenschaft veranschaulicht. Die in diesem Abschnitt definierten Ressourcen werden von den Elementen innerhalb der <xref:System.Windows.DataTemplate>gemeinsam genutzt.  
  
 Erstellen Sie eine Unterklasse von <xref:System.Windows.Controls.DataTemplateSelector>, und überschreiben Sie die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>-Methode, um zu bestimmen, welche <xref:System.Windows.DataTemplate> basierend auf dem `Priority` Wert des Datenobjekts verwendet werden soll. Im folgenden Beispiel stellt die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>-Methode Logik bereit, um die entsprechende Vorlage basierend auf dem Wert der `Priority`-Eigenschaft zurückzugeben. Die zurück zugebende Vorlage befindet sich in den Ressourcen des umschließenden <xref:System.Windows.Window>-Elements.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Wir können dann den `TaskListDataTemplateSelector` als Ressource deklarieren:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Um die Vorlagen Auswahl Ressource zu verwenden, weisen Sie Sie der <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox>zu. Der <xref:System.Windows.Controls.ListBox> Ruft die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>-Methode der `TaskListDataTemplateSelector` für jedes der Elemente in der zugrunde liegenden Auflistung auf. Beim Aufruf wird das Datenobjekt als Elementparameter übergeben. Der <xref:System.Windows.DataTemplate>, der von der-Methode zurückgegeben wird, wird dann auf das Datenobjekt angewendet.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Wenn die Vorlagen Auswahl eingerichtet ist, wird der <xref:System.Windows.Controls.ListBox> jetzt wie folgt angezeigt:  
  
 ![Screenshot: Beispiel für Datenvorlagen](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Damit ist die Erläuterung unseres Beispiels abgeschlossen. Das vollständige Beispiel finden Sie unter [Einführung in das Datenvorlagenbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Formatierung und Vorlagen für ItemsControl  
 Obwohl der <xref:System.Windows.Controls.ItemsControl> nicht der einzige Steuer ungstyp ist, den Sie mit einem <xref:System.Windows.DataTemplate> verwenden können, ist es ein gängiges Szenario, eine <xref:System.Windows.Controls.ItemsControl> an eine Sammlung zu binden. Im Abschnitt [Was gehört zu einem DataTemplate](#what_belongs_in_datatemplate) -Abschnitt wurde erläutert, dass die Definition ihrer <xref:System.Windows.DataTemplate> nur die Darstellung von Daten betreffen sollte. Um zu wissen, wann es nicht für die Verwendung einer <xref:System.Windows.DataTemplate> geeignet ist, müssen Sie sich mit den unterschiedlichen Stil-und Vorlagen Eigenschaften vertraut machen, die vom <xref:System.Windows.Controls.ItemsControl>bereitgestellt werden. Anhand des folgenden Beispiels soll die jeweilige Funktion dieser Eigenschaften veranschaulicht werden. Der <xref:System.Windows.Controls.ItemsControl> in diesem Beispiel ist an dieselbe `Tasks` Auflistung gebunden wie im vorherigen Beispiel. Zu Demonstrationszwecken werden die Formate und die Vorlagen in diesem Beispiel inline deklariert.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Im Folgenden sehen Sie ein Bildschirmfoto des Beispiels nach dem Rendern:  
  
 ![Bildschirm Abbildung von ItemsControl-Beispielen](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Beachten Sie, dass Sie anstelle der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>die <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>verwenden können. Ein Beispiel finden Sie im vorherigen Abschnitt. Ebenso haben Sie die Möglichkeit, die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>zu verwenden, anstatt die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>zu verwenden.  
  
 Zwei weitere Stil bezogene Eigenschaften der <xref:System.Windows.Controls.ItemsControl>, die hier nicht angezeigt werden, sind <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> und <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Unterstützung für hierarchische Daten  
 Bisher haben wir nur erläutert, wie eine einzelne Auflistung gebunden und angezeigt wird. Mitunter kann eine Auflistung auch andere Auflistungen enthalten. Die <xref:System.Windows.HierarchicalDataTemplate>-Klasse ist so konzipiert, dass Sie mit <xref:System.Windows.Controls.HeaderedItemsControl> Typen verwendet wird, um solche Daten anzuzeigen. Im folgenden Beispiel ist `ListLeagueList` eine Liste von `League`-Objekten. Jedes `League`-Objekt verfügt über einen `Name` und eine Auflistung von `Division`-Objekten. Jede `Division` verfügt über einen `Name` und eine Auflistung von `Team`-Objekten, und `Team`Team-Objekt verfügt über einen `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Das Beispiel zeigt, dass Sie mit <xref:System.Windows.HierarchicalDataTemplate>problemlos Listen Daten anzeigen können, die andere Listen enthalten. Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.  
  
 ![Hierarchcaldatatemplate-Beispiel Bildschirmfoto](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Siehe auch

- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
- [Suchen von Elementen, die mit einer DataTemplate generiert wurden](how-to-find-datatemplate-generated-elements.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../controls/gridview-column-header-styles-and-templates-overview.md)
