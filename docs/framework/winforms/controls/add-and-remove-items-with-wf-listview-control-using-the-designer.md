---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 37660061140e38661a27f8f750604ae2609ac57c
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882297"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="f3596-102">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f3596-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="f3596-103">Beim Hinzufügen eines Elements zu einer Windows Forms <xref:System.Windows.Forms.ListView> -Steuerelement besteht aus in erster Linie das Element angeben, und Eigenschaften zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f3596-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="f3596-104">Hinzufügen oder Entfernen von Elementen kann jederzeit erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f3596-104">Adding or removing list items can be done at any time.</span></span>  
  
 <span data-ttu-id="f3596-105">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3596-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f3596-106">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f3596-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3596-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="f3596-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f3596-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f3596-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f3596-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f3596-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="f3596-110">Hinzufügen oder Entfernen von Elementen, die mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f3596-110">To add or remove items using the designer</span></span>  
  
1. <span data-ttu-id="f3596-111">Wählen Sie das <xref:System.Windows.Forms.ListView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3596-111">Select the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
2.  <span data-ttu-id="f3596-112">In der **Eigenschaften** Fenster, klicken Sie auf die **mit den Auslassungspunkten** (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft .</span><span class="sxs-lookup"><span data-stu-id="f3596-112">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="f3596-113">Die **ListViewItem Auflistungs-Editor** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f3596-113">The **ListViewItem Collection Editor** appears.</span></span>  
  
3. <span data-ttu-id="f3596-114">Um ein Element hinzuzufügen, klicken Sie auf die **hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="f3596-114">To add an item, click the **Add** button.</span></span> <span data-ttu-id="f3596-115">Sie können dann Eigenschaften des neuen Elements, z. B. Festlegen der <xref:System.Windows.Forms.ListView.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f3596-115">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
4. <span data-ttu-id="f3596-116">Um ein Element zu entfernen, wählen Sie ihn, und klicken Sie auf die **entfernen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="f3596-116">To remove an item, select it and click the **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3596-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3596-117">See also</span></span>

- [<span data-ttu-id="f3596-118">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f3596-118">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="f3596-119">Vorgehensweise: Hinzufügen von Spalten zu dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3596-119">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="f3596-120">Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3596-120">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="f3596-121">Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3596-121">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="f3596-122">Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f3596-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="f3596-123">Vorgehensweise: Gruppieren von Elementen in ein ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3596-123">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
