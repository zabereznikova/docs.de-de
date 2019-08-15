---
title: 'Vorgehensweise: Erstellen von untergeordneten MDI-Formularen'
ms.date: 03/30/2017
dev_langs:
- CSharp
- CPP
- VB
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: f5e8682caf658d159f044528f040b99676355448
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040111"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="cc7c6-102">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="cc7c6-102">How to: Create MDI child forms</span></span>

<span data-ttu-id="cc7c6-103">Untergeordnete MDI-Formulare sind ein wesentliches Element von [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md), da diese Formen den Mittelpunkt der Benutzerinteraktion bilden.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="cc7c6-104">Im folgenden Verfahren verwenden Sie Visual Studio, um ein untergeordnetes MDI-Formular zu erstellen, in <xref:System.Windows.Forms.RichTextBox> dem ein-Steuerelement ähnlich wie bei den meisten Textverarbeitungsanwendungen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-104">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="cc7c6-105">Indem Sie das <xref:System.Windows.Forms> Steuerelement durch andere Steuerelemente ersetzen, z <xref:System.Windows.Forms.DataGridView> . b. das-Steuerelement oder eine Kombination von Steuerelementen, können Sie untergeordnete MDI-Fenster (und durch Erweiterung MDI-Anwendungen) mit unterschiedlichen Möglichkeiten erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-105">By substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls, you can create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="cc7c6-106">Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="cc7c6-106">Create MDI child forms</span></span>

