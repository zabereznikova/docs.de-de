---
title: SplitContainer-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: d860763e935c88619e3355661038757d00247dfd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963590"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="e9c29-102">SplitContainer-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e9c29-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="e9c29-103">Das `SplitContainer`-Steuerelement in Windows Forms kann als zusammengesetztes Steuerelement betrachtet werden. Es setzt sich aus zwei Bereichen zusammen, die durch eine verschiebbare Leiste getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="e9c29-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="e9c29-104">Wenn sich der Mauszeiger über der Leiste befindet, ändert sich seine Form und zeigt an, dass die Leiste verschiebbar ist.</span><span class="sxs-lookup"><span data-stu-id="e9c29-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9c29-105">In der **Toolbox**ersetzt dieses Steuerelement das <xref:System.Windows.Forms.Splitter> Steuerelement, das in der vorherigen Version von Visual Studio vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="e9c29-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="e9c29-106">Das `SplitContainer`-Steuerelement ist dem <xref:System.Windows.Forms.Splitter>-Steuerelement vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="e9c29-107">Die <xref:System.Windows.Forms.Splitter>-Klasse ist aus Gründen der Kompatibilität mit vorhandenen Anwendungen weiterhin in .NET Framework enthalten. Bei neuen Projekten wird jedoch ausdrücklich die Verwendung des `SplitContainer`-Steuerelements empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="e9c29-108">Mit dem `SplitContainer`-Steuerelement können Sie komplexe Benutzeroberflächen erstellen. Häufig bestimmt die Auswahl in einem Fensterbereich, welche Objekte im anderen Fensterbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e9c29-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="e9c29-109">Diese Anordnung eignet sich sehr gut für die Anzeige und das Durchsuchen von Informationen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="e9c29-110">Die beiden Fensterbereiche ermöglichen Ihnen, Informationen in getrennten Bereichen anzuordnen, und mithilfe der Leiste, die auch als "Splitter" bezeichnet wird, können Benutzer die Größe der Fensterbereiche leicht anpassen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9c29-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9c29-111">In This Section</span></span>  
 [<span data-ttu-id="e9c29-112">Übersicht über das SplitContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e9c29-112">SplitContainer Control Overview</span></span>](splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="e9c29-113">Stellt das `SplitContainer`-Steuerelement vor und beschreibt die am häufigsten verwendeten Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="e9c29-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="e9c29-114">Vorgehensweise: Definieren des Verhaltens der Größenänderung und Positionierung in einem geteilten Fenster</span><span class="sxs-lookup"><span data-stu-id="e9c29-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="e9c29-115">Beschreibt, wie der Splitter innerhalb des `SplitContainer`-Steuerelements gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="e9c29-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="e9c29-116">Vorgehensweise: Fenster horizontal aufteilen</span><span class="sxs-lookup"><span data-stu-id="e9c29-116">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="e9c29-117">Beschreibt, wie die Ausrichtung des Splitters im `SplitContainer`-Steuerelement gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="e9c29-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="e9c29-118">Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9c29-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="e9c29-119">Erstellt eine Multipane-Benutzeroberfläche, die der in Microsoft Outlook ähnelt.</span><span class="sxs-lookup"><span data-stu-id="e9c29-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="e9c29-120">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Horizontales Teilen eines Fensters mithilfe des](how-to-split-a-window-horizontally-using-the-designer.md)Designers [, Vorgehensweise: Erstellen Sie eine Windows-Explorer-–-Schnittstelle](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md)in [einem Windows Form, Vorgehensweise: Erstellen Sie mit dem-Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md)eine Multipane-Benutzeroberfläche mit Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e9c29-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e9c29-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="e9c29-121">Reference</span></span>  
 <span data-ttu-id="e9c29-122"><xref:System.Windows.Forms.SplitContainer>-Klasse</span><span class="sxs-lookup"><span data-stu-id="e9c29-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="e9c29-123">Beschreibt diese Klasse und enthält Links zu allen deren Membern.</span><span class="sxs-lookup"><span data-stu-id="e9c29-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e9c29-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e9c29-124">Related Sections</span></span>  
 [<span data-ttu-id="e9c29-125">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="e9c29-125">Windows Forms Controls</span></span>](index.md)  
 <span data-ttu-id="e9c29-126">Enthält Links zu Themen über Steuerelemente, die speziell für Windows Forms vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="e9c29-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="e9c29-127">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="e9c29-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="e9c29-128">Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e9c29-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
