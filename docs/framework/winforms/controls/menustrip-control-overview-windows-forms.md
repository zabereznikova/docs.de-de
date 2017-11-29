---
title: "Übersicht über das MenuStrip-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06cd4e812f4acf546dad577a2e1ddc571281ebe3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="e8fcb-102">Übersicht über das MenuStrip-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e8fcb-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="e8fcb-103">Menüs Funktionalität verfügbar machen, die Benutzern von Befehlen, die durch eine allgemeine Thematik gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="e8fcb-104">Die <xref:System.Windows.Forms.MenuStrip> -Steuerelement ist in dieser Version von Visual Studio und .NET Framework neu.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-104">The <xref:System.Windows.Forms.MenuStrip> control is new to this version of Visual Studio and the .NET Framework.</span></span> <span data-ttu-id="e8fcb-105">Mit dem Steuerelement können Sie problemlos Menüs wie in Microsoft Office erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-105">With the control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="e8fcb-106">Die <xref:System.Windows.Forms.MenuStrip> Steuerelement unterstützt, die Multiple Document Interface (MDI) und das Zusammenführen von Menüs, QuickInfos und Überlauf.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="e8fcb-107">Sie können die Verwendbarkeit und Lesbarkeit des Menüs durch Hinzufügen von Zugriffstasten, Tastenkombinationen, Häkchen, Bildern und Trennlinien verbessern.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="e8fcb-108">Die <xref:System.Windows.Forms.MenuStrip> -Steuerelement ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.MainMenu> steuern; allerdings die <xref:System.Windows.Forms.MainMenu> Steuerelement wird für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="e8fcb-109">Verwendungsmöglichkeiten für das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e8fcb-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="e8fcb-110">Verwenden der <xref:System.Windows.Forms.MenuStrip> zu steuern:</span><span class="sxs-lookup"><span data-stu-id="e8fcb-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
-   <span data-ttu-id="e8fcb-111">Erstellen Sie leicht anpassbare, häufig verwendete Menüs, die unterstützen erweiterte Benutzer Schnittstelle und das Layout-Funktionen, z. B. Text und Bild Sortierung und Ausrichtung, Drag & Drop-Vorgänge MDI, Überlauf und alternative Modi für den Zugriff auf Befehle im Menü.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
-   <span data-ttu-id="e8fcb-112">Das typische Aussehen und Verhalten des Betriebssystems zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
-   <span data-ttu-id="e8fcb-113">Behandeln Sie Ereignisse einheitlich für alle Container und enthaltene Elemente, auf die gleiche Weise behandeln von Ereignissen für andere Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="e8fcb-114">Die folgende Tabelle zeigt einige besonders wichtigen Eigenschaften der <xref:System.Windows.Forms.MenuStrip> und die zugehörigen Klassen.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="e8fcb-115">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e8fcb-115">Property</span></span>|<span data-ttu-id="e8fcb-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8fcb-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="e8fcb-117">Ruft ab oder legt die <xref:System.Windows.Forms.ToolStripMenuItem> , wird verwendet, um eine Liste von untergeordneten MDI-Formularen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="e8fcb-118">Ruft ab oder legt sie fest, wie untergeordnete Menüs mit übergeordneten Menüs im MDI-Anwendungen zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="e8fcb-119">Ruft ab oder legt die Position eines zusammengeführten Elements in einem Menü im MDI-Anwendungen fest.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="e8fcb-120">Ruft ab oder legt einen Wert, der angibt, ob das Formular ein Container für untergeordnete MDI-Formulare ist.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="e8fcb-121">Ruft ab oder legt einen Wert, der angibt, ob QuickInfos, für angezeigt werden die <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="e8fcb-122">Ruft einen Wert ab, der angibt, ob <xref:System.Windows.Forms.MenuStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="e8fcb-123">Ruft ab oder legt ihn fest zugeordneten Tastenkombinationen der <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="e8fcb-124">Ruft ab oder legt ein Wert, der angibt, ob die Tastenkombination zugeordnet sind die <xref:System.Windows.Forms.ToolStripMenuItem> abfragedarstellung neben der <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="e8fcb-125">Die folgende Tabelle zeigt die wichtigen <xref:System.Windows.Forms.MenuStrip> Assistentenklassen.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="e8fcb-126">Klasse</span><span class="sxs-lookup"><span data-stu-id="e8fcb-126">Class</span></span>|<span data-ttu-id="e8fcb-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8fcb-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="e8fcb-128">Stellt eine auswählbare Option angezeigt, die auf eine <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="e8fcb-129">Stellt ein Kontextmenü dar.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="e8fcb-130">Stellt ein Steuerelement, können ein einzelnes Element aus einer Liste auszuwählen, die angezeigt wird, wenn der Benutzer klickt auf, eine <xref:System.Windows.Forms.ToolStripDropDownButton> oder ein Menüelement.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="e8fcb-131">Stellt grundlegende Funktionen für Steuerelemente abgeleitet <xref:System.Windows.Forms.ToolStripItem> , Dropdownelementen beim anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e8fcb-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8fcb-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8fcb-132">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
