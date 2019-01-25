---
title: 'Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 74d025677682735fc7f1c68116b2364887f0519c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701468"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="b87bb-102">Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b87bb-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="b87bb-103">Auf jedem Windows-Formular, Sie können festlegen, eine <xref:System.Windows.Forms.Button> Steuerelement die Schaltfläche "Abbrechen".</span><span class="sxs-lookup"><span data-stu-id="b87bb-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="b87bb-104">Schaltfläche "Abbrechen" geklickt wird, wenn der Benutzer die ESC-Taste drückt, unabhängig davon, die welche anderen Formular auf das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="b87bb-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="b87bb-105">Eine solche Schaltfläche programmiert wird in der Regel dem Benutzer ermöglichen, schnell einen Vorgang beendet, ohne dass eine Aktion.</span><span class="sxs-lookup"><span data-stu-id="b87bb-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="b87bb-106">Um die Schaltfläche "Abbrechen" zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="b87bb-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="b87bb-107">Festlegen des Formulars <xref:System.Windows.Forms.Form.CancelButton%2A> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b87bb-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b87bb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b87bb-108">See also</span></span>
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="b87bb-109">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b87bb-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="b87bb-110">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b87bb-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="b87bb-111">Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt</span><span class="sxs-lookup"><span data-stu-id="b87bb-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="b87bb-112">Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b87bb-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="b87bb-113">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b87bb-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
