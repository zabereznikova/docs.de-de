---
title: 'Gewusst wie: Automatisches Generieren von Spalten in einem datengebundenen DataGridView-Steuerelement in Windows Forms'
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
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1d6a790f8a43f4ea2f9d3ad2cdb282186554da6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="e90f1-102">Gewusst wie: Automatisches Generieren von Spalten in einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e90f1-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e90f1-103">Im folgenden Codebeispiel wird veranschaulicht, wie anzuzeigenden Spalten aus einer gebundenen Datenquelle in einem <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e90f1-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e90f1-104">Wenn die <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> Eigenschaftswert ist `true` (Standard), eine <xref:System.Windows.Forms.DataGridViewColumn> wird für jede Spalte in der Tabelle für die Datenquellensicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="e90f1-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="e90f1-105">Wenn die <xref:System.Windows.Forms.DataGridView> Steuerelement bereits über Spalten verfügt, beim Festlegen der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> -Eigenschaft, die vorhandene Grenze Spalten sind im Vergleich zu den Spalten in der Datenquelle und beibehalten, wenn eine Übereinstimmung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="e90f1-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="e90f1-106">Ungebundene Spalten werden immer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e90f1-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="e90f1-107">Gebundene Spalten für die keine Übereinstimmung in der Datenquelle vorhanden ist, werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="e90f1-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="e90f1-108">Spalten in der Datenquelle, für die keine Übereinstimmung im Steuerelement vorhanden ist, generieren neue <xref:System.Windows.Forms.DataGridViewColumn> Objekte, die am Ende hinzugefügt werden die <xref:System.Windows.Forms.DataGridView.Columns%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e90f1-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e90f1-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e90f1-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e90f1-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e90f1-110">Compiling the Code</span></span>  
 <span data-ttu-id="e90f1-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e90f1-111">This example requires:</span></span>  
  
-   <span data-ttu-id="e90f1-112">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `customersDataGridView`.</span><span class="sxs-lookup"><span data-stu-id="e90f1-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
-   <span data-ttu-id="e90f1-113">Ein <xref:System.Data.DataSet> Objekt mit dem Namen `customersDataSet` , besitzt eine Tabelle namens `Customers`.</span><span class="sxs-lookup"><span data-stu-id="e90f1-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
-   <span data-ttu-id="e90f1-114">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> und <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e90f1-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90f1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e90f1-115">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e90f1-116">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e90f1-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="e90f1-117">Gewusst wie: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e90f1-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)
