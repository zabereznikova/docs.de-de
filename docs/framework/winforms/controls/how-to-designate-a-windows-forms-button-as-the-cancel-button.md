---
title: Festlegen einer Schaltfläche als Schaltfläche "Abbrechen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743264"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="f69f0-102">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="f69f0-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="f69f0-103">In jedem Windows-Formular können Sie ein <xref:System.Windows.Forms.Button>-Steuerelement als Schaltfläche "Abbrechen" festlegen.</span><span class="sxs-lookup"><span data-stu-id="f69f0-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="f69f0-104">Wenn der Benutzer die ESC-Taste drückt, wird auf eine Schaltfläche Abbrechen geklickt, unabhängig davon, welches andere Steuerelement im Formular den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="f69f0-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="f69f0-105">Eine solche Schaltfläche wird in der Regel so programmiert, dass der Benutzer schnell einen Vorgang beenden kann, ohne dass eine Aktion ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="f69f0-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="f69f0-106">So bestimmen Sie die Schaltfläche Abbrechen</span><span class="sxs-lookup"><span data-stu-id="f69f0-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="f69f0-107">Legen Sie die <xref:System.Windows.Forms.Form.CancelButton%2A>-Eigenschaft des Formulars auf das entsprechende <xref:System.Windows.Forms.Button> Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="f69f0-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f69f0-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f69f0-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="f69f0-109">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f69f0-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="f69f0-110">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f0-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="f69f0-111">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f0-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="f69f0-112">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="f69f0-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="f69f0-113">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f69f0-113">Button Control</span></span>](button-control-windows-forms.md)
