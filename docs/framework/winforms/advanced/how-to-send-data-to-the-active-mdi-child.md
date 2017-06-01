---
title: "Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element | Microsoft Docs"
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
  - "Zwischenablage, Abrufen von Daten aus"
  - "Zwischenablage, Einfügen"
  - "MDI, Senden von Daten an Formulare"
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element
Häufig ist es im Kontext von [MDI\-Anwendungen \(Multiple Document Interface\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md) notwendig, Daten an das aktive untergeordnete Fenster zu senden, z. B. wenn ein Benutzer Daten aus der Zwischenablage in eine MDI\-Anwendung einfügt.  
  
> [!NOTE]
>  Weitere Informationen darüber, wie Sie überprüfen, welches untergeordnete Fenster den Fokus hat und wie Sie dessen Inhalt in die Zwischenablage kopieren, finden Sie unter [Bestimmen des aktiven untergeordneten MDI\-Elements](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md).  
  
### So senden Sie Daten aus der Zwischenablage an das aktive untergeordnete MDI\-Fenster  
  
1.  Kopieren Sie bei einer Methode den Text in der Zwischenablage in das aktive Steuerelement des aktiven untergeordneten Formulars.  
  
    > [!NOTE]
    >  In diesem Beispiel wird vorausgesetzt, dass ein übergeordnetes MDI\-Formular \(`Form1`\) vorhanden ist. Dieses soll ein oder mehrere untergeordnete MDI\-Fenster aufweisen, in denen ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement enthalten ist.  Weitere Informationen finden Sie unter [Erstellen übergeordneter MDI\-Formulare](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
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
  
## Siehe auch  
 [MDI\-Anwendungen \(Multiple Document Interface\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Gewusst wie: Erstellen von übergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Gewusst wie: Erstellen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Gewusst wie: Bestimmen des aktiven untergeordneten MDI\-Elements](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Gewusst wie: Anordnen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)