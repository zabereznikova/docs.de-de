---
title: "Übersicht über das Button-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e04b99c9d85ae92ad4d013abc01c5b16914fe1c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="button-control-overview-windows-forms"></a><span data-ttu-id="3325a-102">Übersicht über das Button-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3325a-102">Button Control Overview (Windows Forms)</span></span>
<span data-ttu-id="3325a-103">Das Windows Forms <xref:System.Windows.Forms.Button>-Steuerelement ermöglicht es dem Benutzer, durch Klicken eine Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3325a-103">The Windows Forms <xref:System.Windows.Forms.Button> control allows the user to click it to perform an action.</span></span> <span data-ttu-id="3325a-104">Wenn der Benutzer auf die Schaltfläche klickt, wird sie als gedrückt bzw. nicht gedrückt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3325a-104">When the button is clicked, it looks as if it is being pushed in and released.</span></span> <span data-ttu-id="3325a-105">Sobald der Benutzer eine Schaltfläche klickt der <xref:System.Windows.Forms.Control.Click> -Ereignishandler wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3325a-105">Whenever the user clicks a button, the <xref:System.Windows.Forms.Control.Click> event handler is invoked.</span></span> <span data-ttu-id="3325a-106">Sie fügen Sie Code in die <xref:System.Windows.Forms.Control.Click> Ereignishandler zum Ausführen aller Aktionen Wählen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="3325a-106">You place code in the <xref:System.Windows.Forms.Control.Click> event handler to perform any action you choose.</span></span>  
  
 <span data-ttu-id="3325a-107">Auf der Schaltfläche angezeigte Text ist Bestandteil der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3325a-107">The text displayed on the button is contained in the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="3325a-108">Wenn der Text die Breite der Schaltfläche überschreitet, wird es in die nächste Zeile umbrochen.</span><span class="sxs-lookup"><span data-stu-id="3325a-108">If your text exceeds the width of the button, it will wrap to the next line.</span></span> <span data-ttu-id="3325a-109">Allerdings wird es abgeschnitten, wenn das Steuerelement nicht die gesamte Höhe aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="3325a-109">However, it will be clipped if the control cannot accommodate its overall height.</span></span> <span data-ttu-id="3325a-110">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen der Text, die durch ein Windows Forms-Steuerelement angezeigt](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="3325a-110">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span> <span data-ttu-id="3325a-111">Die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft kann eine Zugriffstaste, die einem Benutzer ermöglicht, das Steuerelement "klicken", durch Drücken der ALT-Taste durch den Zugriffsschlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="3325a-111">The <xref:System.Windows.Forms.Control.Text%2A> property can contain an access key, which allows a user to "click" the control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="3325a-112">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3325a-112">For details, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span> <span data-ttu-id="3325a-113">Die Darstellung des Texts wird gesteuert, indem Sie die <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft und die <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3325a-113">The appearance of the text is controlled by the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> property.</span></span>  
  
 <span data-ttu-id="3325a-114">Die <xref:System.Windows.Forms.Button> -Steuerelement kann auch Bilder mit Anzeigen der <xref:System.Windows.Forms.ButtonBase.Image%2A> und <xref:System.Windows.Forms.ButtonBase.ImageList%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3325a-114">The <xref:System.Windows.Forms.Button> control can also display images using the <xref:System.Windows.Forms.ButtonBase.Image%2A> and <xref:System.Windows.Forms.ButtonBase.ImageList%2A> properties.</span></span> <span data-ttu-id="3325a-115">Weitere Informationen finden Sie unter [Vorgehensweise: Legen Sie das Bild nicht angezeigt durch ein Windows Forms-Steuerelement](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="3325a-115">For more information, see [How to: Set the Image Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3325a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3325a-116">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="3325a-117">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3325a-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="3325a-118">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3325a-118">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="3325a-119">Gewusst wie: Festlegen eine Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3325a-119">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="3325a-120">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3325a-120">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="3325a-121">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3325a-121">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
