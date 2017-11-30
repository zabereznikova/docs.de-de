---
title: "Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d8bdad3aa17c964871c0d35f6e33b8098f2c649
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="94540-102">Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="94540-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="94540-103">Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="94540-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="94540-104"><xref:System.Windows.Forms.ToolBar>Schaltflächen können Symbole darin enthaltene zur leichteren Identifizierung von Benutzern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="94540-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="94540-105">Dies wird durch Hinzufügen von Bildern, erreicht die <xref:System.Windows.Forms.ImageList> Komponente und verknüpfen es mit der <xref:System.Windows.Forms.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="94540-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
 <span data-ttu-id="94540-106">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.ToolBar> Steuerelement und ein <xref:System.Windows.Forms.ImageList> Komponente.</span><span class="sxs-lookup"><span data-stu-id="94540-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="94540-107">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="94540-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94540-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="94540-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="94540-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="94540-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="94540-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="94540-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="94540-111">Um ein Symbol für eine Symbolleisten-Schaltfläche zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="94540-111">To set an icon for a toolbar button at design time</span></span>  
  
1.  <span data-ttu-id="94540-112">Hinzufügen von Bildern, die <xref:System.Windows.Forms.ImageList> Komponente.</span><span class="sxs-lookup"><span data-stu-id="94540-112">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="94540-113">Weitere Informationen finden Sie unter [wie: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="94540-113">For more information, see [How to: Add or Remove ImageList Images with the Designer](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>  
  
2.  <span data-ttu-id="94540-114">Wählen Sie die <xref:System.Windows.Forms.ToolBar> Steuerelement auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="94540-114">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>  
  
3.  <span data-ttu-id="94540-115">In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolBar> des Steuerelements <xref:System.Windows.Forms.ToolBar.ImageList%2A> Eigenschaft, um die <xref:System.Windows.Forms.ImageList> Komponente.</span><span class="sxs-lookup"><span data-stu-id="94540-115">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
4.  <span data-ttu-id="94540-116">Klicken Sie auf die <xref:System.Windows.Forms.ToolBar> des Steuerelements <xref:System.Windows.Forms.ToolBar.Buttons%2A> Eigenschaft, um auszuwählen, und klicken Sie auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **ToolBarButton Auflistungs-Editor**.</span><span class="sxs-lookup"><span data-stu-id="94540-116">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="94540-117">Verwenden der **hinzufügen** Schaltfläche zum Hinzufügen von Schaltflächen auf der <xref:System.Windows.Forms.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="94540-117">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
6.  <span data-ttu-id="94540-118">In der **Eigenschaften** im Bereich auf der rechten Seite des angezeigten Fenster die **ToolBarButton Auflistungs-Editor**legen die <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> Eigenschaft jeder Symbolleisten-Schaltfläche, um einen der Werte in der Liste der gezeichnet wird, aus der Bilder, die Sie hinzugefügt, um haben die <xref:System.Windows.Forms.ImageList> Komponente.</span><span class="sxs-lookup"><span data-stu-id="94540-118">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94540-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94540-119">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="94540-120">Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen</span><span class="sxs-lookup"><span data-stu-id="94540-120">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [<span data-ttu-id="94540-121">ToolBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="94540-121">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [<span data-ttu-id="94540-122">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="94540-122">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
