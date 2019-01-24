---
title: 'Vorgehensweise: Binden von Objekten an Windows Forms-DataGridView-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: 0e69e67201d95b912467ccfd74bc5fb08196f11d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614666"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="dcb45-102">Vorgehensweise: Binden von Objekten an Windows Forms-DataGridView-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="dcb45-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="dcb45-103">Im folgenden Codebeispiel wird gezeigt, wie eine Auflistung von Objekten so an ein <xref:System.Windows.Forms.DataGridView>-Steuerelement gebunden wird, dass jedes Objekt als eine separate Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dcb45-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="dcb45-104">Das Beispiel zeigt darüber hinaus, wie eine Eigenschaft mit einem Enumerationstyp in einer <xref:System.Windows.Forms.DataGridViewComboBoxColumn> angezeigt wird, sodass die Dropdownliste des Kombinationsfelds die Enumerationswerte enthält.</span><span class="sxs-lookup"><span data-stu-id="dcb45-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcb45-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dcb45-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dcb45-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="dcb45-106">Compiling the Code</span></span>  
 <span data-ttu-id="dcb45-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dcb45-107">This example requires:</span></span>  
  
-   <span data-ttu-id="dcb45-108">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="dcb45-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="dcb45-109">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="dcb45-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="dcb45-110">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="dcb45-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="dcb45-111">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="dcb45-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb45-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcb45-112">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="dcb45-113">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dcb45-113">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="dcb45-114">Vorgehensweise: Zugreifen auf Objekte an in Windows Forms DataGridView-Zeilen gebunden.</span><span class="sxs-lookup"><span data-stu-id="dcb45-114">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
