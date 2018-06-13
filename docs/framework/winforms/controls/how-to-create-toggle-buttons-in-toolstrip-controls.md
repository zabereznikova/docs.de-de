---
title: 'Gewusst wie: Erstellen von Umschaltflächen in ToolStrip-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: a04d531433273328c2d8eb0c5ef614f08c33952a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530379"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="903b3-102">Gewusst wie: Erstellen von Umschaltflächen in ToolStrip-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="903b3-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="903b3-103">Wenn ein Benutzer eine Umschaltfläche klickt, vertieft angezeigt, die abgesenkt beibehalten, bis der Benutzer erneut auf die Schaltfläche klickt.</span><span class="sxs-lookup"><span data-stu-id="903b3-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="903b3-104">So erstellen eine ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="903b3-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="903b3-105">Verwenden Sie Code wie im folgenden Codebeispiel wird ein.</span><span class="sxs-lookup"><span data-stu-id="903b3-105">Use code such as the following code example.</span></span> <span data-ttu-id="903b3-106">Mit diesem Code wird davon ausgegangen, dass das Formular enthält ein <xref:System.Windows.Forms.ToolStrip> -Steuerelement, und dass seine <xref:System.Windows.Forms.ToolStrip.Items%2A> Auflistung enthält ein <xref:System.Windows.Forms.ToolStripButton> aufgerufen `toolStripButton1`.</span><span class="sxs-lookup"><span data-stu-id="903b3-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="903b3-107">Außerdem wird angenommen, dass Sie einen Ereignishandler aufgerufen haben `toolStripButton1_CheckedChanged`.</span><span class="sxs-lookup"><span data-stu-id="903b3-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="903b3-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="903b3-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripButton>  
 [<span data-ttu-id="903b3-109">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="903b3-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
