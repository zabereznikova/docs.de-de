---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 49277073706444fd611ae41e762442388ac50b71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789606"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="d4d12-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="d4d12-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="d4d12-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d4d12-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d4d12-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d4d12-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d4d12-105">Dieses Thema enthält Informationen über [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung für Standard Steuerelemente in Anwendungen, die für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 und Windows Forms entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="d4d12-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="d4d12-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="d4d12-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="d4d12-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4d12-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d4d12-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d4d12-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="d4d12-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d4d12-109">Win32 Controls</span></span>  
 <span data-ttu-id="d4d12-110">Die meisten Win32-Steuerelemente werden über Client seitige Anbieter in "UIAutomationClientsideProviders. dll" [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4d12-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d4d12-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="d4d12-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d4d12-112">Vollständige Unterstützung wird nur für Steuerelemente der Version 6 von *"ComCtrl32. dll*bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d4d12-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="d4d12-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d4d12-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d4d12-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="d4d12-114">Class name</span></span>|<span data-ttu-id="d4d12-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="d4d12-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d4d12-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-116">Button</span></span>|<span data-ttu-id="d4d12-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-117">Button</span></span>|  
|<span data-ttu-id="d4d12-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-118">Button</span></span>|<span data-ttu-id="d4d12-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d4d12-119">RadioButton</span></span>|  
|<span data-ttu-id="d4d12-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-120">Button</span></span>|<span data-ttu-id="d4d12-121">Gruppe</span><span class="sxs-lookup"><span data-stu-id="d4d12-121">Group</span></span>|  
|<span data-ttu-id="d4d12-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-122">Button</span></span>|<span data-ttu-id="d4d12-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-123">CheckBox</span></span>|  
|<span data-ttu-id="d4d12-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-124">Button</span></span>|<span data-ttu-id="d4d12-125">Link</span><span class="sxs-lookup"><span data-stu-id="d4d12-125">Hyperlink</span></span>|  
|<span data-ttu-id="d4d12-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-126">Button</span></span>|<span data-ttu-id="d4d12-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="d4d12-127">SplitButton</span></span>|  
|<span data-ttu-id="d4d12-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-128">Button</span></span>|<span data-ttu-id="d4d12-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-129">CheckBox</span></span>|  
|<span data-ttu-id="d4d12-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="d4d12-130">ComboBoxEx32</span></span>|<span data-ttu-id="d4d12-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-131">ComboBox</span></span>|  
|<span data-ttu-id="d4d12-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-132">ComboBox</span></span>|<span data-ttu-id="d4d12-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-133">ComboBox</span></span>|  
|<span data-ttu-id="d4d12-134">Edit</span><span class="sxs-lookup"><span data-stu-id="d4d12-134">Edit</span></span>|<span data-ttu-id="d4d12-135">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="d4d12-135">Document</span></span>|  
|<span data-ttu-id="d4d12-136">Edit</span><span class="sxs-lookup"><span data-stu-id="d4d12-136">Edit</span></span>|<span data-ttu-id="d4d12-137">Edit</span><span class="sxs-lookup"><span data-stu-id="d4d12-137">Edit</span></span>|  
|<span data-ttu-id="d4d12-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="d4d12-138">SysLink</span></span>|<span data-ttu-id="d4d12-139">Link</span><span class="sxs-lookup"><span data-stu-id="d4d12-139">Hyperlink</span></span>|  
|<span data-ttu-id="d4d12-140">Static</span><span class="sxs-lookup"><span data-stu-id="d4d12-140">Static</span></span>|<span data-ttu-id="d4d12-141">Text</span><span class="sxs-lookup"><span data-stu-id="d4d12-141">Text</span></span>|  
|<span data-ttu-id="d4d12-142">Static</span><span class="sxs-lookup"><span data-stu-id="d4d12-142">Static</span></span>|<span data-ttu-id="d4d12-143">Bild</span><span class="sxs-lookup"><span data-stu-id="d4d12-143">Image</span></span>|  
|<span data-ttu-id="d4d12-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="d4d12-144">SysIPAddress32</span></span>|<span data-ttu-id="d4d12-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="d4d12-145">Custom</span></span>|  
|<span data-ttu-id="d4d12-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="d4d12-146">SysHeader32</span></span>|<span data-ttu-id="d4d12-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="d4d12-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="d4d12-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d4d12-148">SysListView32</span></span>|<span data-ttu-id="d4d12-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d4d12-149">DataGrid</span></span>|  
|<span data-ttu-id="d4d12-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d4d12-150">SysListView32</span></span>|<span data-ttu-id="d4d12-151">Liste</span><span class="sxs-lookup"><span data-stu-id="d4d12-151">List</span></span>|  
|<span data-ttu-id="d4d12-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-152">ListBox</span></span>|<span data-ttu-id="d4d12-153">Liste</span><span class="sxs-lookup"><span data-stu-id="d4d12-153">List</span></span>|  
|<span data-ttu-id="d4d12-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-154">ListBox</span></span>|<span data-ttu-id="d4d12-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="d4d12-155">ListItem</span></span>|  
|<span data-ttu-id="d4d12-156">#32768</span><span class="sxs-lookup"><span data-stu-id="d4d12-156">#32768</span></span>|<span data-ttu-id="d4d12-157">Menü</span><span class="sxs-lookup"><span data-stu-id="d4d12-157">Menu</span></span>|  
|<span data-ttu-id="d4d12-158">#32768</span><span class="sxs-lookup"><span data-stu-id="d4d12-158">#32768</span></span>|<span data-ttu-id="d4d12-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d4d12-159">MenuItem</span></span>|  
|<span data-ttu-id="d4d12-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="d4d12-160">msctls_progress32</span></span>|<span data-ttu-id="d4d12-161">Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="d4d12-161">ProgressBar</span></span>|  
|<span data-ttu-id="d4d12-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="d4d12-162">RichEdit</span></span>|<span data-ttu-id="d4d12-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="d4d12-163">Document.</span></span> <span data-ttu-id="d4d12-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="d4d12-164">See note.</span></span>|  
|<span data-ttu-id="d4d12-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="d4d12-165">RichEdit20A</span></span>|<span data-ttu-id="d4d12-166">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="d4d12-166">Document</span></span>|  
|<span data-ttu-id="d4d12-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="d4d12-167">RichEdit20W</span></span>|<span data-ttu-id="d4d12-168">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="d4d12-168">Document</span></span>|  
|<span data-ttu-id="d4d12-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="d4d12-169">RichEdit50W</span></span>|<span data-ttu-id="d4d12-170">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="d4d12-170">Document</span></span>|  
|<span data-ttu-id="d4d12-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-171">ScrollBar</span></span>|<span data-ttu-id="d4d12-172">Slider</span><span class="sxs-lookup"><span data-stu-id="d4d12-172">Slider</span></span>|  
|<span data-ttu-id="d4d12-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="d4d12-173">msctls_trackbar32</span></span>|<span data-ttu-id="d4d12-174">Slider</span><span class="sxs-lookup"><span data-stu-id="d4d12-174">Slider</span></span>|  
|<span data-ttu-id="d4d12-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="d4d12-175">msctls_updown32</span></span>|<span data-ttu-id="d4d12-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="d4d12-176">Spinner</span></span>|  
|<span data-ttu-id="d4d12-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="d4d12-177">msctls_statusbar32</span></span>|<span data-ttu-id="d4d12-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-178">StatusBar</span></span>|  
|<span data-ttu-id="d4d12-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d4d12-179">SysTabControl32</span></span>|<span data-ttu-id="d4d12-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="d4d12-180">Tab</span></span>|  
|<span data-ttu-id="d4d12-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d4d12-181">SysTabControl32</span></span>|<span data-ttu-id="d4d12-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="d4d12-182">TabItem</span></span>|  
|<span data-ttu-id="d4d12-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d4d12-183">ToolbarWindow32</span></span>|<span data-ttu-id="d4d12-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-184">ToolBar</span></span>|  
|<span data-ttu-id="d4d12-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d4d12-185">ToolbarWindow32</span></span>|<span data-ttu-id="d4d12-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d4d12-186">MenuItem</span></span>|  
|<span data-ttu-id="d4d12-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d4d12-187">ToolbarWindow32</span></span>|<span data-ttu-id="d4d12-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-188">Button</span></span>|  
|<span data-ttu-id="d4d12-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d4d12-189">ToolbarWindow32</span></span>|<span data-ttu-id="d4d12-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-190">CheckBox</span></span>|  
|<span data-ttu-id="d4d12-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d4d12-191">ToolbarWindow32</span></span>|<span data-ttu-id="d4d12-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d4d12-192">RadioButton</span></span>|  
|<span data-ttu-id="d4d12-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d4d12-193">ToolbarWindow32</span></span>|<span data-ttu-id="d4d12-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d4d12-194">Separator</span></span>|  
|<span data-ttu-id="d4d12-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="d4d12-195">tooltips_class32</span></span>|<span data-ttu-id="d4d12-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="d4d12-196">ToolTip</span></span>|  
|<span data-ttu-id="d4d12-197">#32774</span><span class="sxs-lookup"><span data-stu-id="d4d12-197">#32774</span></span>|<span data-ttu-id="d4d12-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="d4d12-198">ToolTip</span></span>|  
|<span data-ttu-id="d4d12-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="d4d12-199">ReBarWindow32</span></span>|<span data-ttu-id="d4d12-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-200">Toolbar</span></span>|  
|<span data-ttu-id="d4d12-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d4d12-201">SysTreeView32</span></span>|<span data-ttu-id="d4d12-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="d4d12-202">Tree</span></span>|  
|<span data-ttu-id="d4d12-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d4d12-203">SysTreeView32</span></span>|<span data-ttu-id="d4d12-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="d4d12-204">TreeItem</span></span>|  
  
 <span data-ttu-id="d4d12-205">**Hinweis** Das RichEdit-Steuerelement wird nur für Versionen unterstützt, die mit Windows Vista ausgeliefert werden (in Riched20. dll, Version 3,1 und höher, und MSF Tedit. dll, Version 4,1 und höher).</span><span class="sxs-lookup"><span data-stu-id="d4d12-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="d4d12-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d4d12-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="d4d12-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="d4d12-207">Class name</span></span>|<span data-ttu-id="d4d12-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="d4d12-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d4d12-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="d4d12-209">SysAnimate32</span></span>|<span data-ttu-id="d4d12-210">Bild</span><span class="sxs-lookup"><span data-stu-id="d4d12-210">Image</span></span>|  
|<span data-ttu-id="d4d12-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="d4d12-211">SysPager</span></span>|<span data-ttu-id="d4d12-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="d4d12-212">Spinner</span></span>|  
|<span data-ttu-id="d4d12-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="d4d12-213">SysDateTimePick32</span></span>|<span data-ttu-id="d4d12-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="d4d12-214">Custom</span></span>|  
|<span data-ttu-id="d4d12-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="d4d12-215">SysMonthCal32</span></span>|<span data-ttu-id="d4d12-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="d4d12-216">Calendar</span></span>|  
|<span data-ttu-id="d4d12-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="d4d12-217">MS_WINNOTE</span></span>|<span data-ttu-id="d4d12-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="d4d12-218">Tooltip</span></span>|  
|<span data-ttu-id="d4d12-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="d4d12-219">VBBubble</span></span>|<span data-ttu-id="d4d12-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="d4d12-220">Tooltip</span></span>|  
|<span data-ttu-id="d4d12-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="d4d12-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="d4d12-222">Slider</span><span class="sxs-lookup"><span data-stu-id="d4d12-222">Slider</span></span>|  
|<span data-ttu-id="d4d12-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="d4d12-223">SuperGrid</span></span>|<span data-ttu-id="d4d12-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="d4d12-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="d4d12-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d4d12-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="d4d12-226">Windows Forms Steuerelemente werden über Client seitige Anbieter in "UIAutomationClientsideProviders. dll" [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d4d12-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d4d12-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="d4d12-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d4d12-228">In der Regel werden Windows Forms Steuerelemente, die verwaltete Wrapper für allgemeine Win32-Steuerelemente sind, von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4d12-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d4d12-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d4d12-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d4d12-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="d4d12-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="d4d12-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="d4d12-231">Button</span></span>|  
|<span data-ttu-id="d4d12-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-232">CheckBox</span></span>|  
|<span data-ttu-id="d4d12-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-233">CheckedListBox</span></span>|  
|<span data-ttu-id="d4d12-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="d4d12-234">ColorDialog</span></span>|  
|<span data-ttu-id="d4d12-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-235">ComboBox</span></span>|  
|<span data-ttu-id="d4d12-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="d4d12-236">FolderBrowser</span></span>|  
|<span data-ttu-id="d4d12-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="d4d12-237">FontDialog</span></span>|  
|<span data-ttu-id="d4d12-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-238">GroupBox</span></span>|  
|<span data-ttu-id="d4d12-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-239">HscrollBar</span></span>|  
|<span data-ttu-id="d4d12-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="d4d12-240">ImageList</span></span>|  
|<span data-ttu-id="d4d12-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="d4d12-241">Label</span></span>|  
|<span data-ttu-id="d4d12-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-242">ListBox</span></span>|  
|<span data-ttu-id="d4d12-243">ListView</span><span class="sxs-lookup"><span data-stu-id="d4d12-243">ListView</span></span>|  
|<span data-ttu-id="d4d12-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="d4d12-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="d4d12-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="d4d12-245">MonthCalendar</span></span>|  
|<span data-ttu-id="d4d12-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="d4d12-246">NotifyIcon</span></span>|  
|<span data-ttu-id="d4d12-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="d4d12-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="d4d12-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="d4d12-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="d4d12-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="d4d12-249">PrintDialog</span></span>|  
|<span data-ttu-id="d4d12-250">Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="d4d12-250">ProgressBar</span></span>|  
|<span data-ttu-id="d4d12-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d4d12-251">RadioButton</span></span>|  
|<span data-ttu-id="d4d12-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-252">RichTextBox</span></span>|  
|<span data-ttu-id="d4d12-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="d4d12-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="d4d12-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="d4d12-254">ScrollableControl</span></span>|  
|<span data-ttu-id="d4d12-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="d4d12-255">SoundPlayer</span></span>|  
|<span data-ttu-id="d4d12-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-256">StatusBar</span></span>|  
|<span data-ttu-id="d4d12-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="d4d12-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="d4d12-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-258">TextBox</span></span>|  
|<span data-ttu-id="d4d12-259">Timer</span><span class="sxs-lookup"><span data-stu-id="d4d12-259">Timer</span></span>|  
|<span data-ttu-id="d4d12-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-260">Toolbar</span></span>|  
|<span data-ttu-id="d4d12-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="d4d12-261">ToolTip</span></span>|  
|<span data-ttu-id="d4d12-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-262">TrackBar</span></span>|  
|<span data-ttu-id="d4d12-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="d4d12-263">TreeView</span></span>|  
|<span data-ttu-id="d4d12-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="d4d12-264">VscrollBar</span></span>|  
|<span data-ttu-id="d4d12-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="d4d12-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="d4d12-266">Die folgenden Steuerelemente sind nur für die Unterstützung von Microsoft Active Accessibility verfügbar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4d12-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="d4d12-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4d12-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="d4d12-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="d4d12-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="d4d12-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="d4d12-269">BindingSource</span></span>|  
|<span data-ttu-id="d4d12-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d4d12-270">DataGrid</span></span>|  
|<span data-ttu-id="d4d12-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="d4d12-271">DataGridView</span></span>|  
|<span data-ttu-id="d4d12-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="d4d12-272">DataNavigator</span></span>|  
|<span data-ttu-id="d4d12-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="d4d12-273">DomainUpDown</span></span>|  
|<span data-ttu-id="d4d12-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="d4d12-274">ErrorProvider</span></span>|  
|<span data-ttu-id="d4d12-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d4d12-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="d4d12-276">Formular</span><span class="sxs-lookup"><span data-stu-id="d4d12-276">Form</span></span>|  
|<span data-ttu-id="d4d12-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d4d12-277">LinkLabel</span></span>|  
|<span data-ttu-id="d4d12-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="d4d12-278">HelpProvider</span></span>|  
|<span data-ttu-id="d4d12-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="d4d12-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d4d12-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="d4d12-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="d4d12-281">NumericUpDown</span></span>|  
|<span data-ttu-id="d4d12-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="d4d12-282">Panel</span></span>|  
|<span data-ttu-id="d4d12-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="d4d12-283">PictureBox</span></span>|  
|<span data-ttu-id="d4d12-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="d4d12-284">PrintDocument</span></span>|  
|<span data-ttu-id="d4d12-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="d4d12-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="d4d12-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="d4d12-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="d4d12-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="d4d12-287">PropertyGrid</span></span>|  
|<span data-ttu-id="d4d12-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="d4d12-288">UserControl</span></span>|  
|<span data-ttu-id="d4d12-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d4d12-289">ToolStrip</span></span>|  
|<span data-ttu-id="d4d12-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d4d12-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="d4d12-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="d4d12-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="d4d12-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="d4d12-292">Splitter</span></span>|  
|<span data-ttu-id="d4d12-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="d4d12-293">RaftingContainer</span></span>|  
|<span data-ttu-id="d4d12-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="d4d12-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4d12-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4d12-295">See also</span></span>

- [<span data-ttu-id="d4d12-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d4d12-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
