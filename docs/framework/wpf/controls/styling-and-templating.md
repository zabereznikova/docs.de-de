---
title: Erstellen von Formaten und Vorlagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- triggers [WPF]
- styles [WPF], referencing
- event triggers [WPF]
- styles [WPF], prerequisites
- styles [WPF], declaring
- styles [WPF], overview
- styles [WPF], extending
- styles [WPF], triggers
- styles [WPF], event triggers
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
ms.openlocfilehash: 9c2c38020bb57a008d0948a360a5b2cbe401089d
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457757"
---
# <a name="styling-and-templating"></a>Erstellen von Formaten und Vorlagen
Zum Erstellen von Stilen und Vorlagen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stehen eine Reihe von Funktionen (Stile, Vorlagen, Trigger und Storyboards) zur Verfügung, mit denen Entwickler und Designer visuell ansprechende Effekte erzeugen und ein einheitliches Erscheinungsbild ihres Produkts erstellen können. Obwohl Entwickler und/oder Designer die Darstellung in den einzelnen Anwendungen umfassend anpassen können, ist ein starkes Stil- und Vorlagenmodell erforderlich, um die Wartung und Freigabe der Darstellung innerhalb von Anwendungen und anwendungsübergreifend zu ermöglichen. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt dieses Modell bereit.  
  
 Eine weitere Funktion des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Stilmodells ist die Trennung von Darstellung und Logik. Dies bedeutet, dass Designer die Darstellung einer Anwendung nur mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] bearbeiten können, während die Entwickler mit C# oder Visual Basic an der Programmierlogik arbeiten.  
  
 Diese Übersicht konzentriert sich auf die Aspekte der Stile und Vorlagen der Anwendung und geht nicht auf Datenbindungskonzepte ein. Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Darüber hinaus ist es wichtig, die Ressourcen zu kennen, die die Wiederverwendung von Stilen und Vorlagen ermöglichen. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).

