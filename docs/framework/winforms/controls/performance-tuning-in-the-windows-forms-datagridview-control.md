---
title: Leistungsoptimierung im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744273"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="02d4d-102">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4d-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="02d4d-103">Beim Arbeiten mit großen Datenmengen kann das `DataGridView`-Steuerelement eine große Menge an Arbeitsspeicher beanspruchen, es sei denn, Sie verwenden es sorgfältig.</span><span class="sxs-lookup"><span data-stu-id="02d4d-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="02d4d-104">Auf Clients mit eingeschränktem Arbeitsspeicher können Sie einen Teil dieses Aufwands vermeiden, indem Sie Features vermeiden, die hohe Arbeitsspeicher Kosten haben.</span><span class="sxs-lookup"><span data-stu-id="02d4d-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="02d4d-105">Sie können auch einige oder alle Aufgaben zur Daten Wartung und-Abruf selbst verwalten, indem Sie den virtuellen Modus verwenden, um die Speicherauslastung für Ihr Szenario anzupassen.</span><span class="sxs-lookup"><span data-stu-id="02d4d-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02d4d-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="02d4d-106">In This Section</span></span>  
 [<span data-ttu-id="02d4d-107">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4d-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="02d4d-108">Beschreibt, wie Sie das `DataGridView`-Steuerelement auf eine Weise verwenden können, die unnötige Speicherauslastung und Leistungseinbußen bei der Arbeit mit großen Datenmengen vermeidet.</span><span class="sxs-lookup"><span data-stu-id="02d4d-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="02d4d-109">Virtueller Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4d-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="02d4d-110">Beschreibt, wie Sie den virtuellen Modus verwenden, um den standardmäßigen Daten Bindungs Mechanismus zu ergänzen oder zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="02d4d-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="02d4d-111">Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4d-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="02d4d-112">Beschreibt das Implementieren von Handlern für mehrere Ereignisse im virtuellen Modus.</span><span class="sxs-lookup"><span data-stu-id="02d4d-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="02d4d-113">Außerdem wird veranschaulicht, wie ein Rollback auf Zeilenebene implementiert und ein Commit für Benutzer bearbeitvorgänge ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="02d4d-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="02d4d-114">Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4d-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="02d4d-115">Beschreibt, wie Daten bei Bedarf geladen werden. Dies ist nützlich, wenn Sie mehr Daten anzeigen müssen, als der verfügbare Client Speicher speichern kann.</span><span class="sxs-lookup"><span data-stu-id="02d4d-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="02d4d-116">Verweis</span><span class="sxs-lookup"><span data-stu-id="02d4d-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="02d4d-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="02d4d-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="02d4d-118">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="02d4d-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d4d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02d4d-119">See also</span></span>

- [<span data-ttu-id="02d4d-120">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="02d4d-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="02d4d-121">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4d-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
