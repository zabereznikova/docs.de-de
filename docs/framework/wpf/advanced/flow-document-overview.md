---
title: "&#220;bersicht &#252;ber Flussdokumente | Microsoft Docs"
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
  - "Inhaltsschema"
  - "Dokumente, Flussdokumente"
  - "Fortlaufende Inhaltselemente [WPF], Flussdokumente"
  - "Flussdokumente"
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# &#220;bersicht &#252;ber Flussdokumente
Flussdokumente sollen die Anzeige und die Lesbarkeit optimieren.  Flussdokumente sind nicht auf ein vordefiniertes Layout festgelegt, sondern passen Inhalte dynamisch an und bauen sie neu auf. Dies geschieht auf der Basis von Laufzeitvariablen, wie z. B. Fenstergröße, Geräteauflösung und optionalen Benutzereinstellungen.  Außerdem bieten Flussdokumente erweiterte Dokumentfeatures, z. B. Paginierung und Spalten.  Dieses Thema enthält eine Übersicht über Flussdokumente und deren Erstellung.  
  
   
  
<a name="what_is_a_flow_document"></a>   
## Was ist ein Flussdokument?  
 Ein Flussdokument soll Inhalte abhängig von der Fenstergröße, der Geräteauflösung und anderen Umgebungsvariablen "neu aufbauen".  Zusätzlich besitzen Flussdokumente eine Anzahl integrierter Features, darunter Suchfunktionen, Anzeigemodi, mit denen die Lesbarkeit verbessert wird, und die Fähigkeit, die Größe und die Darstellung von Schriftarten zu ändern.  Die besten Ergebnisse mit Flussdokumenten werden erzielt, wenn es darum geht, dass Benutzer das Dokument besser lesen können.  Bei einheitlich dargestellten Dokumenten geht es im Gegensatz dazu um die statische Darstellung.  Einheitlich dargestellte Dokumente sind nützlich, wenn eine originalgetreue Wiedergabe des Inhalts der Quelldatei gewünscht wird.  Weitere Informationen über unterschiedliche Dokumenttypen finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
 Die folgende Abbildung zeigt ein Beispielflussdokument, das in mehreren Fenstern mit verschiedenen Größen angezeigt wird.  Wenn sich der Anzeigebereich ändert, wird der Inhalt neu angeordnet, um den verfügbaren Platz optimal zu nutzen.  
  
 ![Flussdokument&#45;Inhalt, geänderte Flussrichtung](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs\_FlowDocument")  
  
 Wie im Bild oben gezeigt, kann der fortlaufende Inhalt viele verschiedene Komponenten enthalten, unter anderem Absätze, Listen und Bilder.  Diese Komponenten entsprechen Elementen in Markup und Objekten in Verfahrenscode.  Diese Klassen werden später im Abschnitt [Flussbezogene Klassen](#flow_related_classes) dieses Überblicks ausführlich beschrieben.  Hier folgt zunächst ein einfaches Codebeispiel, in dem ein Flussdokument erstellt wird, das aus einem Absatz mit teilweise fett formatiertem Text und einer Liste besteht.  
  
 [!code-xml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 Die folgende Abbildung zeigt, wie dieser Codeausschnitt aussieht.  
  
 ![Bildschirmabbildung: Gerendertes FlowDocument&#45;Beispiel](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow\_Ovw\_First\_Example")  
  
 In diesem Beispiel wird das <xref:System.Windows.Controls.FlowDocumentReader>\-Steuerelement verwendet, um den fortlaufenden Inhalt zu hosten.  Weitere Informationen über Steuerelemente zum Hosten von fortlaufendem Inhalt finden Sie in [Flussdokumenttypen](#flow_document_types).  Die Elemente <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem> und <xref:System.Windows.Documents.Bold> werden verwendet, um abhängig von ihrer Reihenfolge im Markup die Formatierung des Inhalts zu steuern.  So umspannt das <xref:System.Windows.Documents.Bold>\-Element nur einen Teil des Texts im Abschnitt, und folglich wird nur dieser Teil des Texts fett formatiert.  Wenn Sie HTML verwendet haben, ist Ihnen dies bekannt.  
  
 Wie in der Abbildung oben hervorgehoben, gibt es mehrere in Flussdokumenten integrierte Features:  
  
-   Suche: Ermöglicht es dem Benutzer, eine Volltextsuche in einem ganzen Dokument auszuführen.  
  
-   Anzeigemodus: Der Benutzer kann seinen bevorzugten Anzeigemodus auswählen. Dazu gehören ein einseitiger \(jeweils einzelne Seiten\) Anzeigemodus, ein Anzeigemodus mit zwei Seiten gleichzeitig \(Buchformat\) und ein Anzeigemodus mit fortlaufendem \(randlosem\) Bildlauf.  Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Steuerelemente für die Seitennavigation: Wenn der Anzeigemodus des Dokuments Seiten verwendet, gehören zu den Steuerelementen für die Seitennavigation eine Schaltfläche für das Wechseln zur nächsten Seite \(Pfeil nach unten\) oder zur vorherigen Seite \(Pfeil nach oben\) sowie Anzeigen für die aktuelle Seitenzahl und die Gesamtseitenzahl.  Auch mit den Tastaturpfeiltasten kann durch Seiten geblättert werden.  
  
-   Zoom: Die Zoomsteuerelemente ermöglichen Benutzern das Vergrößern oder Verkleinern der Zoomstufe durch Klicken auf die Schaltfläche mit dem Plus\- bzw. dem Minuszeichen.  Die Zoomsteuerelemente enthalten außerdem einen Schieberegler zum Anpassen der Zoomstufe.  Weitere Informationen finden Sie unter <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Diese Features können abhängig von dem Steuerelement geändert werden, das verwendet wird, um den fortlaufenden Inhalt zu hosten.  Im nächsten Abschnitt werden die verschiedenen Steuerelemente beschrieben.  
  
<a name="flow_document_types"></a>   
## Flussdokumenttypen  
 Die Darstellung und die Anzeige des Inhalts von Flussdokumenten hängen davon ab, welches Objekt verwendet wird, um den fortlaufenden Inhalt zu hosten.  Es gibt vier Steuerelemente, die das Anzeigen von Flussinhalt unterstützen: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  Diese Steuerelemente werden unten kurz beschrieben.  
  
 **Hinweis:**  <xref:System.Windows.Documents.FlowDocument> ist erforderlich, um fortlaufenden Inhalt direkt zu hosten. All diese Anzeigesteuerelemente verwenden somit <xref:System.Windows.Documents.FlowDocument>, um das Hosten von fortlaufendem Inhalt zu ermöglichen.  
  
### FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> enthält Features, mit denen Benutzer dynamisch zwischen verschiedenen Anzeigemodi auswählen können. Dazu gehören ein einseitiger \(jeweils einzelne Seiten\) Anzeigemodus, ein Anzeigemodus mit zwei Seiten gleichzeitig \(Buchformat\) und ein Anzeigemodus mit fortlaufendem \(randlosem\) Bildlauf.  Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Wenn keine dynamischen Wechsel zwischen den unterschiedlichen Anzeigemodi erforderlich sind, bieten <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> auch weniger umfangreiche Anzeigen für fortlaufenden Inhalt, die auf einen bestimmten Anzeigemodus festgelegt sind.  
  
### FlowDocumentPageViewer und FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> zeigt Inhalt im einseitigen Anzeigemodus an, während <xref:System.Windows.Controls.FlowDocumentScrollViewer> Inhalt im fortlaufenden Bildlaufmodus anzeigt.  Sowohl <xref:System.Windows.Controls.FlowDocumentPageViewer> als auch <xref:System.Windows.Controls.FlowDocumentScrollViewer> sind auf einen bestimmten Anzeigemodus festgelegt.  Im Gegensatz dazu bietet <xref:System.Windows.Controls.FlowDocumentReader> Features für die dynamische Auswahl verschiedener Anzeigemodi \(welche von der <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>\-Enumeration bereitgestellt werden\). Dies ist jedoch ressourcenintensiver als <xref:System.Windows.Controls.FlowDocumentPageViewer> oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Standardmäßig wird immer eine vertikale Bildlaufleiste und eine horizontale Bildlaufleiste nach Bedarf angezeigt.  Die Standardbenutzeroberfläche für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste; die <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A>\-Eigenschaft kann jedoch verwendet werden, um eine integrierte Symbolleiste zu aktivieren.  
  
### RichTextBox  
 Mit einer <xref:System.Windows.Controls.RichTextBox> können Sie es dem Benutzer ermöglichen, fortlaufenden Inhalt zu bearbeiten.  Wenn Sie beispielsweise einen Editor erstellen möchten, der einem Benutzer ermöglicht, Elemente wie Tabellen, kursive und fette Formatierung usw. zu ändern, verwenden Sie eine <xref:System.Windows.Controls.RichTextBox>.  Weitere Informationen finden Sie unter [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
 **Hinweis:** Fortlaufender Inhalt in einer <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie in anderen Steuerelementen enthaltener fortlaufender Inhalt.  Zum Beispiel gibt es in einer <xref:System.Windows.Controls.RichTextBox> keine Spalten und somit auch keine automatische Größenanpassung.  Auch die typischen integrierten Features von fortlaufendem Inhalt wie die Suchfunktion, der Anzeigemodus, die Seitennavigation und die Zoomfunktion stehen in einer <xref:System.Windows.Controls.RichTextBox> nicht zur Verfügung.  
  
<a name="creating_flow_content"></a>   
## Erstellen von fortlaufendem Inhalt  
 Fortlaufender Inhalt kann komplex sein und aus verschiedenen Elementen bestehen, darunter Text, Bilder, Tabellen und sogar Klassen, die von <xref:System.Windows.UIElement> abgeleitet sind, wie z. B. Steuerelemente.  Um zu verstehen, wie komplexer fortlaufender Inhalt erstellt wird, sind die folgenden Punkte wichtig:  
  
-   **Flussbezogene Klassen**: Jede im fortlaufenden Inhalt verwendete Klasse hat einen bestimmten Zweck.  Außerdem hilft die hierarchische Beziehung zwischen flussbezogenen Klassen Ihnen, zu verstehen, wie diese Klassen verwendet werden.  Beispielsweise werden Klassen, die von der <xref:System.Windows.Documents.Block>\-Klasse abgeleitet werden, zur Speicherung anderer Objekte verwendet, während von <xref:System.Windows.Documents.Inline> abgeleitete Klassen Objekte enthalten, die angezeigt werden.  
  
-   **Inhaltsschema**: Ein Flussdokument kann eine beträchtliche Anzahl von geschachtelten Elementen erfordern.  Das Inhaltsschema gibt mögliche Beziehungen zwischen übergeordneten und untergeordneten Elementen an.  
  
 In den folgenden Abschnitten wird jeder dieser Bereiche ausführlicher behandelt.  
  
<a name="flow_related_classes"></a>   
## Flussbezogene Klassen  
 Das Diagramm unten zeigt die für fortlaufenden Inhalt am häufigsten verwendeten Objekte:  
  
 ![Diagramm: Flussinhaltselement&#45;Klassenhierarchie](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow\_Class\_Hierarchy")  
  
 Für den fortlaufenden Inhalt gibt es zwei wichtige Kategorien:  
  
1.  **Von Block abgeleitete Klassen**: Auch "Blockinhaltselemente" oder einfach "Blockelemente" genannt.  Mit Elementen, die von <xref:System.Windows.Documents.Block> erben, können Elemente unter einem gemeinsamen übergeordneten Element gruppiert oder gemeinsame Attribute auf eine Gruppe angewendet werden.  
  
2.  **Von Inline abgeleitete Klassen**: Werden auch "Inlineinhaltselemente" oder einfach "Inlineelemente" genannt.  Elemente, die von <xref:System.Windows.Documents.Inline> erben, sind entweder in einem Blockelement oder einem anderen Inlineelement enthalten.  Inlineelemente werden oft als direkter Container für Inhalt verwendet, der auf den Bildschirm gerendert wird.  Beispielsweise kann ein <xref:System.Windows.Documents.Paragraph> \(Blockelement\) ein <xref:System.Windows.Documents.Run> \(Inlineelement\) enthalten, aber <xref:System.Windows.Documents.Run> enthält den Text, der auf dem Bildschirm gerendert wird.  
  
 Jede Klasse in diesen zwei Kategorien wird unten kurz beschrieben.  
  
### Von Block abgeleitete Klassen  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph> wird in der Regel verwendet, um Inhalt in einen Absatz zu gruppieren.  Die einfachste und häufigste Verwendung von Paragraph ist, einen Absatz mit Text zu erstellen.  
  
 [!code-xml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Aber Sie können auch andere von Inline abgeleitete Elemente verwenden. Dies wird unten erläutert.  
  
 **Abschnitt**  
  
 <xref:System.Windows.Documents.Section> wird nur verwendet, um andere von <xref:System.Windows.Documents.Block> abgeleitete Elemente zu speichern.  Section wendet keine Standardformatierung auf die Elemente an, die es enthält.  Alle für <xref:System.Windows.Documents.Section> festgelegten Eigenschaftswerte gelten jedoch für seine untergeordneten Elemente.  Ein Abschnitt ermöglicht Ihnen auch, seine untergeordnete Auflistung programmgesteuert zu durchlaufen.  <xref:System.Windows.Documents.Section> wird ähnlich verwendet wie das \<DIV\>\-Tag in HTML.  
  
 Im Beispiel unten werden drei Absätze unter einem <xref:System.Windows.Documents.Section> definiert.  Der Abschnitt hat den <xref:System.Windows.Documents.TextElement.Background%2A>\-Eigenschaftswert Red, dementsprechend ist die Hintergrundfarbe für die Absätze ebenfalls Rot.  
  
 [!code-xml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 Mit <xref:System.Windows.Documents.BlockUIContainer> können <xref:System.Windows.UIElement>\-Elemente \(z. B.  <xref:System.Windows.Controls.Button>\) in von Block abgeleiteten fortlaufenden Inhalt eingebettet werden.  <xref:System.Windows.Documents.InlineUIContainer> \(siehe unten\) wird verwendet, um <xref:System.Windows.UIElement>\-Elemente in von Inline abgeleiteten fortlaufenden Inhalt einzubetten.  <xref:System.Windows.Documents.BlockUIContainer> und <xref:System.Windows.Documents.InlineUIContainer> sind wichtig, da es keine andere Möglichkeit gibt, ein <xref:System.Windows.UIElement> in fortlaufendem Inhalt zu verwenden, wenn es nicht in einem dieser zwei Elemente enthalten ist.  
  
 Das folgende Beispiel zeigt, wie das <xref:System.Windows.Documents.BlockUIContainer>\-Element verwendet wird, um <xref:System.Windows.UIElement>\-Objekte im fortlaufenden Inhalt zu hosten.  
  
 [!code-xml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: UIElement eingebettet in fortlaufenden Inhalt](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List> wird verwendet, um eine Aufzählung mit Aufzählungszeichen oder Zahlen zu erstellen.  Legen Sie für die <xref:System.Windows.Documents.List.MarkerStyle%2A>\-Eigenschaft einen <xref:System.Windows.TextMarkerStyle>\-Enumerationswert fest, um den Stil der Liste festzulegen.  Im Beispiel unten wird das Erstellen einer einfachen Liste veranschaulicht.  
  
 [!code-xml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Hinweis:** <xref:System.Windows.Documents.List> ist das einzige Fließelement, das die <xref:System.Windows.Documents.ListItemCollection> verwendet, um untergeordnete Elemente zu verwalten.  
  
 **Tabelle**  
  
 <xref:System.Windows.Documents.Table> wird zum Erstellen einer Tabelle verwendet.  <xref:System.Windows.Documents.Table> ähnelt dem <xref:System.Windows.Controls.Grid>\-Element, besitzt aber mehr Fähigkeiten und erfordert deshalb mehr Ressourcen.  Da <xref:System.Windows.Controls.Grid> ein <xref:System.Windows.UIElement> ist, kann es nicht in fortlaufendem Inhalt verwendet werden, es sei denn, es ist in einem <xref:System.Windows.Documents.BlockUIContainer> oder <xref:System.Windows.Documents.InlineUIContainer> enthalten.  Weitere Informationen zu <xref:System.Windows.Documents.Table> finden Sie unter [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
### Von Inline abgeleitete Klassen  
 **Run**  
  
 <xref:System.Windows.Documents.Run> wird zur Speicherung von unformatiertem Text verwendet.  Man würde erwarten, dass <xref:System.Windows.Documents.Run>\-Objekte in fließendem Inhalt häufig verwendet werden.  <xref:System.Windows.Documents.Run>\-Elemente müssen im Markup jedoch nicht explizit verwendet werden.  <xref:System.Windows.Documents.Run> muss verwendet werden, wenn Flussdokumente mithilfe von Code erstellt oder bearbeitet werden.  So gibt im Markup unten der erste <xref:System.Windows.Documents.Paragraph> das <xref:System.Windows.Documents.Run>\-Element explizit an, der zweite hingegen nicht.  Für beide Absätze ist die Ausgabe gleich.  
  
 [!code-xml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Hinweis:** Ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] ist die <xref:System.Windows.Documents.Run.Text%2A>\-Abhängigkeit des <xref:System.Windows.Documents.Run>\-Objekts eine Abhängigkeitseigenschaft.  Sie können die <xref:System.Windows.Documents.Run.Text%2A>\-Eigenschaft an eine Datenquelle binden, z. B. einen <xref:System.Windows.Controls.TextBlock>.  Die <xref:System.Windows.Documents.Run.Text%2A>\-Eigenschaft unterstützt die unidirektionale Bindung vollständig.  Die <xref:System.Windows.Documents.Run.Text%2A>\-Eigenschaft unterstützt auch die bidirektionale Bindung, außer für <xref:System.Windows.Controls.RichTextBox>.  Ein Beispiel finden Sie unter <xref:System.Windows.Documents.Run.Text%2A?displayProperty=fullName>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> fasst andere Inlineinhaltselemente in einer Gruppe zusammen.  Inhalt in einem <xref:System.Windows.Documents.Span>\-Element wird nicht inhärent gerendert.  Elemente, die von <xref:System.Windows.Documents.Span> erben, darunter <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> und <xref:System.Windows.Documents.Underline>, formatieren jedoch den Text.  
  
 Unten finden Sie ein Beispiel, in dem <xref:System.Windows.Documents.Span> verwendet wird, um Inlineinhalt einschließlich Text, <xref:System.Windows.Documents.Bold>\-Element und <xref:System.Windows.Controls.Button> zu speichern.  
  
 [!code-xml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 Die folgende Bildschirmabbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Gerendertes SPAN&#45;Beispiel](../../../../docs/framework/wpf/advanced/media/flow-spanexample.png "Flow\_SpanExample")  
  
 **InlineUIContainer**  
  
 Mit <xref:System.Windows.Documents.InlineUIContainer> können <xref:System.Windows.UIElement>\-Elemente \(beispielsweise  ein Steuerelement wie <xref:System.Windows.Controls.Button>\) in ein <xref:System.Windows.Documents.Inline>\-Inhaltselement eingebettet werden.  Dieses Element ist die Inlineentsprechung zu dem oben beschriebenen <xref:System.Windows.Documents.BlockUIContainer>.  Unten finden Sie ein Beispiel, in dem <xref:System.Windows.Documents.InlineUIContainer> verwendet wird, um ein <xref:System.Windows.Controls.Button>\-Element inline in einen <xref:System.Windows.Documents.Paragraph> einzufügen.  
  
 [!code-xml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Hinweis:** <xref:System.Windows.Documents.InlineUIContainer> muss nicht explizit in Markup verwendet werden.  Wenn Sie ihn weglassen, wird in jedem Fall ein <xref:System.Windows.Documents.InlineUIContainer> erstellt, wenn der Code kompiliert wird.  
  
 **Figure und Floater**  
  
 <xref:System.Windows.Documents.Figure> und <xref:System.Windows.Documents.Floater> werden verwendet, um Inhalt in Flussdokumenten mit Placement\-Eigenschaften einzubetten, die unabhängig vom fortlaufenden Hauptinhalt angepasst werden können.  Mit <xref:System.Windows.Documents.Figure>\-Elementen oder <xref:System.Windows.Documents.Floater>\-Elementen werden häufig Teile des Inhalts markiert oder hervorgehoben, unterstützende Bilder oder anderer Inhalt im fortlaufenden Hauptinhalt gehostet oder lose verbundener Inhalt eingefügt, z. B. Werbeanzeigen.  
  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Documents.Figure> in einen Textabsatz eingebettet wird.  
  
 [!code-xml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird:  
  
 ![Bildschirmabbildung: Abbildungsbeispiel](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow\_Ovw\_Figure\_Example")  
  
 <xref:System.Windows.Documents.Figure> und <xref:System.Windows.Documents.Floater> unterscheiden sich in vielerlei Hinsicht und werden für verschiedene Szenarios verwendet.  
  
 ****Abbildung:****  
  
-   Kann positioniert werden: Sie können die horizontalen und vertikalen Anker festlegen und die Abbildung relativ zur Seite, zum Inhalt, zur Spalte oder zum Absatz andocken.  Mit der <xref:System.Windows.Documents.Figure.HorizontalOffset%2A>\-Eigenschaft und der <xref:System.Windows.Documents.Figure.VerticalOffset%2A>\-Eigenschaft können Sie auch beliebige Offsets angeben.  
  
-   Die Größe kann an mehrere Spalten angepasst werden: Sie können die Höhe und Breite der <xref:System.Windows.Documents.Figure> für Vielfache von Seiten, des Inhalts oder der Spaltenhöhe oder \-breite festlegen.  Bei Seiten und Inhalt sind Vielfache größer als 1 nicht zulässig.  Beispielsweise können Sie die Breite einer <xref:System.Windows.Documents.Figure> auf eine halbe Seite, ein Viertel des Inhalts oder zwei Spalten festlegen \("0.5 page", "0.25 content", "2 Column"\).  Sie können die Höhe und Breite auch auf absolute Pixelwerte festlegen.  
  
-   Keine Paginierung: Wenn der Inhalt einer <xref:System.Windows.Documents.Figure> größer als die <xref:System.Windows.Documents.Figure> ist, wird so viel Inhalt gerendert, wie eingefügt werden kann; der übrige Inhalt wird nicht angezeigt.  
  
 ****Floater:****  
  
-   Kann nicht positioniert werden und wird gerendert, wo entsprechend Platz verfügbar gemacht werden kann.  Für einen <xref:System.Windows.Documents.Floater> können Sie den Offset nicht festlegen und keine Verankerung angeben.  
  
-   Die Größe kann nicht für mehrere Spalten angepasst werden: In der Standardeinstellung wird die Größe des <xref:System.Windows.Documents.Floater> an eine Spalte angepasst.  Der Floater verfügt über eine <xref:System.Windows.Documents.Floater.Width%2A>\-Eigenschaft, die auf einen absoluten Pixelwert festgelegt werden kann. Wenn der Wert jedoch größer als die Breite einer Spalte ist, wird der Wert ignoriert und der Floater auf die Spaltenbreite festgelegt.  Die Größe kann durch Festlegen der korrekten Pixelbreite so angepasst werden, dass sie kleiner als eine Spalte ist. Das Anpassen der Größe kann jedoch nicht relativ zur Spaltenbreite erfolgen, sodass "0.5Column" kein gültiger Ausdruck für die <xref:System.Windows.Documents.Floater>\-Breite ist.  Eine Eigenschaft für die Höhe ist für den <xref:System.Windows.Documents.Floater> nicht vorhanden, und seine Höhe kann nicht festgelegt werden. Diese hängt vielmehr vom Inhalt ab.  
  
-   <xref:System.Windows.Documents.Floater> werden paginiert: Wenn der Inhalt an der angegebenen Breite größer als 1 Spaltenhöhe ist, wird der Floater umbrochen und auf der nächsten Spalte, Seite usw. paginiert.  
  
 Ein <xref:System.Windows.Documents.Figure>\-Element eignet sich gut zum Einfügen eigenständigen Inhalts, dessen Größe und Positionierung Sie steuern möchten und bei dem Sie sicher sind, dass er in das Element mit der vorgegebenen Größe passt  Ein <xref:System.Windows.Documents.Floater> eignet sich gut zum Einfügen freien fortlaufenden Inhalts, der ähnlich wie der Inhalt der Hauptseite, aber getrennt von diesem verläuft.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> bewirkt, dass ein Zeilenumbruch in fortlaufendem Inhalt auftritt.  Das folgende Beispiel veranschaulicht die Verwendung von <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 Die folgende Bildschirmabbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: LineBreak&#45;Beispiel](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow\_Ovw\_LineBreakExample")  
  
### Auflistung von fortlaufenden Inhaltselementen  
 In vielen der Beispiele oben werden <xref:System.Windows.Documents.BlockCollection> und <xref:System.Windows.Documents.InlineCollection> verwendet, um fortlaufenden Inhalt programmgesteuert zu erstellen.  Um beispielsweise Elemente zu einem <xref:System.Windows.Documents.Paragraph> hinzuzufügen, können Sie diese Syntax verwenden:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 So wird <xref:System.Windows.Documents.Run> zur <xref:System.Windows.Documents.InlineCollection> des <xref:System.Windows.Documents.Paragraph> hinzugefügt.  Dies entspricht dem impliziten <xref:System.Windows.Documents.Run> in einem <xref:System.Windows.Documents.Paragraph> in Markup:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Als Beispiel für die Verwendung der <xref:System.Windows.Documents.BlockCollection> wird im folgenden Beispiel ein neuer <xref:System.Windows.Documents.Section> erstellt und anschließend die **Add**\-Methode verwendet, um einen neuen <xref:System.Windows.Documents.Paragraph> zu den <xref:System.Windows.Documents.Section>\-Inhalten hinzuzufügen.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Sie können nicht nur Elemente zu einer Auflistung von fortlaufenden Inhaltselementen hinzufügen, sondern auch Elemente entfernen.  Im folgenden Beispiel wird das letzte <xref:System.Windows.Documents.Inline>\-Element in <xref:System.Windows.Documents.Span> gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Im folgenden Beispiel wird der gesamte Inhalt \(<xref:System.Windows.Documents.Inline>\-Elemente\) aus <xref:System.Windows.Documents.Span> gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Wenn Sie programmgesteuert mit fortlaufendem Inhalt arbeiten, werden Sie diese Auflistungen wahrscheinlich häufig verwenden.  
  
 Ob ein Fließelement eine <xref:System.Windows.Documents.InlineCollection> \(Inlines\) oder eine <xref:System.Windows.Documents.BlockCollection> \(Blöcke\) zur Speicherung der untergeordneten Elemente verwendet, hängt davon ab, welche Typen von untergeordneten Elementen \(<xref:System.Windows.Documents.Block> oder <xref:System.Windows.Documents.Inline>\) in dem übergeordneten Element enthalten sein können.  Kapselungsregeln für fortlaufende Inhaltselemente werden im Inhaltsschema im nächsten Abschnitt zusammengefasst.  
  
 **Hinweis:** Es gibt einen dritten Auflistungstyp, der mit Fließinhalt verwendet wird, nämlich die <xref:System.Windows.Documents.ListItemCollection>. Diese Auflistung wird aber nur mit einer <xref:System.Windows.Documents.List> verwendet.  Außerdem gibt es mehrere mit <xref:System.Windows.Documents.Table> verwendete Auflistungen.  Weitere Informationen finden Sie unter [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
<a name="content_schema"></a>   
## Inhaltsschema  
 Angesichts der Anzahl von verschiedenen fortlaufenden Inhaltselementen kann es schwierig sein, nachzuverfolgen, welche Arten von untergeordneten Elementen in einem Element gespeichert werden können.   Das Diagramm unten fasst die Kapselungsregeln für Fließelemente zusammen.  Die Pfeile stellen die möglichen Beziehungen zwischen übergeordneten und untergeordneten Elementen dar.  
  
 ![Diagramm: Flussinhalt&#45;Kapselungsschema](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow\_Content\_Schema")  
  
 Wie aus dem Diagramm oben ersichtlich, hängen die für ein Element zulässigen untergeordneten Elemente nicht unbedingt davon ab, ob es sich um ein <xref:System.Windows.Documents.Block>\-Element oder ein <xref:System.Windows.Documents.Inline>\-Element handelt.  Beispielsweise kann <xref:System.Windows.Documents.Span> \(ein <xref:System.Windows.Documents.Inline>\-Element\) nur <xref:System.Windows.Documents.Inline>\-Elemente als untergeordnete Elemente haben, während <xref:System.Windows.Documents.Figure> \(ebenfalls ein <xref:System.Windows.Documents.Inline>\-Element\) nur <xref:System.Windows.Documents.Block>\-Elemente als untergeordnete Elemente haben kann.  Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen enthalten sein kann.  Als Beispiel kann das Diagramm verwendet werden, um festzustellen, wie der Fließinhalt einer <xref:System.Windows.Controls.RichTextBox> konstruiert werden kann.  
  
 **1.** Eine <xref:System.Windows.Controls.RichTextBox> muss ein <xref:System.Windows.Documents.FlowDocument> enthalten, das wiederum ein von einem <xref:System.Windows.Documents.Block> abgeleitetes Objekt enthalten muss.  Unten finden Sie das entsprechende Segment aus dem Diagramm oben.  
  
 ![Diagramm: RichTextBox&#45;Kapselungsregeln](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow\_Ovw\_SchemaWalkThrough1")  
  
 So könnte das Markup zu diesem Zeitpunkt aussehen.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** Gemäß dem Diagramm können Sie zwischen mehreren <xref:System.Windows.Documents.Block>\-Elementen wählen, darunter <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List> und <xref:System.Windows.Documents.BlockUIContainer> \(siehe Von Block abgeleitete Klassen weiter oben\).  Angenommen, das gewünschte Element ist eine <xref:System.Windows.Documents.Table>.  Gemäß dem Diagramm oben enthält eine <xref:System.Windows.Documents.Table> eine <xref:System.Windows.Documents.TableRowGroup>, in der <xref:System.Windows.Documents.TableRow>\-Elemente enthalten sind, die <xref:System.Windows.Documents.TableCell>\-Elemente enthalten, welche ein von einem <xref:System.Windows.Documents.Block> abgeleitetes Objekt enthalten.  Unten befindet sich das entsprechende Segment für <xref:System.Windows.Documents.Table>, das aus dem Diagramm oben entnommen wurde.  
  
 ![Diagramm: Übergeordnetes&#47;Untergeordnetes Schema für Tabelle](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow\_Ovw\_SchemaWalkThrough2")  
  
 Unten finden Sie das entsprechende Markup.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Wiederum sind ein oder mehrere <xref:System.Windows.Documents.Block>\-Elemente unter einer <xref:System.Windows.Documents.TableCell> erforderlich.  Um bei einem einfachen Beispiel zu bleiben, platzieren Sie einen kurzen Text in der Zelle.  Dazu können Sie einen <xref:System.Windows.Documents.Paragraph> mit einem <xref:System.Windows.Documents.Run>\-Element verwenden.  Unten finden Sie die entsprechenden Segmente aus dem Diagramm, die zeigen, dass ein <xref:System.Windows.Documents.Paragraph> ein <xref:System.Windows.Documents.Inline>\-Element und <xref:System.Windows.Documents.Run> \(ein <xref:System.Windows.Documents.Inline>\-Element\) lediglich Nur\-Text enthalten kann.  
  
 ![Diagramm: Übergeordnetes&#47;Untergeordnetes Schema für Absatz](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow\_Ovw\_SchemaWalkThrough3")  
  
 ![Diagramm: Übergeordnetes&#47;Untergeordnetes Schema für Ausführung](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow\_Ovw\_SchemaWalkThrough4")  
  
 Unten sehen Sie das ganze Beispiel in Markup.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## Anpassen von Text  
 Normalerweise ist Text der vorherrschende Inhaltstyp in einem Fließdokument.  Obwohl die oben eingeführten Objekte verwendet werden können, um die meisten Möglichkeiten für das Rendern von Text zu steuern, gibt es einige andere Methoden zum Anpassen von Text, die in diesem Abschnitt erläutert werden.  
  
### Textdekorationen  
 Mit Textdekorationen können Sie die Effekte Unterstreichen, Überstreichen, Baseline und Durchstreichen auf Text anwenden \(siehe Abbildungen unten\).  Diese Dekorationen werden mithilfe der <xref:System.Windows.Documents.Inline.TextDecorations%2A>\-Eigenschaft hinzugefügt, die von mehreren Objekten verfügbar gemacht wird, darunter <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.TextBox>.  
  
 Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Documents.Paragraph.TextDecorations%2A>\-Eigenschaft von einem <xref:System.Windows.Documents.Paragraph> veranschaulicht.  
  
 [!code-xml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Text mit standardmäßigem Durchstreicheffekt](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline\_TextDec\_Strike")  
  
 In den folgenden Abbildungen wird veranschaulicht, wie die Dekorationen **Überstreichen**, **Baseline** und **Unterstreichen** gerendert werden.  
  
 ![Bildschirmabbildung: Überstrich&#45;TextDecorator](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline\_TextDec\_Over")  
  
 ![Bildschirmabbildung: Standardmäßiger Baseline&#45;Effekt auf Text](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline\_TextDec\_Base")  
  
 ![Bildschirmabbildung: Text mit standardmäßigem Unterstreichungseffekt](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline\_TextDec\_Under")  
  
### Typografie  
 Die <xref:System.Windows.Documents.TextElement.Typography%2A>\-Eigenschaft wird von den meisten flussbezogenen Inhalten verfügbar gemacht, darunter <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.TextBox>.  Diese Eigenschaft wird verwendet, um typografische Eigenschaften\/Variationen von Text \(z. B.  Kapitälchen oder Großbuchstaben, hochgestellten und tiefgestellten Text usw.\) zu steuern.  
  
 Im folgenden Beispiel wird anhand des Beispiels <xref:System.Windows.Documents.Paragraph> veranschaulicht, wie das <xref:System.Windows.Documents.TextElement.Typography%2A>\-Attribut festgelegt wird.  
  
 [!code-xml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement\_Typog")  
  
 Im Gegensatz dazu wird in der folgenden Abbildung gezeigt, wie ein ähnliches Beispiel mit den Standardtypografieeigenschaften gerendert wird.  
  
 ![Bildschirmabbildung: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement\_Typog\_Default")  
  
 Im folgenden Beispiel wird veranschaulicht, wie die <xref:System.Windows.Controls.TextBox.Typography%2A>\-Eigenschaft programmgesteuert festgelegt wird.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Weitere Informationen über Typografie finden Sie unter [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
## Siehe auch  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)   
 [Übersicht über das TextElement\-Inhaltsmodell](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)   
 [Übersicht über Anmerkungen](../../../../docs/framework/wpf/advanced/annotations-overview.md)