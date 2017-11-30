---
title: 'Gewusst wie: Ausblenden von ToolStripMenuItems mithilfe des Designers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9549fa11b3f019dce3cc77d5f6d1d08a8485f0cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="88cde-102">Gewusst wie: Ausblenden von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="88cde-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="88cde-103">Ausblenden von Menüelementen ist eine Möglichkeit zum Steuern der Benutzeroberfläche (UI) Ihrer Anwendung, und Benutzerbefehle einschränken.</span><span class="sxs-lookup"><span data-stu-id="88cde-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="88cde-104">Häufig, sollten Sie ein ganzes Menü auszublenden, wenn alle Menüelemente im auf ihm nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="88cde-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="88cde-105">Dies ist weniger verwirrend für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="88cde-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="88cde-106">Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren das Menü oder Menüelement, wie durch das bloße Ausblenden nicht den Benutzer verhindert den Zugriff auf einen Menübefehl über eine Tastenkombination.</span><span class="sxs-lookup"><span data-stu-id="88cde-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="88cde-107">Weitere Informationen zum Deaktivieren von Menüelementen, finden Sie unter [Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="88cde-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88cde-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="88cde-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="88cde-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="88cde-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="88cde-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="88cde-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="88cde-111">So blenden Sie ein Menü der obersten Ebene und seine Untermenüelemente aus</span><span class="sxs-lookup"><span data-stu-id="88cde-111">To hide a top-level menu and its submenu items</span></span>  
  
1.  <span data-ttu-id="88cde-112">Wählen Sie das Menüelement der obersten Ebene, und legen seine <xref:System.Windows.Forms.ToolStripItem.Visible%2A> oder <xref:System.Windows.Forms.ToolStripItem.Available%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="88cde-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="88cde-113">Wenn Sie das Menüelement der obersten Ebene ausblenden, werden auch alle Menüelemente in diesem Menü ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="88cde-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="88cde-114">Außer auf Klicken die <xref:System.Windows.Forms.MenuStrip> nach Einstellung <xref:System.Windows.Forms.ToolStripItem.Visible%2A> zu `false`, die gesamte Menüelement der obersten Ebene und seine Untermenüelemente verschwinden aus dem Formular dargestellt wird daher die Auswirkungen zur Laufzeit Ihre Aktion.</span><span class="sxs-lookup"><span data-stu-id="88cde-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="88cde-115">Um die ausgeblendeten Menüelement der obersten Ebene zur Entwurfszeit anzuzeigen, klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> in der **Komponentenleiste**im **Dokumentgliederung**, oder am Anfang des Eigenschaftenrasters.</span><span class="sxs-lookup"><span data-stu-id="88cde-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88cde-116">Sie werden nur selten ein gesamtes Menü außer mehrere untergeordnete Menüs mit Document Interface (MDI) in einem Szenario mit Zusammenführen ausblenden.</span><span class="sxs-lookup"><span data-stu-id="88cde-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="88cde-117">So blenden Sie ein Untermenüelement aus</span><span class="sxs-lookup"><span data-stu-id="88cde-117">To hide a submenu item</span></span>  
  
1.  <span data-ttu-id="88cde-118">Wählen Sie das Untermenüelement, und legen seine <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="88cde-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="88cde-119">Wenn Sie ein Untermenüelement ausblenden, wird er auf das Formular zur Entwurfszeit angezeigt, damit Sie problemlos zur Bearbeitung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="88cde-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="88cde-120">Es werden tatsächlich zur Laufzeit ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="88cde-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88cde-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88cde-121">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [<span data-ttu-id="88cde-122">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88cde-122">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="88cde-123">Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="88cde-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
