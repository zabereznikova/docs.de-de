---
title: 'Vorgehensweise: Schreibschutz Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 6fbdf661983d39ad4793946f10deb3e224f2f711
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583627"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3248a-102">Vorgehensweise: Schreibschutz Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3248a-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3248a-103">Nicht alle Daten sind zum Bearbeiten bestimmt.</span><span class="sxs-lookup"><span data-stu-id="3248a-103">Not all data is meant for editing.</span></span> <span data-ttu-id="3248a-104">Im <xref:System.Windows.Forms.DataGridView>-Steuerelement bestimmt der Wert der Spalteneigenschaft <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>, ob Benutzer Zellen in dieser Spalte bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="3248a-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="3248a-105">Informationen dazu, wie Sie das Steuerelement vollständig schreibgeschützt machen, finden Sie unter [Vorgehensweise: Verhindern des Hinzufügens der Zeile, und Löschen in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="3248a-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="3248a-106">Visual Studio bietet Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="3248a-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="3248a-107">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Festlegen von Spalten schreibgeschützt in der Windows Forms-DataGridView-Steuerelement mithilfe des Designers](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="3248a-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="3248a-108">So weisen Sie eine schreibgeschützte Spalte programmgesteuert zu</span><span class="sxs-lookup"><span data-stu-id="3248a-108">To make a column read-only programmatically</span></span>  
  
-   <span data-ttu-id="3248a-109">Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="3248a-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3248a-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3248a-110">Compiling the Code</span></span>  
 <span data-ttu-id="3248a-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3248a-111">This example requires:</span></span>  
  
-   <span data-ttu-id="3248a-112">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1` mit einer Spalte namens `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="3248a-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
-   <span data-ttu-id="3248a-113">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3248a-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3248a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3248a-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3248a-115">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3248a-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="3248a-116">Vorgehensweise: Zu verhindern, dass Hinzufügens und Löschens im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3248a-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
