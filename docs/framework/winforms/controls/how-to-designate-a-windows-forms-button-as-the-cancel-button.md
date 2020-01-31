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
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche
In jedem Windows-Formular können Sie ein <xref:System.Windows.Forms.Button>-Steuerelement als Schaltfläche "Abbrechen" festlegen. Wenn der Benutzer die ESC-Taste drückt, wird auf eine Schaltfläche Abbrechen geklickt, unabhängig davon, welches andere Steuerelement im Formular den Fokus besitzt. Eine solche Schaltfläche wird in der Regel so programmiert, dass der Benutzer schnell einen Vorgang beenden kann, ohne dass eine Aktion ausgeführt werden muss.  
  
### <a name="to-designate-the-cancel-button"></a>So bestimmen Sie die Schaltfläche Abbrechen  
  
1. Legen Sie die <xref:System.Windows.Forms.Form.CancelButton%2A>-Eigenschaft des Formulars auf das entsprechende <xref:System.Windows.Forms.Button> Steuerelement fest.  
  
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
- [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Gewusst wie: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Button-Steuerelement](button-control-windows-forms.md)
