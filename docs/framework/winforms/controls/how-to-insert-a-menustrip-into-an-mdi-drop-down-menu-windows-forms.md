---
title: "Gewusst wie: Einf&#252;gen eines MenuStrip in ein MDI-Dropdownmen&#252; (Windows Forms) | Microsoft Docs"
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
  - "MenuStrip-Steuerelement [Windows Forms], Einfügen"
  - "MenuStrip-Steuerelement [Windows Forms], Zusammenführen"
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Einf&#252;gen eines MenuStrip in ein MDI-Dropdownmen&#252; (Windows Forms)
In einigen Anwendungen kann sich die Art eines untergeordneten MDI\-Fensters \(Multiple\-Document Interface\) von der des übergeordneten MDI\-Fensters unterscheiden.  Beispielsweise könnte es sich bei dem übergeordneten MDI\-Fenster um eine Tabellenkalkulation handeln und beim untergeordneten MDI\-Fenster um ein Diagramm.  In diesem Fall sollten Sie den Menüinhalt des übergeordneten MDI\-Fensters mit dem Menüinhalt des untergeordneten MDI\-Fensters aktualisieren, da verschiedene untergeordnete MDI\-Fenster aktiviert werden.  
  
 In der folgenden Prozedur wird mithilfe der Eigenschaften <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> eine Gruppe von Menüelementen aus dem Menü des untergeordneten MDI\-Fensters in das Dropdownmenü des übergeordneten MDI\-Fensters eingefügt.  Durch Schließen des untergeordneten MDI\-Fensters werden die eingefügten Menüelemente aus dem übergeordneten MDI\-Fenster entfernt.  
  
### So fügen Sie einen MenuStrip in ein MDI\-Dropdownmenü ein  
  
1.  Erstellen Sie ein Formular, und legen Sie seine <xref:System.Windows.Forms.Form.IsMdiContainer%2A>\-Eigenschaft auf `true` fest.  
  
2.  Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>\-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest.  
  
3.  Fügen Sie ein Menüelement der obersten Ebene zu `Form1` <xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft auf `&File` fest.  
  
4.  Fügen Sie drei Untermenüelemente dem `&File`\-Menüelement hinzu, und legen Sie deren <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaften auf `&Open`, `&Import from` und `E&xit` fest.  
  
5.  Fügen Sie zwei Untermenüelemente dem `&Import from`\-Untermenüelement hinzu, und legen Sie deren <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaften auf `&Word` und `&Excel` fest.  
  
6.  Fügen Sie dem Projekt ein Formular hinzu, dem Formular einen <xref:System.Windows.Forms.MenuStrip>, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>\-Eigenschaft von `Form2` <xref:System.Windows.Forms.MenuStrip> auf `true` fest.  
  
7.  Fügen Sie ein Menüelement der obersten Ebene zu `Form2` <xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaft auf `&File` fest.  
  
8.  Fügen Sie dem `&File`\-Menü von `Form2` Untermenüelemente in der folgenden Reihenfolge hinzu: ein <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `&Close` `and Save` und ein weiteres <xref:System.Windows.Forms.ToolStripSeparator>.  
  
9. Legen Sie die <xref:System.Windows.Forms.MergeAction>\-Eigenschaft und die <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>\-Eigenschaft der `Form2`\-Menüelemente wie in der folgenden Tabelle gezeigt fest.  
  
    |Form2\-Menüelement|MergeAction\-Wert|MergeIndex\-Wert|  
    |------------------------|-----------------------|----------------------|  
    |Datei|MatchOnly|\-1|  
    |Trennzeichen|Insert|2|  
    |Speichern|Insert|3|  
    |Speichern und schließen|Insert|4|  
    |Trennzeichen|Insert|5|  
  
10. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>\-Ereignis des `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Geben Sie im Ereignishandler mit folgendem Codebeispiel vergleichbaren Code ein, um neue Instanzen von `Form2` als untergeordnete MDI\-Fenster von `Form1` zu erstellen und anzuzeigen.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
12. Platzieren Sie mit folgendem Codebeispiel vergleichbaren Code im `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>, um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
  
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