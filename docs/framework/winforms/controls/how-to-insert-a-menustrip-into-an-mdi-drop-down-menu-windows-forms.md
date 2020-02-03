---
title: 'Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 6e189dd159c48b5779679d0563fab85e9b848992
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736402"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="4cfd6-102">Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4cfd6-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="4cfd6-103">In einigen Anwendungen kann sich die Art eines untergeordneten MDI-Fensters (Multiple-Document Interface) von der des übergeordneten MDI-Fensters unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="4cfd6-104">Beispielsweise könnte das übergeordnete MDI-Fenster eine Kalkulationstabelle und das untergeordnete MDI-Fenster ein Diagramm enthalten.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="4cfd6-105">In diesem Fall möchten Sie möglicherweise den Inhalt des Menüs des übergeordneten MDI-Fensters mit dem Inhalt des Menüs des untergeordneten MDI-Fensters aktualisieren, da untergeordnete MDI-Fenster unterschiedlicher Arten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="4cfd6-106">Im folgenden Verfahren werden die Eigenschaften <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> verwendet, um eine Gruppe von Menü Elementen aus dem untergeordneten MDI-Menü in den Dropdown Bereich des übergeordneten MDI-Menüs einzufügen.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="4cfd6-107">Durch das Schließen des untergeordneten MDI-Fensters werden die eingefügten Menü Elemente aus der übergeordneten MDI-</span><span class="sxs-lookup"><span data-stu-id="4cfd6-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="4cfd6-108">So fügen Sie ein MenuStrip in ein MDI-Dropdown Menü ein</span><span class="sxs-lookup"><span data-stu-id="4cfd6-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="4cfd6-109">Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="4cfd6-110">Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest</span><span class="sxs-lookup"><span data-stu-id="4cfd6-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="4cfd6-111">Fügen Sie ein Menüelement der obersten Ebene zu `Form1`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `&File` fest.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="4cfd6-112">Fügen Sie dem Menü Element `&File` drei unter Menü Elemente hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften auf `&Open`, `&Import from`und `E&xit`fest.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="4cfd6-113">Fügen Sie dem `&Import from` unter Menü Element zwei unter Menü Elemente hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften auf `&Word` und `&Excel`fest.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="4cfd6-114">Fügen Sie dem Projekt ein Formular hinzu, fügen Sie dem Formular ein <xref:System.Windows.Forms.MenuStrip> hinzu, und legen die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft von `Form2`<xref:System.Windows.Forms.MenuStrip> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="4cfd6-115">Fügen Sie ein Menüelement der obersten Ebene zu `Form2`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&File` fest.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="4cfd6-116">Fügen Sie unter Menü Elemente dem Menü `&File` `Form2` in der folgenden Reihenfolge hinzu: eine <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`und eine andere <xref:System.Windows.Forms.ToolStripSeparator>.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="4cfd6-117">Legen Sie die Eigenschaften <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> der `Form2` Menü Elemente fest, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="4cfd6-118">Form2 (Menü Element)</span><span class="sxs-lookup"><span data-stu-id="4cfd6-118">Form2 menu item</span></span>|<span data-ttu-id="4cfd6-119">MergeAction-Wert</span><span class="sxs-lookup"><span data-stu-id="4cfd6-119">MergeAction value</span></span>|<span data-ttu-id="4cfd6-120">Mergeingedex-Wert</span><span class="sxs-lookup"><span data-stu-id="4cfd6-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="4cfd6-121">Datei</span><span class="sxs-lookup"><span data-stu-id="4cfd6-121">File</span></span>|<span data-ttu-id="4cfd6-122">Nur MatchOnly</span><span class="sxs-lookup"><span data-stu-id="4cfd6-122">MatchOnly</span></span>|<span data-ttu-id="4cfd6-123">-1</span><span class="sxs-lookup"><span data-stu-id="4cfd6-123">-1</span></span>|  
    |<span data-ttu-id="4cfd6-124">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-124">Separator</span></span>|<span data-ttu-id="4cfd6-125">Einfügen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-125">Insert</span></span>|<span data-ttu-id="4cfd6-126">2</span><span class="sxs-lookup"><span data-stu-id="4cfd6-126">2</span></span>|  
    |<span data-ttu-id="4cfd6-127">Speichern</span><span class="sxs-lookup"><span data-stu-id="4cfd6-127">Save</span></span>|<span data-ttu-id="4cfd6-128">Einfügen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-128">Insert</span></span>|<span data-ttu-id="4cfd6-129">3</span><span class="sxs-lookup"><span data-stu-id="4cfd6-129">3</span></span>|  
    |<span data-ttu-id="4cfd6-130">Speichern und Schließen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-130">Save and Close</span></span>|<span data-ttu-id="4cfd6-131">Einfügen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-131">Insert</span></span>|<span data-ttu-id="4cfd6-132">4</span><span class="sxs-lookup"><span data-stu-id="4cfd6-132">4</span></span>|  
    |<span data-ttu-id="4cfd6-133">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-133">Separator</span></span>|<span data-ttu-id="4cfd6-134">Einfügen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-134">Insert</span></span>|<span data-ttu-id="4cfd6-135">5</span><span class="sxs-lookup"><span data-stu-id="4cfd6-135">5</span></span>|  
  
10. <span data-ttu-id="4cfd6-136">Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>-Ereignis von `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="4cfd6-137">Fügen Sie im Ereignishandler Code ein, der dem folgenden Codebeispiel ähnelt, um neue Instanzen von `Form2` als untergeordnete MDI-Fenster von `Form1` zu erstellen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
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
  
12. <span data-ttu-id="4cfd6-138">Fügen Sie Code, der dem folgenden Codebeispiel ähnelt, in `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4cfd6-139">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4cfd6-139">Compiling the Code</span></span>  
 <span data-ttu-id="4cfd6-140">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4cfd6-140">This example requires:</span></span>  
  
- <span data-ttu-id="4cfd6-141">Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="4cfd6-142">Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="4cfd6-143">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4cfd6-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfd6-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-144">See also</span></span>

- [<span data-ttu-id="4cfd6-145">Gewusst wie: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-145">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="4cfd6-146">Gewusst wie: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="4cfd6-146">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="4cfd6-147">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4cfd6-147">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
