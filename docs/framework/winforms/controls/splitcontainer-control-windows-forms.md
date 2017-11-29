---
title: SplitContainer-Steuerelement (Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 336243cc4db7039225ba272cac1ba7a3f173f361
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="ce61d-102">SplitContainer-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ce61d-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="ce61d-103">Das `SplitContainer`-Steuerelement in Windows Forms kann als zusammengesetztes Steuerelement betrachtet werden. Es setzt sich aus zwei Bereichen zusammen, die durch eine verschiebbare Leiste getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="ce61d-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="ce61d-104">Wenn sich der Mauszeiger über der Leiste befindet, ändert sich seine Form und zeigt an, dass die Leiste verschiebbar ist.</span><span class="sxs-lookup"><span data-stu-id="ce61d-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce61d-105">In der **Toolbox**, gibt diese steuern ersetzt die <xref:System.Windows.Forms.Splitter> Steuerelement, das in der vorherigen Version von Visual Studio enthalten war.</span><span class="sxs-lookup"><span data-stu-id="ce61d-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="ce61d-106">Das `SplitContainer`-Steuerelement ist dem <xref:System.Windows.Forms.Splitter>-Steuerelement vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="ce61d-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="ce61d-107">Die <xref:System.Windows.Forms.Splitter>-Klasse ist aus Gründen der Kompatibilität mit vorhandenen Anwendungen weiterhin in .NET Framework enthalten. Bei neuen Projekten wird jedoch ausdrücklich die Verwendung des `SplitContainer`-Steuerelements empfohlen. </span><span class="sxs-lookup"><span data-stu-id="ce61d-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="ce61d-108">Mit dem `SplitContainer`-Steuerelement können Sie komplexe Benutzeroberflächen erstellen. Häufig bestimmt die Auswahl in einem Fensterbereich, welche Objekte im anderen Fensterbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce61d-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="ce61d-109">Diese Anordnung eignet sich sehr gut für die Anzeige und das Durchsuchen von Informationen.</span><span class="sxs-lookup"><span data-stu-id="ce61d-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="ce61d-110">Die beiden Fensterbereiche ermöglichen Ihnen, Informationen in getrennten Bereichen anzuordnen, und mithilfe der Leiste, die auch als "Splitter" bezeichnet wird, können Benutzer die Größe der Fensterbereiche leicht anpassen.</span><span class="sxs-lookup"><span data-stu-id="ce61d-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce61d-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ce61d-111">In This Section</span></span>  
 [<span data-ttu-id="ce61d-112">Übersicht über das SplitContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ce61d-112">SplitContainer Control Overview</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="ce61d-113">Stellt das `SplitContainer`-Steuerelement vor und beschreibt die am häufigsten verwendeten Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="ce61d-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="ce61d-114">Gewusst wie: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster</span><span class="sxs-lookup"><span data-stu-id="ce61d-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="ce61d-115">Beschreibt, wie der Splitter innerhalb des `SplitContainer`-Steuerelements gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="ce61d-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="ce61d-116">Gewusst wie: Horizontales Teilen eines Fensters</span><span class="sxs-lookup"><span data-stu-id="ce61d-116">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="ce61d-117">Beschreibt, wie die Ausrichtung des Splitters im `SplitContainer`-Steuerelement gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="ce61d-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="ce61d-118">Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce61d-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="ce61d-119">Erstellt eine Multipane-Benutzeroberfläche, die der in Microsoft Outlook ähnelt.</span><span class="sxs-lookup"><span data-stu-id="ce61d-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="ce61d-120">Siehe auch [wie: Aufteilen einer Fenster horizontal mithilfe des Designers](http://msdn.microsoft.com/library/ms233667\(v=vs.110\)), [wie: Erstellen Sie ein Windows-Explorer-Style-Schnittstelle in einem Windows Form](http://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\)), [wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/ms233661\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ce61d-120">Also see [How to: Split a Window Horizontally Using the Designer](http://msdn.microsoft.com/library/ms233667\(v=vs.110\)), [How to: Create a Windows Explorer–Style Interface on a Windows Form](http://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\)), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](http://msdn.microsoft.com/library/ms233661\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ce61d-121">Verweis</span><span class="sxs-lookup"><span data-stu-id="ce61d-121">Reference</span></span>  
 <span data-ttu-id="ce61d-122"><xref:System.Windows.Forms.SplitContainer>-Klasse</span><span class="sxs-lookup"><span data-stu-id="ce61d-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="ce61d-123">Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="ce61d-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ce61d-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ce61d-124">Related Sections</span></span>  
 [<span data-ttu-id="ce61d-125">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ce61d-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="ce61d-126">Enthält Links zu Themen über Steuerelemente, die speziell für Windows Forms vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="ce61d-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="ce61d-127">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ce61d-127">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="ce61d-128">Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="ce61d-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
