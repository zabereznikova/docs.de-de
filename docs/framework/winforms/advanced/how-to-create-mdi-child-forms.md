---
title: 'Gewusst wie: Erstellen von untergeordneten MDI-Formularen'
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
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a779229a61d18ec835197bafac66579c026e2ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="b1358-102">Gewusst wie: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="b1358-102">How to: Create MDI Child Forms</span></span>
<span data-ttu-id="b1358-103">Untergeordnete MDI-Formulare sind ein wesentliches Element des [Multiple Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), wie diese Formulare den Mittelpunkt der Benutzerinteraktion sind.</span><span class="sxs-lookup"><span data-stu-id="b1358-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>  
  
 <span data-ttu-id="b1358-104">Im folgenden Verfahren erstellen Sie ein untergeordnetes MDI-Formular, das ein <xref:System.Windows.Forms.RichTextBox>-Steuerelement anzeigt, das den meisten Textverarbeitungsprogrammen ähnelt.</span><span class="sxs-lookup"><span data-stu-id="b1358-104">In the following procedure, you will create MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="b1358-105">Durch Ersetzen des <xref:System.Windows.Forms>-Steuerelements durch andere Steuerelementen (z. B. das <xref:System.Windows.Forms.DataGridView>-Steuerelement oder eine Kombination von Steuerelementen können Sie untergeordnete MDI-Fenster (und durch Erweiterung auch MDI-Anwendungen) mit vielfältigen Möglichkeiten erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1358-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1358-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="b1358-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b1358-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b1358-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b1358-108">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b1358-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-mdi-child-forms"></a><span data-ttu-id="b1358-109">So erstellen Sie untergeordnete MDI-Formulare</span><span class="sxs-lookup"><span data-stu-id="b1358-109">To create MDI child forms</span></span>  
  
1.  <span data-ttu-id="b1358-110">Erstellen Sie ein neues Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="b1358-110">Create a new Windows Forms project.</span></span> <span data-ttu-id="b1358-111">In **im Eigenschaftenfenster** für das Formular festgelegt seine <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft `true`, und die zugehörige `WindowsState` Eigenschaft `Maximized`.</span><span class="sxs-lookup"><span data-stu-id="b1358-111">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>  
  
     <span data-ttu-id="b1358-112">Dies kennzeichnet das Formular als MDI-Container für untergeordnete Fenster.</span><span class="sxs-lookup"><span data-stu-id="b1358-112">This designates the form as an MDI container for child windows.</span></span>  
  
2.  <span data-ttu-id="b1358-113">Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der `Toolbox` in das Formular.</span><span class="sxs-lookup"><span data-stu-id="b1358-113">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="b1358-114">Legen Sie dessen `Text` Eigenschaft **Datei**.</span><span class="sxs-lookup"><span data-stu-id="b1358-114">Set its `Text` property to **File**.</span></span>  
  
3.  <span data-ttu-id="b1358-115">Klicken Sie auf die Auslassungspunkte (...) neben dem **Elemente** -Eigenschaft, und klicken Sie auf **hinzufügen** um zwei untergeordnete Menüelemente der Toolleiste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1358-115">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="b1358-116">Legen Sie die `Text` -Eigenschaft für diese Elemente **neu** und **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="b1358-116">Set the `Text` property for these items to **New** and **Window**.</span></span>  
  
4.  <span data-ttu-id="b1358-117">In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, zeigen Sie auf **hinzufügen**, und wählen Sie dann **neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b1358-117">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>  
  
5.  <span data-ttu-id="b1358-118">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Windows Form** (in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder im [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) oder **Windows Forms-Anwendung (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) aus der **Vorlagen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="b1358-118">In the **Add New Item** dialog box, select **Windows Form** (in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="b1358-119">In der **Namen** Feld, nennen Sie das Formular **Form2**.</span><span class="sxs-lookup"><span data-stu-id="b1358-119">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="b1358-120">Klicken Sie auf die **öffnen** Schaltfläche, um das Formular zum Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1358-120">Click the **Open** button to add the form to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1358-121">Das untergeordnete MDI-Formular, das Sie in diesem Schritt erstellten haben, ist ein Standard-Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b1358-121">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="b1358-122">Als solches besitzt es eine Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A>, mit der Sie die Transparenz des Formulars steuern können.</span><span class="sxs-lookup"><span data-stu-id="b1358-122">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="b1358-123">Allerdings wurde die Eigenschaft <xref:System.Windows.Forms.Form.Opacity%2A> für Fenster der obersten Ebene entwickelt.</span><span class="sxs-lookup"><span data-stu-id="b1358-123">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="b1358-124">Verwenden Sie sie nicht mit untergeordneten MDI-Formularen, da Darstellungsprobleme auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b1358-124">Do not use it with MDI child forms, as painting problems can occur.</span></span>  
  
     <span data-ttu-id="b1358-125">Dieses Formular wird die Vorlage für Ihre untergeordneten MDI-Formulare.</span><span class="sxs-lookup"><span data-stu-id="b1358-125">This form will be the template for your MDI child forms.</span></span>  
  
     <span data-ttu-id="b1358-126">Die **Windows Forms-Designer** wird geöffnet und zeigt **Form2**.</span><span class="sxs-lookup"><span data-stu-id="b1358-126">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>  
  
6.  <span data-ttu-id="b1358-127">Aus der **Toolbox**, ziehen Sie eine **RichTextBox** Steuerelement dem Formular.</span><span class="sxs-lookup"><span data-stu-id="b1358-127">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>  
  
7.  <span data-ttu-id="b1358-128">In der **Eigenschaften** legen die `Anchor` Eigenschaft, um **Top, Left** und die `Dock` Eigenschaft, um **füllen**.</span><span class="sxs-lookup"><span data-stu-id="b1358-128">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>  
  
     <span data-ttu-id="b1358-129">Dies bewirkt, dass das <xref:System.Windows.Forms.RichTextBox>-Steuerelement den Bereich des untergeordneten MDI-Formulars selbst dann vollständig ausgefüllt, wenn die Größe des Formulars geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b1358-129">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>  
  
8.  <span data-ttu-id="b1358-130">Doppelklicken klicken Sie auf die **neu** Menüelement zum Erstellen einer <xref:System.Windows.Forms.Control.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b1358-130">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>  
  
9. <span data-ttu-id="b1358-131">Fügen Sie Code ähnlich der folgenden Optionen, um ein neues untergeordnetes MDI-Formular zu erstellen, wenn der Benutzer klickt auf die **neu** Menüelement.</span><span class="sxs-lookup"><span data-stu-id="b1358-131">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1358-132">Im folgenden Beispiel verarbeitet der Ereignishandler das <xref:System.Windows.Forms.Control.Click>-Ereignis für `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="b1358-132">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="b1358-133">Beachten Sie, abhängig von den gegebenheiten Ihrer Anwendungsarchitektur Ihr **neu** Menüelement möglicherweise nicht `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="b1358-133">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>  
  
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
  
     <span data-ttu-id="b1358-134">Fügen Sie in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] die folgende `#include`-Direktive am Anfang von "Form1.h" hinzu:</span><span class="sxs-lookup"><span data-stu-id="b1358-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], add the following `#include` directive at the top of Form1.h:</span></span>  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. <span data-ttu-id="b1358-135">In der Dropdownliste am oberen Rand der **Eigenschaften** Fenster, wählen Sie die Menüleiste, die entspricht der **Datei** Menüleiste, und legen die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft, um das Fenster <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="b1358-135">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
     <span data-ttu-id="b1358-136">Dadurch kann die **Fenster** -Menü, um eine Liste der geöffneten untergeordneten MDI-Fenster mit einem Häkchen neben dem aktiven untergeordneten Fenster verwalten.</span><span class="sxs-lookup"><span data-stu-id="b1358-136">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>  
  
11. <span data-ttu-id="b1358-137">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b1358-137">Press F5 to run the application.</span></span> <span data-ttu-id="b1358-138">Durch Auswahl **neu** aus der **Datei** im Menü Erstellen Sie neue untergeordnete MDI-Formulare, die behalten in den Überblick über sind die **Fenster** Menüelement.</span><span class="sxs-lookup"><span data-stu-id="b1358-138">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1358-139">Wenn ein untergeordnetes MDI-Formular eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt und innerhalb eines übergeordneten MDI-Formulars geöffnet wird, das eine Komponente <xref:System.Windows.Forms.MainMenu> (in der Regel mit einer Menüstruktur aus Menüelementen) besitzt, werden die Menüelemente automatisch zusammengeführt, wenn Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> (und optional die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>) festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="b1358-139">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="b1358-140">Legen Sie die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeType%2A> -beider <xref:System.Windows.Forms.MainMenu>-Komponenten sowie alle Menüelemente des untergeordneten Formulars auf <xref:System.Windows.Forms.MenuMerge.MergeItems> fest.</span><span class="sxs-lookup"><span data-stu-id="b1358-140">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="b1358-141">Legen Sie außerdem die Eigenschaft <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> so fest, dass die Menüelemente aus beiden Menüs in der gewünschten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1358-141">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="b1358-142">Bedenken Sie außerdem, dass beim Schließen eines übergeordneten MDI-Formulars jedes untergeordnete MDI-Formular ein Ereignis <xref:System.Windows.Forms.Form.Closing> auslöst, bevor das Ereignis <xref:System.Windows.Forms.Form.Closing> für das übergeordnete MDI-Formular ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b1358-142">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="b1358-143">Durch das Abbrechen des <xref:System.Windows.Forms.Form.Closing>-Ereignisses eines untergeordneten MDI-Formulars wird nicht verhindert, dass das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars ausgelöst wird. Allerdings ist das <xref:System.ComponentModel.CancelEventArgs>-Argument für das <xref:System.Windows.Forms.Form.Closing>-Ereignis des übergeordneten MDI-Formulars jetzt auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b1358-143">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="b1358-144">Sie können erzwingen, dass das übergeordnete MDI-Element und alle untergeordneten MDI-Formulare geschlossen werden, indem Sie das <xref:System.ComponentModel.CancelEventArgs>-Argument auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="b1358-144">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1358-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1358-145">See Also</span></span>  
 [<span data-ttu-id="b1358-146">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="b1358-146">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="b1358-147">Gewusst wie: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="b1358-147">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="b1358-148">Gewusst wie: Bestimmen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="b1358-148">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="b1358-149">Gewusst wie: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="b1358-149">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="b1358-150">Gewusst wie: Anordnen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="b1358-150">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
