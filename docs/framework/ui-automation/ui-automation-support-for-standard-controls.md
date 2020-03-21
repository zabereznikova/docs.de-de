---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179848"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="33487-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="33487-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="33487-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="33487-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="33487-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="33487-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="33487-105">Dieses Thema enthält [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Informationen zur Unterstützung von [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]Standardsteuerelementen in Anwendungen, die für die , Win32- und Windows Forms-Frameworks entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="33487-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="33487-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="33487-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="33487-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33487-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="33487-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="33487-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="33487-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="33487-109">Win32 Controls</span></span>  
 <span data-ttu-id="33487-110">Die meisten Win32-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über clientseitige Anbieter in UIAutomationClientsideProviders.dll verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="33487-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="33487-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="33487-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="33487-112">Vollständige Unterstützung wird nur für Steuerelemente ab Version 6 von *ComCtrl32.dll*bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33487-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="33487-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="33487-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="33487-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="33487-114">Class name</span></span>|<span data-ttu-id="33487-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="33487-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="33487-116">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-116">Button</span></span>|<span data-ttu-id="33487-117">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-117">Button</span></span>|  
|<span data-ttu-id="33487-118">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-118">Button</span></span>|<span data-ttu-id="33487-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="33487-119">RadioButton</span></span>|  
|<span data-ttu-id="33487-120">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-120">Button</span></span>|<span data-ttu-id="33487-121">Group</span><span class="sxs-lookup"><span data-stu-id="33487-121">Group</span></span>|  
|<span data-ttu-id="33487-122">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-122">Button</span></span>|<span data-ttu-id="33487-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="33487-123">CheckBox</span></span>|  
|<span data-ttu-id="33487-124">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-124">Button</span></span>|<span data-ttu-id="33487-125">Link</span><span class="sxs-lookup"><span data-stu-id="33487-125">Hyperlink</span></span>|  
|<span data-ttu-id="33487-126">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-126">Button</span></span>|<span data-ttu-id="33487-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="33487-127">SplitButton</span></span>|  
|<span data-ttu-id="33487-128">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-128">Button</span></span>|<span data-ttu-id="33487-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="33487-129">CheckBox</span></span>|  
|<span data-ttu-id="33487-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="33487-130">ComboBoxEx32</span></span>|<span data-ttu-id="33487-131">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="33487-131">ComboBox</span></span>|  
|<span data-ttu-id="33487-132">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="33487-132">ComboBox</span></span>|<span data-ttu-id="33487-133">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="33487-133">ComboBox</span></span>|  
|<span data-ttu-id="33487-134">Edit (Bearbeiten)</span><span class="sxs-lookup"><span data-stu-id="33487-134">Edit</span></span>|<span data-ttu-id="33487-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="33487-135">Document</span></span>|  
|<span data-ttu-id="33487-136">Edit (Bearbeiten)</span><span class="sxs-lookup"><span data-stu-id="33487-136">Edit</span></span>|<span data-ttu-id="33487-137">Edit (Bearbeiten)</span><span class="sxs-lookup"><span data-stu-id="33487-137">Edit</span></span>|  
|<span data-ttu-id="33487-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="33487-138">SysLink</span></span>|<span data-ttu-id="33487-139">Link</span><span class="sxs-lookup"><span data-stu-id="33487-139">Hyperlink</span></span>|  
|<span data-ttu-id="33487-140">statischen</span><span class="sxs-lookup"><span data-stu-id="33487-140">Static</span></span>|<span data-ttu-id="33487-141">Text</span><span class="sxs-lookup"><span data-stu-id="33487-141">Text</span></span>|  
|<span data-ttu-id="33487-142">statischen</span><span class="sxs-lookup"><span data-stu-id="33487-142">Static</span></span>|<span data-ttu-id="33487-143">Image</span><span class="sxs-lookup"><span data-stu-id="33487-143">Image</span></span>|  
|<span data-ttu-id="33487-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="33487-144">SysIPAddress32</span></span>|<span data-ttu-id="33487-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="33487-145">Custom</span></span>|  
|<span data-ttu-id="33487-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="33487-146">SysHeader32</span></span>|<span data-ttu-id="33487-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="33487-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="33487-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="33487-148">SysListView32</span></span>|<span data-ttu-id="33487-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="33487-149">DataGrid</span></span>|  
|<span data-ttu-id="33487-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="33487-150">SysListView32</span></span>|<span data-ttu-id="33487-151">List</span><span class="sxs-lookup"><span data-stu-id="33487-151">List</span></span>|  
|<span data-ttu-id="33487-152">Listenfeld</span><span class="sxs-lookup"><span data-stu-id="33487-152">ListBox</span></span>|<span data-ttu-id="33487-153">List</span><span class="sxs-lookup"><span data-stu-id="33487-153">List</span></span>|  
|<span data-ttu-id="33487-154">Listenfeld</span><span class="sxs-lookup"><span data-stu-id="33487-154">ListBox</span></span>|<span data-ttu-id="33487-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="33487-155">ListItem</span></span>|  
|<span data-ttu-id="33487-156">#32768</span><span class="sxs-lookup"><span data-stu-id="33487-156">#32768</span></span>|<span data-ttu-id="33487-157">Menü</span><span class="sxs-lookup"><span data-stu-id="33487-157">Menu</span></span>|  
|<span data-ttu-id="33487-158">#32768</span><span class="sxs-lookup"><span data-stu-id="33487-158">#32768</span></span>|<span data-ttu-id="33487-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="33487-159">MenuItem</span></span>|  
|<span data-ttu-id="33487-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="33487-160">msctls_progress32</span></span>|<span data-ttu-id="33487-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="33487-161">ProgressBar</span></span>|  
|<span data-ttu-id="33487-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="33487-162">RichEdit</span></span>|<span data-ttu-id="33487-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="33487-163">Document.</span></span> <span data-ttu-id="33487-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="33487-164">See note.</span></span>|  
|<span data-ttu-id="33487-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="33487-165">RichEdit20A</span></span>|<span data-ttu-id="33487-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="33487-166">Document</span></span>|  
|<span data-ttu-id="33487-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="33487-167">RichEdit20W</span></span>|<span data-ttu-id="33487-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="33487-168">Document</span></span>|  
|<span data-ttu-id="33487-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="33487-169">RichEdit50W</span></span>|<span data-ttu-id="33487-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="33487-170">Document</span></span>|  
|<span data-ttu-id="33487-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="33487-171">ScrollBar</span></span>|<span data-ttu-id="33487-172">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="33487-172">Slider</span></span>|  
|<span data-ttu-id="33487-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="33487-173">msctls_trackbar32</span></span>|<span data-ttu-id="33487-174">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="33487-174">Slider</span></span>|  
|<span data-ttu-id="33487-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="33487-175">msctls_updown32</span></span>|<span data-ttu-id="33487-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="33487-176">Spinner</span></span>|  
|<span data-ttu-id="33487-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="33487-177">msctls_statusbar32</span></span>|<span data-ttu-id="33487-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="33487-178">StatusBar</span></span>|  
|<span data-ttu-id="33487-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="33487-179">SysTabControl32</span></span>|<span data-ttu-id="33487-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="33487-180">Tab</span></span>|  
|<span data-ttu-id="33487-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="33487-181">SysTabControl32</span></span>|<span data-ttu-id="33487-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="33487-182">TabItem</span></span>|  
|<span data-ttu-id="33487-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="33487-183">ToolbarWindow32</span></span>|<span data-ttu-id="33487-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="33487-184">ToolBar</span></span>|  
|<span data-ttu-id="33487-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="33487-185">ToolbarWindow32</span></span>|<span data-ttu-id="33487-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="33487-186">MenuItem</span></span>|  
|<span data-ttu-id="33487-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="33487-187">ToolbarWindow32</span></span>|<span data-ttu-id="33487-188">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-188">Button</span></span>|  
|<span data-ttu-id="33487-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="33487-189">ToolbarWindow32</span></span>|<span data-ttu-id="33487-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="33487-190">CheckBox</span></span>|  
|<span data-ttu-id="33487-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="33487-191">ToolbarWindow32</span></span>|<span data-ttu-id="33487-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="33487-192">RadioButton</span></span>|  
|<span data-ttu-id="33487-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="33487-193">ToolbarWindow32</span></span>|<span data-ttu-id="33487-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33487-194">Separator</span></span>|  
|<span data-ttu-id="33487-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="33487-195">tooltips_class32</span></span>|<span data-ttu-id="33487-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="33487-196">ToolTip</span></span>|  
|<span data-ttu-id="33487-197">#32774</span><span class="sxs-lookup"><span data-stu-id="33487-197">#32774</span></span>|<span data-ttu-id="33487-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="33487-198">ToolTip</span></span>|  
|<span data-ttu-id="33487-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="33487-199">ReBarWindow32</span></span>|<span data-ttu-id="33487-200">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="33487-200">Toolbar</span></span>|  
|<span data-ttu-id="33487-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="33487-201">SysTreeView32</span></span>|<span data-ttu-id="33487-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="33487-202">Tree</span></span>|  
|<span data-ttu-id="33487-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="33487-203">SysTreeView32</span></span>|<span data-ttu-id="33487-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="33487-204">TreeItem</span></span>|  
  
 <span data-ttu-id="33487-205">**Hinweis** Das RichEdit-Steuerelement wird nur für Versionen unterstützt, die mit Windows Vista ausgeliefert werden (in RichEd20.dll Version 3.1 und höher und MsftEdit.dll Version 4.1 und höher).</span><span class="sxs-lookup"><span data-stu-id="33487-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="33487-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="33487-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="33487-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="33487-207">Class name</span></span>|<span data-ttu-id="33487-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="33487-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="33487-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="33487-209">SysAnimate32</span></span>|<span data-ttu-id="33487-210">Image</span><span class="sxs-lookup"><span data-stu-id="33487-210">Image</span></span>|  
