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
ms.openlocfilehash: f8eacea0d21159d30d48e48be3093ddf8ca3d7d7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722382"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche
Auf jedem Windows-Formular, Sie können festlegen, eine <xref:System.Windows.Forms.Button> Steuerelement die Schaltfläche "Abbrechen". Schaltfläche "Abbrechen" geklickt wird, wenn der Benutzer die ESC-Taste drückt, unabhängig davon, die welche anderen Formular auf das Steuerelement den Fokus besitzt. Eine solche Schaltfläche programmiert wird in der Regel dem Benutzer ermöglichen, schnell einen Vorgang beendet, ohne dass eine Aktion.  
  
### <a name="to-designate-the-cancel-button"></a>Um die Schaltfläche "Abbrechen" zu kennzeichnen.  
  
1.  Festlegen des Formulars <xref:System.Windows.Forms.Form.CancelButton%2A> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.Button> Steuerelement.  
  
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
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt](how-to-respond-to-windows-forms-button-clicks.md)
- [Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Button-Steuerelement](button-control-windows-forms.md)
