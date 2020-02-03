---
title: Binden von Objekten an DataGridView-Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: d5aa5cb64c7fb2b82d69d6c87134ee901b84f5c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746702"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="a25dc-102">Gewusst wie: Binden von Objekten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a25dc-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="a25dc-103">Im folgenden Codebeispiel wird gezeigt, wie eine Auflistung von Objekten so an ein <xref:System.Windows.Forms.DataGridView>-Steuerelement gebunden wird, dass jedes Objekt als eine separate Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a25dc-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="a25dc-104">Das Beispiel zeigt darüber hinaus, wie eine Eigenschaft mit einem Enumerationstyp in einer <xref:System.Windows.Forms.DataGridViewComboBoxColumn> angezeigt wird, sodass die Dropdownliste des Kombinationsfelds die Enumerationswerte enthält.</span><span class="sxs-lookup"><span data-stu-id="a25dc-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a25dc-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a25dc-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a25dc-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a25dc-106">Compiling the Code</span></span>  
 <span data-ttu-id="a25dc-107">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a25dc-107">This example requires:</span></span>  
  
- <span data-ttu-id="a25dc-108">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="a25dc-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25dc-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a25dc-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a25dc-110">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a25dc-110">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a25dc-111">Vorgehensweise: Aufrufen von Objekten, die an DataGridView-Zeilen in Windows Forms gebunden sind</span><span class="sxs-lookup"><span data-stu-id="a25dc-111">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
