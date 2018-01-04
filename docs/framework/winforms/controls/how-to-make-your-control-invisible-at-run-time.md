---
title: 'Gewusst wie: Ausblenden des Steuerelements zur Laufzeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e28a682c6f3bfc52a293daebeade960c1875bb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="6beb8-102">Gewusst wie: Ausblenden des Steuerelements zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6beb8-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="6beb8-103">Es gibt Situationen, wenn Sie möchten möglicherweise ein benutzerdefiniertes Steuerelement zu erstellen, die zur Laufzeit nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="6beb8-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="6beb8-104">Ein Steuerelement, das einen Wecker möglicherweise z. B. nicht sichtbar, außer wenn das Warnsignal.</span><span class="sxs-lookup"><span data-stu-id="6beb8-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="6beb8-105">Dies erfolgt einfach durch Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6beb8-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="6beb8-106">Wenn die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft `true`, erscheint das Steuerelement wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="6beb8-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="6beb8-107">Wenn `false`, wird das Steuerelement ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="6beb8-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="6beb8-108">Obwohl Code in das Steuerelement beim unsichtbar weiter ausgeführt werden kann, werden Sie nicht mit dem Steuerelement über die Benutzeroberfläche interagieren können.</span><span class="sxs-lookup"><span data-stu-id="6beb8-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="6beb8-109">Wenn Sie ein Steuerelement erstellen, das weiterhin auf eine Benutzereingabe (z. B. Mausklicks) reagiert möchten, sollten Sie ein transparente Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="6beb8-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="6beb8-110">Weitere Informationen finden Sie unter [Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="6beb8-110">For more information, see [Giving Your Control a Transparent Background](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="6beb8-111">Um das Steuerelement zur Laufzeit unsichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="6beb8-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="6beb8-112">Legen Sie die <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="6beb8-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6beb8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6beb8-113">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [<span data-ttu-id="6beb8-114">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6beb8-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="6beb8-115">Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6beb8-115">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
