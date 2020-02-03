---
title: Automatische Generierung von Spalten in einem Daten gebundenen DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 860e640e095537358d2f8778c810aa577e9d7ff0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746232"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="55c41-102">Gewusst wie: Automatisches Generieren von Spalten in einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55c41-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="55c41-103">Im folgenden Codebeispiel wird veranschaulicht, wie Spalten aus einer gebundenen Datenquelle in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="55c41-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="55c41-104">Wenn der <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>-Eigenschafts Wert `true` (Standardeinstellung) ist, wird für jede Spalte in der Datenquellen Tabelle eine <xref:System.Windows.Forms.DataGridViewColumn> erstellt.</span><span class="sxs-lookup"><span data-stu-id="55c41-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="55c41-105">Wenn das <xref:System.Windows.Forms.DataGridView> Steuerelement bereits Spalten enthält, wenn Sie die <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>-Eigenschaft festlegen, werden die vorhandenen gebundenen Spalten mit den Spalten in der Datenquelle verglichen und immer dann beibehalten, wenn eine Entsprechung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="55c41-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="55c41-106">Ungebundene Spalten werden immer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="55c41-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="55c41-107">Gebundene Spalten, für die keine Entsprechung in der Datenquelle vorhanden ist, werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="55c41-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="55c41-108">Spalten in der Datenquelle, für die keine Entsprechung im-Steuerelement vorhanden ist, generieren neue <xref:System.Windows.Forms.DataGridViewColumn>-Objekte, die am Ende der <xref:System.Windows.Forms.DataGridView.Columns%2A> Auflistung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="55c41-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55c41-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55c41-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55c41-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="55c41-110">Compiling the Code</span></span>  
 <span data-ttu-id="55c41-111">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="55c41-111">This example requires:</span></span>  
  
- <span data-ttu-id="55c41-112">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `customersDataGridView`.</span><span class="sxs-lookup"><span data-stu-id="55c41-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
- <span data-ttu-id="55c41-113">Ein <xref:System.Data.DataSet> Objekt mit dem Namen `customersDataSet`, das über eine Tabelle mit dem Namen `Customers`verfügt.</span><span class="sxs-lookup"><span data-stu-id="55c41-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
- <span data-ttu-id="55c41-114">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> und <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="55c41-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c41-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55c41-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="55c41-116">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55c41-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="55c41-117">Gewusst wie: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55c41-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