<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>Beispiel für das Erstellen von Stilen und Vorlagen  
 In dieser Übersicht verwendeten Codebeispiele basieren auf einem einfachen Fotobeispiel, das in der folgenden Abbildung dargestellt wird:  
  
 ![Formatierte ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 In diesem einfachen Foto-Beispiel werden Stile und Vorlagen verwendet, um eine visuell ansprechende Benutzeroberfläche zu erstellen. Im Beispiel verfügt über zwei <xref:System.Windows.Controls.TextBlock> Elemente und ein <xref:System.Windows.Controls.ListBox> Steuerelement, um eine Liste der Images gebunden ist. Das vollständige Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>Grundlagen zu Stilen  
 Sie können sich vorstellen eine <xref:System.Windows.Style> als eine einfache Möglichkeit, einen Satz von Eigenschaftenwerten für mehr als ein Element gelten. Angenommen, Sie haben die folgenden <xref:System.Windows.Controls.TextBlock> Elemente und ihre standarddarstellung:  
  
 [!code-xaml[StylingIntroSample_snippet#TextBlocks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![Screenshot des Stilbeispiels](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbefore.PNG "StylingIntro_TextBlocksBefore")  
  
 Sie können die standarddarstellung ändern, indem Sie Eigenschaften festlegen, wie z. B. <xref:System.Windows.Controls.Control.FontSize%2A> und <xref:System.Windows.Controls.Control.FontFamily%2A>, auf jedem <xref:System.Windows.Controls.TextBlock> Element direkt. Jedoch gegebenenfalls Ihre <xref:System.Windows.Controls.TextBlock> Elemente einige Eigenschaften gemeinsam nutzen können Sie erstellen eine <xref:System.Windows.Style> in der `Resources` Teil Ihrer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei, wie hier gezeigt:  
  
 [!code-xaml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xaml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Beim Festlegen der <xref:System.Windows.Style.TargetType%2A> des Formats auf die <xref:System.Windows.Controls.TextBlock> Typ, den Stil gilt für alle der <xref:System.Windows.Controls.TextBlock> Elemente im Fenster.  
  
 Jetzt die <xref:System.Windows.Controls.TextBlock> Elemente wie folgt aussehen:  
  
 ![Screenshot des Stilbeispiels](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbasestyle.PNG "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>Erweitern von Stilen  
 Vielleicht möchten Sie die beiden <xref:System.Windows.Controls.TextBlock> Elemente gemeinsam einige Eigenschaftswerte, z. B. die <xref:System.Windows.Controls.Control.FontFamily%2A> und die zentrierte <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, aber auch den Text "Eigene Bilder", um zusätzliche Eigenschaften haben soll. Sie können dies vornehmen, indem erstellen eine neue Formatvorlage, die auf das erste Format basiert, wie hier gezeigt:  
  
 [!code-xaml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xaml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Beachten Sie, das der vorherige Stil ein `x:Key` erhält. Legen Sie zum Anwenden des Formats der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft auf Ihre <xref:System.Windows.Controls.TextBlock> auf die `x:Key` Wert, wie hier gezeigt:  
  
 [!code-xaml[StylingIntroSnippet#UIText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 Dies <xref:System.Windows.Controls.TextBlock> Stil verfügt jetzt über eine <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Wert <xref:System.Windows.HorizontalAlignment.Center>, eine <xref:System.Windows.Controls.TextBlock.FontFamily%2A> Wert `Comic Sans MS`, eine <xref:System.Windows.Controls.TextBlock.FontSize%2A> Wert 26, und ein <xref:System.Windows.Controls.TextBlock.Foreground%2A> Wert festgelegt wird, um die <xref:System.Windows.Media.LinearGradientBrush> im Beispiel gezeigt. Beachten Sie, die sie überschreibt die <xref:System.Windows.Controls.Control.FontSize%2A> Wert, der die Basis-Format. Wenn es mehr als eine <xref:System.Windows.Setter> dieselbe Eigenschaft festlegen, eine <xref:System.Windows.Style>, wird die <xref:System.Windows.Setter> also deklarierte letzten hat Vorrang.  
  
 Das folgende Beispiel zeigt, was die <xref:System.Windows.Controls.TextBlock> Elemente wie folgt aussehen:  
  
 ![Formatierte TextBlocks](../../../../docs/framework/wpf/controls/media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 Dies `TitleText` Stil erweitert das Format, das für die Erstellung der <xref:System.Windows.Controls.TextBlock> Typ. Sie können einen Stil mit `x:Key` auch mithilfe des `x:Key`-Werts erweitern. Ein Beispiel finden Sie im Beispiel für die <xref:System.Windows.Style.BasedOn%2A> Eigenschaft.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Beziehung zwischen der TargetType-Eigenschaft und dem x:Key-Attribut  
 Wie im ersten Beispiel gezeigt, Festlegen der <xref:System.Windows.Style.TargetType%2A> Eigenschaft `TextBlock` ohne das Format zuzuweisen ein `x:Key` bewirkt, dass die Formatvorlage, die auf alle angewendet werden <xref:System.Windows.Controls.TextBlock> Elemente. In diesem Fall wird `x:Key` implizit auf `{x:Type TextBlock}` festgelegt. Dies bedeutet, dass, wenn Sie explizit festlegen, die `x:Key` auf einen anderen Wert als `{x:Type TextBlock}`, <xref:System.Windows.Style> gilt nicht für alle <xref:System.Windows.Controls.TextBlock> Elemente automatisch. Stattdessen müssen Sie das Format anwenden (mithilfe der `x:Key` Wert), die <xref:System.Windows.Controls.TextBlock> Elemente explizit. Wenn Ihr Format im Ressourcenabschnitt ist, und Sie nicht legen die <xref:System.Windows.Style.TargetType%2A> Eigenschaft für Ihr Format, und Sie müssen angeben einer `x:Key`.  
  
 Geben Sie einen Standardwert für die `x:Key`, die <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt den Typ für die Set-Eigenschaften gelten soll. Wenn Sie keinen angeben einer <xref:System.Windows.Style.TargetType%2A>, müssen Sie die Eigenschaften im qualifizieren der <xref:System.Windows.Setter> Objekte durch einen Klassennamen mit der Syntax `Property="ClassName.Property"`. Angenommen, anstatt durch die Einstellung `Property="FontSize"`, müssen Sie festlegen <xref:System.Windows.Setter.Property%2A> auf `"TextBlock.FontSize"` oder `"Control.FontSize"`.  
  
 Beachten Sie außerdem, dass viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente aus einer Kombination von anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementen bestehen. Wenn Sie einen Stil erstellen, das für alle Steuerelemente eines Typs gilt, erhalten Sie möglicherweise unerwartete Ergebnisse. Z. B., wenn Sie einen Stil erstellen, die <xref:System.Windows.Controls.TextBlock> Geben Sie in einer <xref:System.Windows.Window>, das Format gilt für alle <xref:System.Windows.Controls.TextBlock> Steuerelemente im Fenster auch dann, wenn die <xref:System.Windows.Controls.TextBlock> ist Teil eines anderen Steuerelements, wie eine <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>Stile und Ressourcen  
 Verwenden Sie einen Stil auf ein beliebiges Element, das von abgeleitet ist <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Die gängigste Methode zum Deklarieren eines Stils ist, es als Ressource im `Resources`-Abschnitt einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei zu deklarieren, wie in den vorherigen Beispielen gezeigt. Da es sich bei Stilen um Ressourcen handelt, unterliegen sie die gleichen Bereichsregeln, die für alle Ressourcen gelten: Der Deklarationsort eines Stils wirkt sich darauf aus, wo der Stil angewendet werden kann. Wenn Sie den Stil z.B. im Stammelement Ihrer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei mit der Anwendungsdefinition deklarieren, kann der Stil überall in der Anwendung verwendet werden. Wenn Sie eine Navigationsanwendung erstellen und den Stil in einer von der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dateien der Anwendung deklarieren, kann der Stil nur in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei verwendet werden. Weitere Informationen zu Bereichsregeln für Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Darüber hinaus finden Sie weitere Informationen zu Stilen und Ressourcen in [Gemeinsam genutzte Ressourcen und Designs](#styling_themes) weiter unten in dieser Übersicht.  
  
### <a name="setting-styles-programmatically"></a>Programmgesteuertes Festlegen von Stilen  
 Um ein Element programmgesteuert ein benanntes Format zuzuweisen, ruft den Stil aus der Ressourcen-Auflistung, und weisen Sie sie auf des Elements <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft. Beachten Sie, dass die Elemente in einer Ressourcensammlung vom Typ <xref:System.Object>. Aus diesem Grund müssen Sie das abgerufene Format eine Umwandlung einer <xref:System.Windows.Style> vor dem Zuweisen der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft. Beispielsweise, um die definierten festgelegt `TitleText` Formatvorlage auf einen <xref:System.Windows.Controls.TextBlock> mit dem Namen `textblock1`, gehen Sie folgendermaßen vor:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Beachten Sie, dass ein Stil, sobald er angewendet wurde, versiegelt ist und nicht geändert werden kann. Wenn Sie einen Stil dynamisch ändern möchten, das bereits angewendet wurde, müssen Sie einen neuen Stil erstellen, um das vorhandene zu ersetzen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Style.IsSealed%2A>-Eigenschaft.  
  
 Sie können ein Objekt erstellen, das einen Stil auf Grundlage einer benutzerdefinierten Logik auswählt. Ein Beispiel finden Sie im Beispiel für die <xref:System.Windows.Controls.StyleSelector> Klasse.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>Bindungen, dynamische Ressourcen und Ereignishandler  
 Beachten Sie, dass Sie die `Setter.Value`-Eigenschaft dazu nutzen können, um eine [Bindung als Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) oder eine [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) anzugeben. Weitere Informationen finden Sie unter den Beispielen für die <xref:System.Windows.Setter.Value%2A?displayProperty=nameWithType> Eigenschaft.  
  
 In dieser Übersicht wurde bisher nur die Verwendung von Settern zum Festlegen eines Eigenschaftswerts erläutert. Sie können auch Ereignishandler in einem Stil angeben. Weitere Informationen finden Sie unter <xref:System.Windows.EventSetter>.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>Datenvorlagen  
 In dieser beispielanwendung ist eine <xref:System.Windows.Controls.ListBox> Steuerelement, das auf eine Liste von Fotos gebunden wird:  
  
 [!code-xaml[StylingIntroSnippet#UIListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 Dies <xref:System.Windows.Controls.ListBox> derzeit sieht wie folgt:  
  
 ![ListBox vor der Anwendung der Vorlage](../../../../docs/framework/wpf/controls/media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 Die meisten Steuerelemente verfügen über Inhalte, und dieser Inhalt stammt häufig aus Daten, an die Sie binden. In diesem Beispiel sind die Daten die Liste der Fotos. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Sie verwenden eine <xref:System.Windows.DataTemplate> um die visuelle Darstellung der Daten zu definieren. Im Grunde genommen, was Sie Ablegen einer <xref:System.Windows.DataTemplate> bestimmt, wie die Daten in der gerenderten Anwendung aussieht.  
  
 In unserer Beispielanwendung verfügt jedes benutzerdefinierte `Photo`-Objekt über eine `Source`-Eigenschaft vom Typ Zeichenfolge, die den Pfad des Bilds angibt. Derzeit werden die Fotoobjekte als Dateipfade angezeigt.  
  
 Für die Fotos als Bilder angezeigt werden, erstellen Sie eine <xref:System.Windows.DataTemplate> als Ressource:  
  
 [!code-xaml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#DataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xaml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Beachten Sie, dass die <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft ähnelt stark der <xref:System.Windows.Style.TargetType%2A> Eigenschaft von der <xref:System.Windows.Style>. Wenn Ihre <xref:System.Windows.DataTemplate> ist im Abschnitt für die Ressourcen, wenn Sie angeben der <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft auf einen Typ, und weisen Sie sie keine `x:Key`, die <xref:System.Windows.DataTemplate> wird angewendet, wenn dieses Typs angezeigt wird. Haben Sie immer die Möglichkeit zum Zuweisen der <xref:System.Windows.DataTemplate> mit eine `x:Key` und legen Sie es als ein `StaticResource` für Eigenschaften, <xref:System.Windows.DataTemplate> Typen, z. B. die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft oder die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaft.  
  
 Im Wesentlichen die <xref:System.Windows.DataTemplate> im obigen Beispiel definiert, die immer eine `Photo` -Objekt, es sollte nun wie ein <xref:System.Windows.Controls.Image> innerhalb einer <xref:System.Windows.Controls.Border>. Mit diesem <xref:System.Windows.DataTemplate>, sieht die Anwendung jetzt wie folgt:  
  
 ![Foto](../../../../docs/framework/wpf/controls/media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 Das Datenvorlagenmodell stellt weitere Funktionen bereit. Z. B., wenn Sie Sammlungsdaten anzeigen, die andere mithilfe von Sammlungen enthält eine <xref:System.Windows.Controls.HeaderedItemsControl> Geben Sie z. B. eine <xref:System.Windows.Controls.Menu> oder ein <xref:System.Windows.Controls.TreeView>, besteht die <xref:System.Windows.HierarchicalDataTemplate>. Eine andere Funktion für Datenvorlagen ist die <xref:System.Windows.Controls.DataTemplateSelector>, können Sie wählen eine <xref:System.Windows.DataTemplate> auf Grundlage benutzerdefinierten Logik verwenden. Weitere Informationen finden Sie unter im Artikel [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md), der eine ausführlichere Erläuterung der verschiedenen Vorlagenfunktionen bereitstellt.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>Steuerelementvorlagen  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]die <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements definiert die Darstellung des Steuerelements. Sie können die Struktur und die Darstellung eines Steuerelements ändern, indem Definieren einer neuen <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement. In vielen Fällen erhalten Sie hierdurch die ausreichende Flexibilität, um keine eigenen benutzerdefinierten Steuerelemente schreiben zu müssen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>Trigger  
 Ein Trigger legt Eigenschaften fest oder startet Aktionen, z.B. eine Animation, wenn sich ein Eigenschaftswert ändert oder ein Ereignis ausgelöst wird. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, und <xref:System.Windows.DataTemplate> alle verfügen über eine `Triggers` -Eigenschaft, die eine Reihe von Triggern enthalten kann. Es gibt verschiedene Typen von Triggern.  
  
### <a name="property-triggers"></a>Eigenschaftstrigger  
 Ein <xref:System.Windows.Trigger> , dass die Eigenschaftswerte festlegt oder Aktionen, die anhand des Werts einer Eigenschaft startet einen Eigenschaftsauslöser aufgerufen wird.  
  
 Zum Veranschaulichen der Eigenschaftentrigger verwenden, stellen Sie jede <xref:System.Windows.Controls.ListBoxItem> teilweise transparent, es sei denn, diese Option ausgewählt ist. Im folgenden Format wird der <xref:System.Windows.UIElement.Opacity%2A> Wert, der eine <xref:System.Windows.Controls.ListBoxItem> auf `0.5`. Wenn die <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> Eigenschaft ist `true`, jedoch die <xref:System.Windows.UIElement.Opacity%2A> auf festgelegt ist `1.0`:  
  
 [!code-xaml[StylingIntroSample_snippet#Triggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xaml[StylingIntroSample_snippet#EndTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 Dieses Beispiel verwendet eine <xref:System.Windows.Trigger> Wert einer Eigenschaft festlegen, aber beachten, dass die <xref:System.Windows.Trigger> -Klasse verfügt auch über die <xref:System.Windows.TriggerBase.EnterActions%2A> und <xref:System.Windows.TriggerBase.ExitActions%2A> Eigenschaften, die einen Trigger für Aktionen zu ermöglichen.  
  
 Beachten Sie, dass die <xref:System.Windows.FrameworkElement.MaxHeight%2A> Eigenschaft von der <xref:System.Windows.Controls.ListBoxItem> festgelegt ist, um `75`. In der folgenden Abbildung ist das dritte Element das ausgewählte Element:  
  
 ![Formatierte ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>EventTrigger und Storyboards  
 Ein weiterer Typ von Trigger sind die <xref:System.Windows.EventTrigger>, dem eine Reihe von Aktionen, die abhängig vom Auftreten eines Ereignisses beginnt. Beispielsweise die folgenden <xref:System.Windows.EventTrigger> Objekte angeben, wenn der Mauszeiger wird die <xref:System.Windows.Controls.ListBoxItem>, die <xref:System.Windows.FrameworkElement.MaxHeight%2A> Eigenschaft animiert wird, auf den Wert `90` über eine `0.2` Sekunden-Zeitraums. Wenn sich die Maus vom Element weg bewegt, gibt die Eigenschaft auf den ursprünglichen Wert über einen Zeitraum von `1` Sekunden an. Beachten Sie, wie es nicht notwendig, dass angeben ist ein <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Wert für die <xref:System.Windows.ContentElement.MouseLeave> Animation. Dies liegt daran, dass die Animation den ursprünglichen Wert nachverfolgen kann.  
  
 [!code-xaml[StylingIntroSample_snippet#EventTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 Weitere Informationen finden Sie unter der [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 In der folgenden Abbildung zeigt die Maus auf das dritte Element:  
  
 ![Screenshot des Stilbeispiels](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger und MultiDataTrigger  
 Zusätzlich zu <xref:System.Windows.Trigger> und <xref:System.Windows.EventTrigger>, es gibt andere Arten von Triggern. <xref:System.Windows.MultiTrigger> können Sie Eigenschaftswerte anhand mehrerer Bedingungen festlegen. Verwenden Sie <xref:System.Windows.DataTrigger> und <xref:System.Windows.MultiDataTrigger> Wenn die Eigenschaft der Bedingung datengebunden ist.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>Gemeinsam genutzte Ressourcen und Designs  
 Eine typische Windows Presentation Foundation (WPF)-Anwendung möglicherweise mehrere Ressourcen der Benutzeroberfläche (UI), die in der gesamten Anwendung angewendet werden. Dieser Satz von Ressourcen wird im Ganzen als das Design der Anwendung bezeichnet. Windows Presentation Foundation (WPF) bietet Unterstützung für Verpackung Benutzer Ressourcen der Benutzeroberfläche (UI) als ein Design mit einem Ressourcenwörterbuch, die als gekapselt ist die <xref:System.Windows.ResourceDictionary> Klasse.  
  
 Windows Presentation Foundation (WPF)-Designs sind mit dem Erstellen von Formaten und Vorlagen-Mechanismus, der Windows Presentation Foundation (WPF) verfügbar macht zum Anpassen von visuellen Elemente eines beliebigen Elements definiert.  
  
 Windows Presentation Foundation (WPF) Designressourcen werden im eingebetteten Ressourcenverzeichnis gespeichert. Diese Ressourcenverzeichnisse müssen in einer signierten Assembly eingebettet werden und werden entweder in der gleichen Assembly wie der Code selbst oder in einer parallele Assembly eingebettet. Im Fall PresentationFramework.dll, Assembly, die Windows Presentation Foundation (WPF)-Steuerelemente enthält, sind Designressourcen in einer Reihe von Seite-an-Seite-Assemblys ein.  
  
 Das Design wird zu dem letzten Ort, an dem bei der Suche nach dem Stil eines Elements gesucht wird. In der Regel beginnt die Suche, indem sie die Elementstruktur aufwärts entlang geht und nach einer geeigneten Ressource sucht. Dann wird die Suche in der Ressourcensammlung der Anwendung fortgesetzt, und schließlich wird das System abgefragt. Auf diese Weise können Anwendungsentwickler der Stil für alle Objekte auf Struktur- oder Anwendungsebene neu definieren, bevor das Design erreicht wird.  
  
 Sie können Ressourcenverzeichnisse als einzelne Dateien definieren, die es Ihnen ermöglichen, ein Design in mehreren Anwendungen wieder zu verwenden. Sie können auch austauschbare Designs erstellen, indem Sie mehrere Ressourcenverzeichnisse definieren, welche dieselben Ressourcentypen bereitstellen, jedoch mit unterschiedlichen Werten. Das Neudefinieren dieser Stile oder anderer Ressourcen auf Anwendungsebene ist die empfohlene Vorgehensweise für das Skinning von Anwendungen.  
  
 Sie können eine Reihe von Ressourcen, einschließlich Stile und Vorlagen, anwendungsübergreifend freigeben erstellen eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei, und definieren einen <xref:System.Windows.ResourceDictionary>. Sehen Sie sich z.B. die folgende Abbildung an, die einen Teil des [Beispiels zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) zeigt:

![Beispiele für Steuerelementvorlagen](../../../../docs/framework/wpf/controls/media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 Wenn Sie die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dateien in diesem Beispiel näher betrachten, werden Sie feststellen, dass alle Dateien über Folgendes verfügen:  
  
 [!code-xaml[ControlTemplateExamples#MergedDictionaries](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 Es ist die gemeinsame Nutzung von `shared.xaml`, definiert eine <xref:System.Windows.ResourceDictionary> , enthält eine Reihe von Stil und einem Pinsel Ressourcen, die die Steuerelemente in der Stichprobe, die ein konsistentes Erscheinungsbild haben kann.  
  
 Weitere Informationen finden Sie unter [Zusammengeführte Ressourcenverzeichnisse](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 Wenn Sie ein Design für Ihr ein benutzerdefiniertes Steuerelement erstellen, finden Sie im Abschnitt zur externen Steuerelementbibliothek im Artikel [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Paket-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)  
 [Suchen von Elementen, die mit einer DataTemplate generiert wurden](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
