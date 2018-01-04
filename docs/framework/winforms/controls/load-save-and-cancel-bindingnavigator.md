---
title: "Gewusst wie: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms"
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
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dd45b33fb1f99c280e126b9e601692a85da5dba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="59d1f-102">Gewusst wie: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="59d1f-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="59d1f-103">Die <xref:System.Windows.Forms.BindingNavigator> Steuerelement ist eine zweckgebundene <xref:System.Windows.Forms.ToolStrip> Steuerelement, das zum Navigieren und Bearbeiten von Steuerelementen auf dem Formular, das an Daten gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="59d1f-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="59d1f-104">Da es ist ein <xref:System.Windows.Forms.ToolStrip> -Steuerelement, die <xref:System.Windows.Forms.BindingNavigator> Komponente kann problemlos geändert werden, um zusätzliche oder andere Befehle für den Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="59d1f-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="59d1f-105">Im folgenden Verfahren ein <xref:System.Windows.Forms.TextBox> -Steuerelement an Daten gebunden ist und die <xref:System.Windows.Forms.ToolStrip> dem Formular hinzugefügten Steuerelemente zum Laden, speichern und Abbrechen (Schaltflächen) geändert wird.</span><span class="sxs-lookup"><span data-stu-id="59d1f-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="59d1f-106">Zum Hinzufügen laden, speichern und Abbrechen (Schaltflächen) an das BindingNavigator-Komponente</span><span class="sxs-lookup"><span data-stu-id="59d1f-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="59d1f-107">Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="59d1f-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="59d1f-108">Binden Sie es an eine <xref:System.Windows.Forms.BindingSource>, die an eine Datenquelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="59d1f-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="59d1f-109">In diesem Beispiel die <xref:System.Windows.Forms.BindingSource> an eine Datenbank gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="59d1f-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="59d1f-110">Nachdem das Dataset und der Tabellenadapter generiert wurden, ziehen Sie ein <xref:System.Windows.Forms.BindingNavigator> Steuerelement dem Formular.</span><span class="sxs-lookup"><span data-stu-id="59d1f-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="59d1f-111">Legen Sie die <xref:System.Windows.Forms.BindingNavigator> des Steuerelements <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> Eigenschaft, um die <xref:System.Windows.Forms.BindingSource> auf das Formular, das an die Steuerelemente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="59d1f-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="59d1f-112">Wählen Sie das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="59d1f-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="59d1f-113">Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) daher die **BindingNavigator Aufgaben** Dialogfeld wird angezeigt, und wählen Sie **ElementeBearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="59d1f-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="59d1f-114">Die **-Elementauflistungs-Editor** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="59d1f-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="59d1f-115">In der **-Elementauflistungs-Editor**, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="59d1f-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="59d1f-116">Hinzufügen einer <xref:System.Windows.Forms.ToolStripSeparator> und drei <xref:System.Windows.Forms.ToolStripButton> Elemente durch Auswählen des entsprechenden <xref:System.Windows.Forms.ToolStripItem> und klicken Sie auf die **hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="59d1f-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="59d1f-117">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Name%2A> Eigenschaft der Schaltflächen auf**LoadButton**,**SaveButton**, und**CancelButton**bzw.</span><span class="sxs-lookup"><span data-stu-id="59d1f-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to**LoadButton**,**SaveButton**, and**CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="59d1f-118">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft der Schaltflächen auf**laden** `,` **speichern**, und**"Abbrechen"**.</span><span class="sxs-lookup"><span data-stu-id="59d1f-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to**Load**`,` **Save**, and**Cancel**.</span></span>  
  
    4.  <span data-ttu-id="59d1f-119">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Eigenschaft für die einzelnen Schaltflächen, um**Text**.</span><span class="sxs-lookup"><span data-stu-id="59d1f-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to**Text**.</span></span> <span data-ttu-id="59d1f-120">Alternativ können Sie diese Eigenschaft festlegen, um**Image**oder**ImageAndText**festlegen und das Bild angezeigt werden die <xref:System.Windows.Forms.ToolStripItem.Image%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="59d1f-120">Alternatively, you can set this property to**Image**or**ImageAndText**and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="59d1f-121">Klicken Sie auf **OK** um das Dialogfeld zu schließen. Die Schaltflächen werden hinzugefügt, um die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="59d1f-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="59d1f-122">Mit der rechten Maustaste in des Formulars, und wählen Sie **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="59d1f-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="59d1f-123">Suchen Sie im Code-Editor die Zeile des Codes, die Daten in der Tabellenadapter lädt.</span><span class="sxs-lookup"><span data-stu-id="59d1f-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="59d1f-124">Dieser Code generiert wurde, beim Einrichten der Datenbindung in Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="59d1f-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="59d1f-125">Der Code sollte ähnlich der folgenden sein: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="59d1f-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="59d1f-126">Es werden die meisten werden wahrscheinlich in der Form <xref:System.Windows.Forms.Form.Load> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="59d1f-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="59d1f-127">Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die**laden** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und verschieben Sie diesen Code Laden von Daten in.</span><span class="sxs-lookup"><span data-stu-id="59d1f-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Load**<xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="59d1f-128">Der Code sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="59d1f-128">Your code should now look similar to the following:</span></span>  
  
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
  
11. <span data-ttu-id="59d1f-129">Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die **speichern** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Schreiben Sie Code zum Aktualisieren der Daten innerhalb der Tabelle das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="59d1f-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
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
    >  <span data-ttu-id="59d1f-130">In einigen Fällen die <xref:System.Windows.Forms.BindingNavigator> Komponente müssen bereits ein**speichern** Schaltfläche aber keinen Code von Windows Forms-Designer generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="59d1f-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a**Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="59d1f-131">In diesem Fall können Sie im vorangehenden Code Platzieren der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignishandler für diese Schaltfläche, statt eine völlig neue Schaltfläche zu erstellen, auf die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="59d1f-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="59d1f-132">Allerdings die Schaltfläche "" ist standardmäßig deaktiviert, daher Sie festlegen müssen, die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft der Schaltfläche auf `true` haben Sie die Schaltfläche Funktion ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="59d1f-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>  
  
12. <span data-ttu-id="59d1f-133">Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die**"Abbrechen"** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Code schreiben, um alle Änderungen an den Datensatz "Abbrechen", der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="59d1f-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Cancel**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
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
    >  <span data-ttu-id="59d1f-134">Die <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Methode auf die Datenzeile begrenzt.</span><span class="sxs-lookup"><span data-stu-id="59d1f-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="59d1f-135">Speichern Sie alle Änderungen, die Sie vornehmen, während dieser einzelnen Datensätze vor dem Navigieren zu den nächsten Datensatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="59d1f-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d1f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59d1f-136">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="59d1f-137">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="59d1f-137">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="59d1f-138">Übersicht über die BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="59d1f-138">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