|<span data-ttu-id="33487-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="33487-211">SysPager</span></span>|<span data-ttu-id="33487-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="33487-212">Spinner</span></span>|  
|<span data-ttu-id="33487-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="33487-213">SysDateTimePick32</span></span>|<span data-ttu-id="33487-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="33487-214">Custom</span></span>|  
|<span data-ttu-id="33487-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="33487-215">SysMonthCal32</span></span>|<span data-ttu-id="33487-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="33487-216">Calendar</span></span>|  
|<span data-ttu-id="33487-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="33487-217">MS_WINNOTE</span></span>|<span data-ttu-id="33487-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="33487-218">Tooltip</span></span>|  
|<span data-ttu-id="33487-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="33487-219">VBBubble</span></span>|<span data-ttu-id="33487-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="33487-220">Tooltip</span></span>|  
|<span data-ttu-id="33487-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="33487-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="33487-222">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="33487-222">Slider</span></span>|  
|<span data-ttu-id="33487-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="33487-223">SuperGrid</span></span>|<span data-ttu-id="33487-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="33487-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="33487-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="33487-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="33487-226">Windows Forms-Steuerelemente [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] werden über clientseitige Anbieter in UIAutomationClientsideProviders.dll verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="33487-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="33487-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="33487-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="33487-228">In der Regel werden Windows Forms-Steuerelemente, die verwaltete [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]Wrapper für allgemeine Win32-Steuerelemente sind, von unterstützt.</span><span class="sxs-lookup"><span data-stu-id="33487-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="33487-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="33487-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="33487-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="33487-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="33487-231">Taste</span><span class="sxs-lookup"><span data-stu-id="33487-231">Button</span></span>|  
|<span data-ttu-id="33487-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="33487-232">CheckBox</span></span>|  
|<span data-ttu-id="33487-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="33487-233">CheckedListBox</span></span>|  
|<span data-ttu-id="33487-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="33487-234">ColorDialog</span></span>|  
|<span data-ttu-id="33487-235">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="33487-235">ComboBox</span></span>|  
|<span data-ttu-id="33487-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="33487-236">FolderBrowser</span></span>|  
|<span data-ttu-id="33487-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="33487-237">FontDialog</span></span>|  
|<span data-ttu-id="33487-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="33487-238">GroupBox</span></span>|  
|<span data-ttu-id="33487-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="33487-239">HscrollBar</span></span>|  
|<span data-ttu-id="33487-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="33487-240">ImageList</span></span>|  
|<span data-ttu-id="33487-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="33487-241">Label</span></span>|  
|<span data-ttu-id="33487-242">Listenfeld</span><span class="sxs-lookup"><span data-stu-id="33487-242">ListBox</span></span>|  
|<span data-ttu-id="33487-243">ListView</span><span class="sxs-lookup"><span data-stu-id="33487-243">ListView</span></span>|  
|<span data-ttu-id="33487-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="33487-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="33487-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="33487-245">MonthCalendar</span></span>|  
|<span data-ttu-id="33487-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="33487-246">NotifyIcon</span></span>|  
|<span data-ttu-id="33487-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="33487-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="33487-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="33487-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="33487-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="33487-249">PrintDialog</span></span>|  
|<span data-ttu-id="33487-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="33487-250">ProgressBar</span></span>|  
|<span data-ttu-id="33487-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="33487-251">RadioButton</span></span>|  
|<span data-ttu-id="33487-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="33487-252">RichTextBox</span></span>|  
|<span data-ttu-id="33487-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="33487-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="33487-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="33487-254">ScrollableControl</span></span>|  
|<span data-ttu-id="33487-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="33487-255">SoundPlayer</span></span>|  
|<span data-ttu-id="33487-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="33487-256">StatusBar</span></span>|  
|<span data-ttu-id="33487-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="33487-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="33487-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="33487-258">TextBox</span></span>|  
|<span data-ttu-id="33487-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="33487-259">Timer</span></span>|  
|<span data-ttu-id="33487-260">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="33487-260">Toolbar</span></span>|  
|<span data-ttu-id="33487-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="33487-261">ToolTip</span></span>|  
|<span data-ttu-id="33487-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="33487-262">TrackBar</span></span>|  
|<span data-ttu-id="33487-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="33487-263">TreeView</span></span>|  
|<span data-ttu-id="33487-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="33487-264">VscrollBar</span></span>|  
|<span data-ttu-id="33487-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="33487-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="33487-266">Die folgenden Steuerelemente [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] werden nur durch ihre Unterstützung für Microsoft Active Accessibility verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="33487-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="33487-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="33487-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="33487-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="33487-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="33487-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="33487-269">BindingSource</span></span>|  
|<span data-ttu-id="33487-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="33487-270">DataGrid</span></span>|  
|<span data-ttu-id="33487-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="33487-271">DataGridView</span></span>|  
|<span data-ttu-id="33487-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="33487-272">DataNavigator</span></span>|  
|<span data-ttu-id="33487-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="33487-273">DomainUpDown</span></span>|  
|<span data-ttu-id="33487-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="33487-274">ErrorProvider</span></span>|  
|<span data-ttu-id="33487-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="33487-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="33487-276">Form</span><span class="sxs-lookup"><span data-stu-id="33487-276">Form</span></span>|  
|<span data-ttu-id="33487-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="33487-277">LinkLabel</span></span>|  
|<span data-ttu-id="33487-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="33487-278">HelpProvider</span></span>|  
|<span data-ttu-id="33487-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="33487-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="33487-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="33487-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="33487-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="33487-281">NumericUpDown</span></span>|  
|<span data-ttu-id="33487-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="33487-282">Panel</span></span>|  
|<span data-ttu-id="33487-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="33487-283">PictureBox</span></span>|  
|<span data-ttu-id="33487-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="33487-284">PrintDocument</span></span>|  
|<span data-ttu-id="33487-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="33487-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="33487-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="33487-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="33487-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="33487-287">PropertyGrid</span></span>|  
|<span data-ttu-id="33487-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="33487-288">UserControl</span></span>|  
|<span data-ttu-id="33487-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="33487-289">ToolStrip</span></span>|  
|<span data-ttu-id="33487-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="33487-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="33487-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="33487-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="33487-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="33487-292">Splitter</span></span>|  
|<span data-ttu-id="33487-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="33487-293">RaftingContainer</span></span>|  
|<span data-ttu-id="33487-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="33487-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33487-295">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33487-295">See also</span></span>

- [<span data-ttu-id="33487-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="33487-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
