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
ms.openlocfilehash: 95958491d624052922df9af37b188b9515480397
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714324"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements
Gelegentlich möchten Sie einen Befehl, der ausgeführt wird auf dem Steuerelement bereitstellen, auf dem derzeit aktiven untergeordneten Formular den Fokus besitzt. Nehmen wir beispielsweise an, dass Sie den markierten Text aus des untergeordneten Formulars-Textfeld in die Zwischenablage kopieren möchten. Erstellen Sie eine Prozedur, die ausgewählten Text in die Zwischenablage mithilfe kopiert die <xref:System.Windows.Forms.Control.Click> Ereignis von der Menübefehl zum Kopieren auf die standardmäßige Menü "Bearbeiten".  
  
 Da MDI-Anwendung viele Instanzen der gleichen untergeordneten Formulars verfügen kann, muss die Prozedur wissen, welches Formular verwendet. Um die richtige Form anzugeben, verwenden die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> -Eigenschaft, wodurch das untergeordnete Formular, das den Fokus besitzt, oder das zuletzt aktiv war.  
  
 Wenn Sie mehrere Steuerelemente in einem Formular haben, müssen Sie auch angeben, welches Steuerelement aktiv ist. Wie die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> -Eigenschaft, die <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> Eigenschaft gibt das Steuerelement mit Fokus auf dem aktiven untergeordneten Formular zurück. Das folgende Verfahren veranschaulicht eine Kopierprozedur, die von einem untergeordneten Formularmenü, ein Menü für das MDI-Formular oder eine Symbolleisten-Schaltfläche aufgerufen werden kann.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Bestimmen des aktive untergeordneten MDI-Fensters (um den Text in die Zwischenablage kopieren)  
  
1.  Kopieren Sie den Text zum aktiven Steuerelement des aktiven untergeordneten Formulars innerhalb einer Methode in die Zwischenablage.  
  
    > [!NOTE]
    >  In diesem Beispiel geht davon aus, es ist ein übergeordnetes MDI-Formular (`Form1`), die eine oder mehrere untergeordnete MDI-Fenster mit wurde ein <xref:System.Windows.Forms.RichTextBox> Steuerelement. Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md).  
  
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
- [Vorgehensweise: Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](how-to-create-mdi-child-forms.md)
- [Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element](how-to-send-data-to-the-active-mdi-child.md)
- [Vorgehensweise: Anordnen von untergeordneten MDI-Formularen](how-to-arrange-mdi-child-forms.md)
