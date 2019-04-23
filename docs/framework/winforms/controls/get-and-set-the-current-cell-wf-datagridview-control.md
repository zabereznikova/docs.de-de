---
title: 'Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: fb71a6e3259d3007e11f528377c95a9c4cbeb023
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096978"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4c4d3-102">Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c4d3-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4c4d3-103">Interaktion mit der <xref:System.Windows.Forms.DataGridView> häufig erforderlich, dass Sie programmgesteuert ermitteln, welche Zelle derzeit aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="4c4d3-104">Sie müssen möglicherweise auch die aktuelle Zelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-104">You may also need to change the current cell.</span></span> <span data-ttu-id="4c4d3-105">Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c4d3-106">Können Sie die aktuelle Zelle in einer Zeile oder Spalte, die Festlegen seiner <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> -Eigenschaftensatz auf `false`.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="4c4d3-107">Je nachdem auf die <xref:System.Windows.Forms.DataGridView> Auswahlmodus des Steuerelements ändern der aktuellen Zelle kann die Auswahl ändern.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="4c4d3-108">Weitere Informationen finden Sie unter [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4c4d3-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="4c4d3-109">Um die aktuelle Zelle programmtechnisch zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="4c4d3-110">Verwenden der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="4c4d3-111">So legen Sie die aktuelle Zelle programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="4c4d3-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="4c4d3-112">Legen Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4c4d3-113">Im folgenden Codebeispiel wird die aktuelle Zelle 0, Spalte 1 Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c4d3-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4c4d3-114">Compiling the Code</span></span>  
 <span data-ttu-id="4c4d3-115">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4c4d3-115">This example requires:</span></span>  
  
-   <span data-ttu-id="4c4d3-116"><xref:System.Windows.Forms.Button> Steuerelemente, die mit dem Namen `getCurrentCellButton` und `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="4c4d3-117">In visuellen C#, Anfügen muss der <xref:System.Windows.Forms.Control.Click> Ereignisse für jede Schaltfläche an den zugeordneten Ereignishandler im Beispielcode.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="4c4d3-118">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="4c4d3-119">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4c4d3-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c4d3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c4d3-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4c4d3-121">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c4d3-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="4c4d3-122">Auswahlmodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c4d3-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
