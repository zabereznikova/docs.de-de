---
title: StatusBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
ms.openlocfilehash: 72a93fc32715596efc7fb0f8b941e62f7019d06c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964418"
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="62bb5-102">StatusBar-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="62bb5-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="62bb5-103">Obwohl das <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelement das <xref:System.Windows.Forms.StatusBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.StatusBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="62bb5-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="62bb5-104">Das Windows Forms-Steuerelement <xref:System.Windows.Forms.StatusBar> wird auf Formularen als Bereich verwendet, der in der Regel am unteren Rand eines Fensters angezeigt wird, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="62bb5-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="62bb5-105"><xref:System.Windows.Forms.StatusBar>Steuerelemente können über Status leisten Panels verfügen, in denen Symbole angezeigt werden, um den Zustand anzugeben, oder eine Reihe von Symbolen in einer Animation, die darauf hinweisen, dass ein Prozess funktioniert. beispielsweise Microsoft Word, das angibt, dass das Dokument gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="62bb5-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62bb5-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62bb5-106">In This Section</span></span>  
 [<span data-ttu-id="62bb5-107">Übersicht über das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="62bb5-107">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="62bb5-108">Führt die allgemeinen Konzepte des <xref:System.Windows.Forms.StatusBar> -Steuer Elements ein, das es Benutzern ermöglicht, relevante Informationen für das Steuerelement zu sehen, das den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="62bb5-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="62bb5-109">Vorgehensweise: Hinzufügen von Panels zu einem StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="62bb5-109">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="62bb5-110">Erläutert, wie dem <xref:System.Windows.Forms.StatusBar> -Steuerelement programmierbare Panels hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="62bb5-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="62bb5-111">Vorgehensweise: Legen Sie fest, auf welchem Bereich im Windows Forms StatusBar-Steuerelement geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="62bb5-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="62bb5-112">Erläutert das behandeln <xref:System.Windows.Forms.Control.Click> von Ereignissen, die <xref:System.Windows.Forms.StatusBar> vom-Steuerelement ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="62bb5-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="62bb5-113">Vorgehensweise: Festlegen der Größe von Status leisten Panels</span><span class="sxs-lookup"><span data-stu-id="62bb5-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="62bb5-114">Enthält Details zu den Eigenschaften, die die Breite und Größenänderung von Status leisten Panels zur Laufzeit steuern.</span><span class="sxs-lookup"><span data-stu-id="62bb5-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="62bb5-115">Exemplarische Vorgehensweise: Aktualisieren von Status leisten Informationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="62bb5-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="62bb5-116">Erläutert, wie die Daten in Status leisten Panels Programm gesteuert gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="62bb5-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="62bb5-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="62bb5-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="62bb5-118">Enthält Referenzinformationen zur Klasse und zu ihren Membern.</span><span class="sxs-lookup"><span data-stu-id="62bb5-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="62bb5-119">Ersetzt und fügt Funktionen zum <xref:System.Windows.Forms.StatusBar> -Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="62bb5-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="62bb5-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="62bb5-120">Related Sections</span></span>  
 [<span data-ttu-id="62bb5-121">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="62bb5-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="62bb5-122">Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="62bb5-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
