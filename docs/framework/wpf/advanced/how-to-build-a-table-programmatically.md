---
title: 'Vorgehensweise: Programmgesteuertes Erstellen einer Tabelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 3848032bf527f64ce591eb2cda98028c835d79f7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371931"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="bc4d7-102">Vorgehensweise: Programmgesteuertes Erstellen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="bc4d7-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="bc4d7-103">Die folgenden Beispiele zeigen, wie Sie programmgesteuert erstellen eine <xref:System.Windows.Documents.Table> und mit Inhalt füllen.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="bc4d7-104">Die Inhalte der Tabelle sind in fünf Zeilen aufgeteilt (dargestellt durch <xref:System.Windows.Documents.TableRow> in enthaltenen Objekte eine <xref:System.Windows.Documents.Table.RowGroups%2A> Objekt) und sechs Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Objekte).</span><span class="sxs-lookup"><span data-stu-id="bc4d7-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="bc4d7-105">Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="bc4d7-106">Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="bc4d7-107">Tabellenzellen enthalten den eigentlichen Inhalt, der der Text, Bildern oder nahezu jedem anderen bestehen kann [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Element.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc4d7-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc4d7-108">Example</span></span>  
 <span data-ttu-id="bc4d7-109">Zuerst eine <xref:System.Windows.Documents.FlowDocument> wird erstellt, auf Host der <xref:System.Windows.Documents.Table>, und ein neues <xref:System.Windows.Documents.Table> wird erstellt und hinzugefügt werden, auf den Inhalt des der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="bc4d7-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc4d7-110">Example</span></span>  
 <span data-ttu-id="bc4d7-111">Als Nächstes sechs <xref:System.Windows.Documents.TableColumn> Objekte erstellt und der Tabelle hinzugefügt werden <xref:System.Windows.Documents.Table.Columns%2A> Sammlung mit angewandter Formatierung.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc4d7-112">Beachten Sie, dass der tabellenspezifischen <xref:System.Windows.Documents.Table.Columns%2A> Auflistung standardmäßige nullbasierte Indizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="bc4d7-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc4d7-113">Example</span></span>  
 <span data-ttu-id="bc4d7-114">Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="bc4d7-115">Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="bc4d7-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc4d7-116">Example</span></span>  
 <span data-ttu-id="bc4d7-117">Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="bc4d7-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc4d7-118">Example</span></span>  
 <span data-ttu-id="bc4d7-119">Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="bc4d7-120">Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="bc4d7-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc4d7-121">Example</span></span>  
 <span data-ttu-id="bc4d7-122">Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="bc4d7-123">Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="bc4d7-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc4d7-124">See also</span></span>
- [<span data-ttu-id="bc4d7-125">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="bc4d7-125">Table Overview</span></span>](table-overview.md)
