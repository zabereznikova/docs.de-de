---
title: 'Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7f505d68bfd6d8c65104244f9583fd3cf975dd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element
Häufig innerhalb des Kontexts [Multiple Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), müssen Sie zum Senden von Daten an das aktive untergeordnete Fenster, z. B. wenn der Benutzer Daten aus der Zwischenablage in eine MDI-Anwendung eingefügt.  
  
> [!NOTE]
>  Weitere Informationen zu überprüfen, welche untergeordnetes Fenster den Fokus besitzt, und senden seinen Inhalt in die Zwischenablage, finden Sie unter [bestimmen von aktiven untergeordneten MDI-Fensters](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Um Daten an das aktive untergeordnete MDI-Fenster aus der Zwischenablage zu senden.  
  
1.  Innerhalb einer Methode kopieren Sie den Text in der Zwischenablage in das aktive Steuerelement des aktiven untergeordneten Formulars ein.  
  
    > [!NOTE]
    >  In diesem Beispiel wird vorausgesetzt, es ist ein übergeordnetes MDI-Formular (`Form1`), besitzt eine oder mehrere untergeordnete MDI-Fenster mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement. Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
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
 [Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Gewusst wie: Anordnen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
