---
title: 'Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche'
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
ms.openlocfilehash: a69964b83e9948a844483725616a150234a38c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531939"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche
Auf jedem Windows-Formular, legen Sie eine <xref:System.Windows.Forms.Button> Steuerelement Bestätigungsschaltfläche, auch bekannt als Standardschaltfläche befinden. Wenn der Benutzer die EINGABETASTE drückt, wird die Standardschaltfläche geklickt haben, unabhängig davon, welche anderen Formular auf das Steuerelement den Fokus besitzt.  
  
> [!NOTE]
>  Die Ausnahmen, wenn das Steuerelement den Fokus besitzt eine weitere Schaltfläche ist an diesem – in diesem Fall wird die Schaltfläche mit den Fokus geklickt werden – oder ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE aufgefangen.  
  
### <a name="to-designate-the-accept-button"></a>Die Schaltfläche "Annehmen" festlegen  
  
1.  Richten Sie das Formular <xref:System.Windows.Forms.Form.AcceptButton%2A> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.Button> Steuerelement.  
  
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
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Übersicht über das Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Gewusst wie: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
