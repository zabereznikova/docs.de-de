---
title: 'Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms'
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
ms.openlocfilehash: d75d96f8db216ab78e13ba5f8409ea5aa535d685
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192692"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a><span data-ttu-id="e94e3-102">Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e94e3-102">How to: Create a Multipane User Interface with Windows Forms</span></span>
<span data-ttu-id="e94e3-103">Im folgenden Verfahren erstellen Sie eine multipane-Benutzeroberfläche, die der ähnelt der Verwendung in Microsoft Outlook ist eine **Ordner** Liste eine **Nachrichten** Bereich und eine **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="e94e3-103">In the following procedure, you will create a multipane user interface that is similar to the one used in Microsoft Outlook, with a **Folder** list, a **Messages** pane, and a **Preview** pane.</span></span> <span data-ttu-id="e94e3-104">In dieser Anordnung erfolgt hauptsächlich durch Andocken von Steuerelementen mit dem Formular.</span><span class="sxs-lookup"><span data-stu-id="e94e3-104">This arrangement is achieved chiefly through docking controls with the form.</span></span>  
  
 <span data-ttu-id="e94e3-105">Wenn Sie ein Steuerelement andocken, legen Sie fest, welchen Rand des übergeordneten Containers ein Steuerelement angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="e94e3-105">When you dock a control, you determine which edge of the parent container a control is fastened to.</span></span> <span data-ttu-id="e94e3-106">Folglich setzen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Right>, dem rechten Rand des Steuerelements an den rechten Rand seines übergeordneten Steuerelements angedockt wird.</span><span class="sxs-lookup"><span data-stu-id="e94e3-106">Thus, if you set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Right>, the right edge of the control will be docked to the right edge of its parent control.</span></span> <span data-ttu-id="e94e3-107">Darüber hinaus wird der verankerte Rand des Steuerelements Größe des Containersteuerelements entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e94e3-107">Additionally, the docked edge of the control is resized to match that of its container control.</span></span> <span data-ttu-id="e94e3-108">Weitere Informationen zur Funktionsweise des <xref:System.Windows.Forms.SplitContainer.Dock%2A> -Eigenschaft funktioniert, finden Sie unter [Vorgehensweise: Andocken von Steuerelementen in Windows Forms](how-to-dock-controls-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e94e3-108">For more information about how the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property works, see [How to: Dock Controls on Windows Forms](how-to-dock-controls-on-windows-forms.md).</span></span>  
  
 <span data-ttu-id="e94e3-109">Dieses Verfahren konzentriert sich auf die Anordnung der <xref:System.Windows.Forms.SplitContainer> und andere Steuerelemente auf dem Formular und nicht zum Hinzufügen von Funktionen, die Anwendung, die Microsoft Outlook nachahmen soll.</span><span class="sxs-lookup"><span data-stu-id="e94e3-109">This procedure focuses on arranging the <xref:System.Windows.Forms.SplitContainer> and the other controls on the form, not on adding functionality to make the application mimic Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="e94e3-110">Um diese Benutzeroberfläche zu erstellen, platzieren Sie alle Steuerelemente innerhalb einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement, das enthält eine <xref:System.Windows.Forms.TreeView> Steuerelement im linken Bereich.</span><span class="sxs-lookup"><span data-stu-id="e94e3-110">To create this user interface, you place all the controls within a <xref:System.Windows.Forms.SplitContainer> control, which contains a <xref:System.Windows.Forms.TreeView> control in the left-hand panel.</span></span> <span data-ttu-id="e94e3-111">Der rechte Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement enthält eine zweite <xref:System.Windows.Forms.SplitContainer> steuern Sie mit einer <xref:System.Windows.Forms.ListView> -Steuerelement über eine <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e94e3-111">The right-hand panel of the <xref:System.Windows.Forms.SplitContainer> control contains a second <xref:System.Windows.Forms.SplitContainer> control with a <xref:System.Windows.Forms.ListView> control above a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="e94e3-112">Diese <xref:System.Windows.Forms.SplitContainer> Steuerelemente ermöglichen unabhängigen Ändern der Größe der anderen Steuerelemente im Formular.</span><span class="sxs-lookup"><span data-stu-id="e94e3-112">These <xref:System.Windows.Forms.SplitContainer> controls enable independent resizing of the other controls on the form.</span></span> <span data-ttu-id="e94e3-113">Sie können die Verfahren in diesem Verfahren zum Erstellen benutzerdefinierter Benutzeroberflächen selbst anpassen.</span><span class="sxs-lookup"><span data-stu-id="e94e3-113">You can adapt the techniques in this procedure to craft custom user interfaces of your own.</span></span>  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a><span data-ttu-id="e94e3-114">So erstellen Sie programmgesteuert eine Outlook-Stil-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="e94e3-114">To create an Outlook-style user interface programmatically</span></span>  
  
1.  <span data-ttu-id="e94e3-115">Deklarieren Sie innerhalb eines Formulars jedes Steuerelement, das die Benutzeroberfläche besteht.</span><span class="sxs-lookup"><span data-stu-id="e94e3-115">Within a form, declare each control that comprises your user interface.</span></span> <span data-ttu-id="e94e3-116">In diesem Beispiel verwenden Sie die <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, und <xref:System.Windows.Forms.RichTextBox> Steuerelemente, um die Microsoft Outlook-Benutzeroberfläche zu imitieren.</span><span class="sxs-lookup"><span data-stu-id="e94e3-116">For this example, use the <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, and <xref:System.Windows.Forms.RichTextBox> controls to mimic the Microsoft Outlook user interface.</span></span>  
  
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
  
2.  <span data-ttu-id="e94e3-117">Erstellen Sie eine Prozedur, die Benutzeroberfläche definiert.</span><span class="sxs-lookup"><span data-stu-id="e94e3-117">Create a procedure that defines your user interface.</span></span> <span data-ttu-id="e94e3-118">Der folgende Code legt die Eigenschaften fest, sodass das Formular die Benutzeroberfläche in Microsoft Outlook ähnelt.</span><span class="sxs-lookup"><span data-stu-id="e94e3-118">The following code sets the properties so that the form will resemble the user interface in Microsoft Outlook.</span></span> <span data-ttu-id="e94e3-119">Es ist jedoch mithilfe von anderen Steuerelementen, oder sie anders andocken, andere Benutzeroberflächen zu erstellen, die gleichermaßen flexibles sind genauso einfach.</span><span class="sxs-lookup"><span data-stu-id="e94e3-119">However, by using other controls or docking them differently, it is just as easy to create other user interfaces that are equally flexible.</span></span>  
  
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
  
3.  <span data-ttu-id="e94e3-120">Fügen Sie in Visual Basic einen Aufruf an die Prozedur, die Sie gerade erstellt, in haben der `New()` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="e94e3-120">In Visual Basic, add a call to the procedure you just created in the `New()` procedure.</span></span> <span data-ttu-id="e94e3-121">In visuellen C#, fügen Sie diese Zeile des Codes, an den Konstruktor für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="e94e3-121">In Visual C#, add this line of code to the constructor for the form class.</span></span>  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e94e3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e94e3-122">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="e94e3-123">SplitContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e94e3-123">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
- [<span data-ttu-id="e94e3-124">Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="e94e3-124">How to: Create a Multipane User Interface with Windows Forms Using the Designer</span></span>](create-a-multipane-user-interface-with-wf-using-the-designer.md)
