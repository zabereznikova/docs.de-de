---
title: Übersicht über Tabellen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 01a5233a5436688caee3783cb26d344284df52e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964300"
---
# <a name="table-overview"></a>Übersicht über Tabellen
<xref:System.Windows.Documents.Table>ist ein Element auf Blockebene, das die Raster basierte Darstellung von Fluss Dokument Inhalten unterstützt. Die Flexibilität dieses Elements macht es nicht nur sehr hilfreich, sondern auch schwieriger zu verstehen und richtig zu verwenden.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Grundlagen zu Tabellen](#table_basics)  
  
- [Worin unterscheidet sich eine Tabelle von einem Raster?](#table_vs_Grid)  
  
- [Grundlegende Tabellenstruktur](#basic_table_structure)  
  
- [Tabellenkapselung](#table_containment)  
  
- [Zeilengruppen](#row_groupings)  
  
- [Hintergrundrendering-Rangfolge](#rendering_precedence)  
  
- [Überspannen von Zeilen oder Spalten](#spanning_rows_or_columns)  
  
- [Erstellen einer Tabelle mit Code](#building_a_table_with_code)  
  
- [Verwandte Themen] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>Grundlagen zu Tabellen  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>Worin unterscheidet sich eine Tabelle von einem Raster?  
 <xref:System.Windows.Documents.Table>und <xref:System.Windows.Controls.Grid> verfügen über einige allgemeine Funktionen, aber beide sind für unterschiedliche Szenarien am besten geeignet. Eine <xref:System.Windows.Documents.Table> ist für die Verwendung innerhalb von fortlaufendem Inhalt vorgesehen (Weitere Informationen zu fortlaufendem Inhalt finden Sie unter [Übersicht über Fluss Dokumente](flow-document-overview.md) ). Raster eignen sich am besten für den Einsatz in Formularen (also eigentlich überall dort, wo es keinen fortlaufenden Inhalt gibt). In einer <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Documents.Table> unterstützt <xref:System.Windows.Controls.Grid> das Verhalten von fortlaufenden Inhalten wie Paginierung, Spalten Umfluss und Inhalts Auswahl, während dies nicht der gibt. Auf der anderen Seite wird am besten außerhalb von a <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.Grid> verwendet, <xref:System.Windows.Documents.Table> z. a. durch Hinzufügen von Elementen auf der Grundlage einer Zeilen-und Spalten Indizierung. <xref:System.Windows.Controls.Grid> Das <xref:System.Windows.Controls.Grid> -Element ermöglicht das Schichten von untergeordneten Inhalten, sodass mehr als ein Element in einer einzelnen "Zelle" vorhanden sein kann. <xref:System.Windows.Documents.Table>unterstützt keine Schichten. Untergeordnete Elemente eines <xref:System.Windows.Controls.Grid> können in Bezug auf den Bereich ihrer "Cell"-Begrenzungen absolut positioniert werden. <xref:System.Windows.Documents.Table>Diese Funktion wird von nicht unterstützt. Zum Schluss erfordert <xref:System.Windows.Controls.Grid> ein weniger Ressourcen <xref:System.Windows.Documents.Table> , daher sollten Sie zur Verbesserung der Leistung verwenden. <xref:System.Windows.Controls.Grid>  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Grundlegende Tabellenstruktur  
 <xref:System.Windows.Documents.Table>stellt eine Raster basierte Präsentation bereit, die aus Spalten (dargestellt <xref:System.Windows.Documents.TableColumn> durch-Elemente) und Zeilen ( <xref:System.Windows.Documents.TableRow> dargestellt durch-Elemente) besteht. <xref:System.Windows.Documents.TableColumn>-Elemente hosten keinen Inhalt. Sie definieren einfach Spalten und Merkmale von Spalten. <xref:System.Windows.Documents.TableRow>-Elemente müssen in einem <xref:System.Windows.Documents.TableRowGroup> -Element gehostet werden, das eine Gruppierung von Zeilen für die Tabelle definiert. <xref:System.Windows.Documents.TableCell>-Elemente, die den eigentlichen Inhalt enthalten, der von der Tabelle dargestellt werden soll, müssen in <xref:System.Windows.Documents.TableRow> einem-Element gehostet werden. <xref:System.Windows.Documents.TableCell>darf nur Elemente enthalten, die von <xref:System.Windows.Documents.Block>abgeleitet sind.  Gültige untergeordnete Elemente für <xref:System.Windows.Documents.TableCell> eine include.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>Elemente dürfen Textinhalte nicht direkt hosten. Weitere Informationen zu den Einschluss Regeln für fortlaufende Inhaltselemente <xref:System.Windows.Documents.TableCell>wie finden Sie unter [Übersicht über Fluss Dokumente](flow-document-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table>ähnelt dem <xref:System.Windows.Controls.Grid> -Element, verfügt jedoch über mehr Funktionen und erfordert daher einen höheren Ressourcen Aufwand.  
  
 Im folgenden Beispiel wird eine einfache 2 x 3-Tabelle [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]mit definiert.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot, der zeigt, wie eine einfache Tabelle gerendert wird.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Tabellenkapselung  
 <xref:System.Windows.Documents.Table>wird vom <xref:System.Windows.Documents.Block> -Element abgeleitet und entspricht den allgemeinen Regeln für <xref:System.Windows.Documents.Block> Level-Elemente.  Ein <xref:System.Windows.Documents.Table> -Element kann in einem der folgenden Elemente enthalten sein:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Zeilengruppen  
 Das <xref:System.Windows.Documents.TableRowGroup> -Element bietet eine Möglichkeit, Zeilen in einer Tabelle willkürlich zu gruppieren; jede Zeile in einer Tabelle muss zu einer Zeilen Gruppierung gehören.  Zeilen in einer Zeilengruppe dienen häufig einem gemeinsamen Zweck und können als Gruppe formatiert werden.  Eine häufige Verwendung für Zeilengruppen ist die Trennung von Zeilen mit verschiedenen Zwecken, um z.B. Titel, Kopfzeilen und Fußzeilen vom Hauptinhalt der Tabelle zu trennen.  
  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] verwendet, um eine Tabelle mit formatierten Kopf-und Fußzeilen zu definieren.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Verschaffen Tabellenzeilen Gruppen](./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a>Hintergrundrendering-Rangfolge  
 Tabellenelemente rendern in der folgenden Reihenfolge (Z-Reihenfolge, vom niedrigsten zum höchsten). Diese Reihenfolge kann nicht geändert werden. Beispielsweise gibt es keine „Z-Reihenfolge“-Eigenschaft für diese Elemente, die Sie zum Überschreiben dieser festgelegten Reihenfolge verwenden können.  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 Betrachten Sie das folgende Beispiel, das Hintergrundfarben für jedes dieser Elemente in einer Tabelle definiert.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel (nur Hintergrundfarben werden angezeigt) gerendert wird.  
  
 ![Verschaffen Tabelle z&#45;Order](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Überspannen von Zeilen oder Spalten  
 Tabellenzellen können so konfiguriert werden, dass Sie sich über mehrere Zeilen oder <xref:System.Windows.Documents.TableCell.RowSpan%2A> Spalten <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> erstrecken, indem Sie die-oder-Attribute verwenden.  
  
 Betrachten Sie das folgende Beispiel, in dem eine Zelle drei Spalten umfasst.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Verschaffen Zelle, die alle drei]Spalten umfasst(./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Erstellen einer Tabelle mit Code  
 In den folgenden Beispielen wird gezeigt, wie ein <xref:System.Windows.Documents.Table> Programm gesteuert erstellt und mit Inhalt aufgefüllt wird. Der Inhalt der Tabelle wird in fünf Zeilen (dargestellt durch <xref:System.Windows.Documents.TableRow> in einem <xref:System.Windows.Documents.Table.RowGroups%2A> -Objekt enthaltene-Objekte) und sechs Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> -Objekte) aufgeteilt. Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.  Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften. Tabellenzellen enthalten den eigentlichen Inhalt, der aus Text, Bildern oder nahezu jedem anderen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Element bestehen kann.  
  
 Zuerst wird eine <xref:System.Windows.Documents.FlowDocument> zum <xref:System.Windows.Documents.Table>Hosten von erstellt, und ein neuer <xref:System.Windows.Documents.Table> wird <xref:System.Windows.Documents.FlowDocument>erstellt und dem Inhalt des hinzugefügt.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Als nächstes werden <xref:System.Windows.Documents.TableColumn> sechs Objekte erstellt und der Auflistung der <xref:System.Windows.Documents.Table.Columns%2A> Tabelle hinzugefügt, wobei einige Formatierungen angewendet werden.  
  
> [!NOTE]
> Beachten Sie, dass die <xref:System.Windows.Documents.Table.Columns%2A> -Auflistung der Tabelle eine standardmäßige NULL basierte Indizierung verwendet.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.  Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.  Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.  Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Flussdokumente](flow-document-overview.md)
- [Definieren einer Tabelle mit XAML](how-to-define-a-table-with-xaml.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [Verwenden von fortlaufenden Inhaltselementen](how-to-use-flow-content-elements.md)
