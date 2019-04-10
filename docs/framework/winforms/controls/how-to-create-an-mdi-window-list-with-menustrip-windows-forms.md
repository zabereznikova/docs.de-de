---
title: 'Vorgehensweise: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: ec0d8af81e320bea3d9d69305f91bd56666ba7cc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299643"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="c0f5d-102">Vorgehensweise: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c0f5d-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="c0f5d-103">Verwenden Sie zum Erstellen von Anwendungen, die mehrere Dokumente öffnen, zur gleichen Zeit und kopieren und Einfügen von Inhalt aus einem Dokument in den anderen können die Multiple Document Interface (MDI).</span><span class="sxs-lookup"><span data-stu-id="c0f5d-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="c0f5d-104">Dieses Verfahren zeigt, wie Sie eine Liste aller aktiven untergeordneten Formulare in Fenstermenü des übergeordneten Elements zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="c0f5d-105">Zum Erstellen einer MDI-Fensterliste in einem MenuStrip</span><span class="sxs-lookup"><span data-stu-id="c0f5d-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="c0f5d-106">Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="c0f5d-107">Fügen Sie dem Formular eine <xref:System.Windows.Forms.MenuStrip> hinzu.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="c0f5d-108">Zwei Menüelemente der obersten Ebene zum Hinzufügen der <xref:System.Windows.Forms.MenuStrip> und legen Sie deren <xref:System.Windows.Forms.Control.Text%2A> Eigenschaften `&File` und `&Window`.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="c0f5d-109">Fügen Sie dem `&File`-Menüelement ein Untermenüelement hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&Open` fest.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="c0f5d-110">Legen Sie die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft der <xref:System.Windows.Forms.MenuStrip> auf der `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="c0f5d-111">Das Projekt ein Formular hinzu, und fügen Sie das gewünschte Steuerelement hinzu, z. B. einen anderen <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="c0f5d-112">Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.Control.Click> Ereignis die `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="c0f5d-113">Fügen Sie Code, die etwa wie folgt zu erstellende und anzuzeigende neue Instanzen von innerhalb des ereignishandlers `Form2` als untergeordnete MDI-Fenster von `Form1`.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="c0f5d-114">Fügen Sie Code wie den folgenden in das `&New`<xref:System.Windows.Forms.ToolStripMenuItem> um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0f5d-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c0f5d-115">Compiling the Code</span></span>  
 <span data-ttu-id="c0f5d-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c0f5d-116">This example requires:</span></span>  
  
-   <span data-ttu-id="c0f5d-117">Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="c0f5d-118">Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="c0f5d-119">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0f5d-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f5d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0f5d-120">See also</span></span>

- [<span data-ttu-id="c0f5d-121">Vorgehensweise: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="c0f5d-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="c0f5d-122">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="c0f5d-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="c0f5d-123">MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c0f5d-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
