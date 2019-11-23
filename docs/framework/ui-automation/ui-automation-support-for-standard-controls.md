---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441227"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="87ff8-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="87ff8-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="87ff8-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="87ff8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="87ff8-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="87ff8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="87ff8-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87ff8-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="87ff8-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="87ff8-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="87ff8-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87ff8-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="87ff8-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="87ff8-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="87ff8-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="87ff8-109">Win32 Controls</span></span>  
 <span data-ttu-id="87ff8-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="87ff8-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="87ff8-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="87ff8-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="87ff8-112">Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).</span><span class="sxs-lookup"><span data-stu-id="87ff8-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="87ff8-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="87ff8-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="87ff8-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="87ff8-114">Class name</span></span>|<span data-ttu-id="87ff8-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="87ff8-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="87ff8-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-116">Button</span></span>|<span data-ttu-id="87ff8-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-117">Button</span></span>|  
|<span data-ttu-id="87ff8-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-118">Button</span></span>|<span data-ttu-id="87ff8-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="87ff8-119">RadioButton</span></span>|  
|<span data-ttu-id="87ff8-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-120">Button</span></span>|<span data-ttu-id="87ff8-121">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="87ff8-121">Group</span></span>|  
|<span data-ttu-id="87ff8-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-122">Button</span></span>|<span data-ttu-id="87ff8-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-123">CheckBox</span></span>|  
|<span data-ttu-id="87ff8-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-124">Button</span></span>|<span data-ttu-id="87ff8-125">Link</span><span class="sxs-lookup"><span data-stu-id="87ff8-125">Hyperlink</span></span>|  
|<span data-ttu-id="87ff8-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-126">Button</span></span>|<span data-ttu-id="87ff8-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="87ff8-127">SplitButton</span></span>|  
|<span data-ttu-id="87ff8-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-128">Button</span></span>|<span data-ttu-id="87ff8-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-129">CheckBox</span></span>|  
|<span data-ttu-id="87ff8-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="87ff8-130">ComboBoxEx32</span></span>|<span data-ttu-id="87ff8-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-131">ComboBox</span></span>|  
|<span data-ttu-id="87ff8-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-132">ComboBox</span></span>|<span data-ttu-id="87ff8-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-133">ComboBox</span></span>|  
|<span data-ttu-id="87ff8-134">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="87ff8-134">Edit</span></span>|<span data-ttu-id="87ff8-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="87ff8-135">Document</span></span>|  
|<span data-ttu-id="87ff8-136">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="87ff8-136">Edit</span></span>|<span data-ttu-id="87ff8-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="87ff8-137">Edit</span></span>|  
|<span data-ttu-id="87ff8-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="87ff8-138">SysLink</span></span>|<span data-ttu-id="87ff8-139">Link</span><span class="sxs-lookup"><span data-stu-id="87ff8-139">Hyperlink</span></span>|  
|<span data-ttu-id="87ff8-140">Static</span><span class="sxs-lookup"><span data-stu-id="87ff8-140">Static</span></span>|<span data-ttu-id="87ff8-141">Text</span><span class="sxs-lookup"><span data-stu-id="87ff8-141">Text</span></span>|  
|<span data-ttu-id="87ff8-142">Static</span><span class="sxs-lookup"><span data-stu-id="87ff8-142">Static</span></span>|<span data-ttu-id="87ff8-143">Bild</span><span class="sxs-lookup"><span data-stu-id="87ff8-143">Image</span></span>|  
|<span data-ttu-id="87ff8-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="87ff8-144">SysIPAddress32</span></span>|<span data-ttu-id="87ff8-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="87ff8-145">Custom</span></span>|  
|<span data-ttu-id="87ff8-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="87ff8-146">SysHeader32</span></span>|<span data-ttu-id="87ff8-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="87ff8-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="87ff8-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="87ff8-148">SysListView32</span></span>|<span data-ttu-id="87ff8-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="87ff8-149">DataGrid</span></span>|  
|<span data-ttu-id="87ff8-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="87ff8-150">SysListView32</span></span>|<span data-ttu-id="87ff8-151">Liste</span><span class="sxs-lookup"><span data-stu-id="87ff8-151">List</span></span>|  
|<span data-ttu-id="87ff8-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-152">ListBox</span></span>|<span data-ttu-id="87ff8-153">Liste</span><span class="sxs-lookup"><span data-stu-id="87ff8-153">List</span></span>|  
|<span data-ttu-id="87ff8-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-154">ListBox</span></span>|<span data-ttu-id="87ff8-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="87ff8-155">ListItem</span></span>|  
|<span data-ttu-id="87ff8-156">#32768</span><span class="sxs-lookup"><span data-stu-id="87ff8-156">#32768</span></span>|<span data-ttu-id="87ff8-157">Menü</span><span class="sxs-lookup"><span data-stu-id="87ff8-157">Menu</span></span>|  
|<span data-ttu-id="87ff8-158">#32768</span><span class="sxs-lookup"><span data-stu-id="87ff8-158">#32768</span></span>|<span data-ttu-id="87ff8-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="87ff8-159">MenuItem</span></span>|  
|<span data-ttu-id="87ff8-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="87ff8-160">msctls_progress32</span></span>|<span data-ttu-id="87ff8-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-161">ProgressBar</span></span>|  
|<span data-ttu-id="87ff8-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="87ff8-162">RichEdit</span></span>|<span data-ttu-id="87ff8-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="87ff8-163">Document.</span></span> <span data-ttu-id="87ff8-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="87ff8-164">See note.</span></span>|  
|<span data-ttu-id="87ff8-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="87ff8-165">RichEdit20A</span></span>|<span data-ttu-id="87ff8-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="87ff8-166">Document</span></span>|  
|<span data-ttu-id="87ff8-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="87ff8-167">RichEdit20W</span></span>|<span data-ttu-id="87ff8-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="87ff8-168">Document</span></span>|  
|<span data-ttu-id="87ff8-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="87ff8-169">RichEdit50W</span></span>|<span data-ttu-id="87ff8-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="87ff8-170">Document</span></span>|  
|<span data-ttu-id="87ff8-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-171">ScrollBar</span></span>|<span data-ttu-id="87ff8-172">Slider</span><span class="sxs-lookup"><span data-stu-id="87ff8-172">Slider</span></span>|  
|<span data-ttu-id="87ff8-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="87ff8-173">msctls_trackbar32</span></span>|<span data-ttu-id="87ff8-174">Slider</span><span class="sxs-lookup"><span data-stu-id="87ff8-174">Slider</span></span>|  
|<span data-ttu-id="87ff8-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="87ff8-175">msctls_updown32</span></span>|<span data-ttu-id="87ff8-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="87ff8-176">Spinner</span></span>|  
|<span data-ttu-id="87ff8-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="87ff8-177">msctls_statusbar32</span></span>|<span data-ttu-id="87ff8-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-178">StatusBar</span></span>|  
|<span data-ttu-id="87ff8-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="87ff8-179">SysTabControl32</span></span>|<span data-ttu-id="87ff8-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="87ff8-180">Tab</span></span>|  
|<span data-ttu-id="87ff8-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="87ff8-181">SysTabControl32</span></span>|<span data-ttu-id="87ff8-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="87ff8-182">TabItem</span></span>|  
|<span data-ttu-id="87ff8-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="87ff8-183">ToolbarWindow32</span></span>|<span data-ttu-id="87ff8-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-184">ToolBar</span></span>|  
|<span data-ttu-id="87ff8-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="87ff8-185">ToolbarWindow32</span></span>|<span data-ttu-id="87ff8-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="87ff8-186">MenuItem</span></span>|  
|<span data-ttu-id="87ff8-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="87ff8-187">ToolbarWindow32</span></span>|<span data-ttu-id="87ff8-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-188">Button</span></span>|  
|<span data-ttu-id="87ff8-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="87ff8-189">ToolbarWindow32</span></span>|<span data-ttu-id="87ff8-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-190">CheckBox</span></span>|  
|<span data-ttu-id="87ff8-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="87ff8-191">ToolbarWindow32</span></span>|<span data-ttu-id="87ff8-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="87ff8-192">RadioButton</span></span>|  
|<span data-ttu-id="87ff8-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="87ff8-193">ToolbarWindow32</span></span>|<span data-ttu-id="87ff8-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="87ff8-194">Separator</span></span>|  
|<span data-ttu-id="87ff8-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="87ff8-195">tooltips_class32</span></span>|<span data-ttu-id="87ff8-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="87ff8-196">ToolTip</span></span>|  
|<span data-ttu-id="87ff8-197">#32774</span><span class="sxs-lookup"><span data-stu-id="87ff8-197">#32774</span></span>|<span data-ttu-id="87ff8-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="87ff8-198">ToolTip</span></span>|  
|<span data-ttu-id="87ff8-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="87ff8-199">ReBarWindow32</span></span>|<span data-ttu-id="87ff8-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-200">Toolbar</span></span>|  
|<span data-ttu-id="87ff8-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="87ff8-201">SysTreeView32</span></span>|<span data-ttu-id="87ff8-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="87ff8-202">Tree</span></span>|  
|<span data-ttu-id="87ff8-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="87ff8-203">SysTreeView32</span></span>|<span data-ttu-id="87ff8-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="87ff8-204">TreeItem</span></span>|  
  
 <span data-ttu-id="87ff8-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span><span class="sxs-lookup"><span data-stu-id="87ff8-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="87ff8-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="87ff8-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="87ff8-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="87ff8-207">Class name</span></span>|<span data-ttu-id="87ff8-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="87ff8-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="87ff8-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="87ff8-209">SysAnimate32</span></span>|<span data-ttu-id="87ff8-210">Bild</span><span class="sxs-lookup"><span data-stu-id="87ff8-210">Image</span></span>|  
