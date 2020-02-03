---
title: Integrieren der Benutzerhilfe
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: c402615d68c75327613d21bd35f1587b10f1dbf3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731568"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="16b29-102">Integrieren von Benutzerhilfe in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16b29-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="16b29-103">Ein wichtiger, aber oft übersehen Aspekt der Bildung von Windows-basierten Anwendungen ist das Hilfesystem, da Benutzer in Zeiten von Verwirrung auf Unterstützung setzen.</span><span class="sxs-lookup"><span data-stu-id="16b29-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="16b29-104">Windows Forms unterstützen zwei verschiedene Arten von Hilfe, die jeweils von der [HelpProvider-Komponente](../controls/helpprovider-component-windows-forms.md)bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="16b29-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="16b29-105">Der erste Punkt besteht darin, den Benutzer auf eine Hilfedatei der HTML-oder HTML-Hilfe 1 zu verweisen. das Format *x* oder höher.</span><span class="sxs-lookup"><span data-stu-id="16b29-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="16b29-106">Die zweite kann eine kurze "What es this"-typhilfe zu einzelnen Steuerelementen anzeigen. Dies ist besonders nützlich in Dialogfeldern.</span><span class="sxs-lookup"><span data-stu-id="16b29-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="16b29-107">Beide Arten von Hilfe können im gleichen Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16b29-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="16b29-108">Außerdem kann die QuickInfo- [Komponente](../controls/tooltip-component-windows-forms.md) verwendet werden, um einzelne Hilfe für Steuerelemente auf Windows Forms bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="16b29-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16b29-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="16b29-109">In This Section</span></span>  
 [<span data-ttu-id="16b29-110">Gewusst wie: Bereitstellen von Hilfe in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="16b29-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="16b29-111">Erläutert, wie die `HelpProvider`-Komponente verwendet wird, um Steuerelemente mit Dateien in einem Hilfesystem zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="16b29-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="16b29-112">Gewusst wie: Anzeigen der kontextbezogenen Hilfe</span><span class="sxs-lookup"><span data-stu-id="16b29-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="16b29-113">Erläutert, wie die `HelpProvider` Komponente verwendet wird, um die Popup Hilfe zu Windows Forms anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="16b29-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="16b29-114">Benutzerführung mithilfe von QuickInfos</span><span class="sxs-lookup"><span data-stu-id="16b29-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="16b29-115">Beschreibt die Verwendung der `ToolTip` Komponente, um die Steuerelement spezifische Hilfe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="16b29-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="16b29-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="16b29-116">Related Sections</span></span>  
 [<span data-ttu-id="16b29-117">HelpProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="16b29-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="16b29-118">Erläutert die Grundlagen der `HelpProvider` Komponente.</span><span class="sxs-lookup"><span data-stu-id="16b29-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="16b29-119">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="16b29-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="16b29-120">Erläutert die Grundlagen der `ToolTip` Komponente.</span><span class="sxs-lookup"><span data-stu-id="16b29-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="16b29-121">Übersicht über Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16b29-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="16b29-122">Erläutert die Grundlagen von Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="16b29-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="16b29-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16b29-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="16b29-124">Bietet einen Überblick über Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="16b29-124">Provides an overview of Windows Forms.</span></span>
