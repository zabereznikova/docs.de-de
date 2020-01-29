---
title: Übersicht über das MenuStrip-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734469"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="60bf7-102">Übersicht über das MenuStrip-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="60bf7-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="60bf7-103">Menüs machen die Funktionalität für Ihre Benutzer verfügbar, indem Sie Befehle halten, die nach einem allgemeinen Design gruppiert sind.</span><span class="sxs-lookup"><span data-stu-id="60bf7-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="60bf7-104">Das <xref:System.Windows.Forms.MenuStrip>-Steuerelement wurde in Version 2,0 des .NET Framework eingeführt.</span><span class="sxs-lookup"><span data-stu-id="60bf7-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="60bf7-105">Mit dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie problemlos Menüs erstellen, die sich in Microsoft Office befinden.</span><span class="sxs-lookup"><span data-stu-id="60bf7-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="60bf7-106">Das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt die MDI (Multiple Document Interface) und die Zusammenführung von Menüs, Quick Infos und Überlauf.</span><span class="sxs-lookup"><span data-stu-id="60bf7-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="60bf7-107">Sie können die Benutzerfreundlichkeit und Lesbarkeit Ihrer Menüs verbessern, indem Sie Zugriffstasten, Tastenkombinationen, Häkchen, Bilder und Trenn leisten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60bf7-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="60bf7-108">Das <xref:System.Windows.Forms.MenuStrip> Steuerelement ersetzt das <xref:System.Windows.Forms.MainMenu> Steuerelement und fügt es hinzu. Das <xref:System.Windows.Forms.MainMenu> Steuerelement wird jedoch aus Gründen der Abwärtskompatibilität und zukünftiger Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="60bf7-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="60bf7-109">Möglichkeiten der Verwendung des MenuStrip-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="60bf7-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="60bf7-110">Verwenden Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="60bf7-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="60bf7-111">Erstellen Sie problemlos angepasste, häufig verwendete Menüs, die erweiterte Benutzeroberflächen-und Layoutfeatures unterstützen, wie z. b. Text-und Bild Anordnung und-Ausrichtung, Drag & Drop-Vorgänge, MDI, Überlauf und Alternative Zugriffsmöglichkeiten für Menübefehle.</span><span class="sxs-lookup"><span data-stu-id="60bf7-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="60bf7-112">Unterstützen Sie das typische Aussehen und Verhalten des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="60bf7-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="60bf7-113">Behandeln Sie Ereignisse konsistent für alle Container und enthaltenen Elemente auf die gleiche Weise wie Ereignisse für andere Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="60bf7-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="60bf7-114">In der folgenden Tabelle werden einige besonders wichtige Eigenschaften von <xref:System.Windows.Forms.MenuStrip> und zugeordneten Klassen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60bf7-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="60bf7-115">Die Eigenschaften-</span><span class="sxs-lookup"><span data-stu-id="60bf7-115">Property</span></span>|<span data-ttu-id="60bf7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60bf7-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="60bf7-117">Ruft den <xref:System.Windows.Forms.ToolStripMenuItem> ab, mit dem eine Liste von untergeordneten MDI-Formularen angezeigt wird, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="60bf7-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="60bf7-118">Ruft ab oder legt fest, wie untergeordnete Menüs mit übergeordneten Menüs in MDI-Anwendungen zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="60bf7-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="60bf7-119">Ruft die Position eines zusammengeführten Elements in einem Menü in MDI-Anwendungen ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="60bf7-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="60bf7-120">Dient zum Abrufen oder Festlegen eines Werts, der angibt, ob das Formular ein Container für untergeordnete MDI-Formulare ist.</span><span class="sxs-lookup"><span data-stu-id="60bf7-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="60bf7-121">Ruft einen Wert ab, der angibt, ob Quick Infos für das <xref:System.Windows.Forms.MenuStrip>angezeigt werden, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="60bf7-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="60bf7-122">Ruft einen Wert ab, der angibt, ob <xref:System.Windows.Forms.MenuStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="60bf7-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="60bf7-123">Ruft die dem <xref:System.Windows.Forms.ToolStripMenuItem>zugeordneten Tastenkombinationen ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="60bf7-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="60bf7-124">Ruft einen Wert ab, der angibt, ob die dem <xref:System.Windows.Forms.ToolStripMenuItem> zugeordneten Tastenkombinationen neben dem <xref:System.Windows.Forms.ToolStripMenuItem>angezeigt werden, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="60bf7-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="60bf7-125">In der folgenden Tabelle sind die wichtigen <xref:System.Windows.Forms.MenuStrip>-Begleit Klassen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="60bf7-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="60bf7-126">Klasse</span><span class="sxs-lookup"><span data-stu-id="60bf7-126">Class</span></span>|<span data-ttu-id="60bf7-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60bf7-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="60bf7-128">Stellt eine auswählbare Option dar, die auf einem <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.ContextMenuStrip>angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="60bf7-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="60bf7-129">Stellt ein Kontextmenü dar.</span><span class="sxs-lookup"><span data-stu-id="60bf7-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="60bf7-130">Stellt ein Steuerelement dar, mit dem der Benutzer ein einzelnes Element aus einer Liste auswählen kann, die angezeigt wird, wenn der Benutzer auf eine <xref:System.Windows.Forms.ToolStripDropDownButton> oder auf ein höheres Menü Element klickt.</span><span class="sxs-lookup"><span data-stu-id="60bf7-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="60bf7-131">Stellt grundlegende Funktionen für Steuerelemente bereit, die von <xref:System.Windows.Forms.ToolStripItem> abgeleitet werden, die Dropdown Elemente beim Klicken anzeigen</span><span class="sxs-lookup"><span data-stu-id="60bf7-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60bf7-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60bf7-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
