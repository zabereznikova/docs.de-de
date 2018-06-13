---
title: 'Gewusst wie: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: 5117dfe2e017cf4af1d352fdbf23c6599c0e56a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536272"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="2cc81-102">Gewusst wie: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc81-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2cc81-103">Standardmäßig können Benutzer den Inhalt des aktuellen bearbeiten <xref:System.Windows.Forms.DataGridView> Text im Feld Zelle durch darin eingeben oder durch Drücken von F2.</span><span class="sxs-lookup"><span data-stu-id="2cc81-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="2cc81-104">Dies versetzt die Zelle im Bearbeitungsmodus befindet, wenn alle der folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="2cc81-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
-   <span data-ttu-id="2cc81-105">Die zugrunde liegenden Datenquelle unterstützt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2cc81-105">The underlying data source supports editing.</span></span>  
  
-   <span data-ttu-id="2cc81-106">Die <xref:System.Windows.Forms.DataGridView> Steuerelement aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2cc81-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
-   <span data-ttu-id="2cc81-107">Die <xref:System.Windows.Forms.DataGridView.EditMode%2A> -Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="2cc81-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
-   <span data-ttu-id="2cc81-108">Die `ReadOnly` Eigenschaften der Zelle, Zeile, Spalte und Steuerelement sind auf `false`.</span><span class="sxs-lookup"><span data-stu-id="2cc81-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="2cc81-109">Der Benutzer kann in den Bearbeitungsmodus wechseln ändern Sie den Zellenwert und drücken Sie EINGABETASTE, um einen commit der Änderung oder die ESC-Taste, um die Zelle auf den ursprünglichen Wert zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2cc81-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="2cc81-110">Sie können konfigurieren, eine <xref:System.Windows.Forms.DataGridView> steuern, sodass eine Zelle den Bearbeitungsmodus wechselt, sobald er zur aktiven Zelle wird.</span><span class="sxs-lookup"><span data-stu-id="2cc81-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="2cc81-111">Das Verhalten der EINGABETASTE und ESC-Taste wird in diesem Fall nicht geändert, aber die Zelle im Bearbeitungsmodus bleibt, nachdem der Wert übernommen oder zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2cc81-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="2cc81-112">Sie können auch das Steuerelement konfigurieren, sodass Zellen Bearbeitungsmodus nur, wenn Benutzer geben Sie in die Zelle oder nur, wenn Benutzer F2 drücken.</span><span class="sxs-lookup"><span data-stu-id="2cc81-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="2cc81-113">Schließlich können Sie verhindern Zellen in den Bearbeitungsmodus wechselt, außer beim Aufrufen der <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="2cc81-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="2cc81-114">So ändern Sie den Bearbeitungsmodus eines DataGridView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2cc81-114">To change the edit mode of a DataGridView control</span></span>  
  
-   <span data-ttu-id="2cc81-115">Legen Sie die <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.DataGridViewEditMode> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="2cc81-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2cc81-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2cc81-116">Compiling the Code</span></span>  
 <span data-ttu-id="2cc81-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2cc81-117">This example requires:</span></span>  
  
-   <span data-ttu-id="2cc81-118">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="2cc81-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="2cc81-119">Verweise auf die Assemblys <xref:System> und <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="2cc81-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc81-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cc81-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2cc81-121">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc81-121">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
