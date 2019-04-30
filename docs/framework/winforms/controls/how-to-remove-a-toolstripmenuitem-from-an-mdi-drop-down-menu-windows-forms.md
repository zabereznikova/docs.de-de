---
title: 'Vorgehensweise: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmenü (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 7c84d260783e3a511b5ef6a651c71f1ee55acffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913158"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="38da6-102">Vorgehensweise: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmenü (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="38da6-102">How to: Remove a ToolStripMenuItem from an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="38da6-103">In einigen Anwendungen kann sich die Art eines untergeordneten MDI-Fensters (Multiple-Document Interface) von der des übergeordneten MDI-Fensters unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="38da6-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="38da6-104">Beispielsweise könnte das übergeordnete MDI-Fenster eine Kalkulationstabelle und das untergeordnete MDI-Fenster ein Diagramm enthalten.</span><span class="sxs-lookup"><span data-stu-id="38da6-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="38da6-105">In diesem Fall möchten Sie möglicherweise den Inhalt des Menüs des übergeordneten MDI-Fensters mit dem Inhalt des Menüs des untergeordneten MDI-Fensters aktualisieren, da untergeordnete MDI-Fenster unterschiedlicher Arten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="38da6-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="38da6-106">Im folgenden Verfahren wird die <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> Eigenschaften für ein Menüelement aus dem Dropdownbereich des übergeordneten MDI-Menüs zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="38da6-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to remove a menu item from the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="38da6-107">Schließen die untergeordneten MDI-Fensters wird die entfernte Menüelemente übergeordneten MDI-Menüs wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="38da6-107">Closing the MDI child window restores the removed menu items to the MDI parent menu.</span></span>  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a><span data-ttu-id="38da6-108">So entfernen Sie ein MenuStrip in ein MDI-Dropdownmenü</span><span class="sxs-lookup"><span data-stu-id="38da6-108">To remove a MenuStrip from an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="38da6-109">Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="38da6-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="38da6-110">Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest</span><span class="sxs-lookup"><span data-stu-id="38da6-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="38da6-111">Fügen Sie ein Menüelement der obersten Ebene zu `Form1`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `&File` fest.</span><span class="sxs-lookup"><span data-stu-id="38da6-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="38da6-112">Fügen Sie drei Untermenüelemente an die `&File` Menü, und legen ihre <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften `&Open`, `&Import from`, und `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="38da6-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="38da6-113">Fügen Sie zwei Untermenüelemente hinzu. die `&Import from` Untermenü, und legen ihre <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften `&Word` und `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="38da6-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="38da6-114">Fügen Sie dem Projekt ein Formular hinzu, fügen Sie dem Formular ein <xref:System.Windows.Forms.MenuStrip> hinzu, und legen die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft von `Form2`<xref:System.Windows.Forms.MenuStrip> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="38da6-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="38da6-115">Fügen Sie ein Menüelement der obersten Ebene zu `Form2`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&File` fest.</span><span class="sxs-lookup"><span data-stu-id="38da6-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="38da6-116">Hinzufügen eine `&Import from` Untermenüelement, das auf die `&File` im Menü `Form2`, und fügen eine `&Word` Untermenüelement, das auf die `&File` im Menü.</span><span class="sxs-lookup"><span data-stu-id="38da6-116">Add an `&Import from` submenu item to the `&File` menu of `Form2`, and add an `&Word` submenu item to the `&File` menu.</span></span>  
  
9. <span data-ttu-id="38da6-117">Legen Sie die <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> Eigenschaften der `Form2` Menüelemente, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="38da6-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="38da6-118">Menüelement Form2</span><span class="sxs-lookup"><span data-stu-id="38da6-118">Form2 menu item</span></span>|<span data-ttu-id="38da6-119">MergeAction-Wert</span><span class="sxs-lookup"><span data-stu-id="38da6-119">MergeAction value</span></span>|<span data-ttu-id="38da6-120">MergeIndex-Wert</span><span class="sxs-lookup"><span data-stu-id="38da6-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="38da6-121">Datei</span><span class="sxs-lookup"><span data-stu-id="38da6-121">File</span></span>|<span data-ttu-id="38da6-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="38da6-122">MatchOnly</span></span>|<span data-ttu-id="38da6-123">-1</span><span class="sxs-lookup"><span data-stu-id="38da6-123">-1</span></span>|  
    |<span data-ttu-id="38da6-124">Importieren aus</span><span class="sxs-lookup"><span data-stu-id="38da6-124">Import from</span></span>|<span data-ttu-id="38da6-125">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="38da6-125">MatchOnly</span></span>|<span data-ttu-id="38da6-126">-1</span><span class="sxs-lookup"><span data-stu-id="38da6-126">-1</span></span>|  
    |<span data-ttu-id="38da6-127">Word</span><span class="sxs-lookup"><span data-stu-id="38da6-127">Word</span></span>|<span data-ttu-id="38da6-128">Remove</span><span class="sxs-lookup"><span data-stu-id="38da6-128">Remove</span></span>|<span data-ttu-id="38da6-129">-1</span><span class="sxs-lookup"><span data-stu-id="38da6-129">-1</span></span>|  
  
10. <span data-ttu-id="38da6-130">In `Form1`, erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.Control.Click> Ereignis die `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="38da6-130">In `Form1`, create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="38da6-131">Fügen Sie Code wie im folgenden Codebeispiel wird zu erstellende und anzuzeigende neue Instanzen von innerhalb des ereignishandlers `Form2` als untergeordnete MDI-Fenster von `Form1`:</span><span class="sxs-lookup"><span data-stu-id="38da6-131">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`:</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
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
  
12. <span data-ttu-id="38da6-132">Fügen Sie Code, der dem folgenden Codebeispiel ähnelt, in `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="38da6-132">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38da6-133">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="38da6-133">Compiling the Code</span></span>  
 <span data-ttu-id="38da6-134">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="38da6-134">This example requires:</span></span>  
  
- <span data-ttu-id="38da6-135">Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.</span><span class="sxs-lookup"><span data-stu-id="38da6-135">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="38da6-136">Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.</span><span class="sxs-lookup"><span data-stu-id="38da6-136">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="38da6-137">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="38da6-137">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38da6-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38da6-138">See also</span></span>

- [<span data-ttu-id="38da6-139">Vorgehensweise: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="38da6-139">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="38da6-140">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="38da6-140">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="38da6-141">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="38da6-141">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
