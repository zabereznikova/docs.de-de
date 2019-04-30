---
title: Übersicht über bidirektionale Features in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 575598f48b3cfdf636be78a9de6e0c9a7fd9c208
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032018"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Übersicht über bidirektionale Features in WPF
Im Gegensatz zu anderen Entwicklungsplattformen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über viele Features, die eine schnelle Entwicklung von bidirektionalem Inhalt unterstützen, z. B. Links gemischte links nach rechts und von rechts, um Daten im selben Dokument. Zur gleichen Zeit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erstellt eine hervorragende Erfahrung für Benutzer, die bidirektionale Funktionen wie z.B. Arabisch oder Hebräisch sprechende Benutzer benötigen.  
  
 In den folgenden Abschnitten werden bidirektionale Funktionen sowie Beispiele erklärt, die zeigen, wie die beste Anzeige von bidirektionalem Inhalts erreicht werden kann. Die meisten Beispiele verwenden [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], obwohl Sie einfach die Konzepte zum anwenden können C# oder Microsoft Visual Basic-Code.  

<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 Die grundlegende Eigenschaft, die flussrichtung des Inhalts im definiert eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Diese Eigenschaft kann festgelegt werden, auf einen von zwei Enumerationswerten <xref:System.Windows.FlowDirection.LeftToRight> oder <xref:System.Windows.FlowDirection.RightToLeft>. Die Eigenschaft ist für alle verfügbar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, die von erben <xref:System.Windows.FrameworkElement>.  
  
 Die folgenden Beispiele legen die flussrichtung von einer <xref:System.Windows.Controls.TextBox> Element.  
  
 **Flussrichtung von links nach rechts**  
  
 [!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Flussrichtung von rechts nach links**  
  
 [!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 Die folgende Grafik zeigt, wie der vorherige Code gerendert wird.  
    
 ![Grafik, die die unterschiedlichen flussrichtungen veranschaulicht.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)  
  
 Ein Element in einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] -Struktur erbt die <xref:System.Windows.FrameworkElement.FlowDirection%2A> von seinem Container. Im folgenden Beispiel die <xref:System.Windows.Controls.TextBlock> befindet sich innerhalb einer <xref:System.Windows.Controls.Grid>, befindet sich in einem <xref:System.Windows.Window>. Festlegen der <xref:System.Windows.FrameworkElement.FlowDirection%2A> für die <xref:System.Windows.Window> festlegen, wird es für die <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.TextBlock> ebenfalls.  
  
 Das folgende Beispiel zeigt die Einstellung <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 [!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Die oberste Ebene <xref:System.Windows.Window> verfügt über eine <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>, sodass alle darin enthaltenen Elemente ebenfalls die gleiche erben <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Für ein Element eines angegebenen überschreiben <xref:System.Windows.FrameworkElement.FlowDirection%2A> es muss einen expliziter Richtungswechsel wie z.B. das zweite hinzufügen <xref:System.Windows.Controls.TextBlock> im vorherigen Beispiel in dem Änderungen an <xref:System.Windows.FlowDirection.LeftToRight>. Wenn kein <xref:System.Windows.FrameworkElement.FlowDirection%2A> definiert ist, der Standardwert <xref:System.Windows.FlowDirection.LeftToRight> gilt.  
  
 Die folgende Abbildung zeigt die Ausgabe des vorherigen Beispiels:

 ![Grafik, die die explizite Flow Richtungswechsel veranschaulicht.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)  

<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Viele Entwicklungsplattformen, z. B. [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] und Java, bieten spezielle Unterstützung für die Entwicklung von bidirektionalem Inhalt. Markupsprachen, wie z. B. [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] bieten Inhaltsautoren die notwendigen Markups zum Anzeigen von Text in jeder beliebigen Richtung, z. B. die [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0-Tag, "Dir", das "Rtl" oder "Ltr" als Werte akzeptiert. Dieses Tag ist ähnlich wie die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft, aber die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft eine erweiterte Methode, um Textinhalte zu Layouten funktioniert und für andere Inhalte als Text verwendet werden können.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Documents.FlowDocument> ist ein vielseitiges [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Element, das eine Kombination aus Text, Tabellen, Bildern und anderen Elementen hosten kann. Die Beispiele in den folgenden Abschnitten verwenden dieses Element.  
  
 Hinzufügen von Text zu einem <xref:System.Windows.Documents.FlowDocument> kann in mehrere Methoden ausgeführt werden. Eine einfache Möglichkeit hierzu ist ein <xref:System.Windows.Documents.Paragraph> Dies ist ein Block-Level-Element, das Gruppeninhalte wie z.B. Text verwendet. Hinzufügen von Text zu Inline-Level-Elementen in den Beispielen verwendet <xref:System.Windows.Documents.Span> und <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span> ist ein fortlaufendes Inhaltselement zum Gruppieren anderer Inlineelemente, während eine <xref:System.Windows.Documents.Run> ist ein ein fortlaufendes Inhaltselement Element vorgesehen, die eine Ausführung von nicht formatiertem Text enthalten. Ein <xref:System.Windows.Documents.Span> können enthält mehrere <xref:System.Windows.Documents.Run> Elemente.  
  
 Das erste Dokumentbeispiel enthält ein Dokument, die eine Reihe von Netzwerkfreigabenamen aufweist. z. B. `\\server1\folder\file.ext`. Egal, ob Sie diesen Netzwerklink in einem arabischen oder einem englischen Dokument haben, Sie möchten, dass es immer auf die gleiche Weise angezeigt wird. Die folgende Grafik veranschaulicht die Verwendung des Span-Elements und zeigt den Link in einem arabischen <xref:System.Windows.FlowDirection.RightToLeft> Dokument:

 ![Grafik veranschaulicht, wie das Span-Element. ](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")  
  
 Da der Text ist <xref:System.Windows.FlowDirection.RightToLeft>, alle speziellen Zeichen, z. B. die "\\", trennen den Text in eine Reihenfolge von rechts nach links. Dies führt zu der Link nicht in der richtigen Reihenfolge angezeigt wird, daher um das Problem zu beheben, der Text muss eingebettet werden, um eine Separate beibehalten <xref:System.Windows.Documents.Run> fließen <xref:System.Windows.FlowDirection.LeftToRight>. Anstatt einen separaten <xref:System.Windows.Documents.Run> für jede Sprache eine bessere Möglichkeit zur Lösung des Problems ist, die weniger häufig verwendeten englischen Text in einen größeren arabischen einbetten <xref:System.Windows.Documents.Span>.  
  
 Die folgende Abbildung veranschaulicht diese mithilfe des Testlauf-Elements, das in ein Span-Element eingebettet:

 ![Grafik, die das Ausführen-Element veranschaulicht, die in ein Span-Element eingebettet sind.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)  
  
 Das folgende Beispiel veranschaulicht die Verwendung <xref:System.Windows.Documents.Run> und <xref:System.Windows.Documents.Span> Elemente in Dokumenten.  
  
 [!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Span-Elemente  
 Die <xref:System.Windows.Documents.Span> -Element funktioniert als trennzeichengrenze zwischen Texten mit unterschiedlichen flussrichtungen.  Sogar <xref:System.Windows.Documents.Span> Elemente mit der gleichen flussrichtung gelten, haben andere bidirektionale Geltungsbereiche bedeutet, dass die <xref:System.Windows.Documents.Span> Elemente werden in des Containers sortiert <xref:System.Windows.FlowDirection>, nur der Inhalt innerhalb der <xref:System.Windows.Documents.Span> Element folgt den <xref:System.Windows.FlowDirection> von der <xref:System.Windows.Documents.Span>.  
  
 Die folgende Grafik zeigt die flussrichtung von mehreren <xref:System.Windows.Controls.TextBlock> Elemente.  
    
 ![Grafik, die Textblöcke mit unterschiedlichen flussrichtungen veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Documents.Span> und <xref:System.Windows.Documents.Run> Elemente, die in der vorherigen Abbildung gezeigten Ergebnisse zu erzielen.  
  
 [!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 In der <xref:System.Windows.Controls.TextBlock> Elemente im Beispiel wird die <xref:System.Windows.Documents.Span> Elemente angeordnet werden, gemäß der <xref:System.Windows.FlowDirection> von ihren übergeordneten Elementen, aber der Text innerhalb der einzelnen <xref:System.Windows.Documents.Span> -Elements fließt gemäß seiner eigenen <xref:System.Windows.FlowDirection>. Dies gilt für Latein und Arabisch - oder jede andere Sprache.  
  
### <a name="adding-xmllang"></a>Hinzufügen von xml:lang  
 Die folgende Abbildung zeigt ein anderes Beispiel, Zahlen und arithmetische Ausdrücke, wie z. B. `"200.0+21.4=221.4"`. Beachten Sie, dass nur die <xref:System.Windows.FlowDirection> festgelegt ist.  
    
 ![Grafik, die Zahlen, die nur FlowDirection verwenden anzeigt.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)  
  
 Benutzer dieser Anwendung, obwohl von der Ausgabe enttäuscht der <xref:System.Windows.FlowDirection> richtig ist, wie Arabische Zahlen strukturiert sein sollten, sind die Zahlen nicht strukturiert ist.  
  
 XAML-Elementen zählen eine [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Attribut (`xml:lang`), definiert die Sprache des jeweiligen Elements. XAML unterstützt auch eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Sprache Prinzip durch `xml:lang` Werte, die die übergeordneten Elemente in der Struktur angewendet werden von untergeordneten Elementen verwendet. Im vorherigen Beispiel weil eine Sprache nicht, für definiert wurde die <xref:System.Windows.Documents.Run> Element oder eines der obersten Ebene Elemente, die Standardeinstellung `xml:lang` verwendet wurde, d.h. `en-US` für XAML. Der interne Anzahl strukturieren Algorithmus des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] wählt Zahlen in der entsprechenden Sprache aus – in diesem Fall Englisch. Um die arabischen Zahlen korrekt zu rendern `xml:lang` muss festgelegt werden.  
  
 Die folgende Abbildung zeigt das Beispiel mit `xml:lang` hinzugefügt.  
    
 ![Grafik, die Arabische Zahlen, die von rechts nach links fließen veranschaulicht.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)  
  
 Das folgende Beispiel fügt `xml:lang` an die Anwendung.  
  
 [!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Beachten Sie, dass viele Sprachen unterschiedliche haben `xml:lang` Werte je nach der gewünschten Region, z. B. `"ar-SA"` und `"ar-EG"` zwei Varianten der arabischen Sprache darstellen. Die vorherigen Beispiele zeigen, dass Sie beides definiert, müssen die `xml:lang` und <xref:System.Windows.FlowDirection> Werte.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>FlowDirection mit Nicht-Text-Elementen  
 <xref:System.Windows.FlowDirection> definiert, nicht nur wie Text in einem Textelement, sondern auch die flussrichtung von fast allen anderen fließt [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Element. Die folgende Grafik zeigt eine <xref:System.Windows.Controls.ToolBar> , verwendet eine horizontale <xref:System.Windows.Media.LinearGradientBrush> auf den Hintergrund einer linken zu richtigen Farbverlauf zu zeichnen.  

 ![Grafik, die eine Symbolleiste mit ein von links nach rechts Farbverlauf zeigt.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)  
  
 Nach dem Festlegen der <xref:System.Windows.FlowDirection> zu <xref:System.Windows.FlowDirection.RightToLeft>, nicht nur die <xref:System.Windows.Controls.ToolBar> Schaltflächen werden von rechts nach links, aber auch auf dem angeordnet <xref:System.Windows.Media.LinearGradientBrush> richtet seine Offsets, um die von rechts nach links fließen.  
  
 Die folgende Grafik zeigt die neue Ausrichtung des den <xref:System.Windows.Media.LinearGradientBrush>.  
    
 ![Grafik, die eine Symbolleiste mit der von rechts nach links Farbverlauf zeigt.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)  
  
 Das folgende Beispiel zeichnet eine <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>. (Um sie von links nach rechts zeichnen, entfernen Sie die <xref:System.Windows.FlowDirection> -Attribut für die <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>FlowDirection-Ausnahmen  
 Es gibt einige Fälle, in denen <xref:System.Windows.FlowDirection> nicht wie erwartet verhält. In diesem Abschnitt werden zwei von diesen Ausnahmen behandelt.  
  
 **Image**  
  
 Ein <xref:System.Windows.Controls.Image> stellt ein Steuerelement, das ein Bild anzeigt. In [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] kann verwendet werden, mit einer <xref:System.Windows.Controls.Image.Source%2A> Eigenschaft, die definiert die [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] von der <xref:System.Windows.Controls.Image> angezeigt.  
  
 Im Gegensatz zu anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente ein <xref:System.Windows.Controls.Image> erbt nicht die <xref:System.Windows.FlowDirection> aus dem Container. Aber wenn die <xref:System.Windows.FlowDirection> explizit auf festgelegt ist <xref:System.Windows.FlowDirection.RightToLeft>, eine <xref:System.Windows.Controls.Image> horizontal gespiegelt angezeigt wird. Dies wird als eine praktische Funktion für Entwickler von bidirektionalem Inhalt implementiert, da in einigen Fällen das horizontale Spiegeln des Bildes den gewünschten Effekt erzeugt.  
  
 Die folgende Abbildung zeigt ein gespiegeltes <xref:System.Windows.Controls.Image>.  
    
 ![Grafik, die ein gespiegeltes Bild veranschaulicht.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)  
  
 Das folgende Beispiel zeigt, dass die <xref:System.Windows.Controls.Image> erben nicht die <xref:System.Windows.FlowDirection> aus der <xref:System.Windows.Controls.StackPanel> , die Sie enthält. **Beachten Sie** benötigen Sie eine Datei namens **ms_logo.jpg** auf Ihre C:\ Laufwerk zum Ausführen dieses Beispiels.  
  
 [!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Beachten Sie** enthalten, in die Downloaddateien ist eine **ms_logo.jpg** Datei. Der Code geht davon aus, dass die JPG-Datei sich nicht in Ihrem Projekt, sondern an einer beliebigen Stelle auf dem Laufwerk C:\ befindet. Sie kopieren das .jpg aus den Projektdateien auf Ihr Laufwerk C:\ oder ändern den Code, um die Datei im Projekt zu suchen. Ändern Sie hierzu `Source="file://c:/ms_logo.jpg"` zu `Source="ms_logo.jpg"`.  
  
 **Pfade**  
  
 Zusätzlich zu einer <xref:System.Windows.Controls.Image>, ist ein weiteres interessantes Element <xref:System.Windows.Shapes.Path>. Ein Pfad ist ein Objekt, das eine Reihe von miteinander verbundenen Linien und Kurven zeichnen kann. Es verhält sich ähnlich wie ein <xref:System.Windows.Controls.Image> im Hinblick auf seine <xref:System.Windows.FlowDirection>, z. B. die <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> wird ein horizontaler Spiegel der <xref:System.Windows.FlowDirection.LeftToRight> eine. Anders als bei einer <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> erbt seine <xref:System.Windows.FlowDirection> aus dem Container und einer muss nicht explizit anzugeben.  
  
 Im folgenden Beispiel wird ein einfacher Pfeil mit drei Linien gezeichnet. Der erste Pfeil erbt die <xref:System.Windows.FlowDirection.RightToLeft> flussrichtung aus der <xref:System.Windows.Controls.StackPanel> , damit die Start- und Endpunkt von einem Stammelement auf der rechten Seite gemessen werden. Der zweite Pfeil mit einem expliziten <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> auch auf der rechten Seite beginnt. Der dritte Pfeil hat jedoch seinen Startstamm auf der linken Seite. Weitere Informationen zum Zeichnen finden Sie unter <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels mit Pfeilen, die gezeichnet wird, mit der `Path` Element:

 ![Grafik veranschaulicht, dass die Pfeile, die mit dem Path-Element gezeichnet wird.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)  
  
 Die <xref:System.Windows.Controls.Image> und <xref:System.Windows.Shapes.Path> sind zwei Beispiele für die Verwendung [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verwendet <xref:System.Windows.FlowDirection>. Neben der Ausrichtung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente in einer bestimmten Richtung innerhalb eines Containers, <xref:System.Windows.FlowDirection> können mit Elementen verwendet werden, z. B. <xref:System.Windows.Controls.InkPresenter> die rendert Freihandeingaben auf einer Oberfläche, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Wenn Sie von rechts nach links Verhalten für Ihre Inhalte benötigen, die eine von links nach rechts Verhalten nachahmt oder umgekehrt, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet diese Funktion.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Ersetzen von Zahlen  
 In der Vergangenheit [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] hat zahlenersetzung unterstützt, indem es ermöglicht die Darstellung der verschiedenen kulturellen Formen für die gleichen Ziffern gleichzeitig von den internen Speicher dieser Ziffern unter unterschiedlichen Gebietsschemen für Beispiel Zahlen als gespeichert Ihren bekannten Hexadezimalwerten, 0 x 40, 0 x 41 nach, aber entsprechend der ausgewählten Sprache angezeigt.  
  
 Dadurch konnten Anwendungen, verarbeiten numerische Werte, ohne dass sie von einer Sprache in eine andere zu konvertieren, z. B. ein Benutzers können Sie öffnen ein [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] Arbeitsblatt in einem lokalisierten arabischen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und die Zahlen in Arabisch strukturiert, aber öffnen Sie es in einer Europäischen Version von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und sehen die gleichen Zahlen der Europäischen Darstellung. Dies ist auch für andere Symbole, wie z.B. Kommas als Trennzeichen und das Prozentsatzsymbol notwendig, da sie normalerweise Zahlen in einem Dokument begleiten.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] führt diese Tradition fort und fügt weitere Unterstützung für diese Funktion hinzu, die mehreren Benutzern die Steuerung darüber ermöglicht, wann und wie die Ersetzung verwendet wird. Diese Funktion ist für jede Sprache konzipiert, da sie besonders für bidirektionalen Inhalt nützlich ist, bei dem die Strukturierung von Ziffern für eine bestimmte Sprache in der Regel eine Herausforderung für die Entwickler der Anwendung darstellt, da eine Anwendung aufgrund der verschiedenen Kulturen möglicherweise weiter ausgeführt wird.  
  
 Die Core-Eigenschaft, die Steuern wie zahlenersetzung funktioniert in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> Abhängigkeitseigenschaft. Die <xref:System.Windows.Media.NumberSubstitution> Klasse gibt an, wie Zahlen im Text angezeigt werden. Er verfügt über drei öffentliche Eigenschaften, die sein Verhalten definieren. Es folgt eine Zusammenfassung der einzelnen Eigenschaften.  
  
 **CultureSource:**  
  
 Diese Eigenschaft gibt an, wie die Kultur für Zahlen bestimmt wird. Es akzeptiert einen von drei <xref:System.Windows.Media.NumberCultureSource> -Enumerationswerte fest.  
  
- Außer Kraft setzen: Ist die Kultur der Zahl der <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> Eigenschaft.  
  
- Text: Anzahl ist die Kultur des Lauftexts. Im Markup, wäre dies `xml:lang`, oder dessen Alias `Language` Eigenschaft (<xref:System.Windows.FrameworkElement.Language%2A> oder <xref:System.Windows.FrameworkContentElement.Language%2A>). Darüber hinaus ist die Standardeinstellung für abgeleitete Klassen von <xref:System.Windows.FrameworkContentElement>. Diese Klassen schließen <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> und so weiter.  
  
- Benutzer: Anzahl ist die Kultur des aktuellen Threads. Diese Eigenschaft ist die Standardeinstellung für alle Unterklassen von <xref:System.Windows.FrameworkElement> wie z. B. <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> und <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 Die <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> Eigenschaft wird nur verwendet, wenn die <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> -Eigenschaftensatz auf <xref:System.Windows.Media.NumberCultureSource.Override> und wird andernfalls ignoriert. Es gibt die Kultur der Zahl an. Der Wert `null`, der Standardwert wird als En-US interpretiert.  
  
 **Ersetzung**:  
  
 Diese Eigenschaft gibt den Typ der zu ersetzenden Zahl an. Es akzeptiert einen der folgenden <xref:System.Windows.Media.NumberSubstitutionMethod> -Enumerationswerte fest.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Die Ersetzungsmethode wird basierend auf der Zahlenkultur bestimmt <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> Eigenschaft. Dies ist die Standardeinstellung.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Bei einer arabischen oder persischen Zahlenkultur wird angegeben, dass die Ziffern vom Kontext abhängig sind.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Zahlen werden immer als europäische Ziffern gerendert.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Zahlen werden mit den nationalen Ziffern für die Kultur, laut der Kultur gerendert <xref:System.Globalization.CultureInfo.NumberFormat%2A>.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Zahlen werden mit den traditionellen Ziffern für die Zahlenkultur gerendert. In den meisten Kulturen ist dieser identisch mit <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Allerdings <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> während dieser Wert für alle arabische Kulturen arabische Ziffern für einige arabischen Kulturen lateinische Ziffern führt.  
  
 Was bedeuten diese Werte für einen Entwickler von bidirektionalem Inhalt? In den meisten Fällen muss der Entwickler möglicherweise nur zum Definieren <xref:System.Windows.FlowDirection> und die Sprache von jedem [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Textelement, z.B. `Language="ar-SA"` und <xref:System.Windows.Media.NumberSubstitution> Logik, übernimmt der Anzeige der Zahlen entsprechend der korrekten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Das folgende Beispiel veranschaulicht die Verwendung von Arabische und englische Zahlen in einem [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in einer arabischen Version von ausgeführte Anwendung [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 Die folgende Abbildung zeigt die Ausgabe des obigen Beispiels an, wenn Sie mit der Arabische und englische Zahlen angezeigt, in einer arabischen Version von Windows ausführen:

 ![Grafik, die arabische und englische Zahlen zeigt.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)  
  
 Die <xref:System.Windows.FlowDirection> war wichtig, in diesem Fall denn Festlegen der <xref:System.Windows.FlowDirection> zu <xref:System.Windows.FlowDirection.LeftToRight> würde stattdessen haben ergab europäische Ziffern. In den folgenden Abschnitten wird erläutert, wie eine einheitliche Anzeige von Ziffern im gesamten Dokument möglich ist. Wenn dieses Beispiel in einem arabischen Windows nicht ausgeführt wird, werden alle Ziffern als europäische Ziffern angezeigt.  
  
 **Definieren von Ersetzungsregeln**  
  
 In einer realen Anwendung müssen Sie die Sprache programmgesteuert festlegen. Angenommen, die Sie festlegen möchten die `xml:lang` Attribut verwendet werden, durch der Systemvariable identisch sein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], oder die Sprache je nach den Anwendungsstatus ändern.  
  
 Wenn Sie vornehmen möchten auf Grundlage ändert den Zustand der Anwendung, verwenden Sie andere Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Legen Sie zunächst der Anwendungskomponente `NumberSubstitution.CultureSource="Text"`. Mit dieser Einstellung können Sie sicher, dass die Einstellungen nicht von einem stammen die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für Text-Elemente, die "User" als Standard verwendet, z. B. <xref:System.Windows.Controls.TextBlock>.  
  
Zum Beispiel:  

```xaml  
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

In den entsprechenden C# -Code, legen die `Language` -Eigenschaft, z. B. `"ar-SA"`.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Wenn Sie festlegen müssen die `Language` Eigenschaft, um die aktuelle Sprache der Benutzeroberfläche mithilfe des folgenden Codes.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> die aktuelle Kultur darstellt, die zur Laufzeit vom aktuellen Thread verwendet.  
  
 Das abschließende [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] Beispiel sollte ähnlich wie im folgenden Beispiel werden.  
  
 [!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Das abschließende C# Beispiel sollte etwa wie folgt.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 Die folgende Abbildung zeigt das Fenster für beide Programmiersprachen, die Arabische Zahlen anzeigen:
     
 ![Grafik, die Arabische Zahlen anzeigt.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)  
  
 **Mithilfe der Ersetzungseigenschaft**  
  
 Der Weg zahlenersetzung funktioniert in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sowohl der Sprache des Textelements abhängig und die zugehörige <xref:System.Windows.FlowDirection>. Wenn die <xref:System.Windows.FlowDirection> wird von links nach rechts, und klicken Sie dann die Europäische Ziffern gerendert werden. Aber wenn Arabischer Text vorangestellt ist, oder die Sprache auf "Ar" festgelegt und die <xref:System.Windows.FlowDirection> ist <xref:System.Windows.FlowDirection.RightToLeft>, Arabische Ziffern gerendert werden, stattdessen.  
  
 In einigen Fällen möchten Sie jedoch eine einheitliche Anwendung, zum Beispiel mit europäischen Ziffern für alle Benutzer erstellen. Oder mit arabischen Ziffern in <xref:System.Windows.Documents.Table> Zellen mit einem bestimmten <xref:System.Windows.Style>. Eine einfache Möglichkeit möchten, die verwendet wird, wird die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> Eigenschaft.  
  
 Im folgenden Beispiel ist die erste <xref:System.Windows.Controls.TextBlock> verfügt nicht über die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> -Eigenschaft festgelegt, sodass der Algorithmus zeigt wie erwartet arabische Ziffern an. Jedoch in der zweiten <xref:System.Windows.Controls.TextBlock>, dass Europäisch die Ersetzung festgelegt ist, überschreiben die Standard-Ersetzung für Arabische Zahlen und werden europäische Ziffern angezeigt.  
  
 [!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
