---
title: 'Vorgehensweise: Programmgesteuertes Erstellen einer Tabelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 9c9061d3c4d6b3de5e1ab42a6b98c20813835ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964160"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="a2c94-102">Vorgehensweise: Programmgesteuertes Erstellen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="a2c94-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="a2c94-103">In den folgenden Beispielen wird gezeigt, wie ein <xref:System.Windows.Documents.Table> Programm gesteuert erstellt und mit Inhalt aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="a2c94-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="a2c94-104">Der Inhalt der Tabelle wird in fünf Zeilen (dargestellt durch <xref:System.Windows.Documents.TableRow> in einem <xref:System.Windows.Documents.Table.RowGroups%2A> -Objekt enthaltene-Objekte) und sechs Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> -Objekte) aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="a2c94-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="a2c94-105">Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="a2c94-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="a2c94-106">Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a2c94-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="a2c94-107">Tabellenzellen enthalten den eigentlichen Inhalt, der aus Text, Bildern oder nahezu jedem anderen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Element bestehen kann.</span><span class="sxs-lookup"><span data-stu-id="a2c94-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2c94-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2c94-108">Example</span></span>  
 <span data-ttu-id="a2c94-109">Zuerst wird eine <xref:System.Windows.Documents.FlowDocument> zum <xref:System.Windows.Documents.Table>Hosten von erstellt, und ein neuer <xref:System.Windows.Documents.Table> wird <xref:System.Windows.Documents.FlowDocument>erstellt und dem Inhalt des hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a2c94-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="a2c94-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2c94-110">Example</span></span>  
 <span data-ttu-id="a2c94-111">Als nächstes werden <xref:System.Windows.Documents.TableColumn> sechs Objekte erstellt und der Auflistung der <xref:System.Windows.Documents.Table.Columns%2A> Tabelle hinzugefügt, wobei einige Formatierungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2c94-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2c94-112">Beachten Sie, dass die <xref:System.Windows.Documents.Table.Columns%2A> -Auflistung der Tabelle eine standardmäßige NULL basierte Indizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2c94-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="a2c94-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2c94-113">Example</span></span>  
 <span data-ttu-id="a2c94-114">Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a2c94-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="a2c94-115">Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="a2c94-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="a2c94-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2c94-116">Example</span></span>  
 <span data-ttu-id="a2c94-117">Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="a2c94-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="a2c94-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2c94-118">Example</span></span>  
 <span data-ttu-id="a2c94-119">Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="a2c94-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="a2c94-120">Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.</span><span class="sxs-lookup"><span data-stu-id="a2c94-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="a2c94-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2c94-121">Example</span></span>  
 <span data-ttu-id="a2c94-122">Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.</span><span class="sxs-lookup"><span data-stu-id="a2c94-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="a2c94-123">Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="a2c94-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="a2c94-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2c94-124">See also</span></span>

- [<span data-ttu-id="a2c94-125">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="a2c94-125">Table Overview</span></span>](table-overview.md)
