---
title: "Übersicht über bidirektionale Features in WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 716774efdf62356c2e3253c588dabb51de74470c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="bidirectional-features-in-wpf-overview"></a>Übersicht über bidirektionale Features in WPF
Im Gegensatz zu anderen Entwicklungsplattform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über zahlreiche Features, die schnelle Entwicklung von bidirektionalen Inhalt unterstützen, z. B. Links gemischten links nach rechts und mit der rechten Maustaste auf die Daten im selben Dokument. Zur gleichen Zeit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erstellt eine ausgezeichnete Erfahrung für Benutzer, die bidirektionalen Funktionen wie Arabisch und Hebräisch sprechen Benutzer erfordern.  
  
 In den folgenden Abschnitten werden bidirektionale Funktionen sowie Beispiele erklärt, die zeigen, wie die beste Anzeige von bidirektionalem Inhalts erreicht werden kann. Die meisten der Beispiele verwenden [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], obwohl Sie einfach die Konzepte, die Sie anwenden können [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] oder [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] Code.  
  

  
<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 Die grundlegende-Eigenschaft, die definiert, die Inhalt flussrichtung in einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Diese Eigenschaft kann festgelegt werden, auf einen von zwei Enumerationswerten <xref:System.Windows.FlowDirection.LeftToRight> oder <xref:System.Windows.FlowDirection.RightToLeft>. Die Eigenschaft ist für alle verfügbaren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, die von erben <xref:System.Windows.FrameworkElement>.  
  
 Die folgenden Beispiele stellen die flussrichtung von einer <xref:System.Windows.Controls.TextBox> Element.  
  
 **Flussrichtung von links nach rechts**  
  
 [!code-xaml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Flussrichtung von rechts nach links**  
  
 [!code-xaml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 Die folgende Grafik zeigt, wie der vorherige Code gerendert wird.  
  
 **Grafik, die FlowDirection veranschaulicht**  
  
 ![TextBlock-Ausrichtung](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.PNG "LefttoRightRighttoLeft")  
  
 Ein Element in einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Struktur erben die <xref:System.Windows.FrameworkElement.FlowDirection%2A> aus dem zugehörigen Container. Im folgenden Beispiel die <xref:System.Windows.Controls.TextBlock> befindet sich innerhalb einer <xref:System.Windows.Controls.Grid>, die befindet sich in einem <xref:System.Windows.Window>. Festlegen der <xref:System.Windows.FrameworkElement.FlowDirection%2A> für die <xref:System.Windows.Window> festlegen, wird es für die <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.TextBlock> ebenfalls.  
  
 Das folgende Beispiel veranschaulicht die Einstellung <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 [!code-xaml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Die oberste Ebene <xref:System.Windows.Window> verfügt über eine <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>, sodass alle darin enthaltenen Elemente ebenfalls die gleiche erben <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Nach einem Element einer angegebenen überschreiben <xref:System.Windows.FrameworkElement.FlowDirection%2A> es muss einen expliziter Richtungswechsel z. B. das zweite hinzufügen <xref:System.Windows.Controls.TextBlock> im vorherigen Beispiel die Änderungen an <xref:System.Windows.FlowDirection.LeftToRight>. Wenn kein <xref:System.Windows.FrameworkElement.FlowDirection%2A> definiert ist, der Standardwert <xref:System.Windows.FlowDirection.LeftToRight> gilt.  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels.  
  
 **Grafik, die die explizit zugewiesene FlowDirection anzeigt**  
  
 ![Darstellung der Flussrichtung](../../../../docs/framework/wpf/advanced/media/flowdir.PNG "FlowDir")  
  
<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Viele Entwicklungsplattformen, z. B. [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] und Java, bieten spezielle Unterstützung für die Entwicklung von bidirektionalen Inhalt. Markupsprachen wie z. B. [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] bieten Verfasser des Inhalts der erforderliche Markup zum Anzeigen von Text in eine beliebige Richtung, z. B. die [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 Tag, "Dir", die "Rtl" oder "Ltr" als Werte akzeptiert. Dieses Tag ist ähnlich wie die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft, aber die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft funktioniert auf anspruchsvollere Weise auf Layout Textinhalt und für den Inhalt als Text verwendet werden können.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Documents.FlowDocument> ist eine vielseitige [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Element, das eine Kombination von Text, Tabellen, Bilder und andere Elemente hosten kann. Die Beispiele in den folgenden Abschnitten verwenden dieses Element.  
  
 Hinzufügen von Text zu einem <xref:System.Windows.Documents.FlowDocument> kann mehrere Methoden erfolgen. Eine einfache Möglichkeit hierzu ist, über eine <xref:System.Windows.Documents.Paragraph> ist ein Block-Level-Element, das verwendet zum Gruppieren von Inhalten z. B. Text. Hinzufügen von Text zu Inline-Level-Elementen die Beispiele verwenden <xref:System.Windows.Documents.Span> und <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span>ist ein Element der Inlineebene Inhalt zum Gruppieren anderer Inlineelemente verwendet während einer <xref:System.Windows.Documents.Run> ein Inlineebene Content Element vorgesehen, um eine Ausführung von nicht formatiertem Text enthalten ist. Ein <xref:System.Windows.Documents.Span> kann mehrere enthalten <xref:System.Windows.Documents.Run> Elemente.  
  
 Im erste Dokumentbeispiel enthält ein Dokument, das eine Reihe von Namen aufweisen. z. B. `\\server1\folder\file.ext`. Egal, ob Sie diesen Netzwerklink in einem arabischen oder einem englischen Dokument haben, Sie möchten, dass es immer auf die gleiche Weise angezeigt wird. Die folgende Abbildung zeigt den Link in einem arabischen <xref:System.Windows.FlowDirection.RightToLeft> Dokument.  
  
 **Grafik veranschaulicht, wie das Span-Element zu verwenden ist**  
  
 ![Dokument, das von rechts nach links fließt](../../../../docs/framework/wpf/advanced/media/flowdocument.PNG "FlowDocument")  
  
 Da der Text ist <xref:System.Windows.FlowDirection.RightToLeft>, alle spezielle Zeichen, z. B. die "\\", trennen Sie den Text in von rechts nach links. Das Ergebnis ist des Links nicht in der richtigen Reihenfolge angezeigt wird, daher um das Problem zu beheben, der Text muss werden embedded um einen separaten beizubehalten <xref:System.Windows.Documents.Run> fließen <xref:System.Windows.FlowDirection.LeftToRight>. Anstatt eine Separate <xref:System.Windows.Documents.Run> für jede einzelne Sprache ist eine bessere Möglichkeit zur Behebung des Problems, die weniger häufig verwendeten englischen Text in einem größeren Arabisch einbetten <xref:System.Windows.Documents.Span>.  
  
 Dies wird in der folgenden Grafik dargestellt.  
  
 **Grafik, die veranschaulicht, wie Sie das Laufzeit-Element eingebettet in ein Span-Element verwenden**  
  
 ![XamlPad-Bildschirmabbildung](../../../../docs/framework/wpf/advanced/media/runspan.PNG "RunSpan")  
  
 Das folgende Beispiel veranschaulicht die Verwendung <xref:System.Windows.Documents.Run> und <xref:System.Windows.Documents.Span> Elemente in Dokumenten.  
  
 [!code-xaml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Span-Elemente  
 Die <xref:System.Windows.Documents.Span> Element als Grenze Trennzeichen zwischen Texte mit unterschiedlichen flussrichtungen funktioniert.  Sogar <xref:System.Windows.Documents.Span> Elemente mit dem gleichen flussrichtung als mit anderen bidirektionalen Bereiche Dies bedeutet, dass die <xref:System.Windows.Documents.Span> Elemente werden in des Containers sortiert <xref:System.Windows.FlowDirection>, nur der Inhalt innerhalb der <xref:System.Windows.Documents.Span> Element folgt der <xref:System.Windows.FlowDirection> von der <xref:System.Windows.Documents.Span>.  
  
 Die folgende Abbildung zeigt die flussrichtung von mehreren <xref:System.Windows.Controls.TextBlock> Elemente.  
  
 **Grafik, die FlowDirection in mehreren TextBlock-Elementen veranschaulicht**  
  
 ![Textblöcke mit unterschiedlichen Flussrichtungen](../../../../docs/framework/wpf/advanced/media/span.PNG "Span")  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Documents.Span> und <xref:System.Windows.Documents.Run> Elemente, die in der vorherigen Abbildung gezeigten Ergebnisse zu erzeugen.  
  
 [!code-xaml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 In der <xref:System.Windows.Controls.TextBlock> Elemente im Beispiel wird die <xref:System.Windows.Documents.Span> Elemente angeordnet werden, gemäß der <xref:System.Windows.FlowDirection> von ihren übergeordneten Elementen, jedoch der Text innerhalb der einzelnen <xref:System.Windows.Documents.Span> Element Flüsse gemäß seiner eigenen <xref:System.Windows.FlowDirection>. Dies gilt für Latein und Arabisch - oder jede andere Sprache.  
  
### <a name="adding-xmllang"></a>Hinzufügen von xml:lang  
 Die folgende Abbildung zeigt ein weiteres Beispiel, das Zahlen und arithmetische Ausdrücke, wie z. B. verwendet `"200.0+21.4=221.4"`. Beachten Sie, dass nur die <xref:System.Windows.FlowDirection> festgelegt ist.  
  
 **Grafik, die Zahlen anzeigt, die nur FlowDirection verwenden**  
  
 ![Zahlen, die von rechts nach links fließen](../../../../docs/framework/wpf/advanced/media/langattribute.PNG "LangAttribute")  
  
 Benutzer dieser Anwendung, obwohl von der Ausgabe enttäuscht der <xref:System.Windows.FlowDirection> die Zahlen sind nicht strukturiert, wie Arabische Zahlen korrekt ist.  
  
 XAML-Elementen zählen eine [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Attribut (`xml:lang`), der die Sprache des jeweiligen Elements definiert. XAML unterstützt auch eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Sprache Prinzip bei dem `xml:lang` Werte, die auf übergeordneten Elemente in der Struktur angewendet werden von untergeordneten Elementen verwendet. Im vorherigen Beispiel da eine Sprache für nicht definiert wurde die <xref:System.Windows.Documents.Run> Element oder keines der obersten Ebene Elemente, die Standardeinstellung `xml:lang` verwendet wurde, also `en-US` für XAML. Die internen Anzahl strukturieren Algorithmus des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] wählt Zahlen in die entsprechende Sprache – in diesem Fall Englisch. Um die arabischen Zahlen korrekt zu rendern `xml:lang` muss festgelegt werden.  
  
 Die folgende Abbildung zeigt das Beispiel mit `xml:lang` hinzugefügt.  
  
 **Grafik, die veranschaulicht, wie das xml:lang-Attribut verwendet wird**  
  
 ![Arabische Zahlen, die von rechts nach links fließen](../../../../docs/framework/wpf/advanced/media/langattribute2.PNG "LangAttribute2")  
  
 Im folgenden Beispiel wird `xml:lang` an die Anwendung.  
  
 [!code-xaml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Beachten Sie, dass viele Sprachen verschiedene sind `xml:lang` Werte je nach z. B. die Zielregion `"ar-SA"` und `"ar-EG"` zwei Variationen von Arabisch darstellen. In den vorherigen Beispielen veranschaulichen, dass Sie beide definieren müssen die `xml:lang` und <xref:System.Windows.FlowDirection> Werte.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>FlowDirection mit Nicht-Text-Elementen  
 <xref:System.Windows.FlowDirection>definiert, nicht nur in einem Text-Element, sondern auch die flussrichtung von fast allen anderen Textfluss [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Element. Die folgende Grafik zeigt eine <xref:System.Windows.Controls.ToolBar> , verwendet eine horizontale <xref:System.Windows.Media.LinearGradientBrush> Hintergrund gezeichnet werden soll.  
  
 **Grafik, die eine ToolBar mit einem Farbverlauf von rechts nach links zeigt**  
  
 ![Farbverlauf-Bildschirmabbildung](../../../../docs/framework/wpf/advanced/media/gradient.PNG "Gradient")  
  
 Nach dem Festlegen der <xref:System.Windows.FlowDirection> auf <xref:System.Windows.FlowDirection.RightToLeft>, nicht nur die <xref:System.Windows.Controls.ToolBar> Schaltflächen werden von rechts nach links, aber auch den angeordnet <xref:System.Windows.Media.LinearGradientBrush> richtet die Offsets, um von rechts nach links fließen.  
  
 Die folgende Abbildung zeigt die neu ausrichten, der die <xref:System.Windows.Media.LinearGradientBrush>.  
  
 **Grafik, die eine ToolBar mit einem Farbverlauf von rechts nach links zeigt**  
  
 ![Ein Farbverlauf, der von rechts nach links fließt](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.PNG "Gradient2_WPF")  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>. (Um sie von links nach rechts zeichnen, entfernen Sie die <xref:System.Windows.FlowDirection> -Attribut auf die <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>FlowDirection-Ausnahmen  
 Es gibt einige Fälle, in denen <xref:System.Windows.FlowDirection> verhält sich nicht wie erwartet. In diesem Abschnitt werden zwei von diesen Ausnahmen behandelt.  
  
 **Image**  
  
 Ein <xref:System.Windows.Controls.Image> stellt ein Steuerelement, das ein Bild anzeigt. In [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] kann verwendet werden, mit einer <xref:System.Windows.Controls.Image.Source%2A> , definiert die [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] von der <xref:System.Windows.Controls.Image> angezeigt.  
  
 Im Gegensatz zu anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente ein <xref:System.Windows.Controls.Image> erbt nicht das <xref:System.Windows.FlowDirection> aus dem Container. Jedoch, wenn die <xref:System.Windows.FlowDirection> explizit auf festgelegt ist <xref:System.Windows.FlowDirection.RightToLeft>, einem <xref:System.Windows.Controls.Image> horizontal gekippt angezeigt wird. Dies wird als eine praktische Funktion für Entwickler von bidirektionalem Inhalt implementiert, da in einigen Fällen das horizontale Spiegeln des Bildes den gewünschten Effekt erzeugt.  
  
 Die folgende Abbildung zeigt eine gespiegelte <xref:System.Windows.Controls.Image>.  
  
 **Grafik, die ein gespiegeltes Bild anzeigt**  
  
 ![XamlPad-Bildschirmabbildung](../../../../docs/framework/wpf/advanced/media/image.PNG "Image")  
  
 Das folgende Beispiel zeigt, dass die <xref:System.Windows.Controls.Image> erben nicht die <xref:System.Windows.FlowDirection> aus der <xref:System.Windows.Controls.StackPanel> , die Sie enthält. **Hinweis** benötigen Sie eine Datei namens **ms_logo.jpg** auf dem Laufwerk C:\, um dieses Beispiel ausführen.  
  
 [!code-xaml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Hinweis** eingeschlossene in das Herunterladen von Dateien ist eine **ms_logo.jpg** Datei. Der Code geht davon aus, dass die JPG-Datei sich nicht in Ihrem Projekt, sondern an einer beliebigen Stelle auf dem Laufwerk C:\ befindet. Sie kopieren das .jpg aus den Projektdateien auf Ihr Laufwerk C:\ oder ändern den Code, um die Datei im Projekt zu suchen. Ändern Sie hierzu `Source="file://c:/ms_logo.jpg"` auf `Source="ms_logo.jpg"`.  
  
 **Pfade**  
  
 Zusätzlich zu einer <xref:System.Windows.Controls.Image>, ist ein weiteres interessantes Element <xref:System.Windows.Shapes.Path>. Ein Pfad ist ein Objekt, das eine Reihe von miteinander verbundenen Linien und Kurven zeichnen kann. Verhält er sich auf ähnliche Weise eine <xref:System.Windows.Controls.Image> im Hinblick auf seine <xref:System.Windows.FlowDirection>, z. B. seine <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> horizontale spiegelt die <xref:System.Windows.FlowDirection.LeftToRight> eine. Anders als bei einer <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> erbt seine <xref:System.Windows.FlowDirection> aus dem Container und eine muss nicht explizit anzugeben.  
  
 Im folgenden Beispiel wird ein einfacher Pfeil mit drei Linien gezeichnet. Erbt von der erste Pfeil die <xref:System.Windows.FlowDirection.RightToLeft> flussrichtung aus der <xref:System.Windows.Controls.StackPanel> , damit die Start- und Endpunkte über einen Stamm auf der rechten Seite gemessen werden. Den zweiten Pfeil mit einem expliziten <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> auch auf der rechten Seite beginnt. Der dritte Pfeil hat jedoch seinen Startstamm auf der linken Seite. Weitere Informationen zum Zeichnen finden Sie unter <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xaml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels.  
  
 **Grafik, die mit dem Pfad-Element gezeichnete Pfeile veranschaulicht**  
  
 ![Paths](../../../../docs/framework/wpf/advanced/media/paths.PNG "Paths")  
  
 Die <xref:System.Windows.Controls.Image> und <xref:System.Windows.Shapes.Path> sind zwei Beispiele für die Verwendung [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verwendet <xref:System.Windows.FlowDirection>. Neben radiallayoutmodul [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente in eine bestimmte Richtung innerhalb eines Containers <xref:System.Windows.FlowDirection> können mit Elementen verwendet werden, z. B. <xref:System.Windows.Controls.InkPresenter> rendert Freihandeingaben auf einer Oberfläche <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Rechts nach links-Verhalten für Ihre Inhalte benötigt werden, die eine von links nach rechts-Verhalten imitiert oder umgekehrt, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet diese Funktion.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Ersetzen von Zahlen  
 In der Vergangenheit [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] unterstützt Ersetzen von Zahlen können die Darstellung der verschiedenen Formen für die gleichen Ziffern Weiterleitungstopologie im internen Speicher dieses diese unterschiedliche Gebietsschemas Ziffern für Zahlen gespeichert werden Ihre bekannte Hexadezimalwerte, 0 x 40, 0 x 41 nach, jedoch entsprechend der ausgewählten Sprache angezeigt.  
  
 Dies ist zulässig, Anwendungen zum Verarbeiten von numerischen Werten, ohne dass sie von einer Sprache in eine andere zu konvertieren, z. B. ein Benutzer öffnen kann ein [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] Kalkulationstabelle in eine lokalisierte Arabisch [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und finden Sie unter der Zahlen in Arabisch strukturiert, aber öffnen Sie es in eine Europäischen Version [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und Europäischen Darstellung des gleichen Zahlen angezeigt. Dies ist auch für andere Symbole, wie z.B. Kommas als Trennzeichen und das Prozentsatzsymbol notwendig, da sie normalerweise Zahlen in einem Dokument begleiten.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] führt diese Tradition fort und fügt weitere Unterstützung für diese Funktion hinzu, die mehreren Benutzern die Steuerung darüber ermöglicht, wann und wie die Ersetzung verwendet wird. Diese Funktion ist für jede Sprache konzipiert, da sie besonders für bidirektionalen Inhalt nützlich ist, bei dem die Strukturierung von Ziffern für eine bestimmte Sprache in der Regel eine Herausforderung für die Entwickler der Anwendung darstellt, da eine Anwendung aufgrund der verschiedenen Kulturen möglicherweise weiter ausgeführt wird.  
  
 Die Core-Eigenschaft, die zur Steuerung der Zahlen wie funktioniert in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> Abhängigkeitseigenschaft. Die <xref:System.Windows.Media.NumberSubstitution> Klasse gibt an, wie Zahlen im Text angezeigt werden. Er verfügt über drei öffentliche Eigenschaften, die sein Verhalten definieren. Es folgt eine Zusammenfassung der einzelnen Eigenschaften.  
  
 **CultureSource:**  
  
 Diese Eigenschaft gibt an, wie die Kultur für Zahlen bestimmt wird. Sie akzeptiert einen von drei <xref:System.Windows.Media.NumberCultureSource> Enumerationswerte.  
  
-   Override: Zahl ist die Kultur der <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> Eigenschaft.  
  
-   Text: Die Kultur der Zahl, ist die Kultur der Textausführung. Im Markup, wäre dies `xml:lang`, oder dessen Alias `Language` Eigenschaft (<xref:System.Windows.FrameworkElement.Language%2A> oder <xref:System.Windows.FrameworkContentElement.Language%2A>). Dies ist auch die Standardeinstellung für Klassen ableiten von <xref:System.Windows.FrameworkContentElement>. Diese Klassen umfassen <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> usw. lauten.  
  
-   Benutzer: Die Kultur der Zahl, ist die Kultur des aktuellen Threads. Diese Eigenschaft ist die Standardeinstellung für alle Unterklassen von <xref:System.Windows.FrameworkElement> wie z. B. <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> und <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 Die <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> Eigenschaft wird nur verwendet, wenn die <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> -Eigenschaftensatz auf <xref:System.Windows.Media.NumberCultureSource.Override> und wird andernfalls ignoriert. Es gibt die Kultur der Zahl an. Der Wert `null`, der Standardwert wird als En-US interpretiert.  
  
 **Ersetzung**:  
  
 Diese Eigenschaft gibt den Typ der zu ersetzenden Zahl an. Er nimmt eine der folgenden <xref:System.Windows.Media.NumberSubstitutionMethod> Enumerationswerte.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Die Ersetzungsmethode wird basierend auf der Anzahl Kultur bestimmt <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> Eigenschaft. Dies ist die Standardeinstellung.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Wenn die Kultur eine Kultur Arabisch oder Farsi ist, gibt es an, dass die Ziffern für den Kontext abhängig sind.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Zahlen werden immer als Europäischen Ziffern gerendert.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Zahlen werden mit den nationalen Ziffern für die Kultur, entsprechend den Angaben von der Kultur gerendert <xref:System.Globalization.CultureInfo.NumberFormat%2A>.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Zahlen werden mit den herkömmlichen Ziffern für die Kultur gerendert. Für die meisten Kulturen, dies ist identisch mit <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Allerdings <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> westlichen Ziffern für einige arabischen Kulturen während dieser Wert für alle arabische Kulturen arabische Ziffern führt.  
  
 Was bedeuten diese Werte für einen Entwickler von bidirektionalem Inhalt? In den meisten Fällen muss der Entwickler möglicherweise nur zum Definieren <xref:System.Windows.FlowDirection> und die Sprache des jeweiligen Text [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Element, z. B. `Language="ar-SA"` und <xref:System.Windows.Media.NumberSubstitution> übernimmt die Logik zum Anzeigen von Zahlen entsprechend den richtigen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Das folgende Beispiel veranschaulicht die Verwendung von arabischem und englischem Zahlen in einem [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in einer arabischen Version der ausgeführten Anwendung [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-xaml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 Die folgende Abbildung zeigt die Ausgabe der im vorherigen Beispiel, wenn Sie in einer arabischen Version von ausgeführt werden [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 **Grafik, die arabische und englische Zahlen angezeigt**  
  
 ![XamlPad-Bildschirmabbildung mit Zahlen](../../../../docs/framework/wpf/advanced/media/numbers.PNG "Numbers")  
  
 Die <xref:System.Windows.FlowDirection> wurde wichtig in diesem Fall da das Festlegen der <xref:System.Windows.FlowDirection> auf <xref:System.Windows.FlowDirection.LeftToRight> würde stattdessen haben ergab europäische Ziffern. In den folgenden Abschnitten wird erläutert, wie eine einheitliche Anzeige von Ziffern im gesamten Dokument möglich ist. Wenn dieses Beispiel in einem arabischen Windows nicht ausgeführt wird, werden alle Ziffern als europäische Ziffern angezeigt.  
  
 **Definieren von Ersetzungsregeln**  
  
 In einer realen Anwendung müssen Sie die Sprache programmgesteuert festlegen. Angenommen, die Sie festlegen möchten die `xml:lang` Attribut identisch mit den durch des Systems verwendet werden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], oder die Sprache abhängig vom Zustand Anwendung möglicherweise geändert.  
  
 Wenn Sie möchten Änderungen auf der Grundlage von Zustand der Anwendung, stellen verwenden anderer Funktionen, die von bereitgestellte [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Legen Sie zuerst der Anwendungskomponente `NumberSubstitution.CultureSource="Text"`. Mit dieser Einstellung wird sichergestellt, dass die Einstellungen nicht aus der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für Textelemente, die "User" als Standard verwendet, z. B. auf <xref:System.Windows.Controls.TextBlock>.  
  
 Zum Beispiel:  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 In der entsprechenden [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)] code, legen Sie die `Language` Eigenschaft z. B. zum `"ar-SA"`.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 Wenn Sie festlegen müssen die `Language` Eigenschaft mit des aktuellen Benutzers [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Sprache verwenden Sie den folgenden Code.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A>Stellt die aktuelle Kultur, die vom aktuellen Thread zur Laufzeit verwendet.  
  
 Die fertige [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] Beispiel sollte ähnlich wie im folgenden Beispiel werden.  
  
 [!code-xaml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Die fertige [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] Beispiel sollte etwa wie folgt sein.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 Die folgende Grafik zeigt, wie das Fenster für beide Programmiersprachen aussieht.  
  
 **Grafik, die Arabische Zahlen anzeigt**  
  
 ![Arabische Zahlen](../../../../docs/framework/wpf/advanced/media/numbers2.PNG "Numbers2")  
  
 **Mithilfe der Ersetzungseigenschaft**  
  
 Die Weise Zahlen funktioniert in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] hängt sowohl die Sprache des Textelements und dessen <xref:System.Windows.FlowDirection>. Wenn die <xref:System.Windows.FlowDirection> wird von links nach rechts, und klicken Sie dann europäische Ziffern gerendert werden. Jedoch wenn es arabischen Text vorangestellt ist, oder "Ar" ist die Sprache festgelegt und die <xref:System.Windows.FlowDirection> ist <xref:System.Windows.FlowDirection.RightToLeft>, Arabische Ziffern werden stattdessen gerendert.  
  
 In einigen Fällen möchten Sie jedoch eine einheitliche Anwendung, zum Beispiel mit europäischen Ziffern für alle Benutzer erstellen. Oder arabische Ziffern im <xref:System.Windows.Documents.Table> Zellen mit einem bestimmten <xref:System.Windows.Style>. Eine einfache Möglichkeit dazu verwenden, ist die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> Eigenschaft.  
  
 Im folgenden Beispiel das erste <xref:System.Windows.Controls.TextBlock> verfügt nicht über die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> Eigenschaft festgelegt, damit der Algorithmus Arabische Ziffern zeigt an, wie erwartet. Jedoch in der zweiten <xref:System.Windows.Controls.TextBlock>auf Europäischen Ersatz festgelegt ist, überschreiben die Standard-Ersetzung für Arabische Zahlen und europäische Ziffern werden angezeigt.  
  
 [!code-xaml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
