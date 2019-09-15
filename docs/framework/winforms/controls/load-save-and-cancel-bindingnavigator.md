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
ms.openlocfilehash: 2d4867c0bc4feb7b43e15614fc56a3c709cef9e7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991738"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="355ad-102">Vorgehensweise: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="355ad-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="355ad-103"><xref:System.Windows.Forms.BindingNavigator> Das<xref:System.Windows.Forms.ToolStrip> -Steuerelement ist ein spezielles Steuerelement, das zum Navigieren und Bearbeiten von Steuerelementen auf dem Formular gedacht ist, die an Daten gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="355ad-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="355ad-104">Da es sich um <xref:System.Windows.Forms.ToolStrip> ein Steuerelement <xref:System.Windows.Forms.BindingNavigator> handelt, kann die Komponente problemlos geändert werden, um zusätzliche oder Alternative Befehle für den Benutzer einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="355ad-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="355ad-105">In der folgenden Prozedur ist ein <xref:System.Windows.Forms.TextBox> -Steuerelement an Daten gebunden, und <xref:System.Windows.Forms.ToolStrip> das Steuerelement, das dem Formular hinzugefügt wird, wird so geändert, dass es die Schaltflächen laden, speichern und Abbrechen enthält.</span><span class="sxs-lookup"><span data-stu-id="355ad-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="355ad-106">Hinzufügen von Schaltflächen zum Laden, speichern und Abbrechen zur BindingNavigator-Komponente</span><span class="sxs-lookup"><span data-stu-id="355ad-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="355ad-107">Fügen Sie in Visual Studio ein <xref:System.Windows.Forms.TextBox> -Steuerelement zum Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="355ad-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="355ad-108">Binden Sie es an <xref:System.Windows.Forms.BindingSource>eine, die an eine Datenquelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="355ad-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="355ad-109">In diesem Beispiel ist der <xref:System.Windows.Forms.BindingSource> an eine Datenbank gebunden.</span><span class="sxs-lookup"><span data-stu-id="355ad-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="355ad-110">Nachdem das DataSet und der Tabellen Adapter generiert wurden, ziehen <xref:System.Windows.Forms.BindingNavigator> Sie ein-Steuerelement in das Formular.</span><span class="sxs-lookup"><span data-stu-id="355ad-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="355ad-111">Legen Sie <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> die<xref:System.Windows.Forms.BindingSource> -Eigenschaft des-Steuer Elements auf dem Formular fest, das an die Steuerelemente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="355ad-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="355ad-112">Wählen Sie das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="355ad-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="355ad-113">Klicken Sie auf das Smarttagsymbol (![Smarttag Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), damit das Dialogfeld **BindingNavigator-Aufgaben** angezeigt wird, und klicken Sie auf **Elemente bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="355ad-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="355ad-114">Der Elementauflistungs- **Editor** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="355ad-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="355ad-115">Führen Sie im Elementauflistungs- **Editor**die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="355ad-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="355ad-116">Fügen Sie <xref:System.Windows.Forms.ToolStripSeparator> ein und <xref:System.Windows.Forms.ToolStripButton> drei Elemente hinzu, indem Sie den <xref:System.Windows.Forms.ToolStripItem> entsprechenden Typ von auswählen und auf die Schaltfläche **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="355ad-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="355ad-117">Legen Sie <xref:System.Windows.Forms.ToolStripItem.Name%2A> die-Eigenschaft der Schaltflächen auf **loadButton**, **SaveButton**bzw. **CancelButton**fest.</span><span class="sxs-lookup"><span data-stu-id="355ad-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="355ad-118">Legen Sie <xref:System.Windows.Forms.ToolStripItem.Text%2A> die-Eigenschaft der Schaltflächen auf **Laden**, **Speichern**und **Abbrechen**fest.</span><span class="sxs-lookup"><span data-stu-id="355ad-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="355ad-119">Legen Sie <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> die-Eigenschaft für jede der Schaltflächen auf **Text**fest.</span><span class="sxs-lookup"><span data-stu-id="355ad-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="355ad-120">Alternativ können Sie diese Eigenschaft auf **Image** oder **ImageAndText**festlegen und das Bild so festlegen, dass es in der <xref:System.Windows.Forms.ToolStripItem.Image%2A> -Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="355ad-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="355ad-121">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="355ad-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="355ad-122">Die Schaltflächen werden dem <xref:System.Windows.Forms.ToolStrip>hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="355ad-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="355ad-123">Klicken Sie mit der rechten Maustaste, und wählen Sie **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="355ad-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="355ad-124">Suchen Sie im Code-Editor nach der Codezeile, die Daten in den Tabellen Adapter lädt.</span><span class="sxs-lookup"><span data-stu-id="355ad-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="355ad-125">Dieser Code wurde generiert, als Sie die Datenbindung in Schritt 2 eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="355ad-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="355ad-126">Der Code sollte in etwa wie folgt aussehen: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="355ad-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="355ad-127">Sie wird wahrscheinlich im- <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars angezeigt.</span><span class="sxs-lookup"><span data-stu-id="355ad-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="355ad-128">Erstellen Sie einen Ereignishandler für <xref:System.Windows.Forms.ToolStripItem.Click> das-Ereignis der **Last** <xref:System.Windows.Forms.ToolStripButton> , die Sie zuvor erstellt haben, und verschieben Sie diesen datenladencode hinein.</span><span class="sxs-lookup"><span data-stu-id="355ad-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="355ad-129">Der Code sollte nun in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="355ad-129">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="355ad-130">Erstellen Sie einen Ereignishandler für <xref:System.Windows.Forms.ToolStripItem.Click> das-Ereignis der zuvor erstellten **Speicherung** <xref:System.Windows.Forms.ToolStripButton> , und schreiben Sie Code, um die Daten in der Tabelle zu aktualisieren, an die das Steuerelement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="355ad-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="355ad-131">In einigen Fällen verfügt die <xref:System.Windows.Forms.BindingNavigator> Komponente bereits über eine Schaltfläche zum **Speichern** , aber es wurde kein Code vom Windows Forms-Designer generiert.</span><span class="sxs-lookup"><span data-stu-id="355ad-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="355ad-132">In diesem Fall können Sie den vorangehenden Code im <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignishandler für diese Schaltfläche platzieren, anstatt eine völlig neue Schaltfläche in der <xref:System.Windows.Forms.ToolStrip>zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="355ad-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="355ad-133">Die Schaltfläche ist jedoch standardmäßig deaktiviert, sodass Sie die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> -Eigenschaft der Schaltfläche auf `true` festlegen müssen, damit die Schaltfläche ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="355ad-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="355ad-134">Erstellen <xref:System.Windows.Forms.ToolStripItem.Click> <xref:System.Windows.Forms.ToolStripButton> Sie einen Ereignishandler **für das-** Ereignis von, den Sie zuvor erstellt haben, und schreiben Sie Code, um alle Änderungen am angezeigten Daten Satz abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="355ad-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="355ad-135">Die <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> -Methode wird auf die Daten Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="355ad-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="355ad-136">Speichern Sie alle Änderungen, die Sie vornehmen, während Sie den einzelnen Datensatz anzeigen, bevor Sie zum nächsten Datensatz navigieren.</span><span class="sxs-lookup"><span data-stu-id="355ad-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="355ad-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="355ad-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="355ad-138">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="355ad-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="355ad-139">Übersicht über die BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="355ad-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
