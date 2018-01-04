---
title: "Gewusst wie: Definieren einer Windows Forms-Schaltfläche als \"Annehmen\"-Schaltfläche"
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
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80503cd6fc2fc1c624cdd2aeb1ca3f699ffd9832
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="4a6ab-102">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="4a6ab-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="4a6ab-103">Auf jedem Windows-Formular, legen Sie eine <xref:System.Windows.Forms.Button> Steuerelement Bestätigungsschaltfläche, auch bekannt als Standardschaltfläche befinden.</span><span class="sxs-lookup"><span data-stu-id="4a6ab-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="4a6ab-104">Wenn der Benutzer die EINGABETASTE drückt, wird die Standardschaltfläche geklickt haben, unabhängig davon, welche anderen Formular auf das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="4a6ab-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a6ab-105">Die Ausnahmen, wenn das Steuerelement den Fokus besitzt eine weitere Schaltfläche ist an diesem – in diesem Fall wird die Schaltfläche mit den Fokus geklickt werden – oder ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE aufgefangen.</span><span class="sxs-lookup"><span data-stu-id="4a6ab-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="4a6ab-106">Die Schaltfläche "Annehmen" festlegen</span><span class="sxs-lookup"><span data-stu-id="4a6ab-106">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="4a6ab-107">Richten Sie das Formular <xref:System.Windows.Forms.Form.AcceptButton%2A> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4a6ab-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4a6ab-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a6ab-108">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="4a6ab-109">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4a6ab-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="4a6ab-110">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a6ab-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="4a6ab-111">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a6ab-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="4a6ab-112">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="4a6ab-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [<span data-ttu-id="4a6ab-113">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4a6ab-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
