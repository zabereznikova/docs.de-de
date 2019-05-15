---
title: 'Vorgehensweise: Hinzufügen von ToolStripContainer zu einem Formular'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 3d69bc6ed0cf23da8315ae95565300d151069d51
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582572"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="abaeb-102">Vorgehensweise: Hinzufügen von ToolStripContainer zu einem Formular</span><span class="sxs-lookup"><span data-stu-id="abaeb-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="abaeb-103">Sie können einer Windows Form programmgesteuert einen <xref:System.Windows.Forms.ToolStripContainer> hinzufügen und diesen mit Steuerelementen füllen.</span><span class="sxs-lookup"><span data-stu-id="abaeb-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abaeb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="abaeb-104">Example</span></span>  
 <span data-ttu-id="abaeb-105">Das folgende Codebeispiel zeigt, wie einer Windows Form ein <xref:System.Windows.Forms.ToolStripContainer> und ein <xref:System.Windows.Forms.ToolStrip> hinzugefügt wird, wie dem <xref:System.Windows.Forms.ToolStrip> Elemente hinzugefügt werden und wie der <xref:System.Windows.Forms.ToolStrip> zum <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> des <xref:System.Windows.Forms.ToolStripContainer> hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="abaeb-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="abaeb-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="abaeb-106">Compiling the Code</span></span>  
 <span data-ttu-id="abaeb-107">Für dieses Codebeispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="abaeb-107">This code example requires:</span></span>  
  
- <span data-ttu-id="abaeb-108">Verweise auf die Assemblys "System.Drawing", "System.Text" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="abaeb-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abaeb-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abaeb-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="abaeb-110">ToolStripContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="abaeb-110">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="abaeb-111">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="abaeb-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
