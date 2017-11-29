---
title: Integrieren von Benutzerhilfe in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7ec4d32c5f025cb3e48b1403387273268d83fb8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="62616-102">Integrieren von Benutzerhilfe in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="62616-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="62616-103">Ein Aspekt unerlässlich, aber häufig übersehene Erstellen von Windows-basierten Anwendungen ist das Hilfesystem auf, weil es sich handelt, in dem Benutzer um Unterstützung zu erhalten, in Zeiten Verwirrung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="62616-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="62616-104">Windows Forms unterstützen zwei verschiedene Arten von Hilfe, die [HelpProvider-Komponente](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="62616-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="62616-105">Die erste Möglichkeit besteht, zeigen den Benutzer zu einer Hilfedatei HTML-oder HTML-Hilfe-1. *x* oder höher vorliegen.</span><span class="sxs-lookup"><span data-stu-id="62616-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="62616-106">Die zweite kann anzeigen, kurze "Was This is"-Geben Sie die Hilfe auf einzelne Steuerelemente Dies ist besonders für Dialogfelder.</span><span class="sxs-lookup"><span data-stu-id="62616-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="62616-107">Beide Arten von Hilfe können im selben Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62616-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="62616-108">Darüber hinaus die [ToolTip-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) kann verwendet werden, um individuelle Hilfe für Steuerelemente in Windows Forms bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="62616-108">Additionally, the [ToolTip Component](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62616-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62616-109">In This Section</span></span>  
 [<span data-ttu-id="62616-110">Gewusst wie: Bereitstellen von Hilfe in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="62616-110">How to: Provide Help in a Windows Application</span></span>](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="62616-111">Erklärt, wie die `HelpProvider` Komponente Steuerelemente mit Dateien in einem Hilfesystem verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="62616-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="62616-112">Gewusst wie: Anzeigen der kontextbezogenen Hilfe</span><span class="sxs-lookup"><span data-stu-id="62616-112">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 <span data-ttu-id="62616-113">Erklärt, wie die `HelpProvider` Komponente zum Anzeigen der Hilfe für Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="62616-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="62616-114">Benutzerführung mithilfe von QuickInfos</span><span class="sxs-lookup"><span data-stu-id="62616-114">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 <span data-ttu-id="62616-115">Beschreibt die Verwendung der `ToolTip` Komponente, für das Steuerelement spezifische Hilfe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="62616-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="62616-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="62616-116">Related Sections</span></span>  
 [<span data-ttu-id="62616-117">HelpProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="62616-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="62616-118">Erläutert die Grundlagen von der `HelpProvider` Komponente.</span><span class="sxs-lookup"><span data-stu-id="62616-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="62616-119">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="62616-119">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="62616-120">Erläutert die Grundlagen von der `ToolTip` Komponente.</span><span class="sxs-lookup"><span data-stu-id="62616-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="62616-121">Übersicht über Windows Forms</span><span class="sxs-lookup"><span data-stu-id="62616-121">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 <span data-ttu-id="62616-122">Erläutert die Grundlagen von Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="62616-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="62616-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="62616-123">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)  
 <span data-ttu-id="62616-124">Bietet eine Übersicht über Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="62616-124">Provides an overview of Windows Forms.</span></span>