1. <span data-ttu-id="cc7c6-107">Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-107">Create a new Windows Forms application project in Visual Studio.</span></span> <span data-ttu-id="cc7c6-108">Legen Sie im Fenster **Eigenschaften** für <xref:System.Windows.Forms.Form.IsMdiContainer%2A> das Formular seine-Eigenschaft auf `true` und die `WindowsState` -Eigenschaft auf `Maximized`fest.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-108">In the **Properties** window for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true` and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="cc7c6-109">Dies kennzeichnet das Formular als MDI-Container für untergeordnete Fenster.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-109">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="cc7c6-110">Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der `Toolbox` in das Formular.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-110">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="cc7c6-111">Legen Sie `Text` die-Eigenschaft auf **File**fest.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-111">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="cc7c6-112">Klicken Sie auf die Schaltfläche mit den Auslassungs Zeichen (...) neben der Eigenschaft **Items** , und klicken Sie auf **Hinzufügen** , um zwei untergeordnete Menü Elemente für Tool</span><span class="sxs-lookup"><span data-stu-id="cc7c6-112">Click the ellipsis (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="cc7c6-113">Legen Sie `Text` die-Eigenschaft für diese Elemente auf **neu** und **Window**fest.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-113">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="cc7c6-114">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-114">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

5. <span data-ttu-id="cc7c6-115">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Windows Form** (in Visual Basic oder C#in Visual) oder **Windows Forms Anwendung (.net)** ( C++in Visual) aus dem Bereich **Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-115">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in Visual C++) from the **Templates** pane.</span></span> <span data-ttu-id="cc7c6-116">Benennen Sie im Feld **Name** das Formular **Form2**.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-116">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="cc7c6-117">Wählen Sie **Öffnen** aus, um das Formular dem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-117">Select **Open** to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc7c6-118">Das untergeordnete MDI-Formular, das Sie in diesem Schritt erstellten haben, ist ein Standard-Windows Form.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-118">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="cc7c6-119">Als solches besitzt es eine Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A>, mit der Sie die Transparenz des Formulars steuern können.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-119">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="cc7c6-120">Allerdings wurde die Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A> für Fenster der obersten Ebene entwickelt.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-120">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="cc7c6-121">Verwenden Sie sie nicht mit untergeordneten MDI-Formularen, da Darstellungsprobleme auftreten können.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-121">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="cc7c6-122">Dieses Formular wird die Vorlage für Ihre untergeordneten MDI-Formulare.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-122">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="cc7c6-123">Der **Windows Forms-Designer** wird geöffnet und zeigt **Form2**an.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-123">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="cc7c6-124">Ziehen Sie ein **RichTextBox** -Steuerelement aus der **Toolbox**auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-124">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="cc7c6-125">Legen Sie im Fenster **Eigenschaften** die `Anchor` -Eigenschaft auf **oben, Links** und die `Dock` -Eigenschaft auf **Fill**fest.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-125">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="cc7c6-126">Dies bewirkt, dass das <xref:System.Windows.Forms.RichTextBox>-Steuerelement den Bereich des untergeordneten MDI-Formulars selbst dann vollständig ausgefüllt, wenn die Größe des Formulars geändert wird.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-126">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="cc7c6-127">Doppelklicken Sie auf das **neue** Menü Element, <xref:System.Windows.Forms.Control.Click> um einen-Ereignishandler dafür zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-127">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="cc7c6-128">Fügen Sie Code ähnlich dem folgenden ein, um ein neues untergeordnetes MDI-Formular zu erstellen, wenn der Benutzer auf das **neue** Menü Element klickt.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-128">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cc7c6-129">Im folgenden Beispiel verarbeitet der Ereignishandler das <xref:System.Windows.Forms.Control.Click>-Ereignis für `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-129">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="cc7c6-130">Beachten Sie, dass das **neue** Menü Element abhängig von den Besonderheiten ihrer Anwendungsarchitektur möglicherweise nicht `MenuItem2`ist.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-130">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

    ```vb
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click
       Dim NewMDIChild As New Form2()
       'Set the Parent Form of the Child window.
       NewMDIChild.MdiParent = Me
       'Display the new form.
       NewMDIChild.Show()
    End Sub
    ```

    ```csharp
    protected void MDIChildNew_Click(object sender, System.EventArgs e){
       Form2 newMDIChild = new Form2();
       // Set the Parent Form of the Child window.
       newMDIChild.MdiParent = this;
       // Display the new form.
       newMDIChild.Show();
    }
    ```

    ```cpp
    private:
       void menuItem2_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          Form2^ newMDIChild = gcnew Form2();
          // Set the Parent Form of the Child window.
          newMDIChild->MdiParent = this;
          // Display the new form.
          newMDIChild->Show();
       }
    ```

   <span data-ttu-id="cc7c6-131">Fügen C++Sie in die folgende `#include` Direktive am Anfang von Form1. h hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc7c6-131">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="cc7c6-132">Wählen Sie in der Dropdown Liste am oberen Rand des Fensters **Eigenschaften** die Menüleiste aus, die der **Datei** Menüleiste entspricht, und legen Sie <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> die-Eigenschaft auf <xref:System.Windows.Forms.ToolStripMenuItem>das Fenster fest.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-132">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="cc7c6-133">Dadurch kann das **Fenster** Menü eine Liste mit geöffneten untergeordneten MDI-Fenstern mit einem Häkchen neben dem aktiven untergeordneten Fenster verwalten.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-133">This enables the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="cc7c6-134">Drücken Sie **F5**, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-134">Press **F5** to run the application.</span></span> <span data-ttu-id="cc7c6-135">Wenn Sie im Menü **Datei** die Option **neu** auswählen, können Sie neue untergeordnete MDI-Formulare erstellen, die im **Fenster** Menü Element nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-135">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc7c6-136">Wenn ein untergeordnetes MDI-Formular eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt und innerhalb eines übergeordneten MDI-Formulars geöffnet wird, das eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt, werden die Menüelemente automatisch zusammengeführt, wenn Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> (und optional die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>) festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-136">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="cc7c6-137">Legen Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> -beider <xref:System.Windows.Forms.MainMenu>-Komponenten sowie alle Menüelemente des untergeordneten Formulars auf <xref:System.Windows.Forms.MenuMerge.MergeItems> fest.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-137">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="cc7c6-138">Legen Sie außerdem die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> so fest, dass die Menüelemente aus beiden Menüs in der gewünschten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-138">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="cc7c6-139">Bedenken Sie außerdem, dass beim Schließen eines übergeordneten MDI-Formulars jedes untergeordnete MDI-Formular ein Ereignis <xref:System.Windows.Forms.Form.Closing> auslöst, bevor das Ereignis <xref:System.Windows.Forms.Form.Closing> für das übergeordnete MDI-Formular ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-139">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="cc7c6-140">Durch das Abbrechen des <xref:System.Windows.Forms.Form.Closing>-Ereignisses eines untergeordneten MDI-Formulars wird nicht verhindert, dass das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars ausgelöst wird. Allerdings ist das <xref:System.ComponentModel.CancelEventArgs>-Argument für das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars jetzt auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-140">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="cc7c6-141">Sie können erzwingen, dass das übergeordnete MDI-Element und alle untergeordneten MDI-Formulare geschlossen werden, indem Sie das <xref:System.ComponentModel.CancelEventArgs>-Argument auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="cc7c6-141">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc7c6-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc7c6-142">See also</span></span>

- [<span data-ttu-id="cc7c6-143">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="cc7c6-143">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="cc7c6-144">Vorgehensweise: Übergeordnete MDI-Formulare erstellen</span><span class="sxs-lookup"><span data-stu-id="cc7c6-144">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="cc7c6-145">Vorgehensweise: Festlegen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="cc7c6-145">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="cc7c6-146">Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="cc7c6-146">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="cc7c6-147">Vorgehensweise: Untergeordnete MDI-Formulare anordnen</span><span class="sxs-lookup"><span data-stu-id="cc7c6-147">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
