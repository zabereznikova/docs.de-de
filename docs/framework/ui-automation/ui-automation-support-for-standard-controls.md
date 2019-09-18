---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 6cbf31c8a1cdf6e853e56445d22f4a7513bd1859
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71041995"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="ba80f-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="ba80f-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="ba80f-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ba80f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ba80f-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="ba80f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ba80f-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba80f-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="ba80f-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="ba80f-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="ba80f-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba80f-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="ba80f-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ba80f-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="ba80f-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ba80f-109">Win32 Controls</span></span>  
 <span data-ttu-id="ba80f-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ba80f-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="ba80f-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="ba80f-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="ba80f-112">Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).</span><span class="sxs-lookup"><span data-stu-id="ba80f-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="ba80f-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ba80f-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="ba80f-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="ba80f-114">Class name</span></span>|<span data-ttu-id="ba80f-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="ba80f-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="ba80f-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-116">Button</span></span>|<span data-ttu-id="ba80f-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-117">Button</span></span>|  
|<span data-ttu-id="ba80f-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-118">Button</span></span>|<span data-ttu-id="ba80f-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ba80f-119">RadioButton</span></span>|  
|<span data-ttu-id="ba80f-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-120">Button</span></span>|<span data-ttu-id="ba80f-121">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="ba80f-121">Group</span></span>|  
|<span data-ttu-id="ba80f-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-122">Button</span></span>|<span data-ttu-id="ba80f-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-123">CheckBox</span></span>|  
|<span data-ttu-id="ba80f-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-124">Button</span></span>|<span data-ttu-id="ba80f-125">Link</span><span class="sxs-lookup"><span data-stu-id="ba80f-125">Hyperlink</span></span>|  
|<span data-ttu-id="ba80f-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-126">Button</span></span>|<span data-ttu-id="ba80f-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="ba80f-127">SplitButton</span></span>|  
|<span data-ttu-id="ba80f-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-128">Button</span></span>|<span data-ttu-id="ba80f-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-129">CheckBox</span></span>|  
|<span data-ttu-id="ba80f-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="ba80f-130">ComboBoxEx32</span></span>|<span data-ttu-id="ba80f-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-131">ComboBox</span></span>|  
|<span data-ttu-id="ba80f-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-132">ComboBox</span></span>|<span data-ttu-id="ba80f-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-133">ComboBox</span></span>|  
|<span data-ttu-id="ba80f-134">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="ba80f-134">Edit</span></span>|<span data-ttu-id="ba80f-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="ba80f-135">Document</span></span>|  
|<span data-ttu-id="ba80f-136">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="ba80f-136">Edit</span></span>|<span data-ttu-id="ba80f-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="ba80f-137">Edit</span></span>|  
|<span data-ttu-id="ba80f-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="ba80f-138">SysLink</span></span>|<span data-ttu-id="ba80f-139">Link</span><span class="sxs-lookup"><span data-stu-id="ba80f-139">Hyperlink</span></span>|  
|<span data-ttu-id="ba80f-140">Statisch</span><span class="sxs-lookup"><span data-stu-id="ba80f-140">Static</span></span>|<span data-ttu-id="ba80f-141">Text</span><span class="sxs-lookup"><span data-stu-id="ba80f-141">Text</span></span>|  
|<span data-ttu-id="ba80f-142">Statisch</span><span class="sxs-lookup"><span data-stu-id="ba80f-142">Static</span></span>|<span data-ttu-id="ba80f-143">Bild</span><span class="sxs-lookup"><span data-stu-id="ba80f-143">Image</span></span>|  
|<span data-ttu-id="ba80f-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="ba80f-144">SysIPAddress32</span></span>|<span data-ttu-id="ba80f-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="ba80f-145">Custom</span></span>|  
|<span data-ttu-id="ba80f-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="ba80f-146">SysHeader32</span></span>|<span data-ttu-id="ba80f-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="ba80f-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="ba80f-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="ba80f-148">SysListView32</span></span>|<span data-ttu-id="ba80f-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="ba80f-149">DataGrid</span></span>|  
|<span data-ttu-id="ba80f-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="ba80f-150">SysListView32</span></span>|<span data-ttu-id="ba80f-151">Liste</span><span class="sxs-lookup"><span data-stu-id="ba80f-151">List</span></span>|  
|<span data-ttu-id="ba80f-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-152">ListBox</span></span>|<span data-ttu-id="ba80f-153">Liste</span><span class="sxs-lookup"><span data-stu-id="ba80f-153">List</span></span>|  
|<span data-ttu-id="ba80f-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-154">ListBox</span></span>|<span data-ttu-id="ba80f-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="ba80f-155">ListItem</span></span>|  
|<span data-ttu-id="ba80f-156">#32768</span><span class="sxs-lookup"><span data-stu-id="ba80f-156">#32768</span></span>|<span data-ttu-id="ba80f-157">Menü</span><span class="sxs-lookup"><span data-stu-id="ba80f-157">Menu</span></span>|  
|<span data-ttu-id="ba80f-158">#32768</span><span class="sxs-lookup"><span data-stu-id="ba80f-158">#32768</span></span>|<span data-ttu-id="ba80f-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="ba80f-159">MenuItem</span></span>|  
|<span data-ttu-id="ba80f-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="ba80f-160">msctls_progress32</span></span>|<span data-ttu-id="ba80f-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-161">ProgressBar</span></span>|  
|<span data-ttu-id="ba80f-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="ba80f-162">RichEdit</span></span>|<span data-ttu-id="ba80f-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="ba80f-163">Document.</span></span> <span data-ttu-id="ba80f-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="ba80f-164">See note.</span></span>|  
|<span data-ttu-id="ba80f-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="ba80f-165">RichEdit20A</span></span>|<span data-ttu-id="ba80f-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="ba80f-166">Document</span></span>|  
|<span data-ttu-id="ba80f-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="ba80f-167">RichEdit20W</span></span>|<span data-ttu-id="ba80f-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="ba80f-168">Document</span></span>|  
|<span data-ttu-id="ba80f-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="ba80f-169">RichEdit50W</span></span>|<span data-ttu-id="ba80f-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="ba80f-170">Document</span></span>|  
|<span data-ttu-id="ba80f-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-171">ScrollBar</span></span>|<span data-ttu-id="ba80f-172">Slider</span><span class="sxs-lookup"><span data-stu-id="ba80f-172">Slider</span></span>|  
|<span data-ttu-id="ba80f-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="ba80f-173">msctls_trackbar32</span></span>|<span data-ttu-id="ba80f-174">Slider</span><span class="sxs-lookup"><span data-stu-id="ba80f-174">Slider</span></span>|  
|<span data-ttu-id="ba80f-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="ba80f-175">msctls_updown32</span></span>|<span data-ttu-id="ba80f-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="ba80f-176">Spinner</span></span>|  
|<span data-ttu-id="ba80f-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="ba80f-177">msctls_statusbar32</span></span>|<span data-ttu-id="ba80f-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-178">StatusBar</span></span>|  
|<span data-ttu-id="ba80f-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="ba80f-179">SysTabControl32</span></span>|<span data-ttu-id="ba80f-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="ba80f-180">Tab</span></span>|  
|<span data-ttu-id="ba80f-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="ba80f-181">SysTabControl32</span></span>|<span data-ttu-id="ba80f-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="ba80f-182">TabItem</span></span>|  
|<span data-ttu-id="ba80f-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ba80f-183">ToolbarWindow32</span></span>|<span data-ttu-id="ba80f-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-184">ToolBar</span></span>|  
|<span data-ttu-id="ba80f-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ba80f-185">ToolbarWindow32</span></span>|<span data-ttu-id="ba80f-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="ba80f-186">MenuItem</span></span>|  
|<span data-ttu-id="ba80f-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ba80f-187">ToolbarWindow32</span></span>|<span data-ttu-id="ba80f-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-188">Button</span></span>|  
|<span data-ttu-id="ba80f-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ba80f-189">ToolbarWindow32</span></span>|<span data-ttu-id="ba80f-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-190">CheckBox</span></span>|  
|<span data-ttu-id="ba80f-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ba80f-191">ToolbarWindow32</span></span>|<span data-ttu-id="ba80f-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ba80f-192">RadioButton</span></span>|  
|<span data-ttu-id="ba80f-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ba80f-193">ToolbarWindow32</span></span>|<span data-ttu-id="ba80f-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="ba80f-194">Separator</span></span>|  
|<span data-ttu-id="ba80f-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="ba80f-195">tooltips_class32</span></span>|<span data-ttu-id="ba80f-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="ba80f-196">ToolTip</span></span>|  
|<span data-ttu-id="ba80f-197">#32774</span><span class="sxs-lookup"><span data-stu-id="ba80f-197">#32774</span></span>|<span data-ttu-id="ba80f-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="ba80f-198">ToolTip</span></span>|  
|<span data-ttu-id="ba80f-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="ba80f-199">ReBarWindow32</span></span>|<span data-ttu-id="ba80f-200">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="ba80f-200">Toolbar</span></span>|  
|<span data-ttu-id="ba80f-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="ba80f-201">SysTreeView32</span></span>|<span data-ttu-id="ba80f-202">trEE</span><span class="sxs-lookup"><span data-stu-id="ba80f-202">Tree</span></span>|  
|<span data-ttu-id="ba80f-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="ba80f-203">SysTreeView32</span></span>|<span data-ttu-id="ba80f-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="ba80f-204">TreeItem</span></span>|  
  
 <span data-ttu-id="ba80f-205">**Hinweis** Das RichEdit-Steuerelement wird nur für mit [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] ausgelieferte Versionen unterstützt (in „RichEd20.dll“ ab Version 3.1 und „MsftEdit.dll“ ab Version 4.1).</span><span class="sxs-lookup"><span data-stu-id="ba80f-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="ba80f-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ba80f-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="ba80f-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="ba80f-207">Class name</span></span>|<span data-ttu-id="ba80f-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="ba80f-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="ba80f-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="ba80f-209">SysAnimate32</span></span>|<span data-ttu-id="ba80f-210">Bild</span><span class="sxs-lookup"><span data-stu-id="ba80f-210">Image</span></span>|  
