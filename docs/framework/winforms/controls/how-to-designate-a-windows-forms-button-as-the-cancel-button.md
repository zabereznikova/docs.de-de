---
title: 'Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 8170190145e76a86f5343bc42b39be7fb9d61a0f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344142"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="0f355-102">Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0f355-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="0f355-103">Auf jedem Windows-Formular, Sie können festlegen, eine <xref:System.Windows.Forms.Button> Steuerelement die Schaltfläche "Abbrechen".</span><span class="sxs-lookup"><span data-stu-id="0f355-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="0f355-104">Schaltfläche "Abbrechen" geklickt wird, wenn der Benutzer die ESC-Taste drückt, unabhängig davon, die welche anderen Formular auf das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0f355-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="0f355-105">Eine solche Schaltfläche programmiert wird in der Regel dem Benutzer ermöglichen, schnell einen Vorgang beendet, ohne dass eine Aktion.</span><span class="sxs-lookup"><span data-stu-id="0f355-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="0f355-106">Um die Schaltfläche "Abbrechen" zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0f355-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="0f355-107">Festlegen des Formulars <xref:System.Windows.Forms.Form.CancelButton%2A> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0f355-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f355-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f355-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="0f355-109">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0f355-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="0f355-110">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f355-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="0f355-111">Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f355-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="0f355-112">Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0f355-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="0f355-113">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0f355-113">Button Control</span></span>](button-control-windows-forms.md)
