---
title: Integrieren von Benutzerhilfe in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: 207ceeafa2ea06340310577c636deb5ea1977aae
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715307"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="07cdd-102">Integrieren von Benutzerhilfe in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07cdd-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="07cdd-103">Ein grundlegender, aber häufig übersehene Aspekt erstellen Windows-basierter Anwendungen ist das Hilfesystem, da es sich handelt, in dem Benutzer um Unterstützung zu erhalten, in Zeiten Verwirrung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="07cdd-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="07cdd-104">Windows Forms unterstützen zwei verschiedene Arten von Hilfe, die [HelpProvider-Komponente](../controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="07cdd-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="07cdd-105">Die erste Möglichkeit besteht, zeigen den Benutzer zu einer Hilfedatei HTML oder HTML-Hilfe-1. *x* oder höher vorliegen.</span><span class="sxs-lookup"><span data-stu-id="07cdd-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="07cdd-106">Die zweite kann anzeigen, kurze "Was ist"-Geben Sie die Hilfe auf einzelne Steuerelemente Dies ist besonders nützlich in Dialogfeldern.</span><span class="sxs-lookup"><span data-stu-id="07cdd-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="07cdd-107">Beide Arten von Hilfe können im selben Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07cdd-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="07cdd-108">Darüber hinaus die [ToolTip-Komponente](../controls/tooltip-component-windows-forms.md) können verwendet werden, um individuelle Hilfe bieten für in Windows Forms-Steuerelemente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="07cdd-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07cdd-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="07cdd-109">In This Section</span></span>  
 [<span data-ttu-id="07cdd-110">Vorgehensweise: Bereitstellen von Hilfe in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="07cdd-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="07cdd-111">Erläutert, wie die `HelpProvider` Komponente, um Steuerelemente auf Dateien in einem Hilfesystem verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="07cdd-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="07cdd-112">Vorgehensweise: Anzeigen der kontextbezogenen Hilfe</span><span class="sxs-lookup"><span data-stu-id="07cdd-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="07cdd-113">Erläutert, wie die `HelpProvider` -Komponente zum Anzeigen der kontextbezogenen Hilfe in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="07cdd-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="07cdd-114">Benutzerführung mithilfe von QuickInfos</span><span class="sxs-lookup"><span data-stu-id="07cdd-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="07cdd-115">Beschreibt die Verwendung der `ToolTip` -Komponente zum Anzeigen der Hilfe zu bestimmten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="07cdd-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="07cdd-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="07cdd-116">Related Sections</span></span>  
 [<span data-ttu-id="07cdd-117">HelpProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="07cdd-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="07cdd-118">Erläutert die Grundlagen von der `HelpProvider` Komponente.</span><span class="sxs-lookup"><span data-stu-id="07cdd-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="07cdd-119">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="07cdd-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="07cdd-120">Erläutert die Grundlagen von der `ToolTip` Komponente.</span><span class="sxs-lookup"><span data-stu-id="07cdd-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="07cdd-121">Übersicht über Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07cdd-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="07cdd-122">Erläutert die Grundlagen von Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="07cdd-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="07cdd-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07cdd-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="07cdd-124">Bietet eine Übersicht über Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="07cdd-124">Provides an overview of Windows Forms.</span></span>
