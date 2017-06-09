---
title: "Gewusst wie: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmen&#252; (Windows Forms) | Microsoft Docs"
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
  - "Menüelemente, Entfernen aus MDI-Dropdownmenüs"
  - "MenuStrip-Steuerelement [Windows Forms], Zusammenführen"
  - "MenuStrip-Steuerelement [Windows Forms], Entfernen"
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmen&#252; (Windows Forms)
In einigen Anwendungen kann sich die Art eines untergeordneten MDI\-Fensters \(Multiple\-Document Interface\) von der des übergeordneten MDI\-Fensters unterscheiden.  Beispielsweise könnte es sich bei dem übergeordneten MDI\-Fenster um eine Tabellenkalkulation handeln und beim untergeordneten MDI\-Fenster um ein Diagramm.  In diesem Fall sollten Sie den Menüinhalt des übergeordneten MDI\-Fensters mit dem Menüinhalt des untergeordneten MDI\-Fensters aktualisieren, da verschiedene untergeordnete MDI\-Fenster aktiviert werden.  
  
 In der folgenden Prozedur wird mithilfe der Eigenschaften <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> ein Menüelement aus dem Dropdownbereich des übergeordneten MDI\-Fensters entfernt.  Durch Schließen des untergeordneten MDI\-Fensters wird das entfernte Menüelement im übergeordneten MDI\-Fenster wiederhergestellt.  
  
### So entfernen Sie ein MenuStrip\-Element aus einem MDI\-Dropdownmenü  
  
1.  Erstellen Sie ein Formular, und legen Sie seine <xref:System.Windows.Forms.Form.IsMdiContainer%2A>\-Eigenschaft auf `true` fest.  
  
2.  Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>\-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest.  
  
3.  Fügen Sie ein Menüelement der obersten Ebene `Form1`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie die Eigenschaft auf `&File`<xref:System.Windows.Forms.Control.Text%2A> fest.  
  
4.  Fügen Sie drei Untermenüelemente dem `&File`\-Menüelement hinzu, und legen Sie deren <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaften auf `&Open`, `&Import from` und `E&xit` fest.  
  
5.  Fügen Sie zwei Untermenüelemente dem `&Import from`\-Untermenüelement hinzu, und legen Sie deren <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaften auf `&Word` und `&Excel` fest.  
  
6.  Fügen Sie dem Projekt ein Formular hinzu, fügen Sie dem Formular <xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>\-Eigenschaft `Form2``true`zu<xref:System.Windows.Forms.MenuStrip> fest.  
  
7.  Fügen Sie ein Menüelement der obersten Ebene `Form2`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie die Eigenschaft auf `&File`<xref:System.Windows.Forms.ToolStripItem.Text%2A> fest.  
  
8.  Fügen Sie ein `&Import from`\-Untermenüelement dem `&File`\-Menü von `Form2` und ein `&Word`\-Untermenüelement dem `&File`\-Menü hinzu.  
  
9. Legen Sie die <xref:System.Windows.Forms.MergeAction>\-Eigenschaft und die <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>\-Eigenschaft der `Form2`\-Menüelemente wie in der folgenden Tabelle gezeigt fest.  
  
    |Form2\-Menüelement|MergeAction\-Wert|MergeIndex\-Wert|  
    |------------------------|-----------------------|----------------------|  
    |Datei|MatchOnly|\-1|  
    |Importieren aus|MatchOnly|\-1|  
    |Word|Entfernen|\-1|  
  
10. In `Form1`erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>\-Ereignis `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Geben Sie im Ereignishandler mit folgendem Codebeispiel vergleichbaren Code ein, um neue Instanzen von `Form2` als untergeordnete MDI\-Fenster von `Form1` zu erstellen und anzuzeigen.  
  
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
  
12. Platzieren Sie den Code, der dem folgenden Codebeispiel in `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> , um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
  
    ```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Zwei <xref:System.Windows.Forms.Form>\-Steuerelemente mit den Namen `Form1` und `Form2`.  
  
-   Ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement mit dem Namen `menuStrip1` auf `Form1` und ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement mit dem Namen `menuStrip2` auf `Form2`.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 [Gewusst wie: Erstellen von übergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Gewusst wie: Erstellen von untergeordneten MDI\-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)