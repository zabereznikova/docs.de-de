---
title: 'Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: 0a7a2475891488d1fdd60f0db4a483c144a73f0d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947847"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element
Im Kontext von [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)müssen häufig Daten an das aktive untergeordnete Fenster gesendet werden, z. b., wenn der Benutzerdaten aus der Zwischenablage in eine MDI-Anwendung einfügt.  
  
> [!NOTE]
> Informationen zum Überprüfen, welches untergeordnete Fenster den Fokus besitzt und seinen Inhalt in die Zwischenablage sendet, finden Sie unter [bestimmen des aktiven untergeordneten MDI](how-to-determine-the-active-mdi-child.md)-Elements.  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>So senden Sie Daten aus der Zwischenablage an das aktive untergeordnete MDI-Fenster  
  
1. Kopieren Sie den Text in der Zwischenablage in eine Methode in das aktive Steuerelement des aktiven untergeordneten Formulars.  
  
    > [!NOTE]
    > In diesem Beispiel wird davon ausgegangen, dass ein übergeordnetes`Form1`MDI-Formular () vorhanden ist, das mindestens ein <xref:System.Windows.Forms.RichTextBox> untergeordnetes MDI-Fenster mit einem-Steuerelement Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md).  
  
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

- [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)
- [Vorgehensweise: Übergeordnete MDI-Formulare erstellen](how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](how-to-create-mdi-child-forms.md)
- [Vorgehensweise: Festlegen des aktiven untergeordneten MDI-Elements](how-to-determine-the-active-mdi-child.md)
- [Vorgehensweise: Untergeordnete MDI-Formulare anordnen](how-to-arrange-mdi-child-forms.md)