|<span data-ttu-id="87ff8-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="87ff8-211">SysPager</span></span>|<span data-ttu-id="87ff8-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="87ff8-212">Spinner</span></span>|  
|<span data-ttu-id="87ff8-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="87ff8-213">SysDateTimePick32</span></span>|<span data-ttu-id="87ff8-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="87ff8-214">Custom</span></span>|  
|<span data-ttu-id="87ff8-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="87ff8-215">SysMonthCal32</span></span>|<span data-ttu-id="87ff8-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="87ff8-216">Calendar</span></span>|  
|<span data-ttu-id="87ff8-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="87ff8-217">MS_WINNOTE</span></span>|<span data-ttu-id="87ff8-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="87ff8-218">Tooltip</span></span>|  
|<span data-ttu-id="87ff8-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="87ff8-219">VBBubble</span></span>|<span data-ttu-id="87ff8-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="87ff8-220">Tooltip</span></span>|  
|<span data-ttu-id="87ff8-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="87ff8-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="87ff8-222">Slider</span><span class="sxs-lookup"><span data-stu-id="87ff8-222">Slider</span></span>|  
|<span data-ttu-id="87ff8-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="87ff8-223">SuperGrid</span></span>|<span data-ttu-id="87ff8-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="87ff8-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="87ff8-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="87ff8-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="87ff8-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="87ff8-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="87ff8-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="87ff8-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="87ff8-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87ff8-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="87ff8-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="87ff8-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="87ff8-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="87ff8-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="87ff8-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="87ff8-231">Button</span></span>|  
|<span data-ttu-id="87ff8-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-232">CheckBox</span></span>|  
|<span data-ttu-id="87ff8-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-233">CheckedListBox</span></span>|  
|<span data-ttu-id="87ff8-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="87ff8-234">ColorDialog</span></span>|  
|<span data-ttu-id="87ff8-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-235">ComboBox</span></span>|  
|<span data-ttu-id="87ff8-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="87ff8-236">FolderBrowser</span></span>|  
|<span data-ttu-id="87ff8-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="87ff8-237">FontDialog</span></span>|  
|<span data-ttu-id="87ff8-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-238">GroupBox</span></span>|  
|<span data-ttu-id="87ff8-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-239">HscrollBar</span></span>|  
|<span data-ttu-id="87ff8-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="87ff8-240">ImageList</span></span>|  
|<span data-ttu-id="87ff8-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="87ff8-241">Label</span></span>|  
|<span data-ttu-id="87ff8-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-242">ListBox</span></span>|  
|<span data-ttu-id="87ff8-243">ListView</span><span class="sxs-lookup"><span data-stu-id="87ff8-243">ListView</span></span>|  
|<span data-ttu-id="87ff8-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="87ff8-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="87ff8-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="87ff8-245">MonthCalendar</span></span>|  
|<span data-ttu-id="87ff8-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="87ff8-246">NotifyIcon</span></span>|  
|<span data-ttu-id="87ff8-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="87ff8-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="87ff8-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="87ff8-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="87ff8-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="87ff8-249">PrintDialog</span></span>|  
|<span data-ttu-id="87ff8-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-250">ProgressBar</span></span>|  
|<span data-ttu-id="87ff8-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="87ff8-251">RadioButton</span></span>|  
|<span data-ttu-id="87ff8-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-252">RichTextBox</span></span>|  
|<span data-ttu-id="87ff8-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="87ff8-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="87ff8-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="87ff8-254">ScrollableControl</span></span>|  
|<span data-ttu-id="87ff8-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="87ff8-255">SoundPlayer</span></span>|  
|<span data-ttu-id="87ff8-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-256">StatusBar</span></span>|  
|<span data-ttu-id="87ff8-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="87ff8-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="87ff8-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-258">TextBox</span></span>|  
|<span data-ttu-id="87ff8-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="87ff8-259">Timer</span></span>|  
|<span data-ttu-id="87ff8-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-260">Toolbar</span></span>|  
|<span data-ttu-id="87ff8-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="87ff8-261">ToolTip</span></span>|  
|<span data-ttu-id="87ff8-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-262">TrackBar</span></span>|  
|<span data-ttu-id="87ff8-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="87ff8-263">TreeView</span></span>|  
|<span data-ttu-id="87ff8-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="87ff8-264">VscrollBar</span></span>|  
|<span data-ttu-id="87ff8-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="87ff8-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="87ff8-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="87ff8-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="87ff8-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87ff8-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="87ff8-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="87ff8-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="87ff8-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="87ff8-269">BindingSource</span></span>|  
|<span data-ttu-id="87ff8-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="87ff8-270">DataGrid</span></span>|  
|<span data-ttu-id="87ff8-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="87ff8-271">DataGridView</span></span>|  
|<span data-ttu-id="87ff8-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="87ff8-272">DataNavigator</span></span>|  
|<span data-ttu-id="87ff8-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="87ff8-273">DomainUpDown</span></span>|  
|<span data-ttu-id="87ff8-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="87ff8-274">ErrorProvider</span></span>|  
|<span data-ttu-id="87ff8-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="87ff8-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="87ff8-276">Formular</span><span class="sxs-lookup"><span data-stu-id="87ff8-276">Form</span></span>|  
|<span data-ttu-id="87ff8-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="87ff8-277">LinkLabel</span></span>|  
|<span data-ttu-id="87ff8-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="87ff8-278">HelpProvider</span></span>|  
|<span data-ttu-id="87ff8-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="87ff8-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="87ff8-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="87ff8-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="87ff8-281">NumericUpDown</span></span>|  
|<span data-ttu-id="87ff8-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="87ff8-282">Panel</span></span>|  
|<span data-ttu-id="87ff8-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="87ff8-283">PictureBox</span></span>|  
|<span data-ttu-id="87ff8-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="87ff8-284">PrintDocument</span></span>|  
|<span data-ttu-id="87ff8-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="87ff8-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="87ff8-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="87ff8-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="87ff8-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="87ff8-287">PropertyGrid</span></span>|  
|<span data-ttu-id="87ff8-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="87ff8-288">UserControl</span></span>|  
|<span data-ttu-id="87ff8-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="87ff8-289">ToolStrip</span></span>|  
|<span data-ttu-id="87ff8-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="87ff8-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="87ff8-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="87ff8-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="87ff8-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="87ff8-292">Splitter</span></span>|  
|<span data-ttu-id="87ff8-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="87ff8-293">RaftingContainer</span></span>|  
|<span data-ttu-id="87ff8-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="87ff8-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87ff8-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87ff8-295">See also</span></span>

- [<span data-ttu-id="87ff8-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="87ff8-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
