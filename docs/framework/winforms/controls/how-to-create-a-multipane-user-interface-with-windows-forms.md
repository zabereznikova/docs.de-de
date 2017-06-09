---
title: "Gewusst wie: Erstellen einer Multipane-Benutzeroberfl&#228;che mit Windows&#160;Forms | Microsoft Docs"
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
  - "ListView-Steuerelement [Windows Forms], Beispiele"
  - "Panel-Steuerelement [Windows Forms], Beispiele"
  - "RichTextBox-Steuerelement [Windows Forms], Beispiele"
  - "SplitContainer-Steuerelement [Windows Forms], Beispiele"
  - "Splitter-Steuerelement [Windows Forms], Beispiele"
  - "TreeView-Steuerelement [Windows Forms], Beispiele"
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Gewusst wie: Erstellen einer Multipane-Benutzeroberfl&#228;che mit Windows&#160;Forms
Mit folgenden Schritten erstellen Sie eine Benutzeroberfläche mit mehreren Bereichen, die der in Microsoft Outlook ähnelt und eine Liste **Ordner**, einen Bereich **Nachrichten** und einen Bereich **Vorschau** bietet.  Diese Anordnung wird hauptsächlich durch Andocken von Steuerelementen an das Formular erreicht.  
  
 Wenn Sie ein Steuerelement andocken, bestimmen Sie, auf welcher Seite des übergeordneten Containers ein Steuerelement angedockt wird.  Wenn Sie also die <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> festlegen, wird der rechte Rand des Steuerelements an den rechten Rand des übergeordneten Steuerelements angedockt.  Zusätzlich wird die Größe des angedockten Randes des Steuerelements an die Größe des übergeordneten Steuerelements angepasst.  Weitere Informationen über die Funktionsweise der <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft finden Sie unter [Gewusst wie: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Dieses Vorgehen dient in erster Linie zum Anordnen des <xref:System.Windows.Forms.SplitContainer> und anderer Steuerelemente im Formular und nicht zum Hinzufügen von Funktionalität, mit der die Anwendung Microsoft Outlook nachahmen soll.  
  
 Zum Erstellen dieser Benutzeroberfläche müssen Sie alle Steuerelemente innerhalb eines <xref:System.Windows.Forms.SplitContainer>\-Steuerelements anordnen, das im linken Bereich ein <xref:System.Windows.Forms.TreeView>\-Steuerelement enthält.  Der rechte Bereich des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements enthält ein zweites <xref:System.Windows.Forms.SplitContainer>\-Steuerelement mit einem <xref:System.Windows.Forms.ListView>\-Steuerelement über einem <xref:System.Windows.Forms.RichTextBox>\-Steuerelement.  Diese <xref:System.Windows.Forms.SplitContainer>\-Steuerelemente aktivieren unabhängige Größenanpassungen der anderen Steuerelemente im Formular.  Sie können die Techniken dieser Prozedur anpassen, um eigene Benutzeroberflächen zu entwerfen.  
  
### So erstellen Sie programmgesteuert eine Benutzeroberfläche im Outlook\-Design  
  
1.  Deklarieren Sie innerhalb eines Formulars alle Steuerelemente, aus denen die Benutzeroberfläche besteht.  Verwenden Sie beispielsweise die Steuerelemente <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer> und <xref:System.Windows.Forms.RichTextBox>, um die Microsoft Outlook\-Benutzeroberfläche nachzuahmen.  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
  
    ```  
  
2.  Erstellen Sie eine Prozedur, die die Benutzeroberfläche definiert.  Der folgende Code legt die Eigenschaften so fest, dass das Formular der Benutzeroberfläche in Microsoft Outlook ähnelt.  Wenn Sie jedoch andere Steuerelemente verwenden oder sie anders andocken, können Sie ebenso leicht andere Benutzeroberflächen entwickeln, die genauso flexibel sind.  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
  
    ```  
  
3.  Fügen Sie in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] der Prozedur, die Sie soeben in der `New()`\-Prozedur erstellt haben, einen Aufruf hinzu.  Fügen Sie in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] diese Codezeile dem Konstruktor für die Formularklasse hinzu.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer\-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [Gewusst wie: Erstellen einer Multipane\-Benutzeroberfläche mit Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)