---
title: Anzeigen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement
description: Erfahren Sie, wie Sie Programm gesteuert ermitteln, welche Zelle derzeit aktiv ist, indem Sie die aktuelle Zelle im Windows Forms DataGridView-Steuerelement festlegen und festlegen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 1651ca9c8fa0329f9435a70ce777bce68f15ff63
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622210"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2c9b6-103">Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c9b6-103">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2c9b6-104">Die Interaktion mit dem <xref:System.Windows.Forms.DataGridView> erfordert häufig, dass Sie Programm gesteuert ermitteln, welche Zelle derzeit aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-104">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="2c9b6-105">Möglicherweise müssen Sie auch die aktuelle Zelle ändern.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-105">You may also need to change the current cell.</span></span> <span data-ttu-id="2c9b6-106">Sie können diese Aufgaben mit der- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-106">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c9b6-107">Die aktuelle Zelle kann nicht in einer Zeile oder Spalte festgelegt werden, deren- <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> Eigenschaft auf festgelegt ist `false` .</span><span class="sxs-lookup"><span data-stu-id="2c9b6-107">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="2c9b6-108">Abhängig vom <xref:System.Windows.Forms.DataGridView> Auswahlmodus des-Steuer Elements kann das Ändern der aktuellen Zelle die Auswahl ändern.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-108">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="2c9b6-109">Weitere Informationen finden Sie unter [Auswahl Modi im Windows Forms DataGridView-Steuer](selection-modes-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-109">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="2c9b6-110">So erhalten Sie die aktuelle Zelle Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="2c9b6-110">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="2c9b6-111">Verwenden Sie die <xref:System.Windows.Forms.DataGridView> -Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> .</span><span class="sxs-lookup"><span data-stu-id="2c9b6-111">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="2c9b6-112">So legen Sie die aktuelle Zelle Programm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="2c9b6-112">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="2c9b6-113">Legen Sie die- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft des-Steuer Elements fest <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="2c9b6-113">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2c9b6-114">Im folgenden Codebeispiel wird die aktuelle Zelle auf Zeile 0, Spalte 1, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-114">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c9b6-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2c9b6-115">Compiling the Code</span></span>  
 <span data-ttu-id="2c9b6-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2c9b6-116">This example requires:</span></span>  
  
- <span data-ttu-id="2c9b6-117"><xref:System.Windows.Forms.Button>Steuerelemente mit dem Namen `getCurrentCellButton` und `setCurrentCellButton` .</span><span class="sxs-lookup"><span data-stu-id="2c9b6-117"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="2c9b6-118">In Visual c# müssen Sie die <xref:System.Windows.Forms.Control.Click> Ereignisse für jede Schaltfläche an den zugeordneten Ereignishandler im Beispielcode anfügen.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-118">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="2c9b6-119">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-119">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="2c9b6-120">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c9b6-120">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9b6-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c9b6-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2c9b6-122">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c9b6-122">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="2c9b6-123">Auswahlmodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c9b6-123">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
