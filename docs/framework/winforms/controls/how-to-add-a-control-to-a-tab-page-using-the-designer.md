---
title: "Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: 7ee734e1-e31e-4ed0-bbc0-a7e8a1f20fef
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30c8a73d23a1a0d27f049c09752d76dd7d2d6ef2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-a-control-to-a-tab-page-using-the-designer"></a><span data-ttu-id="5b0d2-102">Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="5b0d2-102">How to: Add a Control to a Tab Page Using the Designer</span></span>
<span data-ttu-id="5b0d2-103">Die Verwendung von Windows Forms <xref:System.Windows.Forms.TabControl> besteht darin, andere Steuerelemente in einer strukturierten Weise anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-103">The use of the Windows Forms <xref:System.Windows.Forms.TabControl> is to display other controls in an organized fashion.</span></span> <span data-ttu-id="5b0d2-104">Sie können diese Anweisungen verwenden, ein Bild auf den Hauptteil einer Registerkarte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-104">You can use these instructions to display a picture on the main part of a tab page.</span></span> <span data-ttu-id="5b0d2-105">Informationen zum Hinzufügen eines Symbols auf der Bezeichnungsteil einer Registerkartenseite finden Sie unter [Vorgehensweise: Ändern der Darstellung der TabControl in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-105">For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
 <span data-ttu-id="5b0d2-106">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.TabControl> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="5b0d2-107">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b0d2-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5b0d2-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5b0d2-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-control-using-the-designer"></a><span data-ttu-id="5b0d2-111">Hinzufügen des Steuerelements mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="5b0d2-111">To add a control using the designer</span></span>  
  
1.  <span data-ttu-id="5b0d2-112">Klicken Sie auf die entsprechende Registerkarte, sodass es im Vordergrund angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-112">Click the appropriate tab page so that it appears on top.</span></span>  
  
2.  <span data-ttu-id="5b0d2-113">Ziehen Sie das Steuerelement auf der Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-113">Draw the control on the tab page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0d2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b0d2-114">See Also</span></span>  
 [<span data-ttu-id="5b0d2-115">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5b0d2-115">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="5b0d2-116">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5b0d2-116">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="5b0d2-117">Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b0d2-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="5b0d2-118">Gewusst wie: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="5b0d2-118">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="5b0d2-119">Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b0d2-119">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
