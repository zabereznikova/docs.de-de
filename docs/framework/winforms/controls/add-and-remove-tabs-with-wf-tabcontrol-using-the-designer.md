---
title: "Gewusst wie: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e603e420be2c5be6174fab3876008fdf73c8459
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="c8a36-102">Gewusst wie: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="c8a36-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="c8a36-103">Beim Platzieren einer <xref:System.Windows.Forms.TabControl> Steuerelement auf dem Formular sie zwei Registerkarten in der Standardeinstellung enthält.</span><span class="sxs-lookup"><span data-stu-id="c8a36-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="c8a36-104">Sie können hinzufügen oder Entfernen von Registerkarten, die mithilfe des Designers.</span><span class="sxs-lookup"><span data-stu-id="c8a36-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="c8a36-105">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.TabControl> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c8a36-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="c8a36-106">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c8a36-106">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8a36-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="c8a36-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c8a36-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c8a36-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c8a36-109">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c8a36-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="c8a36-110">Zum Hinzufügen oder Entfernen einer Registerkarte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="c8a36-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="c8a36-111">Klicken Sie auf das Steuerelement smart Tag auf **Registerkarte hinzufügen** oder **Registerkarte "entfernen"**</span><span class="sxs-lookup"><span data-stu-id="c8a36-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="c8a36-112">- oder - </span><span class="sxs-lookup"><span data-stu-id="c8a36-112">-or-</span></span>  
  
     <span data-ttu-id="c8a36-113">In der **Eigenschaften** Fenster, klicken Sie auf die **Auslassungszeichen** Schaltfläche (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben die <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft so öffnen die **TabPage-Auflistungs-Editor**.</span><span class="sxs-lookup"><span data-stu-id="c8a36-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="c8a36-114">Klicken Sie auf die **hinzufügen** oder **entfernen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="c8a36-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a36-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8a36-115">See Also</span></span>  
 [<span data-ttu-id="c8a36-116">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c8a36-116">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="c8a36-117">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c8a36-117">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="c8a36-118">Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="c8a36-118">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="c8a36-119">Gewusst wie: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="c8a36-119">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="c8a36-120">Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8a36-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
