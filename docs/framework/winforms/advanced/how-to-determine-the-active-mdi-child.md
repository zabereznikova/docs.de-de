---
title: "Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Untergeordnete Formulare"
  - "Zwischenablage, Kopieren von Daten nach"
  - "MDI, Aktivieren von Formularen"
  - "MDI, Untergeordnete Fenster"
  - "MDI, Suchen nach Fokus"
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements
Es kann durchaus vorkommen, dass Sie einen Befehl bereitstellen möchten, der auf das Steuerelement angewendet wird, das im aktuell aktiven untergeordneten Formular fokussiert ist.  Nehmen wir an, dass markierter Text aus dem Textfeld des untergeordneten Formulars in die Zwischenablage kopiert werden soll.  Hierfür wird in der Regel eine Prozedur erstellt, durch die markierter Text über das <xref:System.Windows.Forms.Control.Click>\-Ereignis des Menüelements Kopieren im Standardmenü Bearbeiten in die Zwischenablage kopiert wird.  
  
 Da eine MDI\-Anwendung viele Instanzen desselben untergeordneten Formulars verwenden kann, muss der Prozedur mitgeteilt werden, welches Formular verwendet werden soll.  Verwenden Sie zum Angeben des richtigen Formulars die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A>\-Eigenschaft, die das untergeordnete Formular zurückgibt, das fokussiert ist oder zuletzt aktiv war.  
  
 Wenn in einem Formular mehrere Steuerelemente verwendet werden, muss auch angegeben werden, welches Steuerelement aktiv ist.  Wie bei der <xref:System.Windows.Forms.Form.ActiveMdiChild%2A>\-Eigenschaft wird von der <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A>\-Eigenschaft das Steuerelement zurückgegeben, das im aktiven untergeordneten Formular fokussiert ist.  Mit der folgenden Prozedur wird eine Kopierprozedur veranschaulicht, die von einem Menü eines untergeordneten Formulars, einem Menü im MDI\-Formular oder einer Symbolleisten\-Schaltfläche aufgerufen werden kann.  
  
### So bestimmen Sie das aktive untergeordnete MDI\-Element, um seinen Text in die Zwischenablage zu kopieren  
  
1.  Kopieren Sie bei einer Methode den Text des aktiven Steuerelements des aktiven untergeordneten Formulars in die Zwischenablage.  
  
    > [!NOTE]
    >  In diesem Beispiel wird vorausgesetzt, dass ein übergeordnetes MDI\-Formular \(`Form1`\) vorhanden ist. Dieses soll ein oder mehrere untergeordnete MDI\-Fenster aufweisen, in denen ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement enthalten ist.  Weitere Informationen finden Sie unter [Erstellen übergeordneter MDI\-Formulare](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
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
  
## Siehe auch  
 [MDI\-Anwendungen \(Multiple Document Interface\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Gewusst wie: Erstellen von übergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Gewusst wie: Erstellen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Gewusst wie: Senden von Daten an das aktive untergeordnete MDI\-Element](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [Gewusst wie: Anordnen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)