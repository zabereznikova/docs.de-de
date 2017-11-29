---
title: "Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms"
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
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6db621912e76d24b05c8dcdca7f1d3f4e62c2838
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms
Im folgenden Verfahren erstellen Sie eine multipane-Benutzeroberfläche, die mit dem Umwandlungsoperator in Microsoft Outlook mit verwendet wird eine **Ordner** Liste eine **Nachrichten** Bereich und einer **Vorschau** Bereich. In dieser Anordnung erfolgt hauptsächlich durch Andocken von Steuerelementen mit dem Formular.  
  
 Wenn Sie ein Steuerelement andocken, bestimmen Sie, welche Seite des übergeordneten Containers ein Steuerelement angedockt wird. Daher, wenn Sie festlegen, die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Right>, dem rechten Rand des Steuerelements an den rechten Rand am übergeordneten Steuerelement angedockt wird. Darüber hinaus wird der angedockte Rand des Steuerelements Größe des Containersteuerelements entsprechen. Weitere Informationen darüber, wie die <xref:System.Windows.Forms.SplitContainer.Dock%2A> -Eigenschaft funktioniert, finden Sie unter [Vorgehensweise: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Hierin liegt der Schwerpunkt auf Anordnen der <xref:System.Windows.Forms.SplitContainer> und anderer Steuerelemente auf dem Formular und nicht zum Hinzufügen von Funktionen, damit die Anwendung Microsoft Outlook zu imitieren.  
  
 Um diese Benutzeroberfläche zu erstellen, platzieren Sie alle Steuerelemente innerhalb einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement, das enthält eine <xref:System.Windows.Forms.TreeView> Steuerelement im linken Bereich. Der rechte Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement enthält eine zweite <xref:System.Windows.Forms.SplitContainer> -Steuerelement mit einer <xref:System.Windows.Forms.ListView> Steuerelement oben ein <xref:System.Windows.Forms.RichTextBox> Steuerelement. Diese <xref:System.Windows.Forms.SplitContainer> Steuerelemente ermöglichen unabhängigen Ändern der Größe der Steuerelemente im Formular. Sie können die Verfahren in diesem Verfahren zum Erstellen benutzerdefinierter Benutzeroberflächen Ihrer Wahl anpassen.  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>So erstellen Sie programmgesteuert eine Benutzeroberfläche von Outlook-Stil  
  
1.  Deklarieren Sie in ein Formular jedes Steuerelement, das die Benutzeroberfläche besteht aus. In diesem Beispiel verwendet die <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, und <xref:System.Windows.Forms.RichTextBox> Steuerelemente, die Microsoft Outlook-Benutzeroberfläche zu imitieren.  
  
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
  
2.  Erstellen Sie eine Prozedur, die die Benutzeroberfläche definiert. Der folgende Code legt die Eigenschaften fest, sodass das Formular die Benutzeroberfläche in Microsoft Outlook ähnelt. Andere Steuerelemente verwenden oder sie anders andocken, ist es jedoch ebenso leicht andere Benutzeroberflächen zu erstellen, die genauso flexibel sind.  
  
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
  
3.  In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], fügen Sie einen Aufruf an die Prozedur, die Sie gerade erstellt, in haben der `New()` Prozedur. In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], fügen Sie diese Codezeile an den Konstruktor für die Formularklasse hinzu.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)
