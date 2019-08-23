---
title: Übersicht über bidirektionale Features in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: b009c2503c7cbf6aca847fc7318135842a060f69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965041"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Übersicht über bidirektionale Features in WPF
Anders als bei jeder anderen Entwicklungs [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Plattform bietet viele Funktionen, die eine schnelle Entwicklung von bidirektionalem Inhalt unterstützen, z. b. von links nach rechts und von rechts nach Links zu Daten im selben Dokument. Gleichzeitig wird für Benutzer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , die bidirektionale Features wie arabische und Hebräisch sprachige Benutzer benötigen, eine hervorragende benutzerfreundliche Benutzersprache erstellt.  
  
 In den folgenden Abschnitten werden bidirektionale Funktionen sowie Beispiele erklärt, die zeigen, wie die beste Anzeige von bidirektionalem Inhalts erreicht werden kann. Die meisten der Beispiele verwenden [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], obwohl Sie die Konzepte problemlos auf C# oder Microsoft Visual Basic Code anwenden können.  

<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 Die grundlegende Eigenschaft, die die Richtung des Inhalts Flusses [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Anwendung definiert, ist. Diese Eigenschaft kann auf einen von zwei Enumerationswerten <xref:System.Windows.FlowDirection.LeftToRight> (oder <xref:System.Windows.FlowDirection.RightToLeft>) festgelegt werden. Die-Eigenschaft ist für alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente verfügbar, die <xref:System.Windows.FrameworkElement>von erben.  
  
 In den folgenden Beispielen wird die Fluss Richtung eines <xref:System.Windows.Controls.TextBox> -Elements festgelegt.  
  
 **Flussrichtung von links nach rechts**  
  
 [!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Flussrichtung von rechts nach links**  
  
 [!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 Die folgende Grafik zeigt, wie der vorherige Code gerendert wird.  
    
 ![Grafik, die die verschiedenen Fluss Richtungen veranschaulicht.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)  
  
 Ein Element innerhalb einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Struktur erbt den <xref:System.Windows.FrameworkElement.FlowDirection%2A> von seinem Container. Im folgenden Beispiel <xref:System.Windows.Controls.TextBlock> befindet sich in einem <xref:System.Windows.Controls.Grid>-Wert, der sich in einem <xref:System.Windows.Window>befindet. Das Festlegen <xref:System.Windows.FrameworkElement.FlowDirection%2A> des für <xref:System.Windows.Window> das <xref:System.Windows.Controls.Grid> impliziert, dass es auch <xref:System.Windows.Controls.TextBlock> für und ebenfalls festgelegt wird.  
  
 Im folgenden Beispiel wird das <xref:System.Windows.FrameworkElement.FlowDirection%2A>Festlegen von veranschaulicht.  
  
 [!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Die oberste Ebene <xref:System.Windows.Window> verfügt über <xref:System.Windows.FlowDirection.RightToLeft>eine <xref:System.Windows.FlowDirection>, sodass alle darin enthaltenen Elemente auch denselben <xref:System.Windows.FrameworkElement.FlowDirection%2A>erben. Damit ein Element eine angegebene <xref:System.Windows.FrameworkElement.FlowDirection%2A> überschreiben kann, muss es eine explizite Richtung ändern, wie z <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.FlowDirection.LeftToRight>. b. das zweite im vorherigen Beispiel, das in geändert wird. Wenn kein <xref:System.Windows.FrameworkElement.FlowDirection%2A> definiert ist, wird der <xref:System.Windows.FlowDirection.LeftToRight> Standardwert angewendet.  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels:

 ![Grafik, die die explizite Änderung der Fluss Richtung veranschaulicht.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)  

<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Viele Entwicklungsplattformen, z. b [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] . html und Java, bieten besondere Unterstützung für die bidirektionale Inhalts Entwicklung. Markup Sprachen, wie z. b. html, geben Inhaltsautoren das erforderliche Markup zum Anzeigen von Text in beliebiger Richtung an, z. b. das HTML 4,0-Tag "dir", das "RTL" oder "ltr" als Werte annimmt. Dieses Tag ähnelt der <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft, aber die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft arbeitet in einer komplexeren Methode zum Layout von Textinhalten und kann für andere Inhalte als Text verwendet werden.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ist ein <xref:System.Windows.Documents.FlowDocument> ein vielseitiges [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Element, das eine Kombination aus Text, Tabellen, Bildern und anderen Elementen hosten kann. Die Beispiele in den folgenden Abschnitten verwenden dieses Element.  
  
 Das Hinzufügen von <xref:System.Windows.Documents.FlowDocument> Text zu einem kann auf eine andere Weise erfolgen. Eine einfache Möglichkeit hierfür ist die Verwendung eines <xref:System.Windows.Documents.Paragraph> -Elements auf Blockebene, das zum Gruppieren von Inhalten, z. b. Text, verwendet wird. Um einem Element auf Inline Ebene Text hinzuzufügen, verwenden <xref:System.Windows.Documents.Span> die <xref:System.Windows.Documents.Run>Beispiele und. <xref:System.Windows.Documents.Span>ein fortlaufendes Inhalts Element auf Inline Ebene, das zum Gruppieren anderer Inline Elemente verwendet <xref:System.Windows.Documents.Run> wird, während ein ein fortlaufendes Inhalts Element auf Inline Ebene ist, das eine Ausführung von unformatiertem Text enthalten soll. Ein <xref:System.Windows.Documents.Span> kann mehrere <xref:System.Windows.Documents.Run> -Elemente enthalten.  
  
 Das erste Dokument Beispiel enthält ein Dokument mit einer Reihe von Netzwerkfreigabe Namen. beispielsweise `\\server1\folder\file.ext`. Egal, ob Sie diesen Netzwerklink in einem arabischen oder einem englischen Dokument haben, Sie möchten, dass es immer auf die gleiche Weise angezeigt wird. Die folgende Grafik veranschaulicht die Verwendung des Span-Elements und zeigt den Link in <xref:System.Windows.FlowDirection.RightToLeft> einem arabischen Dokument:

 ![Grafik, die die Verwendung des Span-Elements veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "Fluss Dokument")  
  
 Da der Text ist <xref:System.Windows.FlowDirection.RightToLeft>, trennen alle Sonderzeichen, wie z.\\b. "", den Text in der Reihenfolge von rechts nach links. Das führt dazu, dass der Link nicht in der richtigen Reihenfolge angezeigt wird. um das Problem zu beheben, muss der Text eingebettet werden, <xref:System.Windows.Documents.Run> um <xref:System.Windows.FlowDirection.LeftToRight>einen separaten Fluss zu erhalten. Anstatt für jede Sprache eine <xref:System.Windows.Documents.Run> separate Sprache zu verwenden, ist es besser, das Problem zu beheben, indem der weniger häufig verwendete englische Text in einen größeren <xref:System.Windows.Documents.Span>arabischen Text eingebettet wird.  
  
 Dies wird in der folgenden Abbildung veranschaulicht, indem das in einem span-Element eingebettete Run-Element verwendet wird:

 ![Grafik, die das in einem span-Element eingebettete Run-Element veranschaulicht.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Documents.Run> Verwendung <xref:System.Windows.Documents.Span> von-und-Elementen in Dokumenten veranschaulicht.  
  
 [!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Span-Elemente  
 Das <xref:System.Windows.Documents.Span> -Element fungiert als Begrenzungs Trennzeichen zwischen Texten mit unterschiedlichen Fluss Richtungen.  Sogar <xref:System.Windows.Documents.Span> Elemente <xref:System.Windows.FlowDirection>, die dieselbe Fluss Richtung aufweisen, werden als verschiedene bidirektionale Bereiche betrachtet. <xref:System.Windows.Documents.Span> Dies bedeutet, dass die Elemente im Container, nur dem Inhalt innerhalb <xref:System.Windows.Documents.Span> des Elements, geordnet sind. folgt der <xref:System.Windows.FlowDirection> <xref:System.Windows.Documents.Span>von.  
  
 Die folgende Abbildung zeigt die Fluss Richtung mehrerer <xref:System.Windows.Controls.TextBlock> Elemente.  
    
 ![Grafik, die Textblöcke mit unterschiedlichen Fluss Richtungen veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)  
  
 Im folgenden Beispiel wird gezeigt, wie das <xref:System.Windows.Documents.Span> - <xref:System.Windows.Documents.Run> Element und das-Element verwendet werden, um die in der vorherigen Grafik dargestellten Ergebnisse zu erzielen.  
  
 [!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 In den <xref:System.Windows.Controls.TextBlock> Elementen des Beispiels werden die <xref:System.Windows.Documents.Span> Elemente entsprechend der <xref:System.Windows.FlowDirection> ihrer übergeordneten Elemente angeordnet, aber der Text in jedem <xref:System.Windows.Documents.Span> Element fließt entsprechend seiner eigenen <xref:System.Windows.FlowDirection>. Dies gilt für Latein und Arabisch - oder jede andere Sprache.  
  
### <a name="adding-xmllang"></a>Hinzufügen von xml:lang  
 Die folgende Grafik zeigt ein weiteres Beispiel, in `"200.0+21.4=221.4"`dem Zahlen und arithmetische Ausdrücke verwendet werden, z. b. Beachten Sie, dass <xref:System.Windows.FlowDirection> nur die festgelegt ist.  
    
 ![Grafik, die Zahlen anzeigt, die nur Fluss Richtung verwenden.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)  
  
 Benutzer dieser Anwendung werden von der Ausgabe enttäuscht, auch wenn der <xref:System.Windows.FlowDirection> korrekt ist, werden die Zahlen nicht so strukturiert, dass arabische Zahlen geformt werden.  
  
 XAML-Elemente können ein [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Attribut (`xml:lang`) enthalten, das die Sprache der einzelnen Elemente definiert. XAML unterstützt auch [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ein sprach Prinzip `xml:lang` , bei dem Werte, die auf übergeordnete Elemente in der Struktur angewendet werden, von untergeordneten Elementen verwendet werden. Im vorherigen Beispiel <xref:System.Windows.Documents.Run> wurdeder`xml:lang` Standardwert fürXAMLverwendet,dakeineSprachefürdas-ElementodereinesseinerElementederoberstenEbenedefiniertwurde.`en-US` Die interne Zahl, die den [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Algorithmus von strukturiert, wählt Zahlen in der entsprechenden Sprache aus – in diesem Fall Englisch. Um die arabischen Zahlen korrekt `xml:lang` zu gestalten, muss festgelegt werden.  
  
 Die folgende Abbildung zeigt das Beispiel mit `xml:lang` hinzugefügten.  
    
 ![Grafik, die arabische Zahlen veranschaulicht, die von rechts nach links fließen.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)  
  
 Im folgenden Beispiel wird `xml:lang` der Anwendung hinzugefügt.  
  
 [!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Beachten Sie, dass viele Sprachen abhängig `xml:lang` von der Zielregion über unterschiedliche Werte verfügen, `"ar-SA"` z `"ar-EG"` . b., und stellen zwei Variationen von Arabisch dar. Die vorherigen Beispiele veranschaulichen, dass Sie sowohl die-als `xml:lang` auch <xref:System.Windows.FlowDirection> die-Werte definieren müssen.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>FlowDirection mit Nicht-Text-Elementen  
 <xref:System.Windows.FlowDirection>definiert nicht nur, wie Text in einem Textelement fließt, sondern auch die Fluss Richtung von fast [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] jedem anderen Element. Die folgende Abbildung zeigt einen <xref:System.Windows.Controls.ToolBar> , der einen horizontalen <xref:System.Windows.Media.LinearGradientBrush> zum Zeichnen des Hintergrunds mit einem linken zum rechten Farbverlauf verwendet.  

 ![Grafik, die eine Symbolleiste mit einem Farbverlauf von links nach rechts anzeigt.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)  
  
 Nachdem <xref:System.Windows.FlowDirection> Sie auf <xref:System.Windows.FlowDirection.RightToLeft>festgelegt haben, werden <xref:System.Windows.Controls.ToolBar> nicht nur die Schaltflächen von rechts nach links angeordnet, <xref:System.Windows.Media.LinearGradientBrush> sondern auch das Ausrichten der Offsets, die von rechts nach links fließen.  
  
 In der folgenden Abbildung wird die Neuausrichtung von <xref:System.Windows.Media.LinearGradientBrush>veranschaulicht.  
    
 ![Grafik, die eine Symbolleiste mit einem Farbverlauf von rechts nach Links anzeigt.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>gezeichnet. (Um Sie von links nach rechts zu zeichnen, <xref:System.Windows.FlowDirection> entfernen Sie das <xref:System.Windows.Controls.ToolBar>-Attribut in.  
  
 [!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>FlowDirection-Ausnahmen  
 Es gibt einige Fälle, in <xref:System.Windows.FlowDirection> denen sich nicht wie erwartet verhält. In diesem Abschnitt werden zwei von diesen Ausnahmen behandelt.  
  
 **Image**  
  
 Ein <xref:System.Windows.Controls.Image> -Element stellt ein Steuerelement dar, das ein Bild anzeigt. In [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] kann die-Eigenschaft mit einer <xref:System.Windows.Controls.Image.Source%2A> -Eigenschaft verwendet werden [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] <xref:System.Windows.Controls.Image> , die das-Objekt definiert, das angezeigt werden soll.  
  
 Im Gegensatz [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zu anderen- <xref:System.Windows.Controls.Image> Elementen erbt <xref:System.Windows.FlowDirection> ein nicht vom-Container. Wenn <xref:System.Windows.FlowDirection> jedoch explizit auf <xref:System.Windows.FlowDirection.RightToLeft>festgelegt wird, wird eine <xref:System.Windows.Controls.Image> horizontal geflippt angezeigt. Dies wird als eine praktische Funktion für Entwickler von bidirektionalem Inhalt implementiert, da in einigen Fällen das horizontale Spiegeln des Bildes den gewünschten Effekt erzeugt.  
  
 Die folgende Grafik zeigt ein geflippte <xref:System.Windows.Controls.Image>.  
    
 ![Grafik, die ein geflittenes Bild veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)  
  
 Im folgenden Beispiel wird veranschaulicht, <xref:System.Windows.Controls.Image> dass die nicht die <xref:System.Windows.FlowDirection> von der <xref:System.Windows.Controls.StackPanel> erbt, die Sie enthält. **Hinweis** Sie benötigen eine Datei mit dem Namen " **ms_logo. jpg** " auf "C:\". Laufwerk zum Ausführen dieses Beispiels.  
  
 [!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Hinweis** In den Download Dateien ist eine **ms_logo. jpg** -Datei enthalten. Der Code geht davon aus, dass die JPG-Datei sich nicht in Ihrem Projekt, sondern an einer beliebigen Stelle auf dem Laufwerk C:\ befindet. Sie kopieren das .jpg aus den Projektdateien auf Ihr Laufwerk C:\ oder ändern den Code, um die Datei im Projekt zu suchen. Um dies zu tun `Source="file://c:/ms_logo.jpg"` , `Source="ms_logo.jpg"`ändern Sie in.  
  
 **Pfade**  
  
 Zusätzlich zu einem <xref:System.Windows.Controls.Image>ist <xref:System.Windows.Shapes.Path>ein weiteres interessantes Element. Ein Pfad ist ein Objekt, das eine Reihe von miteinander verbundenen Linien und Kurven zeichnen kann. Sie verhält sich ähnlich <xref:System.Windows.Controls.Image> wie ein <xref:System.Windows.FlowDirection>-Wert, z <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> . b. ist eine horizontale Spiegelung der <xref:System.Windows.FlowDirection.LeftToRight> einen. Im Gegensatz zu <xref:System.Windows.Controls.Image>erbt <xref:System.Windows.Shapes.Path> <xref:System.Windows.FlowDirection> jedoch den von dem Container, der nicht explizit angegeben werden muss.  
  
 Im folgenden Beispiel wird ein einfacher Pfeil mit drei Linien gezeichnet. Der erste Pfeil erbt die <xref:System.Windows.FlowDirection.RightToLeft> Fluss Richtung von der <xref:System.Windows.Controls.StackPanel> , sodass seine Start-und Endpunkte von einem Stamm auf der rechten Seite gemessen werden. Der zweite Pfeil mit einem expliziten <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> beginnt auch auf der rechten Seite. Der dritte Pfeil hat jedoch seinen Startstamm auf der linken Seite. Weitere Informationen zum Zeichnen finden <xref:System.Windows.Media.LineGeometry> Sie unter und. <xref:System.Windows.Media.GeometryGroup>  
  
 [!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels mit Pfeilen, die mithilfe `Path` des-Elements gezeichnet werden:

 ![Grafik, die Pfeile veranschaulicht, die mithilfe des Path-Elements gezeichnet werden.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)  
  
 Und <xref:System.Windows.Controls.Image> sind<xref:System.Windows.Shapes.Path> <xref:System.Windows.FlowDirection>zwei Beispiele für die Verwendungvon.[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Neben <xref:System.Windows.Media.LinearGradientBrush> demanordnen<xref:System.Windows.FlowDirection> von Elementen in einer bestimmten Richtung innerhalb eines Containers kann mit Elementen wie verwendetwerden,diefreiHandEingabenaufeinerOberfläche()rendern.<xref:System.Windows.Media.RadialGradientBrush> <xref:System.Windows.Controls.InkPresenter> Jedes Mal, wenn Sie ein Verhalten von rechts nach Links für Ihre Inhalte benötigen, das das Verhalten von links nach rechts imitiert (oder umgekehrt), wird [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] diese Funktion bereitstellt.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Ersetzen von Zahlen  
 In der Vergangenheit hat Windows das Ersetzen von Zahlen unterstützt, indem es die Darstellung verschiedener kultureller Formen für die gleichen Ziffern ermöglicht und dabei den internen Speicher dieser Ziffern in verschiedenen Gebiets Schemas einheitlich gehalten hat, z. b. Wenn Zahlen in ihren bekannte hexadezimal Werte, 0x40, 0x41, werden jedoch entsprechend der ausgewählten Sprache angezeigt.  
  
 Dadurch haben Anwendungen die Möglichkeit, numerische Werte zu verarbeiten, ohne Sie von einer Sprache in eine andere konvertieren zu müssen. ein Benutzer kann z [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] . b. eine Kalkulations Tabelle in einem lokalisierten arabischen Fenster öffnen und die in Arabisch formatierten Zahlen anzeigen, aber in einem Die Europäische Version von Windows und die Darstellung der gleichen Zahlen in der Europäischen Darstellung. Dies ist auch für andere Symbole, wie z.B. Kommas als Trennzeichen und das Prozentsatzsymbol notwendig, da sie normalerweise Zahlen in einem Dokument begleiten.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] führt diese Tradition fort und fügt weitere Unterstützung für diese Funktion hinzu, die mehreren Benutzern die Steuerung darüber ermöglicht, wann und wie die Ersetzung verwendet wird. Diese Funktion ist für jede Sprache konzipiert, da sie besonders für bidirektionalen Inhalt nützlich ist, bei dem die Strukturierung von Ziffern für eine bestimmte Sprache in der Regel eine Herausforderung für die Entwickler der Anwendung darstellt, da eine Anwendung aufgrund der verschiedenen Kulturen möglicherweise weiter ausgeführt wird.  
  
 Die Kern Eigenschaft, die steuert, wie die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Zahlen Ersetzung <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> in funktioniert, ist die Abhängigkeits Eigenschaft. Die <xref:System.Windows.Media.NumberSubstitution> -Klasse gibt an, wie Zahlen im Text angezeigt werden sollen. Er verfügt über drei öffentliche Eigenschaften, die sein Verhalten definieren. Es folgt eine Zusammenfassung der einzelnen Eigenschaften.  
  
 **CultureSource:**  
  
 Diese Eigenschaft gibt an, wie die Kultur für Zahlen bestimmt wird. Er nimmt einen von drei <xref:System.Windows.Media.NumberCultureSource> Enumerationswerten an.  
  
- Dire Die Zahlen Kultur ist die <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> der Eigenschaft.  
  
- Text: Die Zahlen Kultur ist die Kultur des Lauftexts. In Markup wäre `xml:lang`dies oder die zugehörige Alias `Language` Eigenschaft (<xref:System.Windows.FrameworkElement.Language%2A> oder <xref:System.Windows.FrameworkContentElement.Language%2A>). Außerdem handelt es sich um den Standardwert für Klassen <xref:System.Windows.FrameworkContentElement>, die von abgeleitet werden. Diese Klassen umfassen <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType> <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, usw.<xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>  
  
- Benutzer: Die Zahlen Kultur ist die Kultur des aktuellen Threads. Diese Eigenschaft ist die Standardeinstellung für alle Unterklassen <xref:System.Windows.FrameworkElement> von <xref:System.Windows.Controls.Page>, wie <xref:System.Windows.Window> z <xref:System.Windows.Controls.TextBlock>. b., und.  
  
 **CultureOverride**:  
  
 Die <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> -Eigenschaft wird nur verwendet, <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> wenn die-Eigenschaft <xref:System.Windows.Media.NumberCultureSource.Override> auf festgelegt ist und andernfalls ignoriert wird. Es gibt die Kultur der Zahl an. Der Wert `null`, der Standardwert, wird als en-US interpretiert.  
  
 **Ersetzung**:  
  
 Diese Eigenschaft gibt den Typ der zu ersetzenden Zahl an. Er nimmt einen der folgenden <xref:System.Windows.Media.NumberSubstitutionMethod> Enumerationswerte an:  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Die Ersetzungs Methode wird basierend auf der- <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> Eigenschaft der Zahlen Kultur bestimmt. Dies ist die Standardeinstellung.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Wenn die Zahlen Kultur eine arabische oder persische Kultur ist, gibt Sie an, dass die Ziffern vom Kontext abhängen.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Zahlen werden immer als europäische Ziffern gerendert.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Zahlen werden mithilfe der nationalen Ziffern für die Zahlen Kultur gerendert <xref:System.Globalization.CultureInfo.NumberFormat%2A>, wie durch die der Kultur angegeben.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Zahlen werden mithilfe der herkömmlichen Ziffern für die Zahlen Kultur gerendert. In <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>den meisten Kulturen ist dies mit identisch. <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> Führt jedoch zu lateinischen Ziffern für einige arabische Kulturen, wohingegen dieser Wert arabische Ziffern für alle arabischen Kulturen zur Folge hat.  
  
 Was bedeuten diese Werte für einen Entwickler von bidirektionalem Inhalt? In den meisten Fällen muss der Entwickler möglicherweise nur die <xref:System.Windows.FlowDirection> Sprache der einzelnen Text [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente definieren. die <xref:System.Windows.Media.NumberSubstitution> Logik übernimmt `Language="ar-SA"` z. b. die Anzeige der Zahlen entsprechend der richtigen. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Das folgende Beispiel veranschaulicht die Verwendung von arabischen und englischen Zahlen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in einer-Anwendung, die in einer arabischen Version von Windows ausgeführt wird.  
  
 [!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels, wenn Sie in einer arabischen Version von Windows mit den angezeigten arabischen und englischen Zahlen ausführen:

 ![Grafik, die arabische und englische Zahlen zeigt.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)  
  
 Ist in diesem Fall wichtig, da durch das <xref:System.Windows.FlowDirection> festlegen <xref:System.Windows.FlowDirection.LeftToRight> von auf stattdessen europäische Ziffern zurückgegeben würden. <xref:System.Windows.FlowDirection> In den folgenden Abschnitten wird erläutert, wie eine einheitliche Anzeige von Ziffern im gesamten Dokument möglich ist. Wenn dieses Beispiel in einem arabischen Windows nicht ausgeführt wird, werden alle Ziffern als europäische Ziffern angezeigt.  
  
 **Definieren von Ersetzungsregeln**  
  
 In einer realen Anwendung müssen Sie die Sprache programmgesteuert festlegen. Sie möchten z. b. festlegen, `xml:lang` dass das-Attribut mit dem vom [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]System verwendeten identisch ist, oder Sie können die Sprache abhängig vom Anwendungs Zustand ändern.  
  
 Wenn Sie Änderungen auf der Grundlage des Anwendungs Zustands vornehmen möchten, verwenden Sie andere Funktionen, die von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bereitgestellt werden.  
  
 Legen Sie zunächst die Anwendungs Komponente `NumberSubstitution.CultureSource="Text"`fest. Wenn Sie diese Einstellung verwenden, stellen Sie sicher, dass die Einstellungen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nicht aus der für Textelemente stammen, deren Standardwert "User" <xref:System.Windows.Controls.TextBlock>ist, z. b.  
  
Beispiel:  

```xaml  
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

Legen Sie im C# entsprechenden Code die `Language` -Eigenschaft fest, z. b `"ar-SA"`. auf.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Wenn Sie die `Language` -Eigenschaft auf die Benutzeroberflächen Sprache des aktuellen Benutzers festlegen müssen, verwenden Sie den folgenden Code.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>stellt die aktuelle Kultur dar, die vom aktuellen Thread zur Laufzeit verwendet wird.  
  
 Das abschließende [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] Beispiel sollte in etwa wie im folgenden Beispiel aussehen.  
  
 [!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Das abschließende C# Beispiel sollte in etwa wie folgt aussehen.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 In der folgenden Abbildung wird gezeigt, wie das Fenster für beide Programmiersprachen aussieht und wie arabische Zahlen angezeigt werden:
     
 ![Grafik, in der arabische Zahlen angezeigt werden.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)  
  
 **Mithilfe der Ersetzungseigenschaft**  
  
 Die Art [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.FlowDirection>und Weise, in der die Zahl der Ersetzung funktioniert, hängt sowohl von der Sprache des Text Elements als auch von der Wenn die <xref:System.Windows.FlowDirection> von links nach rechts ist, werden die europäischen Ziffern gerendert. Wenn jedoch ein arabischer Text vorangestellt ist, oder wenn die Sprache auf "ar" festgelegt ist <xref:System.Windows.FlowDirection> und <xref:System.Windows.FlowDirection.RightToLeft>der ist, werden stattdessen arabische Ziffern gerendert.  
  
 In einigen Fällen möchten Sie jedoch eine einheitliche Anwendung, zum Beispiel mit europäischen Ziffern für alle Benutzer erstellen. Oder arabische Ziffern in <xref:System.Windows.Documents.Table> Zellen mit einem bestimmten <xref:System.Windows.Style>. Eine einfache Möglichkeit hierfür ist die Verwendung der <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> -Eigenschaft.  
  
 Im folgenden Beispiel ist die- <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> Eigenschaft in der ersten nicht festgelegt, sodass der Algorithmus wie erwartet arabische Ziffern anzeigt. In der zweiten <xref:System.Windows.Controls.TextBlock>wird die Ersetzung jedoch auf das europäisch festgelegt, das die Standard Ersetzung für arabische Zahlen überschreibt, und die europäischen Ziffern werden angezeigt.  
  
 [!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
