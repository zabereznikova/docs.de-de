---
title: "Methoden zur Auswahl eines Button-Steuerelements in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b6fa31b89b8fbe50077933cf04aa3c17db86438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="5c830-102">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c830-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="5c830-103">Eine Windows Forms-Schaltfläche kann auf folgende Weise ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="5c830-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="5c830-104">Verwenden Sie eine Maus, um auf die Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="5c830-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="5c830-105">Rufen Sie der Schaltfläche <xref:System.Windows.Forms.Control.Click> Ereignis im Code.</span><span class="sxs-lookup"><span data-stu-id="5c830-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="5c830-106">Verschieben Sie den Fokus auf die Schaltfläche mit den durch Drücken der TAB-Taste, und wählen Sie dann die Schaltfläche mit den durch Drücken der LEERTASTE oder EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5c830-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="5c830-107">Drücken Sie die Zugriffstaste (ALT + unterstrichener Buchstabe) für die Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="5c830-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="5c830-108">Weitere Informationen zu Zugriffstasten finden Sie unter [Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5c830-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="5c830-109">Wenn die Schaltfläche "" die Schaltfläche "Annehmen" des Formulars ist, durch Drücken der EINGABETASTE auswählt, die Schaltfläche "", auch wenn ein anderes Steuerelement den Fokus besitzt, außer wenn andere Steuerelements ist eine weitere Schaltfläche, ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE aufgefangen.</span><span class="sxs-lookup"><span data-stu-id="5c830-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="5c830-110">Ist die Schaltfläche "" auf die Schaltfläche "Abbrechen", des Formulars, wählt das Drücken von ESC die Schaltfläche, auch wenn ein anderes Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="5c830-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="5c830-111">Rufen Sie die <xref:System.Windows.Forms.Button.PerformClick%2A> Methode, um programmgesteuert auf die Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="5c830-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c830-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c830-112">See Also</span></span>  
 [<span data-ttu-id="5c830-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5c830-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="5c830-114">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c830-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="5c830-115">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5c830-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
