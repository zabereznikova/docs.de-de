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
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche
In jedem Windows-Formular können <xref:System.Windows.Forms.Button> Sie ein Steuerelement als Annahmeschaltfläche festlegen, die auch als Standardschaltfläche bezeichnet wird. Wenn der Benutzer die ENTER-Taste drückt, wird auf die Standardschaltfläche geklickt, unabhängig davon, welches andere Steuerelement im Formular den Fokus hat.  
  
> [!NOTE]
> Ausnahmen sind, wenn das Steuerelement mit Fokus eine andere Schaltfläche ist – in diesem Fall wird auf die Schaltfläche mit dem Fokus geklickt – oder auf ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das die ENTER-Taste abfängt.  
  
### <a name="to-designate-the-accept-button"></a>So legen Sie die Schaltfläche "Akzeptieren" fest  
  
1. Legen Sie die <xref:System.Windows.Forms.Form.AcceptButton%2A> Eigenschaft des <xref:System.Windows.Forms.Button> Formulars auf das entsprechende Steuerelement fest.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Button-Steuerelement](button-control-windows-forms.md)
