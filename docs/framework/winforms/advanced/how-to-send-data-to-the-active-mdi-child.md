---
title: 'Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element'
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
ms.openlocfilehash: 563be8494cb84dc74b45985d3ba74e4b6a07eb8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182493"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element
Häufig müssen Sie im Kontext von [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)Daten an das aktive untergeordnete Fenster senden, z. B. wenn der Benutzer Daten aus der Zwischenablage in eine MDI-Anwendung einfügt.  
  
> [!NOTE]
> Informationen zum Überprüfen des untergeordneten Fensters und senden des Inhalts an die Zwischenablage finden Sie unter [Bestimmen des aktiven MDI-Untergeordneten](how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>So senden Sie Daten aus der Zwischenablage an das aktive untergeordnete MDI-Fenster  
  
1. Kopieren Sie innerhalb einer Methode den Text in der Zwischenablage in das aktive Steuerelement des aktiven untergeordneten Formulars.  
  
    > [!NOTE]
    > In diesem Beispiel wird davon ausgegangen, dass es ein übergeordnetes MDI-Formular (`Form1`) gibt, das über ein oder mehrere untergeordnete MDI-Fenster verfügt, die ein <xref:System.Windows.Forms.RichTextBox> Steuerelement enthalten. Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md).  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)
- [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md)
- [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](how-to-create-mdi-child-forms.md)
- [Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements](how-to-determine-the-active-mdi-child.md)
- [Gewusst wie: Anordnen von untergeordneten MDI-Formularen](how-to-arrange-mdi-child-forms.md)
