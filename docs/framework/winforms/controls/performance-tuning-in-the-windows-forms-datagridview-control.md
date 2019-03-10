---
title: Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: d425488adb8569a48333de4f8c0312143029fbe0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703163"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8ab86-102">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ab86-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8ab86-103">Bei der Arbeit mit großen Mengen von Daten, die `DataGridView` Steuerelement kann eine große Menge an Arbeitsspeicher, Aufwand, nutzen, es sei denn, Sie es mit Vorsicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ab86-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="8ab86-104">Auf Clients mit eingeschränktem Arbeitsspeicher können Sie vermeiden einige von diesen zusätzlichen Aufwand durch Funktionen, die eine hohe Arbeitsspeicher, Kosten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="8ab86-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="8ab86-105">Sie können auch verwalten, einige oder alle der Wartung von Daten aus, und Abrufen von Aufgaben selbst unter Verwendung des virtuellen Modus vorzunehmen, um die Auslastung des Speichers für Ihr Szenario anzupassen.</span><span class="sxs-lookup"><span data-stu-id="8ab86-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ab86-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ab86-106">In This Section</span></span>  
 [<span data-ttu-id="8ab86-107">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ab86-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8ab86-108">Beschreibt, wie die `DataGridView` -Steuerelement in einer Weise, die Strafen für nicht benötigte Arbeitsspeicher nutzungs- und Leistungsdaten vermeidet, bei der Arbeit mit großen Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="8ab86-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="8ab86-109">Virtueller Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ab86-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8ab86-110">Beschreibt, wie virtuelle Modus zum ergänzen oder ersetzen den Standardmechanismus für die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ab86-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="8ab86-111">Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ab86-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="8ab86-112">Beschreibt, wie Handler für mehrere Ereignisse des virtuellen Modus implementieren.</span><span class="sxs-lookup"><span data-stu-id="8ab86-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="8ab86-113">Außerdem veranschaulicht, wie auf Zeilenebene Rollback und Commit für die benutzerbearbeitungen implementiert.</span><span class="sxs-lookup"><span data-stu-id="8ab86-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="8ab86-114">Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ab86-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="8ab86-115">Beschreibt, wie zum Laden von Daten bei Bedarf, was nützlich ist, wenn weitere Daten angezeigt werden, als der verfügbare Client-Speicher gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ab86-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8ab86-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="8ab86-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="8ab86-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8ab86-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="8ab86-118">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8ab86-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab86-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ab86-119">See also</span></span>
- [<span data-ttu-id="8ab86-120">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8ab86-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="8ab86-121">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ab86-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
