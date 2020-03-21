---
title: Festlegen einer Schaltfläche als Annahmeschaltfläche
ms.date: 03/30/2017
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
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142146"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="66508-102">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="66508-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="66508-103">In jedem Windows-Formular können <xref:System.Windows.Forms.Button> Sie ein Steuerelement als Annahmeschaltfläche festlegen, die auch als Standardschaltfläche bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="66508-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="66508-104">Wenn der Benutzer die ENTER-Taste drückt, wird auf die Standardschaltfläche geklickt, unabhängig davon, welches andere Steuerelement im Formular den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="66508-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66508-105">Ausnahmen sind, wenn das Steuerelement mit Fokus eine andere Schaltfläche ist – in diesem Fall wird auf die Schaltfläche mit dem Fokus geklickt – oder auf ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das die ENTER-Taste abfängt.</span><span class="sxs-lookup"><span data-stu-id="66508-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="66508-106">So legen Sie die Schaltfläche "Akzeptieren" fest</span><span class="sxs-lookup"><span data-stu-id="66508-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="66508-107">Legen Sie die <xref:System.Windows.Forms.Form.AcceptButton%2A> Eigenschaft des <xref:System.Windows.Forms.Button> Formulars auf das entsprechende Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="66508-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66508-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66508-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="66508-109">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="66508-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="66508-110">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66508-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="66508-111">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66508-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="66508-112">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="66508-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="66508-113">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="66508-113">Button Control</span></span>](button-control-windows-forms.md)
