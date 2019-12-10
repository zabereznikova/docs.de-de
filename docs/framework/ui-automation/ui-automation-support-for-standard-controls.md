---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 314526c1164f70e6b261df1a6f11ddce2b5fa240
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960078"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="09ad0-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="09ad0-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="09ad0-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="09ad0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="09ad0-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="09ad0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="09ad0-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="09ad0-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="09ad0-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="09ad0-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="09ad0-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09ad0-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="09ad0-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="09ad0-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="09ad0-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="09ad0-109">Win32 Controls</span></span>  
 <span data-ttu-id="09ad0-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="09ad0-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="09ad0-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="09ad0-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="09ad0-112">Vollständige Unterstützung wird nur für Steuerelemente der Version 6 von *"ComCtrl32. dll*bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="09ad0-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="09ad0-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="09ad0-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="09ad0-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="09ad0-114">Class name</span></span>|<span data-ttu-id="09ad0-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="09ad0-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="09ad0-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-116">Button</span></span>|<span data-ttu-id="09ad0-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-117">Button</span></span>|  
|<span data-ttu-id="09ad0-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-118">Button</span></span>|<span data-ttu-id="09ad0-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="09ad0-119">RadioButton</span></span>|  
|<span data-ttu-id="09ad0-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-120">Button</span></span>|<span data-ttu-id="09ad0-121">Gruppe</span><span class="sxs-lookup"><span data-stu-id="09ad0-121">Group</span></span>|  
|<span data-ttu-id="09ad0-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-122">Button</span></span>|<span data-ttu-id="09ad0-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-123">CheckBox</span></span>|  
|<span data-ttu-id="09ad0-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-124">Button</span></span>|<span data-ttu-id="09ad0-125">Link</span><span class="sxs-lookup"><span data-stu-id="09ad0-125">Hyperlink</span></span>|  
|<span data-ttu-id="09ad0-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-126">Button</span></span>|<span data-ttu-id="09ad0-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="09ad0-127">SplitButton</span></span>|  
|<span data-ttu-id="09ad0-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-128">Button</span></span>|<span data-ttu-id="09ad0-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-129">CheckBox</span></span>|  
|<span data-ttu-id="09ad0-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="09ad0-130">ComboBoxEx32</span></span>|<span data-ttu-id="09ad0-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-131">ComboBox</span></span>|  
|<span data-ttu-id="09ad0-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-132">ComboBox</span></span>|<span data-ttu-id="09ad0-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-133">ComboBox</span></span>|  
|<span data-ttu-id="09ad0-134">Edit</span><span class="sxs-lookup"><span data-stu-id="09ad0-134">Edit</span></span>|<span data-ttu-id="09ad0-135">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="09ad0-135">Document</span></span>|  
|<span data-ttu-id="09ad0-136">Edit</span><span class="sxs-lookup"><span data-stu-id="09ad0-136">Edit</span></span>|<span data-ttu-id="09ad0-137">Edit</span><span class="sxs-lookup"><span data-stu-id="09ad0-137">Edit</span></span>|  
|<span data-ttu-id="09ad0-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="09ad0-138">SysLink</span></span>|<span data-ttu-id="09ad0-139">Link</span><span class="sxs-lookup"><span data-stu-id="09ad0-139">Hyperlink</span></span>|  
|<span data-ttu-id="09ad0-140">Static</span><span class="sxs-lookup"><span data-stu-id="09ad0-140">Static</span></span>|<span data-ttu-id="09ad0-141">Text</span><span class="sxs-lookup"><span data-stu-id="09ad0-141">Text</span></span>|  
|<span data-ttu-id="09ad0-142">Static</span><span class="sxs-lookup"><span data-stu-id="09ad0-142">Static</span></span>|<span data-ttu-id="09ad0-143">Bild</span><span class="sxs-lookup"><span data-stu-id="09ad0-143">Image</span></span>|  
|<span data-ttu-id="09ad0-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="09ad0-144">SysIPAddress32</span></span>|<span data-ttu-id="09ad0-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="09ad0-145">Custom</span></span>|  
|<span data-ttu-id="09ad0-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="09ad0-146">SysHeader32</span></span>|<span data-ttu-id="09ad0-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="09ad0-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="09ad0-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="09ad0-148">SysListView32</span></span>|<span data-ttu-id="09ad0-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="09ad0-149">DataGrid</span></span>|  
|<span data-ttu-id="09ad0-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="09ad0-150">SysListView32</span></span>|<span data-ttu-id="09ad0-151">Liste</span><span class="sxs-lookup"><span data-stu-id="09ad0-151">List</span></span>|  
|<span data-ttu-id="09ad0-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-152">ListBox</span></span>|<span data-ttu-id="09ad0-153">Liste</span><span class="sxs-lookup"><span data-stu-id="09ad0-153">List</span></span>|  
|<span data-ttu-id="09ad0-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-154">ListBox</span></span>|<span data-ttu-id="09ad0-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="09ad0-155">ListItem</span></span>|  
|<span data-ttu-id="09ad0-156">#32768</span><span class="sxs-lookup"><span data-stu-id="09ad0-156">#32768</span></span>|<span data-ttu-id="09ad0-157">Menü</span><span class="sxs-lookup"><span data-stu-id="09ad0-157">Menu</span></span>|  
|<span data-ttu-id="09ad0-158">#32768</span><span class="sxs-lookup"><span data-stu-id="09ad0-158">#32768</span></span>|<span data-ttu-id="09ad0-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="09ad0-159">MenuItem</span></span>|  
|<span data-ttu-id="09ad0-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="09ad0-160">msctls_progress32</span></span>|<span data-ttu-id="09ad0-161">Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="09ad0-161">ProgressBar</span></span>|  
|<span data-ttu-id="09ad0-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="09ad0-162">RichEdit</span></span>|<span data-ttu-id="09ad0-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="09ad0-163">Document.</span></span> <span data-ttu-id="09ad0-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="09ad0-164">See note.</span></span>|  
|<span data-ttu-id="09ad0-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="09ad0-165">RichEdit20A</span></span>|<span data-ttu-id="09ad0-166">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="09ad0-166">Document</span></span>|  
|<span data-ttu-id="09ad0-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="09ad0-167">RichEdit20W</span></span>|<span data-ttu-id="09ad0-168">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="09ad0-168">Document</span></span>|  
|<span data-ttu-id="09ad0-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="09ad0-169">RichEdit50W</span></span>|<span data-ttu-id="09ad0-170">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="09ad0-170">Document</span></span>|  
|<span data-ttu-id="09ad0-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-171">ScrollBar</span></span>|<span data-ttu-id="09ad0-172">Slider</span><span class="sxs-lookup"><span data-stu-id="09ad0-172">Slider</span></span>|  
|<span data-ttu-id="09ad0-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="09ad0-173">msctls_trackbar32</span></span>|<span data-ttu-id="09ad0-174">Slider</span><span class="sxs-lookup"><span data-stu-id="09ad0-174">Slider</span></span>|  
|<span data-ttu-id="09ad0-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="09ad0-175">msctls_updown32</span></span>|<span data-ttu-id="09ad0-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="09ad0-176">Spinner</span></span>|  
|<span data-ttu-id="09ad0-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="09ad0-177">msctls_statusbar32</span></span>|<span data-ttu-id="09ad0-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-178">StatusBar</span></span>|  
|<span data-ttu-id="09ad0-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="09ad0-179">SysTabControl32</span></span>|<span data-ttu-id="09ad0-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="09ad0-180">Tab</span></span>|  
|<span data-ttu-id="09ad0-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="09ad0-181">SysTabControl32</span></span>|<span data-ttu-id="09ad0-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="09ad0-182">TabItem</span></span>|  
|<span data-ttu-id="09ad0-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="09ad0-183">ToolbarWindow32</span></span>|<span data-ttu-id="09ad0-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-184">ToolBar</span></span>|  
|<span data-ttu-id="09ad0-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="09ad0-185">ToolbarWindow32</span></span>|<span data-ttu-id="09ad0-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="09ad0-186">MenuItem</span></span>|  
|<span data-ttu-id="09ad0-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="09ad0-187">ToolbarWindow32</span></span>|<span data-ttu-id="09ad0-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-188">Button</span></span>|  
|<span data-ttu-id="09ad0-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="09ad0-189">ToolbarWindow32</span></span>|<span data-ttu-id="09ad0-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-190">CheckBox</span></span>|  
|<span data-ttu-id="09ad0-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="09ad0-191">ToolbarWindow32</span></span>|<span data-ttu-id="09ad0-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="09ad0-192">RadioButton</span></span>|  
|<span data-ttu-id="09ad0-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="09ad0-193">ToolbarWindow32</span></span>|<span data-ttu-id="09ad0-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="09ad0-194">Separator</span></span>|  
|<span data-ttu-id="09ad0-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="09ad0-195">tooltips_class32</span></span>|<span data-ttu-id="09ad0-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="09ad0-196">ToolTip</span></span>|  
|<span data-ttu-id="09ad0-197">#32774</span><span class="sxs-lookup"><span data-stu-id="09ad0-197">#32774</span></span>|<span data-ttu-id="09ad0-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="09ad0-198">ToolTip</span></span>|  
|<span data-ttu-id="09ad0-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="09ad0-199">ReBarWindow32</span></span>|<span data-ttu-id="09ad0-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-200">Toolbar</span></span>|  
|<span data-ttu-id="09ad0-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="09ad0-201">SysTreeView32</span></span>|<span data-ttu-id="09ad0-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="09ad0-202">Tree</span></span>|  
|<span data-ttu-id="09ad0-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="09ad0-203">SysTreeView32</span></span>|<span data-ttu-id="09ad0-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="09ad0-204">TreeItem</span></span>|  
  
 <span data-ttu-id="09ad0-205">**Hinweis** Das RichEdit-Steuerelement wird nur für Versionen unterstützt, die mit Windows Vista ausgeliefert werden (in Riched20. dll, Version 3,1 und höher, und MSF Tedit. dll, Version 4,1 und höher).</span><span class="sxs-lookup"><span data-stu-id="09ad0-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="09ad0-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="09ad0-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="09ad0-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="09ad0-207">Class name</span></span>|<span data-ttu-id="09ad0-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="09ad0-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="09ad0-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="09ad0-209">SysAnimate32</span></span>|<span data-ttu-id="09ad0-210">Bild</span><span class="sxs-lookup"><span data-stu-id="09ad0-210">Image</span></span>|  
