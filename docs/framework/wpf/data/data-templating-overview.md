---
title: "&#220;bersicht &#252;ber Datenvorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenbindung Vorlagen"
  - "Binden von Daten, Vorlagen"
  - "Daten-Vorlagen"
  - "Datenvorlagen"
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# &#220;bersicht &#252;ber Datenvorlagen
Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Templating Datenmodell bietet Ihnen flexibel definieren die Darstellung Ihrer Daten. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Steuerelemente verfügen über integrierte Funktionen, um die Anpassung der Darstellung von Daten zu unterstützen. In diesem Thema veranschaulicht, wie definieren Sie zuerst eine <xref:System.Windows.DataTemplate> und führt dann andere Templating-Features, wie z. B. die Auswahl von Vorlagen, die basierend auf benutzerdefinierte Logik und die Unterstützung für die Anzeige von hierarchischen Daten.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Dieses Thema konzentriert sich auf Data Templating-Features und ist keine Einführung der Datenbindungskonzepte. Informationen über grundlegende Datenbindungskonzepte finden Sie unter der [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> geht es um die Darstellung von Daten und ist eines der zahlreichen Features von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von Formaten und Vorlagen-Modell. Eine Einführung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Modell von Formaten und Vorlagen, z. B. wie eine <xref:System.Windows.Style> zum Festlegen von Eigenschaften für Steuerelemente finden Sie unter der [von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md) Thema.  
  
 Darüber hinaus ist es wichtig zu verstehen, `Resources`, welche Objekte wie z. B. aktivieren sind <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> wiederverwendet werden soll. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Grundlagen zu Datenvorlagen  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
 Warum veranschaulichen <xref:System.Windows.DataTemplate> ist wichtig, betrachten wir ein Beispiel für die Daten binden. In diesem Beispiel haben wir eine <xref:System.Windows.Controls.ListBox> Bindung an eine Liste der `Task` Objekte. Jede `Task` Objekt verfügt über eine `TaskName` (Zeichenfolge), ein `Description` (Zeichenfolge), ein `Priority` (Int), und eine Eigenschaft des Typs `TaskType`, also ein `Enum` mit Werten `Home` und `Work`.  
  
 [!code-xml[DataTemplatingIntro_snip#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xml[DataTemplatingIntro_snip#UI1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xml[DataTemplatingIntro_snip#UI2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Ohne DataTemplate  
 Ohne ein <xref:System.Windows.DataTemplate>, unsere <xref:System.Windows.Controls.ListBox> derzeit sieht wie folgt:  
  
 ![Beispiel bildschirmabbildung für Datenvorlagen](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Was passiert ist, ohne alle Informationen, die <xref:System.Windows.Controls.ListBox> von Standard-Aufrufe `ToString` beim Anzeigen der Objekte in der Auflistung. Daher, wenn die `Task` -Objekt überschreibt die `ToString` -Methode, die <xref:System.Windows.Controls.ListBox> zeigt die Darstellung der einzelnen Quellobjekt in der zugrunde liegenden Auflistung.  
  
 Z. B. wenn die `Task` -Klasse überschreibt die `ToString` Methode auf diese Weise, in denen `name` ist das Feld für die `TaskName` Eigenschaft:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Die <xref:System.Windows.Controls.ListBox> wie folgt aussieht:  
  
 ![Beispiel bildschirmabbildung für Datenvorlagen](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Das ist jedoch einschränkend und unflexibel. Auch wenn Sie eine Bindung an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten, Sie wäre nicht überschreiben `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definieren einer einfachen DataTemplate  
 Die Lösung besteht darin, definieren Sie eine <xref:System.Windows.DataTemplate>. Eine Möglichkeit dafür ist das Festlegen der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> zu einer <xref:System.Windows.DataTemplate>. Angeben der <xref:System.Windows.DataTemplate> bilden die visuelle Struktur des Datenobjekts. Die folgenden <xref:System.Windows.DataTemplate> ist recht einfach. Wir werden Anweisungen, die jedes Element als drei angezeigt wird, gewähren <xref:System.Windows.Controls.TextBlock> Elemente innerhalb einer <xref:System.Windows.Controls.StackPanel>. Jede <xref:System.Windows.Controls.TextBlock> Element an eine Eigenschaft gebunden ist die `Task` Klasse.  
  
 [!code-xml[DataTemplatingIntro_snip#Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Die zugrunde liegenden Daten für die Beispiele in diesem Thema ist eine Sammlung von [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Objekte. Wenn Sie eine Bindung an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten, die grundlegenden Konzepte sind identisch, aber es gibt syntaktischen Unterschiede. Z. B. statt `Path=TaskName`, legen Sie <xref:System.Windows.Data.Binding.XPath%2A> auf `@TaskName` (Wenn `TaskName` ist ein Attribut des Ihrer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Knoten).  
  
 Jetzt unsere <xref:System.Windows.Controls.ListBox> wie folgt aussieht:  
  
 ![Beispiel bildschirmabbildung für Datenvorlagen](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Erstellen der DataTemplate als Ressource  
 Im obigen Beispiel definiert die <xref:System.Windows.DataTemplate> Inline. Es ist üblicher im Ressourcenabschnitt definieren, sodass sie ein wiederverwendbares Objekt, wie im folgenden Beispiel werden kann:  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#AsResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Nun können Sie `myTaskTemplate` als Ressource, wie im folgenden Beispiel:  
  
 [!code-xml[DataTemplatingIntro_snip#MyTaskTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Da `myTaskTemplate` ist eine Ressource, jetzt können Sie sie für andere Steuerelemente, die über eine Eigenschaft verfügen, die akzeptiert ein <xref:System.Windows.DataTemplate> Typ. Wie oben gezeigt, für <xref:System.Windows.Controls.ItemsControl> Objekte, z. B. die <xref:System.Windows.Controls.ListBox>, ist die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft. Für <xref:System.Windows.Controls.ContentControl> -Objekten ist es die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Die DataType-Eigenschaft  
 Die <xref:System.Windows.DataTemplate> -Klasse verfügt über eine <xref:System.Windows.DataTemplate.DataType%2A> -Eigenschaft, die sehr ähnlich ist der <xref:System.Windows.Style.TargetType%2A> Eigenschaft der <xref:System.Windows.Style> Klasse. Aus diesem Grund anstelle einer `x:Key` für die <xref:System.Windows.DataTemplate> im obigen Beispiel können Sie Folgendes tun:  
  
 [!code-xml[DataTemplatingIntro_snip#DataType](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Diese <xref:System.Windows.DataTemplate> wird automatisch auf alle angewendet `Task` Objekte. Beachten Sie, dass in diesem Fall die `x:Key` implizit festgelegt. Daher diese Zuweisung <xref:System.Windows.DataTemplate> ein `x:Key` Wert, überschreiben Sie den impliziten `x:Key` und <xref:System.Windows.DataTemplate> wird nicht automatisch angewendet.  
  
 Wenn Sie binden ein <xref:System.Windows.Controls.ContentControl> auf eine Auflistung von `Task` Objekte, die <xref:System.Windows.Controls.ContentControl> verwendet keine der oben genannten <xref:System.Windows.DataTemplate> automatisch. Grund hierfür ist die Bindung einer <xref:System.Windows.Controls.ContentControl> benötigt weitere Informationen zu unterscheiden, ob Sie eine vollständige Auflistung und die einzelnen Objekte binden möchten. Wenn Ihre <xref:System.Windows.Controls.ContentControl> verfolgt die Auswahl der ein <xref:System.Windows.Controls.ItemsControl> geben, können Sie festlegen der <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft der <xref:System.Windows.Controls.ContentControl> Binden an "`/`" an, dass Sie das aktuelle Element interessiert sind. Ein Beispiel finden Sie unter [Binden an eine Sammlung und Anzeige Informationen basieren auf der Auswahl des](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md). Andernfalls müssen Sie an der <xref:System.Windows.DataTemplate> explizit durch Festlegen der <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft.  
  
 Die <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft ist besonders nützlich, wenn Sie haben eine <xref:System.Windows.Data.CompositeCollection> verschiedener Typen von Objekten. Ein Beispiel finden Sie unter [Implementieren einer CompositeCollection](../../../../docs/framework/wpf/data/how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Hinzufügen weiterer Elemente zur DataTemplate  
 Die Daten aktuell angezeigt wird, die notwendigen Informationen, es ist jedoch definitiv verbessert. Wir verbessern die Präsentation durch Hinzufügen einer <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>, und einige <xref:System.Windows.Controls.TextBlock> Elemente, die die Daten beschreiben, die angezeigt wird.  
  
 [!code-xml[DataTemplatingIntro#AddingMore](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Der folgende Screenshot zeigt die <xref:System.Windows.Controls.ListBox> mit dieser Änderung <xref:System.Windows.DataTemplate>:  
  
 ![Beispiel bildschirmabbildung für Datenvorlagen](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Wir lassen sich <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> zu <xref:System.Windows.HorizontalAlignment> auf der <xref:System.Windows.Controls.ListBox> um sicherzustellen, dass die Breite der Elemente belegt den gesamten Speicherplatz:  
  
 [!code-xml[DataTemplatingIntro_snip#Stretch](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Mit der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> Eigenschaft festgelegt, um <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.ListBox> sieht nun:  
  
 ![Beispiel bildschirmabbildung für Datenvorlagen](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Verwenden Sie DataTrigger, um Eigenschaftswerte anzuwenden  
 Die aktuelle Präsentation geht nicht hervor, ob ein `Task` ist eine private oder eine Office-Aufgabe. Beachten Sie, dass die `Task` Objekt verfügt über eine `TaskType` Eigenschaft vom Typ `TaskType`, eine Enumeration mit den Werten `Home` und `Work`.  
  
 Im folgenden Beispiel die <xref:System.Windows.DataTrigger> legt die <xref:System.Windows.Controls.Border.BorderBrush%2A> des Elements namens `border` auf `Yellow` Wenn die `TaskType` Eigenschaft ist `TaskType.Home`.  
  
 [!code-xml[DataTemplatingIntro#DT](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xml[DataTemplatingIntro#DataTrigger](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Die Anwendung sieht folgendermaßen aus. Private Aufgaben werden mit einem gelben Rahmen und Office-Aufgaben mit einem hellblauen Rahmen angezeigt:  
  
 ![Beispiel bildschirmabbildung für Datenvorlagen](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 In diesem Beispiel wird die <xref:System.Windows.DataTrigger> verwendet eine <xref:System.Windows.Setter> einen Eigenschaftswert fest. Der Trigger-Klassen verfügen ebenfalls über die <xref:System.Windows.TriggerBase.EnterActions%2A> und <xref:System.Windows.TriggerBase.ExitActions%2A> Eigenschaften, mit denen Sie eine Reihe von Aktionen, wie z. B. Animationen starten können. Darüber hinaus steht eine <xref:System.Windows.MultiDataTrigger> -Klasse, die Sie ändern kann auf der Grundlage von Werten für mehrere datengebundene Eigenschaft.  
  
 Eine alternative Möglichkeit, den gleichen Effekt zu erzielen, besteht darin, binden die <xref:System.Windows.Controls.Border.BorderBrush%2A> Eigenschaft, um die `TaskType` -Eigenschaft und verwendet ein Wertkonverter, die Farbe zurück, die auf Grundlage der `TaskType` Wert. Diesen Effekt mit einem Konverter ist etwas effizienter hinsichtlich der Leistung. Darüber hinaus Flexibilität erstellen einen eigenen Konverter mehr, da Sie Ihre eigene Logik bereitstellen. Letzten Endes hängt von der gewählten Methode Ihr Szenario und Ihren Vorlieben. Weitere Informationen zum Schreiben eines Konverters finden Sie unter <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Was gehört in eine DataTemplate?  
 Im vorherigen Beispiel haben wir den Trigger die <xref:System.Windows.DataTemplate> mithilfe der <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> Eigenschaft. Die <xref:System.Windows.Setter> des Triggers legt den Wert einer Eigenschaft eines Elements (die <xref:System.Windows.Controls.Border> Element), der sich im die <xref:System.Windows.DataTemplate>. Jedoch wenn die Eigenschaften, Ihre `Setters` von Belang sind sind keine Eigenschaften von Elementen, die in der aktuellen <xref:System.Windows.DataTemplate>, möglicherweise besser geeignet, zum Festlegen der Eigenschaften, die mit einer <xref:System.Windows.Style> , ist die <xref:System.Windows.Controls.ListBoxItem> Klasse (ist das Steuerelement, das Sie binden ein <xref:System.Windows.Controls.ListBox>). Angenommen, Sie möchten Ihre <xref:System.Windows.Trigger> Animieren der <xref:System.Windows.UIElement.Opacity%2A> Wert des Elements, wenn eine Maus auf ein Element verweist, definieren Sie die Trigger innerhalb einer <xref:System.Windows.Controls.ListBoxItem> Stil. Ein Beispiel finden Sie unter der [Introduction to Styling and Templating Sample](http://go.microsoft.com/fwlink/?LinkID=160010).  
  
 Im Allgemeinen, Bedenken Sie, dass die <xref:System.Windows.DataTemplate> angewendet wird jedes erstellte <xref:System.Windows.Controls.ListBoxItem> (Weitere Informationen dazu, wie und wo tatsächlich angewandt wird, finden Sie unter der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Seite.). Ihre <xref:System.Windows.DataTemplate> wird nur die Darstellung und das Erscheinungsbild der Datenobjekte von Belang. In den meisten Fällen sieht alle anderen Aspekte der Darstellung, z. B. welche ein Element wie wenn es ausgewählt wird oder wie die <xref:System.Windows.Controls.ListBox> Anordnung der Elemente gehören nicht in der Definition einer <xref:System.Windows.DataTemplate>. Ein Beispiel finden Sie unter der [von Formaten und Vorlagen für ItemsControl](#DataTemplating_ItemsControl) Abschnitt.  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Auswählen einer DataTemplate anhand der Eigenschaften des Datenobjekts  
 In [die DataType-Eigenschaft](#Styling_DataType) Abschnitt wird erläutert, dass Sie verschiedene Datenvorlagen für verschiedene Datenobjekte definieren können. Das ist besonders nützlich, wenn Sie haben eine <xref:System.Windows.Data.CompositeCollection> von anderen Typen oder Sammlungen mit Elemente unterschiedlichen Typs. In der [DataTrigger verwenden, um Eigenschaftswerte gelten](#DataTrigger_to_Apply_Property_Values) Abschnitt haben wir gezeigt, wenn eine von Objekten desselben Typs Sammlung erstellen kann ein <xref:System.Windows.DataTemplate> und verwenden Sie Trigger, um anhand der Eigenschaftswerte der einzelnen Datenobjekte Änderungen zu übernehmen. Trigger können Sie Eigenschaftswerte anwenden oder Animationen starten jedoch sie nicht bieten Ihnen die Flexibilität, die Struktur der Datenobjekte zu rekonstruieren. Einige Szenarien müssen Sie möglicherweise ein anderes erstellen <xref:System.Windows.DataTemplate> für Daten Objekte, die der gleichen geben jedoch über verschiedene Eigenschaften verfügen.  
  
 Beispielsweise, wenn ein `Task` Objekt verfügt über eine `Priority` Wert `1`, kann es ein völlig anderes Erscheinungsbild, um als Warnung zu dienen erhalten soll. In diesem Fall erstellen Sie eine <xref:System.Windows.DataTemplate> für die Anzeige von hoher Priorität `Task` Objekte. Fügen Sie die folgenden <xref:System.Windows.DataTemplate> Abschnitt Ressourcen:  
  
 [!code-xml[DataTemplatingIntro_snip#ImportantTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Beachten Sie in diesem Beispiel verwendet die <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> Eigenschaft. Ressourcen, die definiert, Abschnitt werden gemeinsam genutzt, von den Elementen in der <xref:System.Windows.DataTemplate>.  
  
 Wählen Sie die Logik bereitstellen <xref:System.Windows.DataTemplate> auf der Grundlage der `Priority` Wert des Datenobjekts, erstellen Sie eine Unterklasse von <xref:System.Windows.Controls.DataTemplateSelector> und überschreiben die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode. Im folgenden Beispiel die <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode stellt die Logik zum Zurückgeben der entsprechenden Vorlage basierend auf den Wert der `Priority` Eigenschaft. Die Vorlage, die zurückgegeben befindet sich in den Ressourcen des umschließenden <xref:System.Windows.Window> Element.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Wir können dann deklarieren die `TaskListDataTemplateSelector` als Ressource:  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#DTS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Um die Vorlagenauswahlressource verwenden zu können, weisen Sie ihn der <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox>. Die <xref:System.Windows.Controls.ListBox> Aufrufe der <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> Methode der `TaskListDataTemplateSelector` für jedes der Elemente in der zugrunde liegenden Auflistung. Der Aufruf wird das Datenobjekt als Elementparameter übergeben. Die <xref:System.Windows.DataTemplate> zurückgegeben wird die Methode dann auf dieses Datenobjekt angewendet wird.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemTemplateSelector](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Mit der Vorlagenauswahl die <xref:System.Windows.Controls.ListBox> nun wie folgt angezeigt:  
  
 ![Beispiel bildschirmabbildung für Datenvorlagen](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  
  
 Unsere Diskussion in diesem Beispiel ist nun abgeschlossen. Das vollständige Beispiel finden Sie unter [Introduction to Data Templating Sample](http://go.microsoft.com/fwlink/?LinkID=160009).  
  
<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Erstellen von Formaten und Vorlagen für ItemsControl  
 Obwohl die <xref:System.Windows.Controls.ItemsControl> ist nicht der einzige Steuerelementtyp, mit denen Sie eine <xref:System.Windows.DataTemplate> , es ist ein sehr häufiges Szenario binden ein <xref:System.Windows.Controls.ItemsControl> an eine Auflistung. In der [Was gehört in eine DataTemplate](#what_belongs_in_datatemplate) Abschnitt besprochen, die die Definition der <xref:System.Windows.DataTemplate> sollte nur die Darstellung der Daten. Um zu wissen, wann nicht geeignet ist, verwenden Sie eine <xref:System.Windows.DataTemplate> es ist wichtig zu verstehen, die verschiedenen Stil- und Eigenschaften, die von bereitgestellten der <xref:System.Windows.Controls.ItemsControl>. Im folgende Beispiel soll veranschaulichen Sie die Funktion der einzelnen Eigenschaften. Die <xref:System.Windows.Controls.ItemsControl> in diesem Beispiel wird auf die gleiche gebunden `Tasks` Auflistung wie im vorherigen Beispiel. Zur Veranschaulichung können Zwecke, die Stile und Vorlagen in diesem Beispiel Inline deklariert.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemsControlProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Im folgenden wird ein Screenshot des Beispiels, beim Rendern:  
  
 ![ItemsControl-Beispiel-Screenshot](../../../../docs/framework/wpf/data/media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Beachten Sie, dass anstelle der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, können Sie die <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Finden Sie ein Beispiel für die im vorherigen Abschnitt. Auf ähnliche Weise statt der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, Sie haben die Möglichkeit, die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Zwei weitere Formatvorlagen bezogenen Eigenschaften für die <xref:System.Windows.Controls.ItemsControl> , sind nicht hier gezeigten <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> und <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Unterstützung für hierarchische Daten  
 Bisher haben wir nur erläutert, wie zuweisen und Anzeigen einer einzelnen Auflistung. Manchmal müssen Sie eine Sammlung mit anderen Sammlungen. Die <xref:System.Windows.HierarchicalDataTemplate> -Klasse kann mit <xref:System.Windows.Controls.HeaderedItemsControl> Typen auf solche Daten anzuzeigen. Im folgenden Beispiel `ListLeagueList` ist eine Liste der `League` Objekte. Jede `League` Objekt verfügt über eine `Name` und eine Auflistung von `Division` Objekte. Jede `Division` hat ein `Name` und eine Auflistung von `Team` Objekten, und jedes `Team` Objekt verfügt über eine `Name`.  
  
 [!code-xml[HierarchicalDataTemplateSnippet#HDT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Das Beispiel zeigt, mit der Verwendung von <xref:System.Windows.HierarchicalDataTemplate>, Sie können anzeigen, Daten, die andere Listen enthalten. Im folgenden ist ein Screenshot des Beispiels.  
  
 ![Bildschirmabbildung für HierarchicalDataTemplate Beispiel](../../../../docs/framework/wpf/data/media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Suchen von Elementen einer DataTemplate generiert wurden](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [Von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über die Bindung von Daten](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [GridView-Spaltenheaderstile und Übersicht über Vorlagen](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)