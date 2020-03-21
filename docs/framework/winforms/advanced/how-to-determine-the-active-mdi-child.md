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
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182547"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements
Gelegentlich möchten Sie einen Befehl bereitstellen, der auf dem Steuerelement arbeitet, das sich auf das aktuell aktive untergeordnete Formular konzentriert. Angenommen, Sie möchten ausgewählten Text aus dem Textfeld des untergeordneten Formulars in die Zwischenablage kopieren. Sie erstellen eine Prozedur, die ausgewählten Text <xref:System.Windows.Forms.Control.Click> mithilfe des Menüelements Kopieren im Standardmenü Bearbeiten in die Zwischenablage kopiert.  
  
 Da eine MDI-Anwendung viele Instanzen desselben untergeordneten Formulars enthalten kann, muss die Prozedur wissen, welches Formular verwendet werden soll. Um das richtige Formular <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> anzugeben, verwenden Sie die Eigenschaft, die das untergeordnete Formular zurückgibt, das den Fokus hat oder zuletzt aktiv war.  
  
 Wenn Sie über mehrere Steuerelemente in einem Formular verfügen, müssen Sie auch angeben, welches Steuerelement aktiv ist. Wie <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> die Eigenschaft <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> gibt die Eigenschaft das Steuerelement mit dem Fokus auf das aktive untergeordnete Formular zurück. Das folgende Verfahren veranschaulicht eine Kopierprozedur, die über ein untergeordnetes Formularmenü, ein Menü im MDI-Formular oder eine Symbolleistenschaltfläche aufgerufen werden kann.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>So bestimmen Sie das aktive untergeordnete MDI-Element (um seinen Text in die Zwischenablage zu kopieren)  
  
1. Kopieren Sie innerhalb einer Methode den Text des aktiven Steuerelements des aktiven untergeordneten Formulars in die Zwischenablage.  
  
    > [!NOTE]
    > In diesem Beispiel wird davon ausgegangen, dass es ein übergeordnetes MDI-Formular (`Form1`) gibt, das über ein oder mehrere untergeordnete MDI-Fenster verfügt, die ein <xref:System.Windows.Forms.RichTextBox> Steuerelement enthalten. Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md).  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)
- [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md)
- [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](how-to-create-mdi-child-forms.md)
- [Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element](how-to-send-data-to-the-active-mdi-child.md)
- [Gewusst wie: Anordnen von untergeordneten MDI-Formularen](how-to-arrange-mdi-child-forms.md)
