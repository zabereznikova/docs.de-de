---
title: "Übersicht über Flussdokumente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f7eda2b6761a825dcb2b24ae9f11b2e1262d7e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="flow-document-overview"></a>Übersicht über Flussdokumente
Flussdokumente dienen der Optimierung der Anzeige und Lesbarkeit. Statt auf ein vordefiniertes Layout festgelegt zu werden, passen Flussdokumente ihren Inhalt basierend auf Laufzeitvariablen dynamisch an Variablen wie Fenstergröße, Geräteauflösung und optionale Benutzereinstellungen an und brechen den Inhalt dynamisch um. Zudem bieten Flussdokumente erweiterte Dokumentfunktionen, z.B. Paginierung und Spalten. Dieses Thema enthält eine Übersicht über Flussdokumente und deren Erstellung.  
  

  
<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>Was ist ein Flussdokument?  
 Ein Flussdokument wurde konzipiert, um abhängig von der Fenstergröße, der Geräteauflösung und anderen Umgebungsvariablen den „Inhalt dynamisch umzubrechen“. Zudem verfügen Flussdokumente über eine Vielzahl integrierter Funktionen, inklusive der Suche, Anzeigemodi zur Optimierung der Lesbarkeit und der Möglichkeit zum Ändern der Größe und Darstellung von Schriftarten. Flussdokumente werden am besten verwendet, wenn das erleichterte Lesen das Hauptgebrauchsszenario des Dokuments darstellt. Im Gegensatz dazu sind fixierte Dokumente für eine statische Darstellung entworfen. Fixierte Dokumente sind hilfreich, wenn die Originaltreue des Quellinhalts wichtig ist. Finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md) für Weitere Informationen zu anderen Typen von Dokumenten.  
  
 Die folgende Abbildung zeigt ein Beispielflussdokument in mehreren Fenstern von verschiedener Größe. Wenn sich der Bildschirmbereich ändert, bricht der Inhalt dynamisch um, um den verfügbaren Platz bestmöglich auszunutzen.  
  
 ![Flussdokumentinhalt dynamisch umgebrochen](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 Wie in dem Bild oben dargestellt, kann fortlaufender Inhalt viele Komponenten umfassen, einschließlich Absätzen, Listen, Bilder usw. Diese Komponenten entsprechen Elementen im Markup und Objekten in prozeduralem Code. Wir werden uns diese Klassen werden ausführlich weiter unten in der [verwandten Klassen Flow](#flow_related_classes) Abschnitt dieser Übersicht. Jetzt müssen Sie hier ein einfaches Codebeispiel, das ein Flussdokument bestehend aus einem Absatz mit fett formatierten Text und eine Liste erstellt wird.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieser Codeausschnitt aussieht.  
  
 ![Screenshot: Gerendertes FlowDocument-Beispiel](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 In diesem Beispiel wird die <xref:System.Windows.Controls.FlowDocumentReader> Steuerelement wird zum Hosten des fortlaufenden Inhalts verwendet. Finden Sie unter [Flussdokumenttypen](#flow_document_types) für Weitere Informationen zum Hosten von Steuerelementen Flussinhalt. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, und <xref:System.Windows.Documents.Bold> Elemente werden basierend auf ihrer Reihenfolge im Markup zum Steuern der Formatierung des Inhalts verwendet. Z. B. die <xref:System.Windows.Documents.Bold> Element erstreckt sich auf nur einen Teil des Texts im Absatz; folglich nur dieser Teil des Texts fett formatiert ist. Wenn Sie HTML verwendet haben, wird Ihnen dies vertraut sein.  
  
 Wie in der obigen Abbildung verdeutlicht es gibt verschiedene Funktionen, die Dokumente Flow integriert:
  
-   Suche: Ermöglicht dem Benutzer, eine Volltextsuche auf ein ganzes Dokument auszuführen.  
  
-   Anzeigemodus: Der Benutzer kann seinen bevorzugten Anzeigemodus auswählen, darunter der Anzeigemodus „Einzelne Seite“ (Seite-für-Seite), der Anzeigemodus „Zwei Seiten“ (Buchleseformat) und der fortlaufende Anzeigemodus „Fensterinhalt verschieben“ (unbeschränkt).  Weitere Informationen zu diesen Anzeigemodi, finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Steuerelemente für die Seitennavigation: Wenn der Anzeigemodus des Dokuments Seiten verwendet, umfassen die Steuerelemente für die Seitennavigation eine Schaltfläche zum Springen auf die nächste Seite (Pfeil nach unten) oder die vorherige Seite (Pfeil nach oben) sowie Indikatoren für die aktuelle Seitennummer und die Gesamtzahl der Seiten. Das Blättern durch Seiten funktioniert auch mithilfe der Pfeiltasten auf der Tastatur.  
  
-   Zoom: Die Zoomsteuerelemente ermöglichen es dem Benutzer, die Zoomstufe zu erhöhen oder zu verringern, indem er entsprechend auf die Plus- oder Minusschaltfächen klickt. Die Zoomsteuerelemente umfassen zudem einen Schieberegler zum Anpassen der Zoomstufe. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Diese Funktionen können basierend auf dem zum Hosten des fortlaufenden Inhalts verwendeten Steuerelement bearbeitet werden. Im nächsten Abschnitt werden die verschiedenen Steuerelemente beschrieben.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>Flussdokumenttypen  
 Die Anzeige und Darstellung von Flussdokumentinhalt hängt davon ab, welches Objekt zum Hosten des fortlaufenden Inhalts verwendet wird. Es gibt vier Steuerelemente, Anzeigen von Flussinhalt unterstützen: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, und <xref:System.Windows.Controls.FlowDocumentScrollViewer>. Diese Steuerelemente werden nachstehend kurz beschrieben.  
  
 **Hinweis:** <xref:System.Windows.Documents.FlowDocument> ist erforderlich, um direkt Host Flussinhalt, damit alle der folgenden Steuerelemente anzeigen nutzen einen <xref:System.Windows.Documents.FlowDocument> So aktivieren Sie den Datenfluss Inhalt hosten.  
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>enthält Funktionen, mit die den Benutzer dynamisch auswählen verschiedener Anzeigemodi, einschließlich eines Einzelseiten (Seite-an-a-Time)-Anzeigemodus, eine zwei-Seite-an-a-Time (Buchformat lesen) anzeigen, Modus und einem fortlaufenden Bildlaufmodus (Unbeschränkte) anzeigen können. Weitere Informationen zu diesen Anzeigemodi, finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>. Wenn Sie nicht benötigen, können dynamisch Wechseln zwischen unterschiedlichen Anzeigemodi <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> bieten helleren fortlaufenden Inhalt-Viewer, die in einem bestimmten Anzeigemodus behoben werden.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer und FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>Zeigt den Inhalt im Seite-an-Time Anzeigemodus, while <xref:System.Windows.Controls.FlowDocumentScrollViewer> zeigt den Inhalt im fortlaufenden Modus aus durchführen eines Bildlaufs. Beide <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> werden so repariert, einen bestimmten Anzeigemodus. Im Vergleich mit <xref:System.Windows.Controls.FlowDocumentReader>, inklusive der Funktionen, die dem Benutzer ermöglichen, die dynamisch zwischen verschiedenen Anzeigemodi auswählen (gemäß der <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> Enumeration), aber weitere ressourcenintensiv als <xref:System.Windows.Controls.FlowDocumentPageViewer> oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Eine vertikale Scrollleiste wird standardmäßig immer angezeigt, eine horizontale Scrollleiste nur nach Bedarf. Die Standardeinstellung Benutzeroberfläche für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste, aber die <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> Eigenschaft kann verwendet werden, um eine integrierte Symbolleiste aktivieren.  
  
### <a name="richtextbox"></a>RichTextBox  
 Sie verwenden eine <xref:System.Windows.Controls.RichTextBox> sollen die Benutzer fortlaufendem Inhalt bearbeiten können. Z. B. Wenn Sie beim Erstellen eines Editors, die einen Benutzer bearbeiten dürfen Gegenstände wie Tabellen, kursive und fett formatieren, usw., verwenden Sie eine <xref:System.Windows.Controls.RichTextBox>. Finden Sie unter [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) für Weitere Informationen.  
  
 **Hinweis:** fortlaufende Inhalte innerhalb einer <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie bei anderen Steuerelementen enthaltener Flow-Inhalt. Beispielsweise, sind keine Spalten in einem <xref:System.Windows.Controls.RichTextBox> und daher keine automatische Größenanpassungsverhalten. In der Regel Intergrierte Funktionen fließenden Inhalts wie suchen, Anzeigen von Modus, Seitennavigation und Zoom sind außerdem nicht verfügbar innerhalb einer <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>Erstellen von fortlaufendem Inhalt  
 Fortlaufendem Inhalt kann komplex sein, bestehend aus verschiedenen Elementen, z. B. Text, Bilder, Tabellen, und sogar <xref:System.Windows.UIElement> abgeleiteten Klassen wie Steuerelemente. Um zu verstehen, wie komplexer fortlaufender Inhalt erstellt wird, sind die folgenden Punkte wichtig:  
  
-   **Flussbezogene Klassen**: Jede in fortlaufendem Inhalt verwendete Klasse hat einen bestimmten Zweck. Darüber hinaus hilft Ihnen die hierarchische Beziehung zwischen Flussklassen dabei, zu verstehen, wie sie verwendet werden. Beispielsweise abgeleitete Klassen aus der <xref:System.Windows.Documents.Block> Klasse werden verwendet, um andere Objekte enthalten, während die abgeleitete Klassen <xref:System.Windows.Documents.Inline> Objekte enthalten, die angezeigt werden.  
  
-   **Inhaltsschema**: Ein Flussdokument kann eine beträchtliche Anzahl von geschachtelten Elementen erfordern. Das Inhaltsschema gibt mögliche Übergeordnet/Untergeordnet-Beziehungen zwischen Elementen an.  
  
 In den folgenden Abschnitten wird jeder dieser Bereiche ausführlicher erklärt.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>Flussbezogene Klassen  
 Das folgende Diagramm zeigt die am häufigsten bei fortlaufendem Inhalt verwendeten Objekte:  
  
 ![Diagramm: Flussinhaltselement-Klassenhierarchie](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 Für die Zwecke des fortlaufenden Inhalts gibt es zwei wichtige Kategorien:  
  
1.  **Blockabgeleitete Klassen**: Auch „Blockinhaltselemente“ oder einfach „Blockelemente“ genannt. Elemente, die von erben <xref:System.Windows.Documents.Block> verwendet werden können, Elemente unter einem gemeinsamen übergeordneten Element gruppiert oder gemeinsame Attribute zu einer Gruppe angewendet.  
  
2.  **Inlineabgeleitete Klassen**: Auch „Inlineinhaltselemente“ oder einfach „Inlineelemente“ genannt. Elemente, die von erben <xref:System.Windows.Documents.Inline> entweder in einem Blockelement oder einem anderen Inline-Element enthalten sind. Inlineelemente werden oft als direkter Container für Inhalt verwendet, der auf dem Bildschirm gerendert wird. Z. B. eine <xref:System.Windows.Documents.Paragraph> (Block-Element) darf eine <xref:System.Windows.Documents.Run> (Inline-Element), aber die <xref:System.Windows.Documents.Run> enthält den Text, der auf dem Bildschirm gerendert wird.  
  
 Jede Klasse in diesen zwei Kategorien wird nachstehend kurz beschrieben.  
  
### <a name="block-derived-classes"></a>Blockabgeleitete Klassen  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph>wird normalerweise zum Gruppieren von Inhalten in einem Absatz verwendet. Die einfachste und häufigste Verwendung von Paragraph ist, einen Textabsatz zu erstellen.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Sie können jedoch auch andere Inline abgeleitete Elemente enthalten, wie unten angezeigt wird. 
  
 **Bereich**  
  
 <xref:System.Windows.Documents.Section>wird verwendet, nur um andere enthält <xref:System.Windows.Documents.Block>-Elemente abgeleitet. Sie wendet keine Standardformatierungen auf die Elemente an, die sie einschließt. Allerdings Standardwerte für die Eigenschaft Gruppe auf eine <xref:System.Windows.Documents.Section> gilt für die untergeordneten Elemente. Eine Section-Klasse ermöglicht es Ihnen auch, ihre untergeordnete Auflistung programmgesteuert zu durchlaufen. <xref:System.Windows.Documents.Section>wird verwendet, in ähnlicher Weise wie für die \<DIV >-Tag im HTML.  
  
 Im folgenden Beispiel werden drei Absätze unter einem definiert <xref:System.Windows.Documents.Section>. Der Abschnitt bietet eine <xref:System.Windows.Documents.TextElement.Background%2A> Eigenschaftswert von Rot, daher ist die Hintergrundfarbe der Absätze ist auch Rot.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer>ermöglicht <xref:System.Windows.UIElement> Elemente (d. h. eine <xref:System.Windows.Controls.Button>), im Block abgeleiteten fortlaufenden Inhalt eingebettet werden soll. <xref:System.Windows.Documents.InlineUIContainer>(siehe unten) wird verwendet, um einzubetten <xref:System.Windows.UIElement> Elemente in der abgeleiteten Inline fortlaufenden Inhalt. <xref:System.Windows.Documents.BlockUIContainer>und <xref:System.Windows.Documents.InlineUIContainer> sind wichtig, da es keine andere Möglichkeit zum verwenden ist einer <xref:System.Windows.UIElement> in fortlaufendem Inhalt, es sei denn, sie in einem der beiden Elemente enthalten ist.  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Documents.BlockUIContainer> Element Host <xref:System.Windows.UIElement> Objekte innerhalb des fortlaufenden Inhalts.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: UIElement eingebettet in fortlaufenden Inhalt](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List>wird verwendet, um eine Liste mit Aufzählungszeichen oder numerischen erstellen. Festlegen der <xref:System.Windows.Documents.List.MarkerStyle%2A> Eigenschaft, um eine <xref:System.Windows.TextMarkerStyle> Enumerationswert, um den Stil der Liste festzulegen. Das folgende Beispiel zeigt, wie Sie eine einfache Liste erstellen.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Hinweis:** <xref:System.Windows.Documents.List> ist das einzige Flow-Element, das verwendet die <xref:System.Windows.Documents.ListItemCollection> zum Verwalten von untergeordneten Elementen.  
  
 **Table**  
  
 <xref:System.Windows.Documents.Table>Dient zum Erstellen einer Tabelle. <xref:System.Windows.Documents.Table>ähnelt der <xref:System.Windows.Controls.Grid> sondern Element verfügt über weitere Funktionen und benötigt deshalb das Ressourcenaufwand größer. Da <xref:System.Windows.Controls.Grid> ist ein <xref:System.Windows.UIElement>, es kann nicht in fortlaufendem Inhalt verwendet werden, es sei denn, in dem sie enthalten ist ein <xref:System.Windows.Documents.BlockUIContainer> oder <xref:System.Windows.Documents.InlineUIContainer>. Weitere Informationen zu <xref:System.Windows.Documents.Table>, finden Sie unter [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
### <a name="inline-derived-classes"></a>Inlineabgeleitete Klassen  
 **Run**  
  
 <xref:System.Windows.Documents.Run>wird verwendet, um die unformatierten Text enthalten. Sie erwarten wahrscheinlich <xref:System.Windows.Documents.Run> Objekten umfassenden verwendet werden kann, fortlaufende Inhalte. Allerdings im Markup <xref:System.Windows.Documents.Run> Elemente werden nicht explizit verwendet werden soll. <xref:System.Windows.Documents.Run>wird beim Erstellen oder Bearbeiten von Datenfluss-Dokumente mithilfe von Code verwendet werden soll. Beispielsweise ist in das Markup unterhalb der ersten <xref:System.Windows.Documents.Paragraph> gibt an, die <xref:System.Windows.Documents.Run> Element explizit während der zweite jedoch nicht. Beide Absätze generieren eine identische Ausgabe.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Hinweis:** ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft von der <xref:System.Windows.Documents.Run> Objekt ist eine Abhängigkeitseigenschaft. Sie binden die <xref:System.Windows.Documents.Run.Text%2A> -Eigenschaft an eine Datenquelle, z. B. eine <xref:System.Windows.Controls.TextBlock>. Die <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft unterstützt die unidirektionale Bindung. Die <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft unterstützt auch bidirektionale Bindung, mit Ausnahme von <xref:System.Windows.Controls.RichTextBox>. Ein Beispiel finden Sie unter <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span>gruppiert andere Inline-Inhaltselemente. Keine inhärente Rendern angewendet wird, zu Inhalten innerhalb einer <xref:System.Windows.Documents.Span> Element. Allerdings Elemente, die von erben <xref:System.Windows.Documents.Span> einschließlich <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> und <xref:System.Windows.Documents.Underline> gelten Formatieren von Text.  
  
 Im folgenden finden Sie ein Beispiel für eine <xref:System.Windows.Documents.Span> verwendet wird, um Text, einschließlich Inlineinhalt enthalten eine <xref:System.Windows.Documents.Bold> Element, und ein <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 Der folgende Screenshot zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Gerendertes Span-Beispiel](../../../../docs/framework/wpf/advanced/media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer>ermöglicht <xref:System.Windows.UIElement> Elemente (d. h. ein Steuerelement wie <xref:System.Windows.Controls.Button>) zum Einbetten in einer <xref:System.Windows.Documents.Inline> Content-Element. Dieses Element ist das Äquivalent zu Inline <xref:System.Windows.Documents.BlockUIContainer> oben beschriebenen. Im folgenden finden Sie ein Beispiel, verwendet <xref:System.Windows.Documents.InlineUIContainer> zum Einfügen einer <xref:System.Windows.Controls.Button> Inline in einer <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Hinweis:** <xref:System.Windows.Documents.InlineUIContainer> muss nicht explizit im Markup verwendet werden. Wenn Sie ihn nicht Weg, eine <xref:System.Windows.Documents.InlineUIContainer> wird trotzdem erstellt werden, wenn der Code kompiliert wird.  
  
 **Figure und Floater**  
  
 <xref:System.Windows.Documents.Figure>und <xref:System.Windows.Documents.Floater> werden verwendet, um Inhalte in Dokumenten Fluss mit Platzierungseigenschaften einbetten, die unabhängig von den primären inhaltsdatenfluss angepasst werden kann. <xref:System.Windows.Documents.Figure>oder <xref:System.Windows.Documents.Floater> Elemente sind häufig markiert oder Teile des Inhalts zu unterstützen, Bilder oder andere Inhalte in den main inhaltsdatenfluss Host hervorgehoben oder zum Einfügen von lose verbundener Inhalt, z. B. ankündigen.  
  
 Im folgende Beispiel wird gezeigt, wie zum Einbetten einer <xref:System.Windows.Documents.Figure> in einen Textabsatz.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Figure-Beispiel](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure>und <xref:System.Windows.Documents.Floater> unterscheiden sich auf verschiedene Weise und für verschiedene Szenarien verwendet werden.  
  
 **Figure:**  
  
-   Kann positioniert werden: Sie können die horizontalen und vertikalen Textmarken so festlegen, dass diese relativ an der Seite, dem Inhalt, der Spalte oder dem Absatz andocken. Sie können auch die <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> und <xref:System.Windows.Documents.Figure.VerticalOffset%2A> Eigenschaften an beliebigen Offsets.  
  
-   Ist mehr als einer Spalte beträchtliche Anzahl an: Sie können festlegen, <xref:System.Windows.Documents.Figure> Höhe und Breite auf ein Vielfaches von Seiten, die Inhalte oder Spalte Höhe oder Breite. Beachten Sie, dass im Fall von Seiten und Inhalt keine Vielfachen über 1 zulässig sind. Sie können z. B. die Breite des Festlegen einer <xref:System.Windows.Documents.Figure> "Seite" 0,5 "" oder "0,25 Inhalt" oder "Spalte 2" sein. Sie können die Höhe und Breite auch auf absolute Pixelwerte festlegen.  
  
-   Wird keine Paginierung: Wenn der Inhalt innerhalb einer <xref:System.Windows.Documents.Figure> passt nicht in die <xref:System.Windows.Documents.Figure>, passt der Inhalt wird gerendert und der restliche Inhalt verloren gegangen ist  
  
 **Floater:**  
  
-   Kann nicht positioniert werden und wird gerendert, wo Speicherplatz dafür verfügbar gemacht werden kann. Sie können nicht festgelegt, den Offset oder die Verankerung einer <xref:System.Windows.Documents.Floater>.  
  
-   Kann nicht vergrößert werden, um mehr als eine Spalte: standardmäßig <xref:System.Windows.Documents.Floater> Größen mindestens eine Spalte. Es wurde eine <xref:System.Windows.Documents.Floater.Width%2A> -Eigenschaft, die festgelegt werden kann, um eine absolute Pixelwert, aber wenn Sie diesen Wert größer als eine Spaltenbreite wird ignoriert und der Floater wird mindestens eine Spalte angepasst. Durch Festlegen der richtigen Pixelbreite weniger als einer Spalte Größe, Größe ist jedoch nicht Spalte relativ "0.5Column" ist daher keinen gültigen Ausdruck für <xref:System.Windows.Documents.Floater> Breite. <xref:System.Windows.Documents.Floater>besitzt keine Height-Eigenschaft und Höhe kann nicht festgelegt werden, dessen Höhe hängt vom Inhalt  
  
-   <xref:System.Windows.Documents.Floater>paginiert: Wenn der Inhalt an der angegebenen Breite nach mehr als 1 Spaltenhöhe erstreckt, Floater unterbrochen wird und auf die nächste Spalte, die nächste Seite usw. paginiert.  
  
 <xref:System.Windows.Documents.Figure>ist eine gute Stelle zum eigenständigen Inhalts der Größe steuern soll und Positionierung und sind sicher, dass der Inhalt in die angegebene Größe passt. <xref:System.Windows.Documents.Floater>ist ein guter Ausgangspunkt Weitere frei fließende Inhalte konzentrieren, die ähnlich wie der Inhalt der Hauptseite fließen, aber getrennt von.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak>bewirkt, dass einen Zeilenumbruch in fortlaufendem Inhalt auftreten. Das folgende Beispiel veranschaulicht die Verwendung von <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 Der folgende Screenshot zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: LineBreak-Beispiel](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>Flussauflistungselemente  
 In vielen der Beispiele oben die <xref:System.Windows.Documents.BlockCollection> und <xref:System.Windows.Documents.InlineCollection> werden verwendet, um fortlaufenden Inhalt programmgesteuert zu erstellen. Um beispielsweise zum Hinzufügen von Elementen einer <xref:System.Windows.Documents.Paragraph>, können Sie die Syntax verwenden:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Dadurch wird eine <xref:System.Windows.Documents.Run> auf die <xref:System.Windows.Documents.InlineCollection> von der <xref:System.Windows.Documents.Paragraph>.  Dies ist identisch mit dem impliziten <xref:System.Windows.Documents.Run> befindet sich innerhalb einer <xref:System.Windows.Documents.Paragraph> im Markup:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Als Beispiel zeigt die Verwendung der <xref:System.Windows.Documents.BlockCollection>, das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Section> und verwendet dann die **hinzufügen** Methode zum Hinzufügen einer neuen <xref:System.Windows.Documents.Paragraph> auf die <xref:System.Windows.Documents.Section> Inhalt.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Neben dem Hinzufügen von Elementen zu einer Flussauflistung können Sie auch Elemente entfernen.  Das folgende Beispiel löscht die letzte <xref:System.Windows.Documents.Inline> Element in der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Inline> Elemente) aus dem <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Beim programmgesteuerten Arbeiten mit fortlaufendem Inhalt werden Sie diese Auflistungen wahrscheinlich häufig verwenden.  
  
 Gibt an, ob ein Element für fortlaufenden verwendet ein <xref:System.Windows.Documents.InlineCollection> (Inlines) oder <xref:System.Windows.Documents.BlockCollection> (Blöcke) enthalten den untergeordneten Elementen hängt vom Typ der untergeordneten Elemente (<xref:System.Windows.Documents.Block> oder <xref:System.Windows.Documents.Inline>) vom übergeordneten Element enthalten sein können. Einschlussregeln für Flussinhaltselemente sind im Inhaltsschema im nächsten Abschnitt zusammengefasst.  
  
 **Hinweis:** besteht ein dritter Typ der Auflistung mit fortlaufendem Inhalt verwendet die <xref:System.Windows.Documents.ListItemCollection>, aber diese Auflistung wird nur verwendet, mit einer <xref:System.Windows.Documents.List>. Darüber hinaus stehen einige Sammlungen bereits mit verwendet <xref:System.Windows.Documents.Table>. Finden Sie unter [Übersicht über die Tabelle](../../../../docs/framework/wpf/advanced/table-overview.md) für Weitere Informationen.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>Inhaltsschema  
 In Anbetracht der Anzahl verschiedener Flussinhaltselemente kann es überwältigend sein, den Überblick darüber zu behalten, welchen Typ von untergeordnetem Element ein Element einschließen kann. Das folgende Diagramm fasst die Einschlussregeln für Inhaltselemente zusammen. Die Pfeile stellen die möglichen Übergeordnet/Untergeordnet-Beziehungen dar.  
  
 ![Diagramm: Flussinhalt-Einschlussschema](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 Wie aus der Abbildung oben dargestellt, die untergeordneten Elemente für ein Element zulässig sind nicht unbedingt bestimmt, ob es sich handelt eine <xref:System.Windows.Documents.Block> Element oder ein <xref:System.Windows.Documents.Inline> Element. Z. B. eine <xref:System.Windows.Documents.Span> (ein <xref:System.Windows.Documents.Inline> Element) ist nur zulässig <xref:System.Windows.Documents.Inline> untergeordnete Elemente beim eine <xref:System.Windows.Documents.Figure> (auch eine <xref:System.Windows.Documents.Inline> Element) ist nur zulässig <xref:System.Windows.Documents.Block> untergeordnete Elemente. Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Beispielsweise ermöglicht die Verwendung des Diagramms bestimmen, wie zum Erstellen von fortlaufenden Inhalt von einem <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Ein <xref:System.Windows.Controls.RichTextBox> darf eine <xref:System.Windows.Documents.FlowDocument> enthalten wiederum müssen eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im Folgenden finden Sie das entsprechende Segment aus dem Diagramm oben.  
  
 ![Diagramm: RichTextBox-Einschlussregeln](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 Bis jetzt könnte das Markup wie folgt aussehen.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** Gemäß dem Diagramm stehen verschiedene <xref:System.Windows.Documents.Block> Elemente einschließlich auswählbarer <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, und <xref:System.Windows.Documents.BlockUIContainer> (Siehe Block abgeleitete Klassen, die weiter oben). Angenommen, wir möchten einen <xref:System.Windows.Documents.Table>. Gemäß der Abbildung oben eine <xref:System.Windows.Documents.Table> enthält eine <xref:System.Windows.Documents.TableRowGroup> mit <xref:System.Windows.Documents.TableRow> Elemente, die enthalten <xref:System.Windows.Documents.TableCell> -Elemente enthalten eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im folgenden finden Sie die entsprechende Segment für <xref:System.Windows.Documents.Table> aus dem oben stehenden Diagramm übernommen.  
  
 ![Diagramm: Übergeordnet&#47;Untergeordnet-Schema für Table](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 Im Folgenden finden Sie das entsprechende Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Erneut, eine oder mehrere <xref:System.Windows.Documents.Block> Elemente sind erforderlich, darunter eine <xref:System.Windows.Documents.TableCell>. Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Wir können dazu eine <xref:System.Windows.Documents.Paragraph> mit einem <xref:System.Windows.Documents.Run> Element. Im folgenden finden Sie die entsprechenden Segmente aus dem Diagramm anzeigen, die eine <xref:System.Windows.Documents.Paragraph> dauert ein <xref:System.Windows.Documents.Inline> -Element und einem <xref:System.Windows.Documents.Run> (ein <xref:System.Windows.Documents.Inline> Element) dauert nur nur-Text.  
  
 ![Diagramm: Übergeordnet&#47;Untergeordnet-Schema für Paragraph](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![Diagramm: Übergeordnet&#47;Untergeordnet-Schema für Run](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Nachstehend finden Sie das gesamte Beispiel im Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>Anpassen von Text  
 In der Regel ist Text der am weitesten verbreitete Inhaltstyp in einem Flussdokument. Obwohl die oben eingeführten Objekte verwendet werden können, um die meisten Aspekte beim Rendern von Text zu steuern, gibt es einige andere Methoden zum Anpassen von Text, die in diesem Abschnitt abgedeckt werden.  
  
### <a name="text-decorations"></a>Textverzierungen  
 Textverzierungen ermöglichen es Ihnen, die Effekte „Unterstreichen“, „Überstreichen“, „Grundlinie“ und „Durchgestrichen“ auf den Text anzuwenden (siehe Bilder unten). Diese Ergänzungen werden hinzugefügt, mit der <xref:System.Windows.Documents.Inline.TextDecorations%2A> -Eigenschaft, die durch eine Reihe von Objekten, einschließlich verfügbar gemacht wird <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, und <xref:System.Windows.Controls.TextBox>.  
  
 Das folgende Beispiel veranschaulicht das Festlegen der <xref:System.Windows.Documents.Paragraph.TextDecorations%2A>-Eigenschaft einer <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Text mit Standardeffekt „Durchstreichen“](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 Der folgenden Abbildung wird wie die **überlagernde Linie**, **Baseline**, und **Unterstreichen** Ergänzungen zu rendern, bzw.  
  
 ![Screenshot: Überstrich-TextDecorator](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![Screenshot: Standardgrundlinieneffekt auf Text](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![Screenshot: Text mit Standardunterstricheffekt](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>Typografie  
 Die <xref:System.Windows.Documents.TextElement.Typography%2A> -Eigenschaft verfügbar gemacht wird, von den meisten Flow-bezogenen Inhalte einschließlich <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, und <xref:System.Windows.Controls.TextBox>. Diese Eigenschaft wird verwendet, um typografische Eigenschaften/Variationen von Text (d.h. Kapitälchen oder Großbuchstaben, hoch- und tiefgestellter Text usw.) zu steuern.  
  
 Im folgende Beispiel wird gezeigt, wie zum Festlegen der <xref:System.Windows.Documents.TextElement.Typography%2A> -Attribut mit <xref:System.Windows.Documents.Paragraph> wie das Beispielelement.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 Im Gegensatz dazu zeigt die folgende Abbildung, wie ein ähnliches Beispiel mit typografischen Standardeigenschaften gerendert wird.  
  
 ![Screenshot: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 Im folgende Beispiel wird gezeigt, wie zum Festlegen der <xref:System.Windows.Controls.TextBox.Typography%2A> Eigenschaft programmgesteuert.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Finden Sie unter [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md) für Weitere Informationen zu Typografie.  
  
## <a name="see-also"></a>Siehe auch  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)  
 [Übersicht über das TextElement-Inhaltsmodell](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [Übersicht über Anmerkungen](../../../../docs/framework/wpf/advanced/annotations-overview.md)
