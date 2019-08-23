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
ms.openlocfilehash: 670708f342e1cd1ac495c215b7508093349ac2e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933702"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2b07d-102">Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b07d-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2b07d-103">Die Interaktion mit <xref:System.Windows.Forms.DataGridView> dem erfordert häufig, dass Sie Programm gesteuert ermitteln, welche Zelle derzeit aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="2b07d-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="2b07d-104">Möglicherweise müssen Sie auch die aktuelle Zelle ändern.</span><span class="sxs-lookup"><span data-stu-id="2b07d-104">You may also need to change the current cell.</span></span> <span data-ttu-id="2b07d-105">Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> -Eigenschaft ausführen.</span><span class="sxs-lookup"><span data-stu-id="2b07d-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b07d-106">Die aktuelle Zelle kann nicht in einer Zeile oder Spalte festgelegt werden, <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> deren-Eigenschaft `false`auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2b07d-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="2b07d-107">Abhängig vom Auswahl <xref:System.Windows.Forms.DataGridView> Modus des-Steuer Elements kann das Ändern der aktuellen Zelle die Auswahl ändern.</span><span class="sxs-lookup"><span data-stu-id="2b07d-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="2b07d-108">Weitere Informationen finden Sie unter [Auswahl Modi im Windows Forms DataGridView-Steuer](selection-modes-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="2b07d-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="2b07d-109">So erhalten Sie die aktuelle Zelle Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="2b07d-109">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="2b07d-110">Verwenden Sie <xref:System.Windows.Forms.DataGridView> die- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft des-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="2b07d-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="2b07d-111">So legen Sie die aktuelle Zelle Programm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="2b07d-111">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="2b07d-112">Legen Sie <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> die-Eigenschaft <xref:System.Windows.Forms.DataGridView> des-Steuer Elements fest.</span><span class="sxs-lookup"><span data-stu-id="2b07d-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2b07d-113">Im folgenden Codebeispiel wird die aktuelle Zelle auf Zeile 0, Spalte 1, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2b07d-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b07d-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2b07d-114">Compiling the Code</span></span>  
 <span data-ttu-id="2b07d-115">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2b07d-115">This example requires:</span></span>  
  
- <span data-ttu-id="2b07d-116"><xref:System.Windows.Forms.Button>Steuerelemente `getCurrentCellButton` mit `setCurrentCellButton`dem Namen und.</span><span class="sxs-lookup"><span data-stu-id="2b07d-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="2b07d-117">In Visual C#müssen Sie die <xref:System.Windows.Forms.Control.Click> Ereignisse für jede Schaltfläche an den zugeordneten Ereignishandler im Beispielcode anfügen.</span><span class="sxs-lookup"><span data-stu-id="2b07d-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="2b07d-118">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="2b07d-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="2b07d-119">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b07d-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b07d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b07d-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2b07d-121">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b07d-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="2b07d-122">Auswahlmodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b07d-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
