---
title: 'Gewusst wie: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: c28d969f9d4976c7432e7293afb13e7f340f7e97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535232"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="76862-102">Gewusst wie: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76862-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="76862-103">Sie können die Dateneingabe bequemer vornehmen, wenn die Anwendung im Standardmodus für neu hinzugefügte Zeilen aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="76862-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="76862-104">Mit der <xref:System.Windows.Forms.DataGridView> -Klasse, Sie können Standardwerte mit der <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="76862-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="76862-105">Dieses Ereignis wird ausgelöst, wenn der Benutzer die Zeile für neue Datensätze eingibt.</span><span class="sxs-lookup"><span data-stu-id="76862-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="76862-106">Wenn Code auf dieses Ereignis verarbeitet, können Sie die gewünschte Zellen mit Werten Ihrer Wahl auffüllen.</span><span class="sxs-lookup"><span data-stu-id="76862-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="76862-107">Im folgenden Codebeispiel wird veranschaulicht, wie an Standardwerte für neue Zeilen, die mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="76862-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76862-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76862-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="76862-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="76862-109">Compiling the Code</span></span>  
 <span data-ttu-id="76862-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="76862-110">This example requires:</span></span>  
  
-   <span data-ttu-id="76862-111">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="76862-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="76862-112">Ein `NewCustomerId` Funktion zum Generieren eindeutiger `CustomerID` Werte.</span><span class="sxs-lookup"><span data-stu-id="76862-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="76862-113">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76862-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76862-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76862-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [<span data-ttu-id="76862-115">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76862-115">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="76862-116">Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76862-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