|<span data-ttu-id="09ad0-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="09ad0-211">SysPager</span></span>|<span data-ttu-id="09ad0-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="09ad0-212">Spinner</span></span>|  
|<span data-ttu-id="09ad0-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="09ad0-213">SysDateTimePick32</span></span>|<span data-ttu-id="09ad0-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="09ad0-214">Custom</span></span>|  
|<span data-ttu-id="09ad0-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="09ad0-215">SysMonthCal32</span></span>|<span data-ttu-id="09ad0-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="09ad0-216">Calendar</span></span>|  
|<span data-ttu-id="09ad0-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="09ad0-217">MS_WINNOTE</span></span>|<span data-ttu-id="09ad0-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="09ad0-218">Tooltip</span></span>|  
|<span data-ttu-id="09ad0-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="09ad0-219">VBBubble</span></span>|<span data-ttu-id="09ad0-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="09ad0-220">Tooltip</span></span>|  
|<span data-ttu-id="09ad0-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="09ad0-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="09ad0-222">Slider</span><span class="sxs-lookup"><span data-stu-id="09ad0-222">Slider</span></span>|  
|<span data-ttu-id="09ad0-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="09ad0-223">SuperGrid</span></span>|<span data-ttu-id="09ad0-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="09ad0-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="09ad0-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="09ad0-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="09ad0-226">Windows Forms Steuerelemente werden über Client seitige Anbieter in "UIAutomationClientsideProviders. dll" [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="09ad0-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="09ad0-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="09ad0-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="09ad0-228">In der Regel werden Windows Forms Steuerelemente, die verwaltete Wrapper für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] allgemeine Steuerelemente sind, von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09ad0-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="09ad0-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="09ad0-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="09ad0-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="09ad0-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="09ad0-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="09ad0-231">Button</span></span>|  
|<span data-ttu-id="09ad0-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-232">CheckBox</span></span>|  
|<span data-ttu-id="09ad0-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-233">CheckedListBox</span></span>|  
|<span data-ttu-id="09ad0-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="09ad0-234">ColorDialog</span></span>|  
|<span data-ttu-id="09ad0-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-235">ComboBox</span></span>|  
|<span data-ttu-id="09ad0-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="09ad0-236">FolderBrowser</span></span>|  
|<span data-ttu-id="09ad0-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="09ad0-237">FontDialog</span></span>|  
|<span data-ttu-id="09ad0-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-238">GroupBox</span></span>|  
|<span data-ttu-id="09ad0-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-239">HscrollBar</span></span>|  
|<span data-ttu-id="09ad0-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="09ad0-240">ImageList</span></span>|  
|<span data-ttu-id="09ad0-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="09ad0-241">Label</span></span>|  
|<span data-ttu-id="09ad0-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-242">ListBox</span></span>|  
|<span data-ttu-id="09ad0-243">ListView</span><span class="sxs-lookup"><span data-stu-id="09ad0-243">ListView</span></span>|  
|<span data-ttu-id="09ad0-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="09ad0-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="09ad0-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="09ad0-245">MonthCalendar</span></span>|  
|<span data-ttu-id="09ad0-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="09ad0-246">NotifyIcon</span></span>|  
|<span data-ttu-id="09ad0-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="09ad0-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="09ad0-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="09ad0-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="09ad0-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="09ad0-249">PrintDialog</span></span>|  
|<span data-ttu-id="09ad0-250">Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="09ad0-250">ProgressBar</span></span>|  
|<span data-ttu-id="09ad0-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="09ad0-251">RadioButton</span></span>|  
|<span data-ttu-id="09ad0-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-252">RichTextBox</span></span>|  
|<span data-ttu-id="09ad0-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="09ad0-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="09ad0-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="09ad0-254">ScrollableControl</span></span>|  
|<span data-ttu-id="09ad0-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="09ad0-255">SoundPlayer</span></span>|  
|<span data-ttu-id="09ad0-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-256">StatusBar</span></span>|  
|<span data-ttu-id="09ad0-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="09ad0-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="09ad0-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-258">TextBox</span></span>|  
|<span data-ttu-id="09ad0-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="09ad0-259">Timer</span></span>|  
|<span data-ttu-id="09ad0-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-260">Toolbar</span></span>|  
|<span data-ttu-id="09ad0-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="09ad0-261">ToolTip</span></span>|  
|<span data-ttu-id="09ad0-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-262">TrackBar</span></span>|  
|<span data-ttu-id="09ad0-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="09ad0-263">TreeView</span></span>|  
|<span data-ttu-id="09ad0-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="09ad0-264">VscrollBar</span></span>|  
|<span data-ttu-id="09ad0-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="09ad0-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="09ad0-266">Die folgenden Steuerelemente sind nur für die Unterstützung von Microsoft Active Accessibility verfügbar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09ad0-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="09ad0-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="09ad0-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="09ad0-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="09ad0-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="09ad0-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="09ad0-269">BindingSource</span></span>|  
|<span data-ttu-id="09ad0-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="09ad0-270">DataGrid</span></span>|  
|<span data-ttu-id="09ad0-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="09ad0-271">DataGridView</span></span>|  
|<span data-ttu-id="09ad0-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="09ad0-272">DataNavigator</span></span>|  
|<span data-ttu-id="09ad0-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="09ad0-273">DomainUpDown</span></span>|  
|<span data-ttu-id="09ad0-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="09ad0-274">ErrorProvider</span></span>|  
|<span data-ttu-id="09ad0-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="09ad0-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="09ad0-276">Formular</span><span class="sxs-lookup"><span data-stu-id="09ad0-276">Form</span></span>|  
|<span data-ttu-id="09ad0-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="09ad0-277">LinkLabel</span></span>|  
|<span data-ttu-id="09ad0-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="09ad0-278">HelpProvider</span></span>|  
|<span data-ttu-id="09ad0-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="09ad0-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="09ad0-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="09ad0-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="09ad0-281">NumericUpDown</span></span>|  
|<span data-ttu-id="09ad0-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="09ad0-282">Panel</span></span>|  
|<span data-ttu-id="09ad0-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="09ad0-283">PictureBox</span></span>|  
|<span data-ttu-id="09ad0-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="09ad0-284">PrintDocument</span></span>|  
|<span data-ttu-id="09ad0-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="09ad0-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="09ad0-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="09ad0-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="09ad0-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="09ad0-287">PropertyGrid</span></span>|  
|<span data-ttu-id="09ad0-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="09ad0-288">UserControl</span></span>|  
|<span data-ttu-id="09ad0-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="09ad0-289">ToolStrip</span></span>|  
|<span data-ttu-id="09ad0-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="09ad0-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="09ad0-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="09ad0-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="09ad0-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="09ad0-292">Splitter</span></span>|  
|<span data-ttu-id="09ad0-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="09ad0-293">RaftingContainer</span></span>|  
|<span data-ttu-id="09ad0-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="09ad0-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09ad0-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09ad0-295">See also</span></span>

- [<span data-ttu-id="09ad0-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="09ad0-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
