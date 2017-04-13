---
title: "&#220;bersicht &#252;ber bidirektionale Features in WPF | Microsoft Docs"
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
  - "Bidirektionale Features"
  - "FlowDirection-Eigenschaft"
  - "FlowDocument-Eigenschaft"
  - "Span-Elemente"
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# &#220;bersicht &#252;ber bidirektionale Features in WPF
Im Gegensatz zu anderen Entwicklungsplattformen bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viele Features, die die schnelle Entwicklung von bidirektionalem Inhalt unterstützen, beispielsweise Daten, die in einem Dokument von links nach rechts und von rechts nach links dargestellt werden.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist auf Benutzer zugeschnitten, die bidirektionale Features benötigen, z. B. Benutzer, die Arabisch oder Hebräisch sprechen.  
  
 In den folgenden Abschnitten werden bidirektionale Features beschrieben und Beispiele bereitgestellt, die veranschaulichen, wie die beste Anzeige von bidirektionalem Inhalts erzielt wird.  Bei den meisten Beispielen wird [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] verwendet, aber Sie können die Konzepte problemlos in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]\-Code oder [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]\-Code anwenden.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="FlowDirection"></a>   
## FlowDirection  
 Die grundlegende Eigenschaft, die die Flussrichtung des Inhalts in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung definiert, ist <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  Diese Eigenschaft kann auf einen von zwei Enumerationswerten, <xref:System.Windows.FlowDirection> oder <xref:System.Windows.FlowDirection>, festgelegt werden.  Die Eigenschaft steht allen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elementen zur Verfügung, die vom <xref:System.Windows.FrameworkElement> erben.  
  
 In den folgenden Beispielen wird die Flussrichtung eines <xref:System.Windows.Controls.TextBox>\-Elements festgelegt.  
  
 ****Flussrichtung von links nach rechts****  
  
 [!code-xml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 ****Flussrichtung von rechts nach links****  
  
 [!code-xml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 Die folgende Grafik zeigt, wie der Code oben gerendert wird.  
  
 ****Grafik, die die FlowDirection veranschaulicht****  
  
 ![TextBlock&#45;Ausrichtung](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.png "LefttoRightRighttoLeft")  
  
 Ein Element innerhalb einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Struktur erbt die <xref:System.Windows.FrameworkElement.FlowDirection%2A> von seinem Container.  Im folgenden Beispiel befindet sich der <xref:System.Windows.Controls.TextBlock> in einem <xref:System.Windows.Controls.Grid>, das sich in einem <xref:System.Windows.Window> befindet.  Wenn Sie die <xref:System.Windows.FrameworkElement.FlowDirection%2A> für das <xref:System.Windows.Window> festlegen, wird sie auch für das <xref:System.Windows.Controls.Grid> und den <xref:System.Windows.Controls.TextBlock> festgelegt.  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.FrameworkElement.FlowDirection%2A> festgelegt wird.  
  
 [!code-xml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Für das <xref:System.Windows.Window> auf der obersten Ebene ist die <xref:System.Windows.FlowDirection> auf <xref:System.Windows.FlowDirection> festgelegt, sodass alle darin enthaltenen Elemente ebenfalls die gleiche <xref:System.Windows.FrameworkElement.FlowDirection%2A> erben.  Wenn für ein Element eine angegebene <xref:System.Windows.FrameworkElement.FlowDirection%2A> überschrieben werden soll, muss ein expliziter Richtungswechsel hinzugefügt werden, wie z. B. der zweite <xref:System.Windows.Controls.TextBlock> im vorherigen Beispiel, in dem zu <xref:System.Windows.FlowDirection> gewechselt wird.  Wenn keine <xref:System.Windows.FrameworkElement.FlowDirection%2A> definiert ist, wird standardmäßig <xref:System.Windows.FlowDirection> angewendet.  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels.  
  
 ****Grafik, die die explizit zugewiesene FlowDirection veranschaulicht****  
  
 ![Darstellung der Flussrichtung](../../../../docs/framework/wpf/advanced/media/flowdir.png "FlowDir")  
  
<a name="FlowDocument"></a>   
## FlowDocument  
 Viele Entwicklungsplattformen, z. B. [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] und Java, bieten besondere Unterstützung für die Entwicklung von bidirektionalem Inhalt.  Markupsprachen, wie [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], bieten das notwendige Markup für den Verfasser des Inhalts, um den Text in jeder beliebigen Richtung anzuzeigen, beispielsweise den Tag "dir" in [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0, der "rtl" oder "ltr" als Werte akzeptiert.  Dieser Tag ähnelt der <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft, aber die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft bietet erweiterte Möglichkeiten für das Layout von Textinhalt und kann für Inhalte verwendet werden, die kein Text sind.  
  
 <xref:System.Windows.Documents.FlowDocument> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist ein vielseitiges [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Element, das eine Kombination aus Text, Tabellen, Bildern und anderen Elementen hosten kann.  Dieses Element wird in den Beispielen in den folgenden Abschnitten verwendet.  
  
 Es gibt mehrere Methoden für das Hinzufügen von Text zu einem <xref:System.Windows.Documents.FlowDocument>.  Eine einfache Methode besteht darin, einen <xref:System.Windows.Documents.Paragraph> zu verwenden. Es handelt sich dabei um ein Element auf Blockebene, mit dem Inhalt \(beispielsweise Text\) gruppiert werden kann.  In den Beispielen werden die Elemente <xref:System.Windows.Documents.Span> und <xref:System.Windows.Documents.Run> verwendet, um Text zu Elementen auf Inlineebene hinzuzufügen.  <xref:System.Windows.Documents.Span> ist ein fortlaufendes Inhaltselement auf Inlineebene, das zum Gruppieren anderer Inlineelemente verwendet wird, während es sich bei  <xref:System.Windows.Documents.Run> um ein fortlaufendes Inhaltselement auf Inlineebene handelt, das unformatierten Text enthalten kann.  Ein <xref:System.Windows.Documents.Span>\-Element kann mehrere <xref:System.Windows.Documents.Run>\-Elemente enthalten.  
  
 Das erste Dokumentbeispiel enthält ein Dokument, in dem eine Reihe von Netzwerkfreigabenamen enthalten sind, beispielsweise `\\server1\folder\file.ext`.  Dieser Netzwerklink soll immer gleich angezeigt werden, unabhängig davon, ob er in einem arabischen oder einem englischen Dokument enthalten ist.  Die folgende Grafik zeigt den Link in einem arabischen <xref:System.Windows.FlowDirection>\-Dokument.  
  
 ****Grafik, die veranschaulicht, wie das Span\-Element verwendet wird****  
  
 ![Dokument, das von rechts nach links fließt](../../../../docs/framework/wpf/advanced/media/flowdocument.png "FlowDocument")  
  
 Da der Text <xref:System.Windows.FlowDirection> ist, trennen alle Sonderzeichen, wie das Zeichen "\\", den Text in der Reihenfolge von rechts nach links.  Dies führt dazu, dass der Link nicht in der richtigen Reihenfolge angezeigt wird. Zum Beheben des Problems muss der Text eingebettet werden, um ein separates <xref:System.Windows.Documents.Run>\-Element mit der Richtung <xref:System.Windows.FlowDirection> beizubehalten.  Statt für jede Sprache ein separates <xref:System.Windows.Documents.Run>\-Element einzufügen, sollte der weniger häufig verwendete englische Text in ein größeres arabisches <xref:System.Windows.Documents.Span>\-Element eingebettet werden.  
  
 Dies wird in der folgenden Grafik veranschaulicht.  
  
 ****Grafik, die veranschaulicht, wie das in einem Span\-Element eingebettete Run\-Element verwendet wird****  
  
 ![XamlPad&#45;Bildschirmabbildung](../../../../docs/framework/wpf/advanced/media/runspan.png "RunSpan")  
  
 Im folgenden Beispiel wird veranschaulicht, wie das <xref:System.Windows.Documents.Run>\-Element und das <xref:System.Windows.Documents.Span>\-Element in Dokumenten verwendet wird.  
  
 [!code-xml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## Span\-Elemente  
 Das <xref:System.Windows.Documents.Span>\-Element funktioniert als ein Begrenzungstrennzeichen zwischen Textabschnitten mit verschiedenen Flussrichtungen.  Selbst <xref:System.Windows.Documents.Span>\-Elemente mit der gleichen Flussrichtung werden als Elemente mit verschiedenen bidirektionalen Bereichen betrachtet. Das bedeutet, dass die <xref:System.Windows.Documents.Span>\-Elemente in der <xref:System.Windows.FlowDirection> des Containers angeordnet werden. Lediglich der Inhalt im <xref:System.Windows.Documents.Span>\-Element hat die <xref:System.Windows.FlowDirection> des <xref:System.Windows.Documents.Span>\-Elements.  
  
 Die folgende Grafik zeigt die Flussrichtung von mehreren <xref:System.Windows.Controls.TextBlock>\-Elementen.  
  
 ****Grafik, die die FlowDirection in mehreren TextBlock\-Elementen veranschaulicht****  
  
 ![Textblöcke mit unterschiedlichen Flussrichtungen](../../../../docs/framework/wpf/advanced/media/span.png "Span")  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie das <xref:System.Windows.Documents.Span>\-Element und das <xref:System.Windows.Documents.Run>\-Element verwenden, um das in der vorherigen Grafik angezeigte Resultat zu erzielen.  
  
 [!code-xml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 In den <xref:System.Windows.Controls.TextBlock>\-Elementen im Beispiel werden die <xref:System.Windows.Documents.Span>\-Elemente gemäß der <xref:System.Windows.FlowDirection> ihrer übergeordneten Elemente angeordnet. Der Text innerhalb jedes <xref:System.Windows.Documents.Span>\-Elements fließt jedoch gemäß seiner eigenen <xref:System.Windows.FlowDirection>.  Dies gilt für alle Sprachen, sei es Latein oder Arabisch.  
  
### Hinzufügen von xml:lang  
 Die folgende Grafik zeigt ein anderes Beispiel, in dem Zahlen und arithmetische Ausdrücke verwendet werden, z. B. `"200.0+21.4=221.4"`.  Beachten Sie, dass nur die <xref:System.Windows.FlowDirection> festgelegt ist.  
  
 ****Grafik, in der beim Anzeigen von Zahlen nur die FlowDirection verwendet wird****  
  
 ![Zahlen, die von rechts nach links fließen](../../../../docs/framework/wpf/advanced/media/langattribute.png "LangAttribute")  
  
 Benutzer dieser Anwendung werden von der Ausgabe enttäuscht sein, denn obwohl die <xref:System.Windows.FlowDirection> korrekt ist, entspricht die Form der Zahlen nicht der Form, die für arabische Zahlen erwartet wird.  
  
 XAML\-Elemente können ein [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Attribut \(`xml:lang`\) enthalten, das die Sprache jedes Elements definiert.  XAML unterstützt auch ein [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Sprachprinzip, nach dem auf übergeordnete Elemente in der Struktur angewendete `xml:lang`\-Werte von den untergeordneten Elementen verwendet werden.  Da im vorherigen Beispiel weder für das <xref:System.Windows.Documents.Run>\-Element noch für die übergeordneten Elemente der obersten Ebene eine Sprache definiert wurde, wird der Standard\-`xml:lang`\-Wert verwendet, der für XAML `en-US` ist.  Der interne [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Algorithmus für die Zahlendarstellung wählt Zahlen in der entsprechenden Sprache aus \- in diesem Fall Englisch.  Um die arabischen Zahlen korrekt zu rendern, muss `xml:lang` festgelegt werden.  
  
 Die folgende Grafik zeigt das Beispiel, nachdem ein `xml:lang`\-Wert hinzugefügt wurde.  
  
 ****Grafik, die veranschaulicht, wie das xml:lang\-Attribut verwendet wird****  
  
 ![Arabische Zahlen, die von rechts nach links fließen](../../../../docs/framework/wpf/advanced/media/langattribute2.png "LangAttribute2")  
  
 Im folgenden Beispiel wird der Anwendung `xml:lang` hinzugefügt.  
  
 [!code-xml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Beachten Sie, dass es für viele Sprachen unterschiedliche `xml:lang`\-Werte gibt, die von der gewünschten Region abhängen. `"ar-SA"` und `"ar-EG"` stellen zum Beispiel zwei Variationen des Arabischen dar.   In den vorherigen Beispielen wird veranschaulicht, dass Sie sowohl den `xml:lang`\-Wert als auch den <xref:System.Windows.FlowDirection>\-Wert definieren müssen.  
  
<a name="FlowDirectionNontext"></a>   
## FlowDirection mit Elementen, die kein Text sind  
 <xref:System.Windows.FlowDirection> definiert nicht nur die Flussrichtung für Text in einem Textelement, sondern auch für fast alle anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente.  Die folgende Grafik zeigt eine <xref:System.Windows.Controls.ToolBar>, die einen horizontalen <xref:System.Windows.Media.LinearGradientBrush> verwendet, um den Hintergrund zu zeichnen.  
  
 ****Grafik, die eine Symbolleiste mit einem Farbverlauf von links nach rechts zeigt****  
  
 ![Bildschirmabbildung für Farbverlauf](../../../../docs/framework/wpf/advanced/media/gradient.png "Gradient")  
  
 Nachdem die <xref:System.Windows.FlowDirection> auf <xref:System.Windows.FlowDirection> festgelegt ist, werden nicht nur die <xref:System.Windows.Controls.ToolBar>\-Schaltflächen von rechts nach links angeordnet. Selbst der <xref:System.Windows.Media.LinearGradientBrush> ordnet seine Offsets neu von rechts nach links an.  
  
 Die folgende Grafik zeigt die Neuanordnung für den <xref:System.Windows.Media.LinearGradientBrush>.  
  
 ****Grafik, die eine Symbolleiste mit einem Farbverlauf von rechts nach links zeigt****  
  
 ![Ein Farbverlauf, der von rechts nach links fließt](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.png "Gradient2\_WPF")  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.FlowDirection>\-<xref:System.Windows.Controls.ToolBar> gezeichnet.  \(Um sie von links nach rechts zu zeichnen, entfernen Sie das <xref:System.Windows.FlowDirection>\-Attribut auf der <xref:System.Windows.Controls.ToolBar>.\)  
  
 [!code-xml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### FlowDirection\-Ausnahmen  
 Es gibt einige Fälle, in denen sich die <xref:System.Windows.FlowDirection> nicht so verhält, wie erwartet.  In diesem Abschnitt werden zwei von diesen Ausnahmen behandelt.  
  
 **Bild**  
  
 Ein <xref:System.Windows.Controls.Image> stellt ein Steuerelement dar, das ein Bild anzeigt.  In [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] kann es mit einer <xref:System.Windows.Controls.Image.Source%2A>\-Eigenschaft verwendet werden, die den [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] für das anzuzeigende <xref:System.Windows.Controls.Image> enthält.  
  
 Im Gegensatz zu anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elementen erbt ein <xref:System.Windows.Controls.Image> die <xref:System.Windows.FlowDirection> nicht vom Container.  Wenn die <xref:System.Windows.FlowDirection> jedoch explizit auf <xref:System.Windows.FlowDirection> festgelegt wird, wird ein <xref:System.Windows.Controls.Image> horizontal gekippt angezeigt.  Dies wurde als ein praktisches Feature für Entwickler von bidirektionalem Inhalt implementiert, da in manchen Fällen durch das horizontale Kippen des Bilds der gewünschte Effekt erzielt wird.  
  
 Die folgende Grafik zeigt ein gekipptes <xref:System.Windows.Controls.Image>.  
  
 ****Grafik, die ein gekipptes Bild veranschaulicht****  
  
 ![XamlPad&#45;Bildschirmabbildung](../../../../docs/framework/wpf/advanced/media/image.png "Image")  
  
 Im folgenden Beispiel wird veranschaulicht, dass das <xref:System.Windows.Controls.Image> nicht die <xref:System.Windows.FlowDirection> von dem <xref:System.Windows.Controls.StackPanel> erbt, in dem es enthalten ist.  **Hinweis** Beachten Sie, dass auf Laufwerk C:\\ eine Datei mit dem Namen **ms\_logo.jpg** vorhanden sein muss, um dieses Beispiel auszuführen.  
  
 [!code-xml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Hinweis** Die Downloaddateien enthalten die Datei **ms\_logo.jpg**.  Im Code wird davon ausgegangen, dass sich die JPG\-Datei nicht im Projekt, sondern an einem Speicherort auf dem Laufwerk C:\\ befindet.  Sie müssen die JPG\-Datei aus den Projektdateien auf das Laufwerk C:\\ kopieren oder den Code so ändern, dass die Datei im Projekt gesucht wird.  Ändern Sie hierzu `Source="file://c:/ms_logo.jpg"` in `Source="ms_logo.jpg"`.  
  
 ****Pfade****  
  
 Neben einem <xref:System.Windows.Controls.Image> ist ein <xref:System.Windows.Shapes.Path> ein weiteres interessantes Element.  Ein Path ist ein Objekt, das eine Reihe von verbundenen Linien und Kurven zeichnen kann.  Im Hinblick auf die <xref:System.Windows.FlowDirection> verhält er sich ähnlich wie ein <xref:System.Windows.Controls.Image>; beispielsweise ist seine <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection> eine horizontale Spiegelung seiner <xref:System.Windows.FlowDirection>\-Flussrichtung.  Im Gegensatz zu einem <xref:System.Windows.Controls.Image> erbt der <xref:System.Windows.Shapes.Path> seine <xref:System.Windows.FlowDirection> jedoch vom Container, sie muss nicht explizit festgelegt werden.  
  
 Im folgenden Beispiel wird ein einfacher Pfeil mit 3 Linien gezeichnet.  Der erste Pfeil erbt die <xref:System.Windows.FlowDirection>\-Flussrichtung vom <xref:System.Windows.Controls.StackPanel>, sodass seine Anfangs\- und Endpunkte von einem Stammelement auf der rechten Seite gemessen werden.  Der zweite Pfeil, der eine explizite <xref:System.Windows.FlowDirection><xref:System.Windows.FlowDirection> hat, beginnt ebenfalls auf der rechten Seite.  Der dritte Pfeil hat sein Stammelement für den Start auf der linken Seite.  Weitere Informationen zum Zeichnen finden Sie unter <xref:System.Windows.Media.LineGeometry> und unter <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels.  
  
 ****Grafik, die mit dem Path\-Element gezeichnete Pfeile veranschaulicht****  
  
 ![Pfade](../../../../docs/framework/wpf/advanced/media/paths.png "Paths")  
  
 <xref:System.Windows.Controls.Image> und <xref:System.Windows.Shapes.Path> sind zwei Beispiele dafür, wie [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die <xref:System.Windows.FlowDirection> verwendet.  Neben der Ausrichtung von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elementen in einer bestimmten Richtung innerhalb eines Containers kann die <xref:System.Windows.FlowDirection> mit Elementen wie <xref:System.Windows.Controls.InkPresenter> \(rendert Tinte auf einer Oberfläche\), <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush> verwendet werden.  Wenn Sie ein Rechts\-nach\-Links\-Verhalten für Inhalt benötigen, das ein Links\-nach\-Rechts\-Verhalten nachahmt, oder umgekehrt, stellt Ihnen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die erforderlichen Funktionen zur Verfügung.  
  
<a name="NumberSubstitution"></a>   
## Ersetzen von Zahlen  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] hat das Ersetzen von Zahlen traditionell dadurch unterstützt, dass die kulturell verschiedenen Formen für die gleichen Ziffern dargestellt werden können, wobei diese Ziffern intern für unterschiedliche Gebietsschemas einheitlich gespeichert werden. Zahlen werden beispielsweise als bekannte Hexadezimalwerte gespeichert \(0x40, 0x41\), aber je nach gewählter Sprache unterschiedlich angezeigt.  
  
 So können Anwendungen numerische Werte verarbeiten, ohne dass sie von einer Sprache in eine andere konvertiert werden müssen. Ein Benutzer kann beispielsweise ein [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)]\-Arbeitsblatt in einer lokalisierten arabischen Version von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] öffnen und die Zahlen in arabischer Form anzeigen. Er kann auch das gleiche Arbeitsblatt in einer europäischen Version von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] öffnen und die europäische Darstellung der gleichen Zahlen anzeigen.  Dies ist auch für andere Symbole notwendig, z. B. für das Kommatrennzeichen und das Prozentzeichen, da diese Zeichen normalerweise zusammen mit Zahlen in einem Dokument verwendet werden.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] führt diese Tradition fort und fügt zusätzliche Unterstützung für dieses Feature hinzu, mit dem der Benutzer besser steuern kann, wann und wie die Ersetzung verwendet wird.  Während dieses Feature für alle Sprachen entworfen wurde, ist es bei bidirektionalem Inhalt besonders nützlich, da eine Darstellung von Zahlen für eine spezifische Sprache aufgrund der verschiedenen Kulturen, in denen eine Anwendung ausgeführt wird, für gewöhnlich eine Herausforderung für Anwendungsentwickler ist.  
  
 Die Kerneigenschaft, die steuert, wie die Zahlenersetzung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funktioniert, ist die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>\-Abhängigkeitseigenschaft.  Die <xref:System.Windows.Media.NumberSubstitution>\-Klasse gibt an, wie Zahlen im Text angezeigt werden.  Sie hat drei öffentliche Eigenschaften, die ihr Verhalten definieren.  Im Folgenden finden Sie eine Zusammenfassung der einzelnen Eigenschaften.  
  
 ****CultureSource:****  
  
 Diese Eigenschaft gibt an, wie die Kultur für Zahlen bestimmt wird.  Sie akzeptiert einen von drei <xref:System.Windows.Media.NumberCultureSource>\-Enumerationswerten.  
  
-   Override: Die Zahlenkultur ist die Kultur der <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>\-Eigenschaft.  
  
-   Text: Die Zahlenkultur ist die Kultur der Textausführung.  In Markup entspricht dies dem `xml:lang`\-Wert oder der Alias\-`Language`\-Eigenschaft \(<xref:System.Windows.FrameworkElement.Language%2A> oder <xref:System.Windows.FrameworkContentElement.Language%2A>\).  Dies ist auch der Standard für von <xref:System.Windows.FrameworkContentElement> abgeleitete Klassen.  Zu diesen Klassen gehören unter anderem <xref:System.Windows.Documents.Paragraph?displayProperty=fullName>, <xref:System.Windows.Documents.Table?displayProperty=fullName> und <xref:System.Windows.Documents.TableCell?displayProperty=fullName>.  
  
-   User: Die Zahlenkultur ist die Kultur des aktuellen Threads.  Diese Eigenschaft ist die Standardeinstellung für alle Unterklassen von <xref:System.Windows.FrameworkElement> wie <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> und <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 Die <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>\-Eigenschaft wird nur dann verwendet, wenn die <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A>\-Eigenschaft auf <xref:System.Windows.Media.NumberCultureSource> festgelegt ist. Andernfalls wird sie ignoriert.  Sie gibt die Zahlenkultur an.  Der Wert `null`, der Standardwert, wird als en\-US interpretiert.  
  
 **Substitution**:  
  
 Diese Eigenschaft gibt den Typ der auszuführenden Zahlenersetzung an.  Sie akzeptiert einen der folgenden <xref:System.Windows.Media.NumberSubstitutionMethod>\-Enumerationswerte.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: Die Ersetzungsmethode wird auf Grundlage der <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=fullName>\-Eigenschaft der Zahlenkultur bestimmt.  Dies ist die Standardeinstellung.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: Gibt an, dass die Ziffern vom Kontext abhängen, wenn die Zahlenkultur Arabisch oder Farsi ist.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: Zahlen werden immer als europäische Ziffern gerendert.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: Zahlen werden mit den nationalen Ziffern für die Zahlenkultur gerendert, die von der <xref:System.Globalization.CultureInfo.NumberFormat%2A>\-Eigenschaft der Kultur angegeben werden.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: Zahlen werden mit den traditionellen Ziffern für die Zahlenkultur gerendert.  Bei den meisten Kulturen entspricht dies <xref:System.Windows.Media.NumberSubstitutionMethod>.  Bei Verwendung von <xref:System.Windows.Media.NumberSubstitutionMethod> können jedoch für einige arabische Kulturen lateinische Ziffern gerendert werden, während mit diesem Wert für alle arabische Kulturen arabische Ziffern gerendert werden.  
  
 Was bedeuten diese Werte für einen Entwickler von bidirektionalem Inhalt?  In den meisten Fällen muss der Entwickler möglicherweise nur die <xref:System.Windows.FlowDirection> und die Sprache jedes [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Textelements definieren, zum Beispiel `Language="ar-SA"`, und die <xref:System.Windows.Media.NumberSubstitution>\-Logik zeigt dann die Zahlen entsprechend der korrekten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an.  Im folgenden Beispiel wird veranschaulicht, wie arabische und englische Zahlen in einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendung verwendet werden, die in einer arabischen Version von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ausgeführt wird.  
  
 [!code-xml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 Die folgende Grafik zeigt die Ausgabe des vorherigen Beispiels, wenn Sie eine Anwendung in einer arabischen Version von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ausführen.  
  
 ****Grafik mit den angezeigten arabischen und englischen Zahlen****  
  
 ![XamlPad&#45;Bildschirmabbildung mit Zahlen](../../../../docs/framework/wpf/advanced/media/numbers.png "Numbers")  
  
 Die <xref:System.Windows.FlowDirection> war in diesem Fall wichtig, denn wenn die <xref:System.Windows.FlowDirection> stattdessen auf <xref:System.Windows.FlowDirection> festgelegt worden wäre, hätte dies europäische Ziffern zur Folge gehabt.  In den folgenden Abschnitten wird erläutert, wie Sie eine einheitliche Anzeige von Ziffern im gesamten Dokument erzielen.  Wenn dieses Beispiel nicht unter der arabischen Version von Windows ausgeführt wird, werden alle Ziffern als europäische Ziffern angezeigt.  
  
 ****Definieren von Ersetzungsregeln****  
  
 In einer wirklichen Anwendung müssen Sie die Sprache unter Umständen programmgesteuert festlegen.  Angenommen, Sie möchten festlegen, dass das `xml:lang`\-Attribut mit dem identisch ist, das von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] des Systems verwendet wird, oder Sie möchten die Sprache abhängig vom Anwendungsstatus ändern.  
  
 Wenn Sie Änderungen auf der Grundlage des Anwendungsstatus vornehmen möchten, verwenden Sie andere von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellte Features.  
  
 Legen Sie zunächst die `NumberSubstitution.CultureSource="Text"` für die Anwendungskomponente fest.  Durch Verwenden dieser Einstellung wird sichergestellt, dass für Textelemente mit "User" als Standardeinstellung, zum Beispiel <xref:System.Windows.Controls.TextBlock>, nicht die Einstellungen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] verwendet werden.  
  
 Beispiele:  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 Legen Sie im entsprechenden [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)]\-Code die `Language`\-Eigenschaft z. B. auf `"ar-SA"` fest.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 Wenn Sie die `Language`\-Eigenschaft auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Sprache des aktuellen Benutzers festlegen müssen, verwenden Sie den folgenden Code.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> repräsentiert die vom aktuellen Thread zur Laufzeit verwendete aktuelle Kultur.  
  
 Das abschließende [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Beispiel sollte ähnlich wie das folgende Beispiel aussehen.  
  
 [!code-xml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Das abschließende [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]\-Beispiel sollte ähnlich wie das folgende Beispiel aussehen.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 Die folgende Grafik zeigt, wie das Fenster für die beiden Programmiersprachen jeweils aussieht.  
  
 ****Grafik, die arabische Zahlen anzeigt****  
  
 ![Arabische Zahlen](../../../../docs/framework/wpf/advanced/media/numbers2.png "Numbers2")  
  
 ****Verwenden der Substitution\-Eigenschaft****  
  
 Wie die Zahlenersetzung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funktioniert, hängt sowohl von der Sprache als auch von der <xref:System.Windows.FlowDirection> des Textelements ab.  Wenn die <xref:System.Windows.FlowDirection> von links nach rechts ist, werden europäische Ziffern gerendert.  Wenn dem Textelement jedoch arabischer Text vorangestellt ist, oder wenn die Sprache auf "ar" und die <xref:System.Windows.FlowDirection> auf <xref:System.Windows.FlowDirection> festgelegt ist, werden stattdessen arabische Ziffern gerendert.  
  
 Möglicherweise möchten Sie jedoch in manchen Fällen eine einheitliche Anwendung erstellen, zum Beispiel mit europäischen Ziffern für alle Benutzer,  oder mit arabischen Ziffern in <xref:System.Windows.Documents.Table>\-Zellen mit einem bestimmten <xref:System.Windows.Style>.  Mit der <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>\-Eigenschaft kann dies ganz einfach erreicht werden.  
  
 Im folgenden Beispiel ist für den ersten <xref:System.Windows.Controls.TextBlock> nicht die <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>\-Eigenschaft festgelegt, und der Algorithmus zeigt wie erwartet arabische Ziffern an.  Im zweiten <xref:System.Windows.Controls.TextBlock> ist die Ersetzung jedoch auf European festgelegt, was die Standardersetzung für arabische Zahlen überschreibt. Es werden europäische Ziffern angezeigt.  
  
 [!code-xml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]