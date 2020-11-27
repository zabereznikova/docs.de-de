---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
description: Hier finden Sie Informationen zur Benutzeroberflächenautomatisierungs-Unterstützung für Standard Steuerelemente in Anwendungen, die für Windows Presentation Foundation (WPF), Win32 und Windows Forms entwickelt wurden.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 0a5a0b61a6492d9efb62799fa610859b247cf26e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261071"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="5916d-103">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="5916d-103">UI Automation Support for Standard Controls</span></span>

> [!NOTE]
> <span data-ttu-id="5916d-104">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5916d-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5916d-105">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="5916d-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="5916d-106">Dieses Thema enthält Informationen zur- [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung für Standard Steuerelemente in Anwendungen, die für die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Frameworks, Win32 und Windows Forms entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="5916d-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>

## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="5916d-107">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="5916d-107">Windows Presentation Foundation Controls</span></span>  

 <span data-ttu-id="5916d-108">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5916d-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5916d-109">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="5916d-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>

## <a name="win32-controls"></a><span data-ttu-id="5916d-110">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="5916d-110">Win32 Controls</span></span>  

 <span data-ttu-id="5916d-111">Die meisten Win32-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über Client seitige Anbieter in UIAutomationClientsideProviders.dll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5916d-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5916d-112">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="5916d-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5916d-113">Vollständige Unterstützung wird nur für Steuerelemente ab Version 6 von *ComCtrl32.dll* bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5916d-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="5916d-114">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5916d-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5916d-115">Klassenname</span><span class="sxs-lookup"><span data-stu-id="5916d-115">Class name</span></span>|<span data-ttu-id="5916d-116">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="5916d-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5916d-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-117">Button</span></span>|<span data-ttu-id="5916d-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-118">Button</span></span>|  
|<span data-ttu-id="5916d-119">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-119">Button</span></span>|<span data-ttu-id="5916d-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5916d-120">RadioButton</span></span>|  
|<span data-ttu-id="5916d-121">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-121">Button</span></span>|<span data-ttu-id="5916d-122">Group</span><span class="sxs-lookup"><span data-stu-id="5916d-122">Group</span></span>|  
|<span data-ttu-id="5916d-123">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-123">Button</span></span>|<span data-ttu-id="5916d-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5916d-124">CheckBox</span></span>|  
|<span data-ttu-id="5916d-125">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-125">Button</span></span>|<span data-ttu-id="5916d-126">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5916d-126">Hyperlink</span></span>|  
|<span data-ttu-id="5916d-127">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-127">Button</span></span>|<span data-ttu-id="5916d-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="5916d-128">SplitButton</span></span>|  
|<span data-ttu-id="5916d-129">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-129">Button</span></span>|<span data-ttu-id="5916d-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5916d-130">CheckBox</span></span>|  
|<span data-ttu-id="5916d-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="5916d-131">ComboBoxEx32</span></span>|<span data-ttu-id="5916d-132">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="5916d-132">ComboBox</span></span>|  
|<span data-ttu-id="5916d-133">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="5916d-133">ComboBox</span></span>|<span data-ttu-id="5916d-134">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="5916d-134">ComboBox</span></span>|  
|<span data-ttu-id="5916d-135">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="5916d-135">Edit</span></span>|<span data-ttu-id="5916d-136">Dokument</span><span class="sxs-lookup"><span data-stu-id="5916d-136">Document</span></span>|  
|<span data-ttu-id="5916d-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="5916d-137">Edit</span></span>|<span data-ttu-id="5916d-138">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="5916d-138">Edit</span></span>|  
|<span data-ttu-id="5916d-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="5916d-139">SysLink</span></span>|<span data-ttu-id="5916d-140">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5916d-140">Hyperlink</span></span>|  
|<span data-ttu-id="5916d-141">statischen</span><span class="sxs-lookup"><span data-stu-id="5916d-141">Static</span></span>|<span data-ttu-id="5916d-142">Text</span><span class="sxs-lookup"><span data-stu-id="5916d-142">Text</span></span>|  
|<span data-ttu-id="5916d-143">statischen</span><span class="sxs-lookup"><span data-stu-id="5916d-143">Static</span></span>|<span data-ttu-id="5916d-144">Image</span><span class="sxs-lookup"><span data-stu-id="5916d-144">Image</span></span>|  
|<span data-ttu-id="5916d-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="5916d-145">SysIPAddress32</span></span>|<span data-ttu-id="5916d-146">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="5916d-146">Custom</span></span>|  
|<span data-ttu-id="5916d-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="5916d-147">SysHeader32</span></span>|<span data-ttu-id="5916d-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="5916d-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="5916d-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5916d-149">SysListView32</span></span>|<span data-ttu-id="5916d-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5916d-150">DataGrid</span></span>|  
|<span data-ttu-id="5916d-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5916d-151">SysListView32</span></span>|<span data-ttu-id="5916d-152">List</span><span class="sxs-lookup"><span data-stu-id="5916d-152">List</span></span>|  
|<span data-ttu-id="5916d-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="5916d-153">ListBox</span></span>|<span data-ttu-id="5916d-154">List</span><span class="sxs-lookup"><span data-stu-id="5916d-154">List</span></span>|  
|<span data-ttu-id="5916d-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="5916d-155">ListBox</span></span>|<span data-ttu-id="5916d-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="5916d-156">ListItem</span></span>|  
|<span data-ttu-id="5916d-157">#32768</span><span class="sxs-lookup"><span data-stu-id="5916d-157">#32768</span></span>|<span data-ttu-id="5916d-158">Menü</span><span class="sxs-lookup"><span data-stu-id="5916d-158">Menu</span></span>|  
|<span data-ttu-id="5916d-159">#32768</span><span class="sxs-lookup"><span data-stu-id="5916d-159">#32768</span></span>|<span data-ttu-id="5916d-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5916d-160">MenuItem</span></span>|  
|<span data-ttu-id="5916d-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="5916d-161">msctls_progress32</span></span>|<span data-ttu-id="5916d-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5916d-162">ProgressBar</span></span>|  
|<span data-ttu-id="5916d-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="5916d-163">RichEdit</span></span>|<span data-ttu-id="5916d-164">Dokument.</span><span class="sxs-lookup"><span data-stu-id="5916d-164">Document.</span></span> <span data-ttu-id="5916d-165">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="5916d-165">See note.</span></span>|  
|<span data-ttu-id="5916d-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="5916d-166">RichEdit20A</span></span>|<span data-ttu-id="5916d-167">Dokument</span><span class="sxs-lookup"><span data-stu-id="5916d-167">Document</span></span>|  
|<span data-ttu-id="5916d-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="5916d-168">RichEdit20W</span></span>|<span data-ttu-id="5916d-169">Dokument</span><span class="sxs-lookup"><span data-stu-id="5916d-169">Document</span></span>|  
|<span data-ttu-id="5916d-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="5916d-170">RichEdit50W</span></span>|<span data-ttu-id="5916d-171">Dokument</span><span class="sxs-lookup"><span data-stu-id="5916d-171">Document</span></span>|  
|<span data-ttu-id="5916d-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="5916d-172">ScrollBar</span></span>|<span data-ttu-id="5916d-173">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="5916d-173">Slider</span></span>|  
|<span data-ttu-id="5916d-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="5916d-174">msctls_trackbar32</span></span>|<span data-ttu-id="5916d-175">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="5916d-175">Slider</span></span>|  
|<span data-ttu-id="5916d-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="5916d-176">msctls_updown32</span></span>|<span data-ttu-id="5916d-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="5916d-177">Spinner</span></span>|  
|<span data-ttu-id="5916d-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="5916d-178">msctls_statusbar32</span></span>|<span data-ttu-id="5916d-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5916d-179">StatusBar</span></span>|  
|<span data-ttu-id="5916d-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5916d-180">SysTabControl32</span></span>|<span data-ttu-id="5916d-181">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="5916d-181">Tab</span></span>|  
|<span data-ttu-id="5916d-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5916d-182">SysTabControl32</span></span>|<span data-ttu-id="5916d-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="5916d-183">TabItem</span></span>|  
|<span data-ttu-id="5916d-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5916d-184">ToolbarWindow32</span></span>|<span data-ttu-id="5916d-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5916d-185">ToolBar</span></span>|  
|<span data-ttu-id="5916d-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5916d-186">ToolbarWindow32</span></span>|<span data-ttu-id="5916d-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5916d-187">MenuItem</span></span>|  
|<span data-ttu-id="5916d-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5916d-188">ToolbarWindow32</span></span>|<span data-ttu-id="5916d-189">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-189">Button</span></span>|  
|<span data-ttu-id="5916d-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5916d-190">ToolbarWindow32</span></span>|<span data-ttu-id="5916d-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5916d-191">CheckBox</span></span>|  
|<span data-ttu-id="5916d-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5916d-192">ToolbarWindow32</span></span>|<span data-ttu-id="5916d-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5916d-193">RadioButton</span></span>|  
|<span data-ttu-id="5916d-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5916d-194">ToolbarWindow32</span></span>|<span data-ttu-id="5916d-195">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5916d-195">Separator</span></span>|  
|<span data-ttu-id="5916d-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="5916d-196">tooltips_class32</span></span>|<span data-ttu-id="5916d-197">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5916d-197">ToolTip</span></span>|  
|<span data-ttu-id="5916d-198">#32774</span><span class="sxs-lookup"><span data-stu-id="5916d-198">#32774</span></span>|<span data-ttu-id="5916d-199">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5916d-199">ToolTip</span></span>|  
|<span data-ttu-id="5916d-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="5916d-200">ReBarWindow32</span></span>|<span data-ttu-id="5916d-201">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="5916d-201">Toolbar</span></span>|  
|<span data-ttu-id="5916d-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5916d-202">SysTreeView32</span></span>|<span data-ttu-id="5916d-203">Struktur</span><span class="sxs-lookup"><span data-stu-id="5916d-203">Tree</span></span>|  
|<span data-ttu-id="5916d-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5916d-204">SysTreeView32</span></span>|<span data-ttu-id="5916d-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="5916d-205">TreeItem</span></span>|  
  
 <span data-ttu-id="5916d-206">**Hinweis** Das RichEdit-Steuerelement wird nur für Versionen unterstützt, die mit Windows Vista ausgeliefert wurden (in RichEd20.dll Version 3,1 und höher sowie MsftEdit.dll Version 4,1 und höher).</span><span class="sxs-lookup"><span data-stu-id="5916d-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="5916d-207">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5916d-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="5916d-208">Klassenname</span><span class="sxs-lookup"><span data-stu-id="5916d-208">Class name</span></span>|<span data-ttu-id="5916d-209">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="5916d-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5916d-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="5916d-210">SysAnimate32</span></span>|<span data-ttu-id="5916d-211">Image</span><span class="sxs-lookup"><span data-stu-id="5916d-211">Image</span></span>|  
|<span data-ttu-id="5916d-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="5916d-212">SysPager</span></span>|<span data-ttu-id="5916d-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="5916d-213">Spinner</span></span>|  
|<span data-ttu-id="5916d-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="5916d-214">SysDateTimePick32</span></span>|<span data-ttu-id="5916d-215">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="5916d-215">Custom</span></span>|  
|<span data-ttu-id="5916d-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="5916d-216">SysMonthCal32</span></span>|<span data-ttu-id="5916d-217">Kalender</span><span class="sxs-lookup"><span data-stu-id="5916d-217">Calendar</span></span>|  
|<span data-ttu-id="5916d-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="5916d-218">MS_WINNOTE</span></span>|<span data-ttu-id="5916d-219">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="5916d-219">Tooltip</span></span>|  
|<span data-ttu-id="5916d-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="5916d-220">VBBubble</span></span>|<span data-ttu-id="5916d-221">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="5916d-221">Tooltip</span></span>|  
|<span data-ttu-id="5916d-222">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="5916d-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="5916d-223">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="5916d-223">Slider</span></span>|  
|<span data-ttu-id="5916d-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="5916d-224">SuperGrid</span></span>|<span data-ttu-id="5916d-225">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="5916d-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>

## <a name="windows-forms-controls"></a><span data-ttu-id="5916d-226">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="5916d-226">Windows Forms Controls</span></span>  

 <span data-ttu-id="5916d-227">Windows Forms-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über Client seitige Anbieter in UIAutomationClientsideProviders.dll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5916d-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5916d-228">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="5916d-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5916d-229">In der Regel werden Windows Forms Steuerelemente, die verwaltete Wrapper für allgemeine Win32-Steuerelemente sind, von unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5916d-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5916d-230">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5916d-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5916d-231">Klassenname</span><span class="sxs-lookup"><span data-stu-id="5916d-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="5916d-232">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5916d-232">Button</span></span>|  
|<span data-ttu-id="5916d-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5916d-233">CheckBox</span></span>|  
|<span data-ttu-id="5916d-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="5916d-234">CheckedListBox</span></span>|  
|<span data-ttu-id="5916d-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="5916d-235">ColorDialog</span></span>|  
|<span data-ttu-id="5916d-236">Kombinationsfeld</span><span class="sxs-lookup"><span data-stu-id="5916d-236">ComboBox</span></span>|  
|<span data-ttu-id="5916d-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="5916d-237">FolderBrowser</span></span>|  
|<span data-ttu-id="5916d-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="5916d-238">FontDialog</span></span>|  
|<span data-ttu-id="5916d-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="5916d-239">GroupBox</span></span>|  
|<span data-ttu-id="5916d-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="5916d-240">HscrollBar</span></span>|  
|<span data-ttu-id="5916d-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="5916d-241">ImageList</span></span>|  
|<span data-ttu-id="5916d-242">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="5916d-242">Label</span></span>|  
|<span data-ttu-id="5916d-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="5916d-243">ListBox</span></span>|  
|<span data-ttu-id="5916d-244">ListView</span><span class="sxs-lookup"><span data-stu-id="5916d-244">ListView</span></span>|  
|<span data-ttu-id="5916d-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5916d-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="5916d-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="5916d-246">MonthCalendar</span></span>|  
|<span data-ttu-id="5916d-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="5916d-247">NotifyIcon</span></span>|  
|<span data-ttu-id="5916d-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="5916d-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="5916d-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="5916d-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="5916d-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="5916d-250">PrintDialog</span></span>|  
|<span data-ttu-id="5916d-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5916d-251">ProgressBar</span></span>|  
|<span data-ttu-id="5916d-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5916d-252">RadioButton</span></span>|  
|<span data-ttu-id="5916d-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="5916d-253">RichTextBox</span></span>|  
|<span data-ttu-id="5916d-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5916d-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="5916d-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="5916d-255">ScrollableControl</span></span>|  
|<span data-ttu-id="5916d-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="5916d-256">SoundPlayer</span></span>|  
|<span data-ttu-id="5916d-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5916d-257">StatusBar</span></span>|  
|<span data-ttu-id="5916d-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="5916d-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="5916d-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="5916d-259">TextBox</span></span>|  
|<span data-ttu-id="5916d-260">Timer</span><span class="sxs-lookup"><span data-stu-id="5916d-260">Timer</span></span>|  
|<span data-ttu-id="5916d-261">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="5916d-261">Toolbar</span></span>|  
|<span data-ttu-id="5916d-262">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5916d-262">ToolTip</span></span>|  
|<span data-ttu-id="5916d-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="5916d-263">TrackBar</span></span>|  
|<span data-ttu-id="5916d-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="5916d-264">TreeView</span></span>|  
|<span data-ttu-id="5916d-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="5916d-265">VscrollBar</span></span>|  
|<span data-ttu-id="5916d-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="5916d-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="5916d-267">Die folgenden Steuerelemente sind nur für die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung von Microsoft Active Accessibility verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5916d-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="5916d-268">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5916d-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="5916d-269">Name des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5916d-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="5916d-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="5916d-270">BindingSource</span></span>|  
|<span data-ttu-id="5916d-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5916d-271">DataGrid</span></span>|  
|<span data-ttu-id="5916d-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="5916d-272">DataGridView</span></span>|  
|<span data-ttu-id="5916d-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="5916d-273">DataNavigator</span></span>|  
|<span data-ttu-id="5916d-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5916d-274">DomainUpDown</span></span>|  
|<span data-ttu-id="5916d-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="5916d-275">ErrorProvider</span></span>|  
|<span data-ttu-id="5916d-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5916d-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="5916d-277">Formular</span><span class="sxs-lookup"><span data-stu-id="5916d-277">Form</span></span>|  
|<span data-ttu-id="5916d-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="5916d-278">LinkLabel</span></span>|  
|<span data-ttu-id="5916d-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="5916d-279">HelpProvider</span></span>|  
|<span data-ttu-id="5916d-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="5916d-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="5916d-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="5916d-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="5916d-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="5916d-282">NumericUpDown</span></span>|  
|<span data-ttu-id="5916d-283">Bereich</span><span class="sxs-lookup"><span data-stu-id="5916d-283">Panel</span></span>|  
|<span data-ttu-id="5916d-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="5916d-284">PictureBox</span></span>|  
|<span data-ttu-id="5916d-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="5916d-285">PrintDocument</span></span>|  
|<span data-ttu-id="5916d-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="5916d-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="5916d-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="5916d-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="5916d-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="5916d-288">PropertyGrid</span></span>|  
|<span data-ttu-id="5916d-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="5916d-289">UserControl</span></span>|  
|<span data-ttu-id="5916d-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5916d-290">ToolStrip</span></span>|  
|<span data-ttu-id="5916d-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5916d-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="5916d-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="5916d-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="5916d-293">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="5916d-293">Splitter</span></span>|  
|<span data-ttu-id="5916d-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="5916d-294">RaftingContainer</span></span>|  
|<span data-ttu-id="5916d-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="5916d-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5916d-296">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5916d-296">See also</span></span>

- [<span data-ttu-id="5916d-297">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="5916d-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
