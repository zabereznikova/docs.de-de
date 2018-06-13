---
title: 'Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 0b084d204361764af1b36b154acfc5b360fc977e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521717"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements
In manchen Fällen sollten Sie einen Befehl, der ausgeführt wird auf das Steuerelement bereitstellen, auf dem derzeit aktiven untergeordneten Formular den Fokus besitzt. Nehmen Sie z. B. an, dass Sie den ausgewählten Text aus dem Textfeld des untergeordneten Formulars in die Zwischenablage kopieren möchten. Erstellen Sie eine Prozedur, die ausgewählten Text in die Zwischenablage verwenden kopiert die <xref:System.Windows.Forms.Control.Click> -Ereignis des Menüelements kopieren im Standardmenü bearbeiten.  
  
 Da eine MDI-Anwendung viele Instanzen des gleichen untergeordneten Formulars verfügen kann, muss die Prozedur wissen, welches Formular verwendet. Um das richtige Format anzugeben, verwenden Sie die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> -Eigenschaft, die das untergeordnete Formular zurückgibt, die den Fokus besitzt, oder, die zuletzt aktiv war.  
  
 Wenn Sie mehrere Steuerelemente in einem Formular verfügen, müssen Sie auch angeben, welches Steuerelement aktiv ist. Wie die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> -Eigenschaft, die <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> Eigenschaft gibt das Steuerelement mit Fokus auf das aktive untergeordnete Formular. Das folgende Verfahren veranschaulicht eine Kopierprozedur, die von einem Menü untergeordnete Formular eines Menüs für MDI-Formulars oder einer Symbolleisten-Schaltfläche aufgerufen werden kann.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Bestimmen von aktiven untergeordneten MDI-Fensters (um den Text in die Zwischenablage zu kopieren)  
  
1.  Kopieren Sie den Text, der das zum aktiven Steuerelement des aktiven untergeordneten Formulars innerhalb einer Methode in die Zwischenablage.  
  
    > [!NOTE]
    >  In diesem Beispiel wird vorausgesetzt, es ist ein übergeordnetes MDI-Formular (`Form1`), besitzt eine oder mehrere untergeordnete MDI-Fenster mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement. Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [MDI-Anwendungen (Multiple Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Gewusst wie: Anordnen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
