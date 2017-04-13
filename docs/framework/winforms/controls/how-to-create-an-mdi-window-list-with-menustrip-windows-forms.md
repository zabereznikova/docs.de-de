---
title: "Gewusst wie: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MDI, Erstellen von Fensterlisten"
  - "MenuStrip-Steuerelement [Windows Forms], Erstellen von Fensterlisten"
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip (Windows Forms)
Mithilfe der MDI \(Multiple\-Document Interface\) können Sie Anwendungen erstellen, die mehrere Dokumente gleichzeitig öffnen und Inhalt von einem Dokument in ein anderes kopieren und einfügen können.  
  
 In dieser Prozedur wird gezeigt, wie eine Liste aller aktiven untergeordneten Formulare im Menü Fenster des übergeordneten Formulars erstellt wird.  
  
### So erstellen Sie eine MDI\-Fensterliste auf einem MenuStrip  
  
1.  Erstellen Sie ein Formular, und legen Sie seine <xref:System.Windows.Forms.Form.IsMdiContainer%2A>\-Eigenschaft auf `true` fest.  
  
2.  Fügen Sie dem Formular einen <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Fügen Sie zwei Menüelemente der obersten Ebene zu <xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie deren <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaften auf `&File` und auf `&Window` fest.  
  
4.  Fügen Sie ein Untermenüelement dem `&File`\-Menüelement hinzu, und legen Sie seine <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaft auf `&Open` fest.  
  
5.  Legen Sie die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>\-Eigenschaft <xref:System.Windows.Forms.MenuStrip><xref:System.Windows.Forms.ToolStripMenuItem>zu `&Window`fest.  
  
6.  Fügen Sie dem Projekt ein Formular hinzu, und fügen Sie diesem das gewünschte Steuerelement hinzu, z. B. erneut <xref:System.Windows.Forms.MenuStrip>.  
  
7.  Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>\-Ereignis `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8.  Geben Sie im Ereignishandler mit folgendem Codebeispiel vergleichbaren Code ein, um neue Instanzen von `Form2` als untergeordnete MDI\-Fenster von `Form1` zu erstellen und anzuzeigen:  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
  
    ```  
  
     \[C\#\]  
  
    ```  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
9. Platzieren Sie Code wie den folgenden in `&New`<xref:System.Windows.Forms.ToolStripMenuItem> , um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
  
    ```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Zwei <xref:System.Windows.Forms.Form>\-Steuerelemente mit den Namen `Form1` und `Form2`.  
  
-   Ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement mit dem Namen `menuStrip1` auf `Form1` und ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement mit dem Namen `menuStrip2` auf `Form2`.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 [Gewusst wie: Erstellen von übergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Gewusst wie: Erstellen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)