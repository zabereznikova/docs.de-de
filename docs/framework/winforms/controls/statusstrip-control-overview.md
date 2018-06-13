---
title: Übersicht über das StatusStrip-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: b915be2db6865a95d2d37afda58983dbb2edca27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537907"
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="9a6a7-102">Übersicht über das StatusStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9a6a7-102">StatusStrip Control Overview</span></span>
<span data-ttu-id="9a6a7-103">Ein <xref:System.Windows.Forms.StatusStrip>-Steuerelement zeigt Informationen zu einem Objekt an, das in einem <xref:System.Windows.Forms.Form> angezeigt wird, zu den Komponenten des Objekts oder Kontextinformationen, die sich auf die Operation dieses Objekts in Ihrer Anwendung beziehen.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="9a6a7-104">Ein <xref:System.Windows.Forms.StatusStrip>-Steuerelement besteht normalerweise aus <xref:System.Windows.Forms.ToolStripStatusLabel>-Objekten, von denen jedes Text, ein Symbol oder beides anzeigt.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="9a6a7-105">Der <xref:System.Windows.Forms.StatusStrip> kann zudem auch <xref:System.Windows.Forms.ToolStripDropDownButton>-, <xref:System.Windows.Forms.ToolStripSplitButton> und <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="9a6a7-106">Der standardmäßige <xref:System.Windows.Forms.StatusStrip> weist keine Panels auf.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="9a6a7-107">Verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>-Methode, um einem <xref:System.Windows.Forms.StatusStrip> Panels hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9a6a7-108">Es gibt umfassende Unterstützung für den Umgang mit <xref:System.Windows.Forms.StatusStrip>-Elementen und häufig verwendeten Befehle in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="9a6a7-109">Siehe auch [StatusStrip-Elementauflistungs-Editor](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [StatusStrip-Aufgaben-Dialogfeld](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9a6a7-109">Also see [StatusStrip Items Collection Editor](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [StatusStrip Tasks Dialog Box](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)).</span></span>  
  
 <span data-ttu-id="9a6a7-110">Obwohl <xref:System.Windows.Forms.StatusStrip> das <xref:System.Windows.Forms.StatusBar>-Steuerelement vorheriger Versionen ersetzt und erweitert, wird das <xref:System.Windows.Forms.StatusBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="9a6a7-111">Wichtige StatusStrip-Member</span><span class="sxs-lookup"><span data-stu-id="9a6a7-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="9a6a7-112">Name</span><span class="sxs-lookup"><span data-stu-id="9a6a7-112">Name</span></span>|<span data-ttu-id="9a6a7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a6a7-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="9a6a7-114">Ruft einen Wert ab, der angibt, ob <xref:System.Windows.Forms.StatusStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="9a6a7-115">Ruft einen Wert ab, der angibt, ob sich das <xref:System.Windows.Forms.StatusStrip>-Objekt in seinem <xref:System.Windows.Forms.ToolStripContainer>-Objekt von einem Ende zum anderen Ende erstreckt, oder legt diesen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="9a6a7-116">Wichtige StatusStrip-Begleitklassen</span><span class="sxs-lookup"><span data-stu-id="9a6a7-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="9a6a7-117">Name</span><span class="sxs-lookup"><span data-stu-id="9a6a7-117">Name</span></span>|<span data-ttu-id="9a6a7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a6a7-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="9a6a7-119">Stellt ein Panel in einem <xref:System.Windows.Forms.StatusStrip>-Steuerelement dar.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="9a6a7-120">Zeigt eine zugehörige <xref:System.Windows.Forms.ToolStripDropDown> an, aus der der Benutzer ein einzelnes Element auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="9a6a7-121">Stellt ein zweiteiliges Steuerelement dar, das aus einer Standardschaltfläche und einem Dropdownmenü besteht.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="9a6a7-122">Zeigt den Fortschrittsstatus eines Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="9a6a7-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a6a7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a6a7-123">See Also</span></span>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
