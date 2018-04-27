---
title: 'Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b53d135a1d019ce20dfc8c5c2c1ba59e5968306e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="844de-102">Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="844de-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="844de-103">Interaktion mit der <xref:System.Windows.Forms.DataGridView> erfordert oft, dass Sie programmgesteuert ermitteln, welche Zelle gerade aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="844de-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="844de-104">Sie müssen möglicherweise auch die aktive Zelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="844de-104">You may also need to change the current cell.</span></span> <span data-ttu-id="844de-105">Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="844de-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="844de-106">Die aktuelle Zelle kann nicht festgelegt werden, in einer Zeile oder Spalte mit seiner <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> -Eigenschaftensatz auf `false`.</span><span class="sxs-lookup"><span data-stu-id="844de-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="844de-107">Je nach den <xref:System.Windows.Forms.DataGridView> Auswahlmodus des Steuerelements, Ändern der aktuellen Zelle können Sie die Auswahl ändern.</span><span class="sxs-lookup"><span data-stu-id="844de-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="844de-108">Weitere Informationen finden Sie unter [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="844de-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="844de-109">Die aktuelle Zelle programmgesteuert abrufen</span><span class="sxs-lookup"><span data-stu-id="844de-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="844de-110">Verwenden der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="844de-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="844de-111">So legen Sie die aktuelle Zelle programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="844de-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="844de-112">Legen Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="844de-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="844de-113">Im folgenden Codebeispiel wird die aktive Zelle 0, Spalte 1 Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="844de-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="844de-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="844de-114">Compiling the Code</span></span>  
 <span data-ttu-id="844de-115">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="844de-115">This example requires:</span></span>  
  
-   <span data-ttu-id="844de-116"><xref:System.Windows.Forms.Button> -Steuerelemente namens `getCurrentCellButton` und `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="844de-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="844de-117">In Visual c# Anfügen muss der <xref:System.Windows.Forms.Control.Click> Ereignisse für jede Schaltfläche an den zugehörigen Ereignishandler im Beispielcode.</span><span class="sxs-lookup"><span data-stu-id="844de-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="844de-118">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="844de-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="844de-119">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="844de-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844de-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="844de-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="844de-121">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="844de-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="844de-122">Auswahlmodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="844de-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
