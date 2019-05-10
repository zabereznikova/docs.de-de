---
title: 'Vorgehensweise: Ausblenden von Spaltenheadern im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: 888ff59d42f44db652d3188e016b9e10a9590139
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651673"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c24d8-102">Vorgehensweise: Ausblenden von Spaltenheadern im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c24d8-102">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c24d8-103">Manchmal sollten Sie zum Anzeigen einer <xref:System.Windows.Forms.DataGridView> ohne Spaltenheader.</span><span class="sxs-lookup"><span data-stu-id="c24d8-103">Sometimes you will want to display a <xref:System.Windows.Forms.DataGridView> without column headers.</span></span> <span data-ttu-id="c24d8-104">In der <xref:System.Windows.Forms.DataGridView> -Steuerelement, das <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> Eigenschaftswert bestimmt, ob die Spaltenköpfe angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c24d8-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> property value determines whether the column headers are displayed.</span></span>  
  
### <a name="to-hide-the-column-headers"></a><span data-ttu-id="c24d8-105">So blenden Sie die Spaltenüberschriften aus</span><span class="sxs-lookup"><span data-stu-id="c24d8-105">To hide the column headers</span></span>  
  
- <span data-ttu-id="c24d8-106">Legen Sie die <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> -Eigenschaft auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="c24d8-106">Set the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c24d8-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c24d8-107">Compiling the Code</span></span>  
 <span data-ttu-id="c24d8-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c24d8-108">This example requires:</span></span>  
  
- <span data-ttu-id="c24d8-109">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="c24d8-109">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="c24d8-110">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c24d8-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24d8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c24d8-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c24d8-112">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c24d8-112">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
