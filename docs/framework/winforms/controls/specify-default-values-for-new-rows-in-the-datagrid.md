---
title: 'Vorgehensweise: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 8a90cbef7032fd3753a6c9ec0b856a4e2ea1db27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193693"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2cbd0-102">Vorgehensweise: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cbd0-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2cbd0-103">Sie können die Dateneingabe praktischer vornehmen, wenn die Anwendung im standardmäßigen Werte für neu hinzugefügte Zeilen füllt.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="2cbd0-104">Mit der <xref:System.Windows.Forms.DataGridView> -Klasse, Sie können Standardwerte mit dem <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="2cbd0-105">Dieses Ereignis wird ausgelöst, wenn der Benutzer die Zeile für neue Datensätze eingibt.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="2cbd0-106">Wenn Ihr Code auf dieses Ereignis verarbeitet, können Sie die gewünschte Zellen mit den Werten Ihrer Wahl auffüllen.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="2cbd0-107">Im folgenden Codebeispiel wird veranschaulicht, wie zum Angeben von Standardwerten für neue Zeilen mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cbd0-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cbd0-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2cbd0-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2cbd0-109">Compiling the Code</span></span>  
 <span data-ttu-id="2cbd0-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2cbd0-110">This example requires:</span></span>  
  
-   <span data-ttu-id="2cbd0-111">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="2cbd0-112">Ein `NewCustomerId` Funktion zum Generieren von eindeutigen `CustomerID` Werte.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="2cbd0-113">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2cbd0-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbd0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cbd0-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="2cbd0-115">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cbd0-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2cbd0-116">Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cbd0-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
