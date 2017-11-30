---
title: Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 452c55d38a896ec96e0992a4b9826f08dc4caa0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="06b8d-102">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06b8d-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="06b8d-103">Bei der Arbeit mit großen Mengen von Daten, die `DataGridView` Steuerelement nutzen kann eine große Menge an Arbeitsspeicher in Mehraufwand, es sei denn, Sie sorgfältig verwenden.</span><span class="sxs-lookup"><span data-stu-id="06b8d-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="06b8d-104">Auf Clients mit begrenzten Arbeitsspeicher können Sie vermeiden einige dieser Aufwand durch das Vermeiden der Funktionen, die über eine hohe Arbeitsspeicher Kosten.</span><span class="sxs-lookup"><span data-stu-id="06b8d-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="06b8d-105">Darüber hinaus können Sie einige oder alle der Datenwartung verwalten und Aufgaben auf Abruf selbst unter Verwendung des virtuellen Modus vorzunehmen, um die Auslastung des Speichers für Ihr Szenario anzupassen.</span><span class="sxs-lookup"><span data-stu-id="06b8d-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06b8d-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="06b8d-106">In This Section</span></span>  
 [<span data-ttu-id="06b8d-107">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06b8d-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06b8d-108">Beschreibt, wie die `DataGridView` -Steuerelement in einer Weise, die nicht benötigte Arbeitsspeicher nutzungs- und Leistungsdaten Sanktionen wird vermieden, bei der Arbeit mit großen Mengen von Daten.</span><span class="sxs-lookup"><span data-stu-id="06b8d-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="06b8d-109">Virtueller Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06b8d-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06b8d-110">Beschreibt, wie der virtuelle Modus ergänzen oder ersetzen den Standardmechanismus für die Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="06b8d-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="06b8d-111">Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06b8d-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="06b8d-112">Beschreibt, wie Ereignishandler für mehrere Ereignisse des virtuellen Modus implementieren.</span><span class="sxs-lookup"><span data-stu-id="06b8d-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="06b8d-113">Außerdem veranschaulicht, wie auf Zeilenebene Rollback und Commit für die benutzerbearbeitungen implementiert.</span><span class="sxs-lookup"><span data-stu-id="06b8d-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="06b8d-114">Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06b8d-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="06b8d-115">Beschreibt, wie Daten bei Bedarf zu laden, was nützlich ist, wenn weitere Daten, die angezeigt wird, als der verfügbaren Clientnamen-Speicher gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="06b8d-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="06b8d-116">Verweis</span><span class="sxs-lookup"><span data-stu-id="06b8d-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="06b8d-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="06b8d-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="06b8d-118">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="06b8d-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b8d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06b8d-119">See Also</span></span>  
 [<span data-ttu-id="06b8d-120">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="06b8d-120">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="06b8d-121">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06b8d-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
