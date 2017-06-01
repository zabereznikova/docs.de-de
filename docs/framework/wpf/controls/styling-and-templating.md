---
title: "Erstellen von Formaten und Vorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Trigger"
  - "Stile, verweisen auf"
  - "Ereignistrigger"
  - "Stile, erforderliche Komponenten"
  - "Deklarieren von Stilen"
  - "Stile, Übersicht"
  - "Erweitern von Formaten"
  - "Stile, Trigger"
  - "Formatvorlagen-Ereignis ausgelöst"
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Erstellen von Formaten und Vorlagen
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]von Formaten und Vorlagen finden Sie in eine Suite von Features (Formate, Vorlagen, Trigger und Storyboards), mit denen Entwickler und Designer visuell überzeugende Effekte erzeugen und ein einheitliches Erscheinungsbild ihres Produkts zu erstellen. Entwickler und Designer die Darstellung häufig auf der Grundlage von Anwendung angepasst werden können, ist ein sicheres Modell von Formaten und Vorlagen erforderlich, Wartung und Freigabe der Darstellung innerhalb und zwischen Anwendungen zu ermöglichen. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]stellt dieses Modell bereit.  
  
 Ein weiteres Feature von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stil Modell ist die Trennung von Darstellung und Logik. Dies bedeutet, dass Designer auf die Darstellung einer Anwendung können nur mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zur gleichen Zeit, die Entwickler die Programmierlogik mit c# oder Visual Basic.  
  
 Diese Übersicht konzentriert sich auf die von Formaten und Vorlagen Aspekte der Anwendung und keine Datenbindungskonzepte behandelt. Informationen zum Binden von Daten finden Sie unter [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Darüber hinaus ist es wichtig zu verstehen, Ressourcen, die Stile und Vorlagen für die Wiederverwendung ermöglichen. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
   
  
<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>Erstellen von Formaten und Beispiel  
 In dieser Übersicht verwendeten Codebeispiele basieren auf einem einfachen Foto-Beispiel in der folgenden Abbildung dargestellt:  
  
 ![ListView formatiert](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 In diesem einfachen Foto-Beispiel werden von Formaten und Vorlagen verwendet, um eine visuell beeindruckende Benutzeroberfläche zu erstellen. Das Beispiel verfügt über zwei <xref:System.Windows.Controls.TextBlock> Elemente und <xref:System.Windows.Controls.ListBox> Steuerelement, das an eine Liste von Bildern gebunden ist. Das vollständige Beispiel finden Sie unter [Introduction to Styling and Templating Sample](http://go.microsoft.com/fwlink/?LinkID=160010).  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>Grundlagen zu Formaten  
 Sie können sich vorstellen, eine <xref:System.Windows.Style> als eine einfache Möglichkeit, eine Reihe von Eigenschaftswerten auf mehr als ein Element anzuwenden. Betrachten Sie z. B. die folgenden <xref:System.Windows.Controls.TextBlock> Elemente und deren Erscheinungsbild:  
  
 [!code-xml[StylingIntroSample_snippet#TextBlocks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![Stil-Beispiel-Screenshot](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")  
  
 Sie können das Erscheinungsbild ändern, indem Sie Eigenschaften festlegen, z. B. <xref:System.Windows.Controls.Control.FontSize%2A> und <xref:System.Windows.Controls.Control.FontFamily%2A>, auf jedem <xref:System.Windows.Controls.TextBlock> Element direkt. Jedoch ggf. Ihre <xref:System.Windows.Controls.TextBlock> -Elemente einige Eigenschaften gemeinsam nutzen können eine <xref:System.Windows.Style> in der `Resources` Teil Ihrer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei, wie hier gezeigt:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Beim Festlegen der <xref:System.Windows.Style.TargetType%2A> des Formats auf die <xref:System.Windows.Controls.TextBlock> Typ, der Stil angewendet wird, auf alle die <xref:System.Windows.Controls.TextBlock> Elemente im Fenster.  
  
 Jetzt die <xref:System.Windows.Controls.TextBlock> Elemente wie folgt aussehen:  
  
 ![Stil-Beispiel-Screenshot](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>Erweitern von Formaten  
 Vielleicht möchten Sie die beiden <xref:System.Windows.Controls.TextBlock> -Elemente einige Eigenschaftswerte wie z. B. die <xref:System.Windows.Controls.Control.FontFamily%2A> und die zentrierte <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, aber der Text "My Pictures" zusätzliche Eigenschaften haben soll. Sie können hierzu erstellen ein neues Format, das auf dem ersten Format basiert, wie hier gezeigt:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Beachten Sie, das das vorherige Format angegebenen ist ein `x:Key`. Zum Anwenden des Formats legen Sie die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft auf Ihre <xref:System.Windows.Controls.TextBlock> zu den `x:Key` -Wert fest, wie hier gezeigt:  
  
 [!code-xml[StylingIntroSnippet#UIText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 Dies <xref:System.Windows.Controls.TextBlock> Stil verfügt jetzt über eine <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Wert der <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.TextBlock.FontFamily%2A> Wert `Comic Sans MS`, <xref:System.Windows.Controls.TextBlock.FontSize%2A> -Wert von 26 und ein <xref:System.Windows.Controls.TextBlock.Foreground%2A> Wert festgelegt der <xref:System.Windows.Media.LinearGradientBrush> im Beispiel gezeigt. Beachten Sie, den sie überschreibt die <xref:System.Windows.Controls.Control.FontSize%2A> Wert, der die Basis-Format. Wenn es mehr als eine <xref:System.Windows.Setter> dieselbe Eigenschaft festlegen, eine <xref:System.Windows.Style>, <xref:System.Windows.Setter> , deklarierten letzten hat Vorrang.  
  
 Das folgende Beispiel zeigt, was die <xref:System.Windows.Controls.TextBlock> Elemente wie folgt aussehen:  
  
 ![Formatiert TextBlocks](../../../../docs/framework/wpf/controls/media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 Diese `TitleText` Stil erweitert die Formatvorlage, die für die Erstellung der <xref:System.Windows.Controls.TextBlock> Typ. Sie können auch eine Formatvorlage mit erweitern ein `x:Key` mithilfe der `x:Key` Wert. Ein Beispiel finden Sie im Beispiel für die <xref:System.Windows.Style.BasedOn%2A> Eigenschaft.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Beziehung zwischen der TargetType-Eigenschaft und das X: Key-Attribut  
 Wie im ersten Beispiel gezeigt, Festlegen der <xref:System.Windows.Style.TargetType%2A> -Eigenschaft `TextBlock` ohne das Format zuzuweisen ein `x:Key` , wird auf alle angewendet <xref:System.Windows.Controls.TextBlock> Elemente. In diesem Fall die `x:Key` implizit auf festgelegt ist `{x:Type TextBlock}`. Dies bedeutet, dass, wenn Sie explizit die `x:Key` auf einen anderen Wert als `{x:Type TextBlock}`, <xref:System.Windows.Style> gilt nicht für alle <xref:System.Windows.Controls.TextBlock> Elemente automatisch. Stattdessen müssen Sie die Formatvorlage anwenden (mithilfe der `x:Key` Wert), die <xref:System.Windows.Controls.TextBlock> Elemente explizit. Wenn sich das Format im Ressourcenabschnitt und nicht Festlegen der <xref:System.Windows.Style.TargetType%2A> -Eigenschaft auf die Formatvorlage, und Sie muss Bereitstellen einer `x:Key`.  
  
 Zusätzlich zur Bereitstellung eines Standardwerts für die `x:Key`, <xref:System.Windows.Style.TargetType%2A> -Eigenschaft gibt den Typ für die Setter-Eigenschaften gelten. Wenn Sie nicht angeben einer <xref:System.Windows.Style.TargetType%2A>, müssen Sie die Eigenschaften im qualifizieren der <xref:System.Windows.Setter> Objekte mit dem Klassennamen mithilfe der Syntax `Property="ClassName.Property"`. Anstatt z. B. `Property="FontSize"`, müssen Sie festlegen, <xref:System.Windows.Setter.Property%2A> auf `"TextBlock.FontSize"` oder `"Control.FontSize"`.  
  
 Beachten Sie außerdem, dass viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente bestehen aus einer Kombination von anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente. Wenn Sie eine Formatvorlage, die auf alle Steuerelemente eines Typs angewendet wird erstellen, erhalten Sie möglicherweise unerwartete Ergebnisse. Beispielsweise, wenn Sie eine Formatvorlage erstellen, die <xref:System.Windows.Controls.TextBlock> Geben Sie ein <xref:System.Windows.Window>, der Stil angewendet wird, um alle <xref:System.Windows.Controls.TextBlock> Steuerelemente im Fenster selbst wenn die <xref:System.Windows.Controls.TextBlock> ist Teil eines anderen Steuerelements, wie z. B. ein <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>Formate und Ressourcen  
 Verwenden Sie einen Stil auf alle Elemente, die von abgeleitet ist <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Die gängigste Methode zum Deklarieren einer Formatvorlage wird als Ressource in die `Resources` im Abschnitt eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei, wie in den vorherigen Beispielen gezeigt. Da Stilen um Ressourcen handelt, unterliegen sie die gleichen Bereichsregeln, die für alle Ressourcen gelten; in dem Sie eine Formatvorlage wirkt sich auf deklarieren, der Stil angewendet werden kann. Wenn Sie das Format in das Stammelement Ihrer Anwendungsdefinition deklarieren z. B. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei kann das Format überall in der Anwendung verwendet werden. Wenn Sie eine navigationsanwendung erstellen, und deklarieren die Formatvorlage in einer von der Anwendungsverzeichnis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien, die Formatvorlage können verwendet werden, nur in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei. Weitere Informationen zu Bereichsregeln für Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Darüber hinaus finden Sie weitere Informationen zu Formaten und Ressourcen in [gemeinsam genutzte Ressourcen und Designs](#styling_themes) weiter unten in dieser Übersicht.  
  
### <a name="setting-styles-programmatically"></a>Programmgesteuertes Festlegen von Formaten  
 Um einen benannten Stil auf ein Element programmgesteuert zuweisen möchten, rufen Sie den Stil aus der Resources-Auflistung, und weisen Sie sie auf des Elements <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft. Beachten Sie, dass die Elemente in eine Resources-Auflistung des Typs <xref:System.Object>. Aus diesem Grund müssen Sie das abgerufene Format umwandeln einer <xref:System.Windows.Style> vor der Zuweisung zu den <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft. Beispielsweise, um die definierten festgelegt `TitleText` Stil auf ein <xref:System.Windows.Controls.TextBlock> namens `textblock1`, gehen Sie folgendermaßen vor:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Beachten Sie, dass wenn ein Stil angewendet wurde, versiegelt ist und kann nicht geändert werden. Wenn Sie möchten ein Format dynamisch zu ändern, die bereits angewendet wurde, müssen Sie ein neues Format, um das vorhandene zu ersetzen erstellen. Weitere Informationen finden Sie unter der <xref:System.Windows.Style.IsSealed%2A> Eigenschaft.  
  
 Sie können ein Objekt erstellen, die ein Format anwenden auf Grundlage benutzerdefinierten Logik auswählt. Ein Beispiel finden Sie im Beispiel für die <xref:System.Windows.Controls.StyleSelector> Klasse.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>Bindungen, dynamische Ressourcen und Ereignishandler  
 Hinweis, mit denen Sie die `Setter.Value` -Eigenschaft an eine [Binding-Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) oder [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Weitere Informationen finden Sie unter den Beispielen für die <xref:System.Windows.Setter.Value%2A?displayProperty=fullName> Eigenschaft.  
  
 In dieser Übersicht erläutert bisher nur die Verwendung von Settern einen Eigenschaftswert festlegen. Sie können auch Ereignishandler in einem Format angeben. Weitere Informationen finden Sie unter <xref:System.Windows.EventSetter>.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>Datenvorlagen  
 In dieser beispielanwendung ist eine <xref:System.Windows.Controls.ListBox> Steuerelement, um eine Liste der Fotos gebunden ist:  
  
 [!code-xml[StylingIntroSnippet#UIListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 Diese <xref:System.Windows.Controls.ListBox> derzeit wie folgt aussieht:  
  
 ![ListBox vor dem Anwenden der Vorlage](../../../../docs/framework/wpf/controls/media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 Die meisten Steuerelemente verfügen über Inhalte und Inhalte, die häufig von Daten, an die gebunden werden, abgerufen. In diesem Beispiel sind die Daten für die Liste der Fotos. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Sie verwenden ein <xref:System.Windows.DataTemplate> die visuelle Darstellung der Daten zu definieren. Im Grunde genommen, was Sie in den versetzen einer <xref:System.Windows.DataTemplate> bestimmt, wie die Daten in der gerenderten Anwendung dargestellt.  
  
 In unserer beispielanwendung einzelnen benutzerdefinierten `Photo` Objekt verfügt über eine `Source` -Eigenschaft vom Typ String, der den Pfad des Bilds angibt. Derzeit werden die Fotoobjekte als Dateipfade angezeigt.  
  
 Damit die Fotos als Bilder angezeigt werden, erstellen Sie eine <xref:System.Windows.DataTemplate> als Ressource:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#DataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Beachten Sie, dass die <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft ähnelt der <xref:System.Windows.Style.TargetType%2A> Eigenschaft der <xref:System.Windows.Style>. Wenn Ihre <xref:System.Windows.DataTemplate> ist im Abschnitt "Ressourcen", wenn Sie angeben der <xref:System.Windows.DataTemplate.DataType%2A> -Eigenschaft auf einen Typ, und weisen Sie sie keine `x:Key`, die <xref:System.Windows.DataTemplate> angewendet wird, wenn dieser Typ vorkommt. Sie haben immer die Option zum Zuweisen der <xref:System.Windows.DataTemplate> mit ein `x:Key` und legen sie als eine `StaticResource` für Eigenschaften, <xref:System.Windows.DataTemplate> Typen, z. B. die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft oder die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft.  
  
 Im Wesentlichen die <xref:System.Windows.DataTemplate> im obigen Beispiel definiert, die bei jeder ein `Photo` -Objekt, es sollte angezeigt werden, als ein <xref:System.Windows.Controls.Image> innerhalb einer <xref:System.Windows.Controls.Border>. Mit diesem <xref:System.Windows.DataTemplate>, sieht die Anwendung jetzt wie folgt:  
  
 ![Bild](../../../../docs/framework/wpf/controls/media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 Das Textvorlagen-Datenmodell bietet weitere Features. Beispielsweise, wenn Sie angezeigt, die angezeigt werden, die andere mithilfe von Sammlungen enthält eine <xref:System.Windows.Controls.HeaderedItemsControl> Geben Sie z. B. eine <xref:System.Windows.Controls.Menu> oder eine <xref:System.Windows.Controls.TreeView>, ist die <xref:System.Windows.HierarchicalDataTemplate>. Eine andere Funktion für Datenvorlagen ist die <xref:System.Windows.Controls.DataTemplateSelector>, können Sie wählen eine <xref:System.Windows.DataTemplate> auf Grundlage benutzerdefinierten Logik zu verwenden. Weitere Informationen finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md), stellt eine ausführlichere Erläuterung der verschiedenen Templating-Features.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>Steuerelementvorlagen  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements definiert die Darstellung des Steuerelements. Sie können die Struktur und die Darstellung eines Steuerelements ändern, indem Definieren einer neuen <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement. In vielen Fällen die dadurch ausreichende Flexibilität, damit Sie keine eigene benutzerdefinierte Steuerelemente schreiben. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>Trigger  
 Trigger werden Eigenschaften festgelegt oder Aktionen, z. B. eine Animation beginnt, wenn ein Eigenschaftswert ändert oder wenn ein Ereignis ausgelöst wird. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, und <xref:System.Windows.DataTemplate> verfügen alle über eine `Triggers` -Eigenschaft, die eine Reihe von Triggern enthalten kann. Es gibt verschiedene Typen von Triggern.  
  
### <a name="property-triggers"></a>Eigenschaftstrigger  
 Ein <xref:System.Windows.Trigger> , dass die Eigenschaftswerte festlegt oder Aktionen basierend auf dem Wert einer Eigenschaft gestartet wird als Eigenschaftentrigger bezeichnet.  
  
 Um Eigenschaftstrigger veranschaulichen, stellen Sie jede <xref:System.Windows.Controls.ListBoxItem> teilweise transparent, es sei denn, diese Option ausgewählt ist. Im folgenden Format wird der <xref:System.Windows.UIElement.Opacity%2A> Wert einer <xref:System.Windows.Controls.ListBoxItem> zu `0.5`. Wenn die <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> Eigenschaft ist `true`, jedoch die <xref:System.Windows.UIElement.Opacity%2A> auf festgelegt ist `1.0`:  
  
 [!code-xml[StylingIntroSample_snippet#Triggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xml[StylingIntroSample_snippet#EndTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 Dieses Beispiel verwendet eine <xref:System.Windows.Trigger> Wert einer Eigenschaft festlegen, aber beachten, dass die <xref:System.Windows.Trigger> -Klasse verfügt auch über die <xref:System.Windows.TriggerBase.EnterActions%2A> und <xref:System.Windows.TriggerBase.ExitActions%2A> Eigenschaften, die einen Trigger zum Ausführen von Aktionen zu ermöglichen.  
  
 Beachten Sie, dass die <xref:System.Windows.FrameworkElement.MaxHeight%2A> Eigenschaft der <xref:System.Windows.Controls.ListBoxItem> Wert `75`. In der folgenden Abbildung ist das dritte Element des ausgewählten Elements:  
  
 ![ListView formatiert](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>EventTrigger und Storyboards  
 Ein weiterer Trigger ist die <xref:System.Windows.EventTrigger>, die eine Reihe von Aktionen, die auf Basis des Vorkommens eines Ereignisses startet. Z. B. die folgenden <xref:System.Windows.EventTrigger> Objekte angeben, wenn der Mauszeiger bewegt wird die <xref:System.Windows.Controls.ListBoxItem>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> Eigenschaft animiert, auf den Wert `90` über eine `0.2` Sekunden-Zeitraums. Wenn die Maus von dem Element weg bewegt, gibt die Eigenschaft auf den ursprünglichen Wert über einen Zeitraum von `1` zweiten. Beachten Sie, wie es nicht notwendig, anzugeben ist eine <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> -Wert für die <xref:System.Windows.ContentElement.MouseLeave> Animation. Dies ist darin, dass die Animation zum Nachverfolgen den ursprünglichen Wert kann.  
  
 [!code-xml[StylingIntroSample_snippet#EventTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 Weitere Informationen finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 In der folgenden Abbildung zeigt die Maus auf das dritte Element:  
  
 ![Stil-Beispiel-Screenshot](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger und MultiDataTrigger  
 Zusätzlich zu <xref:System.Windows.Trigger> und <xref:System.Windows.EventTrigger>, es gibt weitere Typen von Triggern. <xref:System.Windows.MultiTrigger> können Sie die Eigenschaftswerte, die auf mehreren Kriterien basierenden festlegen. Verwenden Sie <xref:System.Windows.DataTrigger> und <xref:System.Windows.MultiDataTrigger> Wenn die Eigenschaft der Bedingung datengebunden ist.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>Freigegebene Ressourcen und Designs  
 Ein herkömmliches [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Anwendung möglicherweise mehrere Benutzer-Benutzeroberfläche (UI)-Ressourcen, die in der gesamten Anwendung angewendet werden. Zusammen kann diese Gruppe von Ressourcen als das Design für die Anwendung betrachtet werden. [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]bietet Unterstützung zum Verpacken die Ressourcen der Benutzeroberfläche (UI) als ein Design mit einem Ressourcenwörterbuch, das als gekapselt ist die <xref:System.Windows.ResourceDictionary> Klasse.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]Designs mithilfe des Mechanismus von Formaten und Vorlagen definiert sind, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] zum Anpassen der Darstellung eines Elements verfügbar macht.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]Designressourcen werden in eingebetteten Ressourcenwörterbüchern gespeichert. Diese Ressourcenwörterbücher müssen in einer signierten Assembly eingebettet werden, und können werden entweder in der gleichen Assembly wie der Code selbst oder in einer Seite-an-Seite-Assembly eingebettet. Im Fall von PresentationFramework.dll, der Assembly enthält [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Steuerelemente Designressourcen in einer Reihe von Side-by-Side Assemblies sind.  
  
 Das Design ist das Ziel, um für das Format eines Elements gesucht. In der Regel die Suche beginnt ermöglicht die Suche nach einer geeigneten Ressource Elementstruktur und suchen Sie in der Anwendung Ressourcensammlung und schließlich Abfragen des Systems. Diese Weise können Anwendungsentwickler das Format für alle Objekte auf der Struktur oder Anwendungsebene neu definieren, bevor das Design erreicht wird.  
  
 Sie können als einzelne Dateien Ressourcenverzeichnisse definieren, mit denen Sie ein Design anwendungsübergreifend wiederzuverwenden. Sie können auch umschaltbare Designs erstellen, definieren Sie mehrere Ressourcenverzeichnisse, die die gleichen Typen von Ressourcen, jedoch mit unterschiedlichen Werten bereitstellen. Diese Formate oder andere Ressourcen auf Anwendungsebene neu zu definieren ist die empfohlene Vorgehensweise für eine Anwendung skinning.  
  
 Eine Reihe von Ressourcen, wie Formate und Vorlagen, anwendungsübergreifend gemeinsam nutzen können eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei, und definieren Sie eine <xref:System.Windows.ResourceDictionary>. Beispielsweise sehen Sie sich die folgende Abbildung, das Teil zeigt die [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041):  
  
 ![Beispiele für Steuerelementvorlagen steuern](../../../../docs/framework/wpf/controls/media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 Beim Betrachten der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Dateien in diesem Beispiel werden Sie feststellen, dass alle Dateien über Folgendes verfügen:  
  
 [!code-xml[ControlTemplateExamples#MergedDictionaries](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 Es ist die gemeinsame Nutzung von `shared.xaml`, definiert ein <xref:System.Windows.ResourceDictionary> , enthält eine Reihe von Stil und einem Pinsel Ressourcen die Steuerelemente in der Stichprobe, ein einheitliches Erscheinungsbild.  
  
 Weitere Informationen finden Sie unter [zusammengeführte Ressourcenwörterbücher](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 Wenn Sie ein Design für Sie ein benutzerdefiniertes Steuerelement erstellen, finden Sie im Abschnitt externe Steuerelementbibliothek der [Übersicht über das Erstellen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Paket-URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Gewusst wie: Suchen von Elementen einer ControlTemplate generiert wurden](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [Suchen von Elementen einer DataTemplate generiert wurden](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)