---
title: 'Vorgehensweise: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: a743cda36a8bf78fafeea94b0c6af8e30c7fe15a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711160"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="91454-102">Vorgehensweise: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91454-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="91454-103">Sie können die Darstellung von <xref:System.Windows.Forms.DataGridView>-Zeilen steuern, indem Sie eines oder beide der Ereignisse <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> und <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> behandeln.</span><span class="sxs-lookup"><span data-stu-id="91454-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="91454-104">Diese Ereignisse sind so konzipiert, dass Sie nur das Gewünschte zeichnen und das <xref:System.Windows.Forms.DataGridView>-Steuerelement den Rest zeichnen lassen.</span><span class="sxs-lookup"><span data-stu-id="91454-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="91454-105">Wenn Sie beispielsweise einen benutzerdefinierten Hintergrund zeichnen möchten, können Sie das <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>-Ereignis behandeln und dafür sorgen, dass einzelne Zellen ihren eigenen Vordergrundinhalt zeichnen.</span><span class="sxs-lookup"><span data-stu-id="91454-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="91454-106">Alternativ können Sie dafür sorgen, dass sich die Zellen selbst zeichnen und in einem Handler des <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>-Ereignisses benutzerdefinierte Vordergrundinhalte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="91454-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="91454-107">Sie können auch das Zeichnen von Zellen deaktivieren und in einem <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>-Ereignishandler alles selbst zeichnen.</span><span class="sxs-lookup"><span data-stu-id="91454-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="91454-108">Im folgende Codebeispiel werden Handler für beide Ereignisse implementiert, um einen Hintergrund mit einer Farbverlaufsauswahl und einige benutzerdefinierte Vordergrundinhalte bereitzustellen, die über mehrere Spalten gehen.</span><span class="sxs-lookup"><span data-stu-id="91454-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91454-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91454-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91454-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="91454-110">Compiling the Code</span></span>  
 <span data-ttu-id="91454-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="91454-111">This example requires:</span></span>  
  
-   <span data-ttu-id="91454-112">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="91454-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="91454-113">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="91454-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="91454-114">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="91454-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="91454-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91454-115">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="91454-116">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91454-116">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="91454-117">Architektur des DataGridView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="91454-117">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
