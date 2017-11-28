---
title: "Übersicht über Tabellen"
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
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb9edf0439c985af015d6badd11c026449a82f57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="table-overview"></a>Übersicht über Tabellen
<xref:System.Windows.Documents.Table>ist ein Block-Level-Element, das rasterbasierte Darstellung des Dokumentinhalts Fluss unterstützt. Die Flexibilität dieses Elements macht es nicht nur sehr hilfreich, sondern auch schwieriger zu verstehen und richtig zu verwenden.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Grundlagen zu Tabellen](#table_basics)  
  
-   [Worin unterscheidet sich eine Tabelle von einem Raster?](#table_vs_Grid)  
  
-   [Grundlegende Tabellenstruktur](#basic_table_structure)  
  
-   [Tabellenkapselung](#table_containment)  
  
-   [Zeilengruppen](#row_groupings)  
  
-   [Hintergrundrendering-Rangfolge](#rendering_precedence)  
  
-   [Überspannen von Zeilen oder Spalten](#spanning_rows_or_columns)  
  
-   [Erstellen einer Tabelle mit Code](#building_a_table_with_code)  
  
-   [Verwandte Themen] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>Grundlagen zu Tabellen  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>Worin unterscheidet sich eine Tabelle von einem Raster?  
 <xref:System.Windows.Documents.Table>und <xref:System.Windows.Controls.Grid> haben einige allgemeine Funktionen gemeinsam, aber jede eignet sich optimal für verschiedene Szenarien. Ein <xref:System.Windows.Documents.Table> dient zur Verwendung innerhalb des fortlaufenden Inhalts (finden Sie unter [Nachrichtenfluss-Dokument (Übersicht)](../../../../docs/framework/wpf/advanced/flow-document-overview.md) für Weitere Informationen zu fortlaufendem Inhalt). Raster eignen sich am besten für den Einsatz in Formularen (also eigentlich überall dort, wo es keinen fortlaufenden Inhalt gibt). Innerhalb einer <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> unterstützt flow Content Verhalten wie die Paginierung Spalte Umfließen und Inhaltsauswahl beim eine <xref:System.Windows.Controls.Grid> hingegen nicht. Ein <xref:System.Windows.Controls.Grid> andererseits wird außerhalb der am besten verwendet eine <xref:System.Windows.Documents.FlowDocument> vielen Gründen <xref:System.Windows.Controls.Grid> fügt Elemente basierend auf einer Zeile und Spalte Index <xref:System.Windows.Documents.Table> hingegen nicht. Die <xref:System.Windows.Controls.Grid> -Element ermöglicht die Anordnung von untergeordnetem Inhalt, sodass mehr als ein Element in einer "Zelle" vorhanden sein <xref:System.Windows.Documents.Table>Ebenenstruktur unterstützt nicht. Untergeordnete Elemente von einem <xref:System.Windows.Controls.Grid> relativ zum Bereich des Umrisslinien "Zelle" absolut positioniert werden kann. <xref:System.Windows.Documents.Table>Dieses Feature wird nicht unterstützt werden. Schließlich eine <xref:System.Windows.Controls.Grid> weniger Ressourcen erfordert ein <xref:System.Windows.Documents.Table> daher sollten Sie mithilfe einer <xref:System.Windows.Controls.Grid> zur Verbesserung der Leistung.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Grundlegende Tabellenstruktur  
 <xref:System.Windows.Documents.Table>Stellt eine rasterbasierte Darstellung aus Spalten besteht (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und Zeilen (dargestellt durch <xref:System.Windows.Documents.TableRow> Elemente). <xref:System.Windows.Documents.TableColumn>Elemente hosten keinen Inhalt. einfach definieren die Spalten und die Eigenschaften der Spalten. <xref:System.Windows.Documents.TableRow>Elemente müssen gehostet werden, einem <xref:System.Windows.Documents.TableRowGroup> -Element, das eine Gruppe von Zeilen für die Tabelle definiert. <xref:System.Windows.Documents.TableCell>Elemente, die enthalten, den tatsächlichen Inhalt der Tabelle dargestellt werden soll, müssen gehostet werden, einem <xref:System.Windows.Documents.TableRow> Element. <xref:System.Windows.Documents.TableCell>kann nur Elemente enthalten, die Ableitung <xref:System.Windows.Documents.Block>.  Gültige untergeordnete Elemente für eine <xref:System.Windows.Documents.TableCell> enthalten.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell>Elemente können nicht direkt-Text-Inhalt hosten. Weitere Informationen über die Kapselungsregeln für fortlaufenden Inhaltselemente wie <xref:System.Windows.Documents.TableCell>, finden Sie unter [Nachrichtenfluss-Dokument (Übersicht)](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table>ähnelt der <xref:System.Windows.Controls.Grid> Element aber verfügt über weitere Funktionen und daher benötigt größer Ressourcenaufwand.  
  
 Das folgende Beispiel definiert eine einfache 2 x 3-Tabelle mit [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Rendern einer Basistabelle](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Tabellenkapselung  
 <xref:System.Windows.Documents.Table>leitet sich von der <xref:System.Windows.Documents.Block> Element, und befolgt die allgemeinen Regeln für <xref:System.Windows.Documents.Block> Elemente der Ebene.  Ein <xref:System.Windows.Documents.Table> Element kann eines der folgenden Elemente enthalten sein:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Zeilengruppen  
 Die <xref:System.Windows.Documents.TableRowGroup> -Element stellt eine Möglichkeit zum Gruppieren von Zeilen in einer Tabelle nach dem Zufallsprinzip bereit; jede Zeile in einer Tabelle muss eine zeilengruppierung angehören.  Zeilen in einer Zeilengruppe dienen häufig einem gemeinsamen Zweck und können als Gruppe formatiert werden.  Eine häufige Verwendung für Zeilengruppen ist die Trennung von Zeilen mit verschiedenen Zwecken, um z.B. Titel, Kopfzeilen und Fußzeilen vom Hauptinhalt der Tabelle zu trennen.  
  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] zum Definieren einer Tabelle mit formatierten Kopf- und Fußzeile Zeilen.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Tabellenzeilengruppen](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a>Hintergrundrendering-Rangfolge  
 Tabellenelemente rendern in der folgenden Reihenfolge (Z-Reihenfolge, vom niedrigsten zum höchsten). Diese Reihenfolge kann nicht geändert werden. Beispielsweise gibt es keine „Z-Reihenfolge“-Eigenschaft für diese Elemente, die Sie zum Überschreiben dieser festgelegten Reihenfolge verwenden können.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 Betrachten Sie das folgende Beispiel, das Hintergrundfarben für jedes dieser Elemente in einer Tabelle definiert.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel (nur Hintergrundfarben werden angezeigt) gerendert wird.  
  
 ![Screenshot: Tabellen-Z-Reihenfolge](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Überspannen von Zeilen oder Spalten  
 Tabellenzellen können konfiguriert werden, damit mehrere Zeilen oder Spalten mit umfassen die <xref:System.Windows.Documents.TableCell.RowSpan%2A> oder <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> -Attribute.  
  
 Betrachten Sie das folgende Beispiel, in dem eine Zelle drei Spalten umfasst.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Zelle umfasst alle drei Spalten](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Erstellen einer Tabelle mit Code  
 Den folgenden Beispielen wird veranschaulicht, wie Sie programmgesteuert erstellen eine <xref:System.Windows.Documents.Table> und füllen sie mit dem Inhalt. Der Inhalt der Tabelle in fünf Zeilen aufgeteilt werden (dargestellte <xref:System.Windows.Documents.TableRow> enthaltenen Objekte eine <xref:System.Windows.Documents.Table.RowGroups%2A> Objekt) und sechs Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Objekte). Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.  Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften. Tabellenzellen enthalten den tatsächlichen Inhalt, der der Text, Bilder oder fast jeder beliebigen anderen bestehen kann [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Element.  
  
 Zuerst eine <xref:System.Windows.Documents.FlowDocument> wird erstellt, auf Host der <xref:System.Windows.Documents.Table>, und eine neue <xref:System.Windows.Documents.Table> erstellt und hinzugefügt werden, um den Inhalt des der <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Als Nächstes sechs <xref:System.Windows.Documents.TableColumn> -Objekte erstellt und der Tabelle hinzugefügt <xref:System.Windows.Documents.Table.Columns%2A> -Auflistung, mit einigen Formatierung angewendet.  
  
> [!NOTE]
>  Beachten Sie, dass der Tabelle <xref:System.Windows.Documents.Table.Columns%2A> Auflistung verwendet standardmäßige nullbasierter Indizierung.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.  Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.  Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.  Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [Definieren einer Tabelle mit XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Verwenden von fortlaufenden Inhaltselementen](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)
