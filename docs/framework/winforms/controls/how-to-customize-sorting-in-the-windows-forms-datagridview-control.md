---
title: Anpassen der Sortierung in einem DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 20f581b2df6fd172a0a1998aed60c56b0306f2eb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743182"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2cb0f-102">Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cb0f-102">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2cb0f-103">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement ermöglicht die automatische Sortierung. Je nach Ihren Anforderungen müssen Sie die Sortiervorgänge jedoch möglicherweise anpassen.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic sorting but, depending on your needs, you might need to customize sort operations.</span></span> <span data-ttu-id="2cb0f-104">Sie können beispielsweise mit der programmgesteuerten Sortierung eine alternative Benutzeroberfläche (UI) erstellen.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-104">For example, you can use programmatic sorting to create an alternate user interface (UI).</span></span> <span data-ttu-id="2cb0f-105">Alternativ können Sie das <xref:System.Windows.Forms.DataGridView.SortCompare>-Ereignis behandeln oder die `Sort(IComparer)`-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode aufrufen, um flexibler sortieren zu können, z. B. beim Sortieren mehrerer Spalten.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-105">Alternatively, you can handle the <xref:System.Windows.Forms.DataGridView.SortCompare> event or call the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method for greater sorting flexibility, such as sorting multiple columns.</span></span>  
  
 <span data-ttu-id="2cb0f-106">In den folgenden Codebeispielen werden diese drei Ansätze der benutzerdefinierten Sortierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-106">The following code examples demonstrate these three approaches to custom sorting.</span></span> <span data-ttu-id="2cb0f-107">Weitere Informationen finden Sie unter [Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="2cb0f-107">For more information, see [Column Sort Modes in the Windows Forms DataGridView Control](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="programmatic-sorting"></a><span data-ttu-id="2cb0f-108">Programmgesteuertes Sortieren</span><span class="sxs-lookup"><span data-stu-id="2cb0f-108">Programmatic Sorting</span></span>  
 <span data-ttu-id="2cb0f-109">Im folgenden Codebeispiel wird eine programmgesteuerte Sortierung veranschaulicht, bei der die <xref:System.Windows.Forms.DataGridView.SortOrder%2A>-Eigenschaft und die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A>-Eigenschaft zum Festlegen der Sortierrichtung verwendet werden und die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A>-Eigenschaft verwendet wird, um das Sortiersymbol manuell festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-109">The following code example demonstrates a programmatic sort using the <xref:System.Windows.Forms.DataGridView.SortOrder%2A> and <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> properties to determine the direction of the sort, and the <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> property to manually set the sort glyph.</span></span> <span data-ttu-id="2cb0f-110">Die `Sort(DataGridViewColumn,ListSortDirection)`-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode wird verwendet, um Daten nur in einer einzigen Spalte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-110">The `Sort(DataGridViewColumn,ListSortDirection)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method is used to sort data only in a single column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a><span data-ttu-id="2cb0f-111">Benutzerdefinierte Sortierung mit dem SortCompare-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2cb0f-111">Custom Sorting Using the SortCompare Event</span></span>  
 <span data-ttu-id="2cb0f-112">Im folgenden Codebeispiel wird eine benutzerdefinierte Sortierung mit einem <xref:System.Windows.Forms.DataGridView.SortCompare>-Ereignishandler veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-112">The following code example demonstrates custom sorting using a <xref:System.Windows.Forms.DataGridView.SortCompare> event handler.</span></span> <span data-ttu-id="2cb0f-113">Die ausgewählte <xref:System.Windows.Forms.DataGridViewColumn> wird sortiert, und wenn die Spalte doppelte Werte enthält, wird die ID-Spalte verwendet, um die endgültige Reihenfolge zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-113">The selected <xref:System.Windows.Forms.DataGridViewColumn> is sorted and, if there are duplicate values in the column, the ID column is used to determine the final order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a><span data-ttu-id="2cb0f-114">Benutzerdefinierte Sortierung mit der IComparer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cb0f-114">Custom Sorting Using the IComparer Interface</span></span>  
 <span data-ttu-id="2cb0f-115">Im folgenden Codebeispiel wird eine benutzerdefinierte Sortierung mit der `Sort(IComparer)`-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode veranschaulicht, bei der durch die Implementierung der <xref:System.Collections.IComparer>-Schnittstelle mehrere Spalten sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="2cb0f-115">The following code example demonstrates custom sorting using the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method, which takes an implementation of the <xref:System.Collections.IComparer> interface to perform a multiple-column sort.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2cb0f-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2cb0f-116">Compiling the Code</span></span>  
 <span data-ttu-id="2cb0f-117">Diese Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2cb0f-117">These examples require:</span></span>  
  
- <span data-ttu-id="2cb0f-118">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="2cb0f-118">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb0f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cb0f-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="2cb0f-120">Sortieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cb0f-120">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2cb0f-121">Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cb0f-121">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2cb0f-122">Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cb0f-122">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)
