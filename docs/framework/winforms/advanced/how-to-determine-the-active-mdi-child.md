---
title: 'Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements'
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
ms.openlocfilehash: 91100b37e4cae9041479b209e40034efe376df5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946217"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements
Gelegentlich möchten Sie einen Befehl bereitstellen, der auf dem Steuerelement mit Fokus auf das momentan aktive untergeordnete Formular basiert. Angenommen, Sie möchten den ausgewählten Text aus dem Textfeld des untergeordneten Formulars in die Zwischenablage kopieren. Erstellen Sie eine Prozedur, die markierten Text in die Zwischenablage kopiert, <xref:System.Windows.Forms.Control.Click> indem Sie das-Ereignis des Menü Elements Kopieren im Standardmenü Bearbeiten verwenden.  
  
 Da eine MDI-Anwendung viele Instanzen desselben untergeordneten Formulars aufweisen kann, muss die Prozedur wissen, welches Formular verwendet werden soll. Um das richtige Formular anzugeben, verwenden Sie <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> die-Eigenschaft, die das untergeordnete Formular zurückgibt, das den Fokus besitzt oder das zuletzt aktiv war.  
  
 Wenn Sie mehrere Steuerelemente auf einem Formular haben, müssen Sie auch angeben, welches Steuerelement aktiv ist. Wie die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> -Eigenschaft gibt <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> die-Eigenschaft das-Steuerelement mit dem Fokus auf das aktive untergeordnete Formular zurück. Im folgenden Verfahren wird eine Kopier Prozedur veranschaulicht, die über ein untergeordnetes Formular Menü, ein Menü auf dem MDI-Formular oder eine Symbolleisten-Schaltfläche aufgerufen werden kann.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>So bestimmen Sie das aktive untergeordnete MDI-Element (um den Text in die Zwischenablage zu kopieren)  
  
1. Kopieren Sie in einer Methode den Text des aktiven Steuer Elements des aktiven untergeordneten Formulars in die Zwischenablage.  
  
    > [!NOTE]
    > In diesem Beispiel wird davon ausgegangen, dass ein übergeordnetes`Form1`MDI-Formular () vorhanden ist, das mindestens ein <xref:System.Windows.Forms.RichTextBox> untergeordnetes MDI-Fenster mit einem-Steuerelement Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md).  
  
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

- [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)
- [Vorgehensweise: Übergeordnete MDI-Formulare erstellen](how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](how-to-create-mdi-child-forms.md)
- [Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element](how-to-send-data-to-the-active-mdi-child.md)
- [Vorgehensweise: Untergeordnete MDI-Formulare anordnen](how-to-arrange-mdi-child-forms.md)
