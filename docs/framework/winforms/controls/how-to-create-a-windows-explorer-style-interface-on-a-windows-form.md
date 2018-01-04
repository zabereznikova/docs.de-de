---
title: "Gewusst wie: Erstellen einer Oberfläche im Stil von Windows Explorer in einem Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c30dd18e7303cf9fe913760da3f9dad7bca3c95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="49d35-102">Gewusst wie: Erstellen einer Oberfläche im Stil von Windows Explorer in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="49d35-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="49d35-103">Windows-Explorer wird eine gemeinsame Benutzeroberfläche Wahl für Anwendungen aufgrund seiner Kenntnisse in bereit.</span><span class="sxs-lookup"><span data-stu-id="49d35-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="49d35-104">Windows-Explorer ist im Wesentlichen eine <xref:System.Windows.Forms.TreeView> Steuerelement und ein <xref:System.Windows.Forms.ListView> Steuerelement auf separate Bereiche.</span><span class="sxs-lookup"><span data-stu-id="49d35-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="49d35-105">Die Bereiche sind durch eine Trennleiste in der Größe veränderbaren vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="49d35-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="49d35-106">Diese Anordnung von Steuerelementen ist sehr gut für die Anzeige und das Durchsuchen von Informationen.</span><span class="sxs-lookup"><span data-stu-id="49d35-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="49d35-107">Die folgenden Schritte zeigen, wie zum Anordnen von Steuerelementen in einer Windows-Explorer-ähnlichen Format.</span><span class="sxs-lookup"><span data-stu-id="49d35-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="49d35-108">Enthalten sie die Datei durchsuchen Funktionalität von Windows Explorer-Anwendung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="49d35-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49d35-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="49d35-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="49d35-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="49d35-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="49d35-111">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="49d35-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="49d35-112">So erstellen ein Windows Explorer-ähnliche Windows Form</span><span class="sxs-lookup"><span data-stu-id="49d35-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="49d35-113">Erstellen Sie ein neues Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="49d35-113">Create a new Windows Application project.</span></span> <span data-ttu-id="49d35-114">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="49d35-114">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="49d35-115">Aus der **Toolbox**:</span><span class="sxs-lookup"><span data-stu-id="49d35-115">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="49d35-116">Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="49d35-116">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="49d35-117">Ziehen Sie eine <xref:System.Windows.Forms.TreeView> steuern in **SplitterPanel1** (der Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement markiert **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="49d35-117">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="49d35-118">Ziehen Sie eine <xref:System.Windows.Forms.ListView> steuern in **SplitterPanel2** (der Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement markiert **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="49d35-118">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="49d35-119">Wählen Sie alle drei Steuerelemente, indem Sie die STRG-Taste drücken, und klicken sie dann auf.</span><span class="sxs-lookup"><span data-stu-id="49d35-119">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="49d35-120">Bei Auswahl der <xref:System.Windows.Forms.SplitContainer> steuern, und klicken Sie auf die Teilerleiste, anstatt die Bereiche.</span><span class="sxs-lookup"><span data-stu-id="49d35-120">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49d35-121">Verwenden Sie nicht die **Alles markieren** Befehl die **bearbeiten** Menü.</span><span class="sxs-lookup"><span data-stu-id="49d35-121">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="49d35-122">In diesem Fall die Eigenschaft, die im nächsten Schritt benötigt erscheint nicht der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="49d35-122">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="49d35-123">In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="49d35-123">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="49d35-124">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="49d35-124">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="49d35-125">Das Formular zeigt eine zweiteilige Benutzeroberfläche ähnelt der von der Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="49d35-125">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49d35-126">Wenn Sie den Splitter ziehen, Größe der Bereiche selbst ändern.</span><span class="sxs-lookup"><span data-stu-id="49d35-126">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d35-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49d35-127">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="49d35-128">Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49d35-128">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [<span data-ttu-id="49d35-129">Gewusst wie: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster</span><span class="sxs-lookup"><span data-stu-id="49d35-129">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [<span data-ttu-id="49d35-130">Gewusst wie: Horizontales Teilen eines Fensters</span><span class="sxs-lookup"><span data-stu-id="49d35-130">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [<span data-ttu-id="49d35-131">SplitContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="49d35-131">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
