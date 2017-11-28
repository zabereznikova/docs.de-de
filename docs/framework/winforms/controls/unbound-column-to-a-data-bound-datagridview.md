---
title: "Gewusst wie: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cd6a1494a98d912469f7e45c7751a0a9741ff17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="d77a6-102">Gewusst wie: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d77a6-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d77a6-103">Die Daten, die Sie im <xref:System.Windows.Forms.DataGridView>-Steuerelement anzeigen, stammen normalerweise aus einer Datenquelle einer bestimmten Art, aber möglicherweise möchten Sie eine Spalte mit Daten anzeigen, die nicht aus der Datenquelle stammen.</span><span class="sxs-lookup"><span data-stu-id="d77a6-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="d77a6-104">Diese Art von Spalte wird als ungebundene Spalte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d77a6-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="d77a6-105">Ungebundene Spalten können viele Formen annehmen.</span><span class="sxs-lookup"><span data-stu-id="d77a6-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="d77a6-106">Häufig werden sie verwendet, um Zugriff auf die Details einer Datenzeile bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d77a6-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="d77a6-107">Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer nicht gebundenen Spalte des **Details** Schaltflächen für die Anzeige einer untergeordneten Tabelle im Zusammenhang mit einer bestimmten Zeile in einer übergeordneten Tabelle, wenn Sie eine Master/Detail-Szenario implementieren.</span><span class="sxs-lookup"><span data-stu-id="d77a6-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="d77a6-108">Um auf Klicks auf Schaltflächen zu reagieren, implementieren Sie einen <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>-Ereignishandler, der ein Formular mit der untergeordneten Tabelle anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d77a6-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="d77a6-109">Visual Studio bietet Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="d77a6-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="d77a6-110">Siehe auch [wie: Hinzufügen und Entfernen von Spalten in der Windows Forms DataGridView-Steuerelement mithilfe des Designers](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="d77a6-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))</span></span>  
  
## <a name="example"></a><span data-ttu-id="d77a6-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d77a6-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d77a6-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d77a6-112">Compiling the Code</span></span>  
 <span data-ttu-id="d77a6-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d77a6-113">This example requires:</span></span>  
  
-   <span data-ttu-id="d77a6-114">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="d77a6-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="d77a6-115">Verweise auf die <xref:System?displayProperty=nameWithType>-Assembly und die <xref:System.Windows.Forms?displayProperty=nameWithType>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="d77a6-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d77a6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d77a6-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="d77a6-117">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d77a6-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d77a6-118">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d77a6-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
