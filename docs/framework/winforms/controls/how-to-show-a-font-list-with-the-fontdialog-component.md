---
title: 'Gewusst wie: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente'
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
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 781daeb43a952ef25e73edd577fa17c61b02b426
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>Gewusst wie: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente
Die [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) Komponente ermöglicht Benutzern das Auswählen einer Schriftart sowie deren Anzeige ändern, z. B. Gewichtung und Größe.  
  
 Klicken Sie im Dialogfeld ausgewählte Schriftart wird zurückgegeben, der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft. Daher ist das Nutzen der vom Benutzer ausgewählten Schriftart so einfach wie eine Eigenschaft zu lesen.  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>Auswählen von Schriftarteigenschaften, die mit der FontDialog-Komponente  
  
1.  Anzeigen des Dialogfelds mit den <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
2.  Verwenden der <xref:System.Windows.Forms.DialogResult> -Eigenschaft können Sie bestimmen, wie das Dialogfeld geschlossen wurde.  
  
3.  Verwenden der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft, um die gewünschte Schriftart fest.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler öffnet eine <xref:System.Windows.Forms.FontDialog> Komponente. Wenn eine Schriftart ausgewählt wurde und der Benutzer klickt **OK**, die <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft von einem <xref:System.Windows.Forms.TextBox> Steuerelement, das auf dem Formular auf die ausgewählte Schriftart festgelegt ist. Im Beispiel wird vorausgesetzt, das Formular verfügt über eine <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.TextBox> -Steuerelement, und ein <xref:System.Windows.Forms.FontDialog> Komponente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FontDialog>  
 [FontDialog-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
