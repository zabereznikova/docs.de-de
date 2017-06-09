---
title: "Gewusst wie: Programmgesteuertes Erstellen einer Tabelle | Microsoft Docs"
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
  - "Erstellen, Tabellen (Programmgesteuert)"
  - "Dokumente, Programmgesteuertes Erstellen von Tabellen"
  - "Tabellen, Programmgesteuertes Erstellen"
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Programmgesteuertes Erstellen einer Tabelle
Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Documents.Table> programmgesteuert erstellt und mit Inhalt gefüllt wird.  Die Inhalte der Tabelle sind auf fünf Zeilen \(dargestellt durch <xref:System.Windows.Documents.TableRow>\-Objekte, die in einem <xref:System.Windows.Documents.Table.RowGroups%2A>\-Objekt enthalten sind\) und sechs Spalten \(dargestellt durch <xref:System.Windows.Documents.TableColumn>\-Objekte\) aufgeteilt.  Die Zeilen werden für verschiedene Darstellungszwecke verwendet. Unter anderem gibt es eine Titelzeile, die als Überschrift für die gesamte Tabelle dient, eine Kopfzeile, die die Datenspalten der Tabelle beschreibt, und eine Fußzeile mit Zusammenfassungsinformationen.  Beachten Sie, dass die Begriffe "Titelzeile", "Kopfzeile" und "Fußzeile" keine spezifischen Bestandteile der Tabelle sind. Es handelt sich lediglich um Zeilen mit unterschiedlichen Eigenschaften.  Tabellenzellen enthalten den eigentlichen Inhalt, der aus Text, Bildern oder nahezu jedem beliebigen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Element bestehen kann.  
  
## Beispiel  
 Zuerst wird ein <xref:System.Windows.Documents.FlowDocument>, das die <xref:System.Windows.Documents.Table> hostet, sowie eine neue <xref:System.Windows.Documents.Table> erstellt und zu den Inhalten von <xref:System.Windows.Documents.FlowDocument> hinzugefügt.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## Beispiel  
 Anschließend werden sechs <xref:System.Windows.Documents.TableColumn>\-Objekte erstellt und mit einigen Formatierungen zur <xref:System.Windows.Documents.Table.Columns%2A>\-Auflistung der Tabelle hinzugefügt.  
  
> [!NOTE]
>  Beachten Sie, dass die <xref:System.Windows.Documents.Table.Columns%2A>\-Auflistung der Tabelle nullbasierte Standardindizierung verwendet.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## Beispiel  
 Anschließend wird eine Titelzeile erstellt und mit etwas Formatierung zur Tabelle hinzugefügt.  Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle überspannt.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## Beispiel  
 Anschließend wird ein Header erstellt und zur Tabelle hinzugefügt. Die Zellen im Header werden erstellt und mit Inhalt gefüllt.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## Beispiel  
 Anschließend wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt. Die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.  Das Erstellen dieser Zeile ähnelt der Erstellung des Headers, mit leichten Unterschieden bei der Formatierung.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## Beispiel  
 Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.  Genau wie die Titelzeile enthält auch die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle überspannt.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## Siehe auch  
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)