|<span data-ttu-id="ba80f-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="ba80f-211">SysPager</span></span>|<span data-ttu-id="ba80f-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="ba80f-212">Spinner</span></span>|  
|<span data-ttu-id="ba80f-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="ba80f-213">SysDateTimePick32</span></span>|<span data-ttu-id="ba80f-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="ba80f-214">Custom</span></span>|  
|<span data-ttu-id="ba80f-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="ba80f-215">SysMonthCal32</span></span>|<span data-ttu-id="ba80f-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="ba80f-216">Calendar</span></span>|  
|<span data-ttu-id="ba80f-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="ba80f-217">MS_WINNOTE</span></span>|<span data-ttu-id="ba80f-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="ba80f-218">Tooltip</span></span>|  
|<span data-ttu-id="ba80f-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="ba80f-219">VBBubble</span></span>|<span data-ttu-id="ba80f-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="ba80f-220">Tooltip</span></span>|  
|<span data-ttu-id="ba80f-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="ba80f-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="ba80f-222">Slider</span><span class="sxs-lookup"><span data-stu-id="ba80f-222">Slider</span></span>|  
|<span data-ttu-id="ba80f-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="ba80f-223">SuperGrid</span></span>|<span data-ttu-id="ba80f-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="ba80f-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="ba80f-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ba80f-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="ba80f-226">Windows Forms-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über Client seitige Anbieter in "UIAutomationClientsideProviders. dll" für verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ba80f-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="ba80f-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="ba80f-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="ba80f-228">In der Regel werden Windows Forms Steuerelemente, die verwaltete [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Wrapper für allgemeine Steuerelemente [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]sind, von unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ba80f-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="ba80f-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ba80f-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="ba80f-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="ba80f-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="ba80f-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ba80f-231">Button</span></span>|  
|<span data-ttu-id="ba80f-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-232">CheckBox</span></span>|  
|<span data-ttu-id="ba80f-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-233">CheckedListBox</span></span>|  
|<span data-ttu-id="ba80f-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="ba80f-234">ColorDialog</span></span>|  
|<span data-ttu-id="ba80f-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-235">ComboBox</span></span>|  
|<span data-ttu-id="ba80f-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="ba80f-236">FolderBrowser</span></span>|  
|<span data-ttu-id="ba80f-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="ba80f-237">FontDialog</span></span>|  
|<span data-ttu-id="ba80f-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-238">GroupBox</span></span>|  
|<span data-ttu-id="ba80f-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-239">HscrollBar</span></span>|  
|<span data-ttu-id="ba80f-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="ba80f-240">ImageList</span></span>|  
|<span data-ttu-id="ba80f-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="ba80f-241">Label</span></span>|  
|<span data-ttu-id="ba80f-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-242">ListBox</span></span>|  
|<span data-ttu-id="ba80f-243">ListView</span><span class="sxs-lookup"><span data-stu-id="ba80f-243">ListView</span></span>|  
|<span data-ttu-id="ba80f-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="ba80f-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="ba80f-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="ba80f-245">MonthCalendar</span></span>|  
|<span data-ttu-id="ba80f-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="ba80f-246">NotifyIcon</span></span>|  
|<span data-ttu-id="ba80f-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="ba80f-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="ba80f-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="ba80f-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="ba80f-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="ba80f-249">PrintDialog</span></span>|  
|<span data-ttu-id="ba80f-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-250">ProgressBar</span></span>|  
|<span data-ttu-id="ba80f-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ba80f-251">RadioButton</span></span>|  
|<span data-ttu-id="ba80f-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-252">RichTextBox</span></span>|  
|<span data-ttu-id="ba80f-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="ba80f-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="ba80f-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="ba80f-254">ScrollableControl</span></span>|  
|<span data-ttu-id="ba80f-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="ba80f-255">SoundPlayer</span></span>|  
|<span data-ttu-id="ba80f-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-256">StatusBar</span></span>|  
|<span data-ttu-id="ba80f-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="ba80f-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="ba80f-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-258">TextBox</span></span>|  
|<span data-ttu-id="ba80f-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="ba80f-259">Timer</span></span>|  
|<span data-ttu-id="ba80f-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-260">Toolbar</span></span>|  
|<span data-ttu-id="ba80f-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="ba80f-261">ToolTip</span></span>|  
|<span data-ttu-id="ba80f-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-262">TrackBar</span></span>|  
|<span data-ttu-id="ba80f-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="ba80f-263">TreeView</span></span>|  
|<span data-ttu-id="ba80f-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="ba80f-264">VscrollBar</span></span>|  
|<span data-ttu-id="ba80f-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="ba80f-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="ba80f-266">Die folgenden Steuerelemente sind [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] nur für die Unterstützung von Microsoft Active Accessibility verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba80f-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="ba80f-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba80f-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="ba80f-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="ba80f-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="ba80f-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="ba80f-269">BindingSource</span></span>|  
|<span data-ttu-id="ba80f-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="ba80f-270">DataGrid</span></span>|  
|<span data-ttu-id="ba80f-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="ba80f-271">DataGridView</span></span>|  
|<span data-ttu-id="ba80f-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="ba80f-272">DataNavigator</span></span>|  
|<span data-ttu-id="ba80f-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="ba80f-273">DomainUpDown</span></span>|  
|<span data-ttu-id="ba80f-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="ba80f-274">ErrorProvider</span></span>|  
|<span data-ttu-id="ba80f-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ba80f-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="ba80f-276">Formular</span><span class="sxs-lookup"><span data-stu-id="ba80f-276">Form</span></span>|  
|<span data-ttu-id="ba80f-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="ba80f-277">LinkLabel</span></span>|  
|<span data-ttu-id="ba80f-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="ba80f-278">HelpProvider</span></span>|  
|<span data-ttu-id="ba80f-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="ba80f-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="ba80f-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="ba80f-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="ba80f-281">NumericUpDown</span></span>|  
|<span data-ttu-id="ba80f-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="ba80f-282">Panel</span></span>|  
|<span data-ttu-id="ba80f-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="ba80f-283">PictureBox</span></span>|  
|<span data-ttu-id="ba80f-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="ba80f-284">PrintDocument</span></span>|  
|<span data-ttu-id="ba80f-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="ba80f-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="ba80f-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="ba80f-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="ba80f-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="ba80f-287">PropertyGrid</span></span>|  
|<span data-ttu-id="ba80f-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="ba80f-288">UserControl</span></span>|  
|<span data-ttu-id="ba80f-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ba80f-289">ToolStrip</span></span>|  
|<span data-ttu-id="ba80f-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ba80f-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="ba80f-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="ba80f-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="ba80f-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="ba80f-292">Splitter</span></span>|  
|<span data-ttu-id="ba80f-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="ba80f-293">RaftingContainer</span></span>|  
|<span data-ttu-id="ba80f-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="ba80f-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba80f-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba80f-295">See also</span></span>

- [<span data-ttu-id="ba80f-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ba80f-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
