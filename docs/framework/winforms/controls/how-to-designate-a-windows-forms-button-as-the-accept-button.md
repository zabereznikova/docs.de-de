---
title: 'Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche'
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
ms.openlocfilehash: 8e608bb2cb4635ef1d29fd7a0aff3ac95fcd9af5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309822"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche
Auf jedem Windows-Formular, Sie können festlegen, eine <xref:System.Windows.Forms.Button> Steuerelement "Annehmen"-Schaltfläche, auch bekannt als die Standardschaltfläche. Wenn der Benutzer die EINGABETASTE drückt, wird die Schaltfläche "Standard" geklickt haben, unabhängig davon, welche anderen Formular auf das Steuerelement den Fokus besitzt.  
  
> [!NOTE]
>  Die Ausnahmen von dieser sind, wenn das Steuerelement mit Fokus auf eine andere Schaltfläche ist – in diesem Fall wird die Schaltfläche mit den Fokus geklickt werden, oder ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das fängt die EINGABETASTE.  
  
### <a name="to-designate-the-accept-button"></a>Festlegen von "Annehmen"-Schaltfläche  
  
1. Festlegen des Formulars <xref:System.Windows.Forms.Form.AcceptButton%2A> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.Button> Steuerelement.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Button-Steuerelement](button-control-windows-forms.md)
