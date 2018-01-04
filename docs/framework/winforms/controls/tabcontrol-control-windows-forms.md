---
title: "TabControl-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TabControl control [Windows Forms]
- tab controls
- tab controls [Windows Forms], creating
- multipage dialog boxes
- dialog boxes [Windows Forms], creating multipage
- property pages [Windows Forms], creating
- tab dialog boxes
ms.assetid: 915091af-93ac-4d3d-8283-738dd2d21ea7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 705f9dbb8ea7f4d462a2b19cc0c6b845ae8f578b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tabcontrol-control-windows-forms"></a><span data-ttu-id="f6191-102">TabControl-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f6191-102">TabControl Control (Windows Forms)</span></span>
<span data-ttu-id="f6191-103">Mit `TabControl` in Windows Forms werden mehrere Registerkarten wie Karteireiter in einem Notizbuch oder Reiter in einem Satz von Ordnern in einem Aktenschrank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6191-103">The Windows Forms `TabControl` displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="f6191-104">Die Registerkarten können Bilder und weitere Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6191-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="f6191-105">Verwenden Sie `TabControl`, um Eigenschaftenseiten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6191-105">Use the `TabControl` to create property pages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6191-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f6191-106">In This Section</span></span>  
 [<span data-ttu-id="f6191-107">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f6191-107">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="f6191-108">Hier werden das Steuerelement und seine wichtigsten Funktionen und Eigenschaften erläutert.</span><span class="sxs-lookup"><span data-stu-id="f6191-108">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="f6191-109">Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="f6191-109">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 <span data-ttu-id="f6191-110">Enthält Anweisungen zum Anzeigen von Steuerelementen auf Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="f6191-110">Gives directions for displaying controls on tab pages.</span></span>  
  
 [<span data-ttu-id="f6191-111">Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6191-111">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="f6191-112">Enthält Anweisungen zum Hinzufügen und Entfernen von Registerkarten im Designer oder im Code.</span><span class="sxs-lookup"><span data-stu-id="f6191-112">Gives directions for adding and removing tabs in the designer or in code.</span></span>  
  
 [<span data-ttu-id="f6191-113">Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6191-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="f6191-114">Enthält Anweisungen zum Anpassen der Eigenschaften, die die Darstellung der einzelnen Registerkarten beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="f6191-114">Gives directions for adjusting properties that affect the appearance of individual tabs.</span></span>  
  
 [<span data-ttu-id="f6191-115">Gewusst wie: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="f6191-115">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 <span data-ttu-id="f6191-116">Erläutert, wie der Zugriff auf eine Registerkarte (möglicherweise auf Grundlage von Benutzeranmeldeinformationen) eingeschränkt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f6191-116">Explains how to restrict access to a tab page, possibly based on user credentials.</span></span>  
  
 <span data-ttu-id="f6191-117">Siehe auch [wie: Hinzufügen und Entfernen von Registerkarten mit Windows Forms TabControl mithilfe des Designers](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte mithilfe des Designers](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f6191-117">Also see [How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [How to: Add a Control to a Tab Page Using the Designer](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f6191-118">Verweis</span><span class="sxs-lookup"><span data-stu-id="f6191-118">Reference</span></span>  
 <span data-ttu-id="f6191-119"><xref:System.Windows.Forms.TabControl>-Klasse</span><span class="sxs-lookup"><span data-stu-id="f6191-119"><xref:System.Windows.Forms.TabControl> class</span></span>  
 <span data-ttu-id="f6191-120">Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="f6191-120">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f6191-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f6191-121">Related Sections</span></span>  
 [<span data-ttu-id="f6191-122">Dialogfelder in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6191-122">Dialog Boxes in Windows Forms</span></span>](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)  
 <span data-ttu-id="f6191-123">Enthält eine Liste von Aufgaben für Dialogfelder, von denen häufig Registerkarten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f6191-123">Provides a list of tasks for dialog boxes, which often display tabs.</span></span>  
  
 [<span data-ttu-id="f6191-124">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="f6191-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="f6191-125">Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f6191-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
