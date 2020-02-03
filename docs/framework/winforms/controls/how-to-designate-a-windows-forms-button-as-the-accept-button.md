---
title: Festlegen einer Schaltfläche als "annehmen"-Schaltfläche
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
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743268"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche
In jedem Windows-Formular können Sie ein <xref:System.Windows.Forms.Button> Steuerelement als Accept-Schaltfläche festlegen, das auch als Standard Schaltfläche bezeichnet wird. Wenn der Benutzer die EINGABETASTE drückt, wird die Standard Schaltfläche unabhängig davon, welches andere Steuerelement im Formular den Fokus besitzt, angeklickt.  
  
> [!NOTE]
> Dies gilt auch, wenn das Steuerelement mit dem Fokus eine andere Schaltfläche ist – in diesem Fall wird auf die Schaltfläche mit dem Fokus geklickt – oder ein mehrzeilige Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE fängt.  
  
### <a name="to-designate-the-accept-button"></a>So bestimmen Sie die Accept-Schaltfläche  
  
1. Legen Sie die <xref:System.Windows.Forms.Form.AcceptButton%2A>-Eigenschaft des Formulars auf das entsprechende <xref:System.Windows.Forms.Button> Steuerelement fest.  
  
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
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Gewusst wie: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Button-Steuerelement](button-control-windows-forms.md)
