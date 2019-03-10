---
title: 'Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: 4db424b27af09dcb7def0051fba070fe9ccf0491
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721969"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms
Im folgenden Verfahren erstellen Sie eine multipane-Benutzeroberfläche, die der ähnelt der Verwendung in Microsoft Outlook ist eine **Ordner** Liste eine **Nachrichten** Bereich und eine **Vorschau** Bereich. In dieser Anordnung erfolgt hauptsächlich durch Andocken von Steuerelementen mit dem Formular.  
  
 Wenn Sie ein Steuerelement andocken, legen Sie fest, welchen Rand des übergeordneten Containers ein Steuerelement angedockt ist. Folglich setzen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Right>, dem rechten Rand des Steuerelements an den rechten Rand seines übergeordneten Steuerelements angedockt wird. Darüber hinaus wird der verankerte Rand des Steuerelements Größe des Containersteuerelements entsprechen. Weitere Informationen zur Funktionsweise des <xref:System.Windows.Forms.SplitContainer.Dock%2A> -Eigenschaft funktioniert, finden Sie unter [Vorgehensweise: Andocken von Steuerelementen in Windows Forms](how-to-dock-controls-on-windows-forms.md).  
  
 Dieses Verfahren konzentriert sich auf die Anordnung der <xref:System.Windows.Forms.SplitContainer> und andere Steuerelemente auf dem Formular und nicht zum Hinzufügen von Funktionen, die Anwendung, die Microsoft Outlook nachahmen soll.  
  
 Um diese Benutzeroberfläche zu erstellen, platzieren Sie alle Steuerelemente innerhalb einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement, das enthält eine <xref:System.Windows.Forms.TreeView> Steuerelement im linken Bereich. Der rechte Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement enthält eine zweite <xref:System.Windows.Forms.SplitContainer> steuern Sie mit einer <xref:System.Windows.Forms.ListView> -Steuerelement über eine <xref:System.Windows.Forms.RichTextBox> Steuerelement. Diese <xref:System.Windows.Forms.SplitContainer> Steuerelemente ermöglichen unabhängigen Ändern der Größe der anderen Steuerelemente im Formular. Sie können die Verfahren in diesem Verfahren zum Erstellen benutzerdefinierter Benutzeroberflächen selbst anpassen.  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>So erstellen Sie programmgesteuert eine Outlook-Stil-Benutzeroberfläche  
  
1.  Deklarieren Sie innerhalb eines Formulars jedes Steuerelement, das die Benutzeroberfläche besteht. In diesem Beispiel verwenden Sie die <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, und <xref:System.Windows.Forms.RichTextBox> Steuerelemente, um die Microsoft Outlook-Benutzeroberfläche zu imitieren.  
  
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
  
2.  Erstellen Sie eine Prozedur, die Benutzeroberfläche definiert. Der folgende Code legt die Eigenschaften fest, sodass das Formular die Benutzeroberfläche in Microsoft Outlook ähnelt. Es ist jedoch mithilfe von anderen Steuerelementen, oder sie anders andocken, andere Benutzeroberflächen zu erstellen, die gleichermaßen flexibles sind genauso einfach.  
  
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
  
3.  Fügen Sie in Visual Basic einen Aufruf an die Prozedur, die Sie gerade erstellt, in haben der `New()` Verfahren. In visuellen C#, fügen Sie diese Zeile des Codes, an den Konstruktor für die Klasse.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer-Steuerelement](splitcontainer-control-windows-forms.md)
- [Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers](create-a-multipane-user-interface-with-wf-using-the-designer.md)
