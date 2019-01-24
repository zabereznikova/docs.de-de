---
title: 'Vorgehensweise: Ausblenden des Steuerelements zur Laufzeit'
ms.date: 03/30/2017
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
ms.openlocfilehash: 00f352e0b2c0582c45710f7e5a26e68ab7fbd944
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597791"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="ba835-102">Vorgehensweise: Ausblenden des Steuerelements zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ba835-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="ba835-103">Es gibt Situationen, wenn Sie möchten möglicherweise ein Benutzersteuerelement zu erstellen, die zur Laufzeit nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="ba835-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="ba835-104">Beispielsweise, ein Steuerelement, das einen Wecker ist möglicherweise nicht sichtbar, außer wenn der Wecker klingelt wurde.</span><span class="sxs-lookup"><span data-stu-id="ba835-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="ba835-105">Dies erfolgt einfach durch Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ba835-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="ba835-106">Wenn die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft `true`, das Steuerelement wird normal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba835-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="ba835-107">Wenn `false`, das Steuerelement ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba835-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="ba835-108">Obwohl Code in das Steuerelement beim unsichtbar weiterhin ausgeführt werden kann, werden Sie nicht über die Benutzeroberfläche mit dem Steuerelement interagieren können.</span><span class="sxs-lookup"><span data-stu-id="ba835-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="ba835-109">Wenn Sie ein Steuerelement zu erstellen, das immer noch auf Benutzereingaben (z. B. Mausklicks) reagiert möchten, sollten Sie transparentes Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba835-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="ba835-110">Weitere Informationen finden Sie unter [Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="ba835-110">For more information, see [Giving Your Control a Transparent Background](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="ba835-111">Um das Steuerelement zur Laufzeit unsichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="ba835-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="ba835-112">Legen Sie die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="ba835-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ba835-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba835-113">See also</span></span>
- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="ba835-114">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ba835-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="ba835-115">Vorgehensweise: Fügen Sie dem Steuerelement einen transparenten Hintergrund</span><span class="sxs-lookup"><span data-stu-id="ba835-115">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
