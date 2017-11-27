---
title: "StatusBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 775d1a350075811dc02ae33efd1a6ae05328c4ff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="b57e7-102">StatusBar-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b57e7-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="b57e7-103">Obwohl das <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelement das <xref:System.Windows.Forms.StatusBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.StatusBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b57e7-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="b57e7-104">Das Windows Forms-Steuerelement <xref:System.Windows.Forms.StatusBar> wird auf Formularen als Bereich verwendet, der in der Regel am unteren Rand eines Fensters angezeigt wird, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="b57e7-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="b57e7-105"><xref:System.Windows.Forms.StatusBar>Steuerelemente können Statusleistenbereichs darauf enthalten, Symbole, um anzugeben, Status oder eine Reihe von Symbolen in einer Animation, die darauf hinweisen, dass ein Prozess ausgeführt wird. Beispielsweise wird Microsoft Word zeigt an, dass das Dokument gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b57e7-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b57e7-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b57e7-106">In This Section</span></span>  
 [<span data-ttu-id="b57e7-107">Übersicht über das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b57e7-107">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="b57e7-108">Stellt die allgemeinen Konzepte von der <xref:System.Windows.Forms.StatusBar> -Steuerelement, das ermöglicht es Benutzern, relevanten Informationen für das Steuerelement anzuzeigen, die Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="b57e7-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="b57e7-109">Vorgehensweise: Hinzufügen von Bereichen zu einem StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b57e7-109">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="b57e7-110">Erläutert das Hinzufügen programmierbarer Bereiche der <xref:System.Windows.Forms.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b57e7-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="b57e7-111">Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="b57e7-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="b57e7-112">Erläutert das behandeln <xref:System.Windows.Forms.Control.Click> Ereignisse ausgelöst werden, aus der <xref:System.Windows.Forms.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b57e7-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="b57e7-113">Gewusst wie: Festlegen der Größe eines Statusleistenbereichs</span><span class="sxs-lookup"><span data-stu-id="b57e7-113">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="b57e7-114">Bietet Informationen über die Eigenschaften, die die Breite des Steuerelements, und ändern Sie die Größe eines Statusleistenbereichs Verhalten zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b57e7-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="b57e7-115">Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b57e7-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="b57e7-116">Erläutert, wie die Daten im Statusleistenbereichs programmgesteuert zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="b57e7-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b57e7-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="b57e7-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="b57e7-118">Enthält Referenzinformationen zur Klasse und zu ihren Membern.</span><span class="sxs-lookup"><span data-stu-id="b57e7-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="b57e7-119">Ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b57e7-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b57e7-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b57e7-120">Related Sections</span></span>  
 [<span data-ttu-id="b57e7-121">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b57e7-121">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="b57e7-122">Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="b57e7-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
