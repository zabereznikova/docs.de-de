---
title: "Gewusst wie: Anh&#228;ngen eines MenuStrip an ein &#252;bergeordnetes MDI-Fenster (Windows Forms) | Microsoft Docs"
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
  - "MDI, Zusammenführen von Menüelementen"
  - "MenuStrip-Steuerelement [Windows Forms], Anhängen"
  - "MenuStrip-Steuerelement [Windows Forms], Zusammenführen"
ms.assetid: ab70c936-b452-4653-b417-17be57bb795b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Anh&#228;ngen eines MenuStrip an ein &#252;bergeordnetes MDI-Fenster (Windows Forms)
In einigen Anwendungen kann sich die Art eines untergeordneten MDI\-Fensters \(Multiple\-Document Interface\) von der des übergeordneten MDI\-Fensters unterscheiden.  Beispielsweise könnte das übergeordnete MDI\-Fenster eine Kalkulationstabelle und das untergeordnete MDI\-Fenster ein Diagramm enthalten.  In diesem Fall möchten Sie möglicherweise den Inhalt des Menüs des übergeordneten MDI\-Fensters mit dem Inhalt des Menüs des untergeordneten MDI\-Fensters aktualisieren, da untergeordnete MDI\-Fenster unterschiedlicher Arten aktiviert werden.  
  
 Im folgenden Verfahren werden die Eigenschaften <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> verwendet, um das Menü des untergeordneten MDI\-Fensters an das Menü des übergeordneten MDI\-Fensters anzuhängen.  Wird das untergeordnete MDI\-Fensters geschlossen, wird das angefügte Menü aus dem übergeordneten MDI\-Fenster entfernt.  
  
 Weitere Informationen finden Sie unter [MDI\-Anwendungen \(Multiple Document Interface\)](http://msdn.microsoft.com/library/xyhh2e7e\(v=vs.110\)).  
  
### So fügen Sie ein Menüelement an ein übergeordnetes MDI\-Fenster an  
  
1.  Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>\-Eigenschaft auf `true` fest.  
  
2.  Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>\-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest  
  
3.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A>\-Eigenschaft von `Form1`<xref:System.Windows.Forms.MenuStrip> auf `false` fest.  
  
4.  Fügen Sie ein Menüelement der obersten Ebene zu `Form1`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft auf `&File` fest.  
  
5.  Fügen Sie dem `&File`\-Menüelement ein Untermenüelement hinzu, und legen Sie dessen <xref:System.Windows.Forms.Form.Text%2A>\-Eigenschaft auf `&Open` fest.  
  
6.  Fügen Sie dem Projekt ein Formular hinzu, fügen Sie dem Formular ein <xref:System.Windows.Forms.MenuStrip> hinzu, und legen die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>\-Eigenschaft von `Form2`<xref:System.Windows.Forms.MenuStrip> auf `true` fest.  
  
7.  Fügen Sie ein Menüelement der obersten Ebene zu `Form2`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Form.Text%2A>\-Eigenschaft auf `&Special` fest.  
  
8.  Fügen Sie dem `&Special`\-Menüelement zwei Untermenüelemente hinzu, und legen Sie deren <xref:System.Windows.Forms.Form.Text%2A>\-Eigenschaften auf `Command&1` bzw. `Command&2` fest.  
  
9. Legen Sie die <xref:System.Windows.Forms.MergeAction>\-Eigenschaft der Menüelemente `&Special`, `Command&1` und `Command&2` auf <xref:System.Windows.Forms.MergeAction> fest.  
  
10. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>\-Ereignis von `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Fügen Sie im Ereignishandler Code ein, der dem folgenden Codebeispiel ähnelt, um neue Instanzen von `Form2` als untergeordnete MDI\-Fenster von `Form1` zu erstellen und anzuzeigen.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
  
    ```  
  
     \[C\#\]  
  
    ```  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
12. Fügen Sie Code, der dem folgenden Codebeispiel ähnelt, in `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> ein, um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
  
    ```  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Zwei <xref:System.Windows.Forms.Form>\-Steuerelemente namens `Form1` und `Form2`.  
  
-   Ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.