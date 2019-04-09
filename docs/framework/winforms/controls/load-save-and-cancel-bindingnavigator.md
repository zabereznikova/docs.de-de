---
title: 'Vorgehensweise: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 52d4fc32836a5d20bd99d8ebfd3119c761376e30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098714"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="4c1cc-102">Vorgehensweise: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c1cc-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="4c1cc-103">Die <xref:System.Windows.Forms.BindingNavigator> Steuerelement ist eine zweckgebundene <xref:System.Windows.Forms.ToolStrip> -Steuerelement, das zum Navigieren und Bearbeiten von Steuerelementen im Formular, das an Daten gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="4c1cc-104">Da es ist eine <xref:System.Windows.Forms.ToolStrip> -Steuerelement, das <xref:System.Windows.Forms.BindingNavigator> Komponente kann problemlos geändert werden, um zusätzliche oder andere Befehle für den Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="4c1cc-105">Im folgenden Verfahren eine <xref:System.Windows.Forms.TextBox> -Steuerelement an Daten gebunden ist und die <xref:System.Windows.Forms.ToolStrip> -Steuerelement, das dem Formular hinzugefügt wird geändert, um das Laden, speichern und Abbrechen (Schaltflächen).</span><span class="sxs-lookup"><span data-stu-id="4c1cc-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="4c1cc-106">Zum Hinzufügen laden, speichern und Abbrechen (Schaltflächen) der BindingNavigator-Komponente</span><span class="sxs-lookup"><span data-stu-id="4c1cc-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="4c1cc-107">Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="4c1cc-108">Binden Sie es an eine <xref:System.Windows.Forms.BindingSource>, das an eine Datenquelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="4c1cc-109">In diesem Beispiel die <xref:System.Windows.Forms.BindingSource> an eine Datenbank gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="4c1cc-110">Nachdem die Adapter Dataset und eine Tabelle generiert wurden, ziehen Sie eine <xref:System.Windows.Forms.BindingNavigator> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="4c1cc-111">Legen Sie die <xref:System.Windows.Forms.BindingNavigator> des Steuerelements <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> Eigenschaft, um die <xref:System.Windows.Forms.BindingSource> auf das Formular, das an die Steuerelemente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="4c1cc-112">Wählen Sie das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="4c1cc-113">Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) daher **BindingNavigator-Aufgaben** Dialogfeld wird angezeigt, und wählen Sie **ElementeBearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="4c1cc-114">Die **-Elementauflistungs-Editor** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="4c1cc-115">In der **-Elementauflistungs-Editor**, führen Sie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="4c1cc-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="4c1cc-116">Hinzufügen einer <xref:System.Windows.Forms.ToolStripSeparator> und drei <xref:System.Windows.Forms.ToolStripButton> Elemente nach Auswahl des entsprechenden Typs <xref:System.Windows.Forms.ToolStripItem> und klicken Sie auf die **hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="4c1cc-117">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Name%2A> Eigenschaft die Schaltflächen für die **LoadButton**, **SaveButton**, und **CancelButton**bzw.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="4c1cc-118">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft die Schaltflächen für die **Load**, **speichern**, und **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>  
  
    4.  <span data-ttu-id="4c1cc-119">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> -Eigenschaft für die Schaltflächen um **Text**.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="4c1cc-120">Alternativ können Sie diese Eigenschaft festlegen, um **Image** oder **ImageAndText**, festlegen und das Bild anzuzeigenden der <xref:System.Windows.Forms.ToolStripItem.Image%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="4c1cc-121">Klicken Sie auf **OK** um das Dialogfeld zu schließen. Die Schaltflächen werden hinzugefügt, um die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="4c1cc-122">Mit der rechten Maustaste in des Formulars, und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="4c1cc-123">Suchen Sie im Code-Editor, die Zeile des Codes, der Daten in der Tabellenadapter lädt.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="4c1cc-124">Dieser Code wurde generiert, wenn Sie die Datenbindung in Schritt 2 einrichten.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="4c1cc-125">Der Code sollte ähnlich der folgenden sein: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="4c1cc-126">Die meisten wird voraussichtlich im des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="4c1cc-127">Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis die **Load** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und verschieben Sie diesen Code Laden von Daten in.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="4c1cc-128">Der Code sollte jetzt etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4c1cc-128">Your code should now look similar to the following:</span></span>  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. <span data-ttu-id="4c1cc-129">Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis die **speichern** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Schreiben Sie Code zum Aktualisieren der Daten in der Tabelle das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="4c1cc-130">In einigen Fällen die <xref:System.Windows.Forms.BindingNavigator> Komponente verfügen bereits über eine **speichern** Schaltfläche, aber keinen Code vom Windows Forms-Designer generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a **Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="4c1cc-131">In diesem Fall können Sie in den vorangehenden Code Platzieren der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignishandler für diese Schaltfläche, anstatt eine komplett neue Schaltfläche auf der <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="4c1cc-132">Allerdings die Schaltfläche ist standardmäßig deaktiviert, daher Sie festlegen müssen, die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft der Schaltfläche auf `true` um die Funktion der Schaltfläche richtig zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>
  
12. <span data-ttu-id="4c1cc-133">Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis die **Abbrechen** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Schreiben von Code zum Abbrechen von Änderungen an den Datensatz, der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4c1cc-134">Die <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Methode bezieht sich auf die Zeile der Daten.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="4c1cc-135">Speichern Sie alle Änderungen, die Sie vornehmen, während der Anzeige dieser einzelnen Datensätze vor der Navigation zum nächsten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="4c1cc-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1cc-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c1cc-136">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="4c1cc-137">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4c1cc-137">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="4c1cc-138">Übersicht über die BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="4c1cc-138">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
