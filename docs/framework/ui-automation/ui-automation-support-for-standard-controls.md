---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
description: Hier finden Sie Informationen zur Benutzeroberflächenautomatisierungs-Unterstützung für Standard Steuerelemente in Anwendungen, die für Windows Presentation Foundation (WPF), Win32 und Windows Forms entwickelt wurden.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 17916a6978008439e91caae00d8b6f26045f9018
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166116"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="a5387-103">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="a5387-103">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="a5387-104">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a5387-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a5387-105">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="a5387-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a5387-106">Dieses Thema enthält Informationen zur- [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung für Standard Steuerelemente in Anwendungen, die für die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Frameworks, Win32 und Windows Forms entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="a5387-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="a5387-107">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="a5387-107">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="a5387-108">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5387-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a5387-109">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="a5387-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="a5387-110">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a5387-110">Win32 Controls</span></span>  
 <span data-ttu-id="a5387-111">Die meisten Win32-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über Client seitige Anbieter in UIAutomationClientsideProviders.dll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a5387-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a5387-112">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="a5387-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a5387-113">Vollständige Unterstützung wird nur für Steuerelemente ab Version 6 von *ComCtrl32.dll*bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a5387-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="a5387-114">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a5387-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a5387-115">Klassenname</span><span class="sxs-lookup"><span data-stu-id="a5387-115">Class name</span></span>|<span data-ttu-id="a5387-116">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="a5387-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a5387-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-117">Button</span></span>|<span data-ttu-id="a5387-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-118">Button</span></span>|  
|<span data-ttu-id="a5387-119">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-119">Button</span></span>|<span data-ttu-id="a5387-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a5387-120">RadioButton</span></span>|  
|<span data-ttu-id="a5387-121">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-121">Button</span></span>|<span data-ttu-id="a5387-122">Group</span><span class="sxs-lookup"><span data-stu-id="a5387-122">Group</span></span>|  
|<span data-ttu-id="a5387-123">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-123">Button</span></span>|<span data-ttu-id="a5387-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a5387-124">CheckBox</span></span>|  
|<span data-ttu-id="a5387-125">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-125">Button</span></span>|<span data-ttu-id="a5387-126">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="a5387-126">Hyperlink</span></span>|  
|<span data-ttu-id="a5387-127">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-127">Button</span></span>|<span data-ttu-id="a5387-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="a5387-128">SplitButton</span></span>|  
|<span data-ttu-id="a5387-129">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-129">Button</span></span>|<span data-ttu-id="a5387-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a5387-130">CheckBox</span></span>|  
|<span data-ttu-id="a5387-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="a5387-131">ComboBoxEx32</span></span>|<span data-ttu-id="a5387-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a5387-132">ComboBox</span></span>|  
|<span data-ttu-id="a5387-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a5387-133">ComboBox</span></span>|<span data-ttu-id="a5387-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a5387-134">ComboBox</span></span>|  
|<span data-ttu-id="a5387-135">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="a5387-135">Edit</span></span>|<span data-ttu-id="a5387-136">Dokument</span><span class="sxs-lookup"><span data-stu-id="a5387-136">Document</span></span>|  
|<span data-ttu-id="a5387-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="a5387-137">Edit</span></span>|<span data-ttu-id="a5387-138">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="a5387-138">Edit</span></span>|  
|<span data-ttu-id="a5387-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="a5387-139">SysLink</span></span>|<span data-ttu-id="a5387-140">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="a5387-140">Hyperlink</span></span>|  
|<span data-ttu-id="a5387-141">statischen</span><span class="sxs-lookup"><span data-stu-id="a5387-141">Static</span></span>|<span data-ttu-id="a5387-142">Text</span><span class="sxs-lookup"><span data-stu-id="a5387-142">Text</span></span>|  
|<span data-ttu-id="a5387-143">statischen</span><span class="sxs-lookup"><span data-stu-id="a5387-143">Static</span></span>|<span data-ttu-id="a5387-144">Image</span><span class="sxs-lookup"><span data-stu-id="a5387-144">Image</span></span>|  
|<span data-ttu-id="a5387-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="a5387-145">SysIPAddress32</span></span>|<span data-ttu-id="a5387-146">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="a5387-146">Custom</span></span>|  
|<span data-ttu-id="a5387-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="a5387-147">SysHeader32</span></span>|<span data-ttu-id="a5387-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="a5387-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="a5387-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a5387-149">SysListView32</span></span>|<span data-ttu-id="a5387-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a5387-150">DataGrid</span></span>|  
|<span data-ttu-id="a5387-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a5387-151">SysListView32</span></span>|<span data-ttu-id="a5387-152">List</span><span class="sxs-lookup"><span data-stu-id="a5387-152">List</span></span>|  
|<span data-ttu-id="a5387-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="a5387-153">ListBox</span></span>|<span data-ttu-id="a5387-154">List</span><span class="sxs-lookup"><span data-stu-id="a5387-154">List</span></span>|  
|<span data-ttu-id="a5387-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="a5387-155">ListBox</span></span>|<span data-ttu-id="a5387-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="a5387-156">ListItem</span></span>|  
|<span data-ttu-id="a5387-157">#32768</span><span class="sxs-lookup"><span data-stu-id="a5387-157">#32768</span></span>|<span data-ttu-id="a5387-158">Menü</span><span class="sxs-lookup"><span data-stu-id="a5387-158">Menu</span></span>|  
|<span data-ttu-id="a5387-159">#32768</span><span class="sxs-lookup"><span data-stu-id="a5387-159">#32768</span></span>|<span data-ttu-id="a5387-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a5387-160">MenuItem</span></span>|  
|<span data-ttu-id="a5387-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="a5387-161">msctls_progress32</span></span>|<span data-ttu-id="a5387-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a5387-162">ProgressBar</span></span>|  
|<span data-ttu-id="a5387-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="a5387-163">RichEdit</span></span>|<span data-ttu-id="a5387-164">Dokument.</span><span class="sxs-lookup"><span data-stu-id="a5387-164">Document.</span></span> <span data-ttu-id="a5387-165">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="a5387-165">See note.</span></span>|  
|<span data-ttu-id="a5387-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="a5387-166">RichEdit20A</span></span>|<span data-ttu-id="a5387-167">Dokument</span><span class="sxs-lookup"><span data-stu-id="a5387-167">Document</span></span>|  
|<span data-ttu-id="a5387-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="a5387-168">RichEdit20W</span></span>|<span data-ttu-id="a5387-169">Dokument</span><span class="sxs-lookup"><span data-stu-id="a5387-169">Document</span></span>|  
|<span data-ttu-id="a5387-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="a5387-170">RichEdit50W</span></span>|<span data-ttu-id="a5387-171">Dokument</span><span class="sxs-lookup"><span data-stu-id="a5387-171">Document</span></span>|  
|<span data-ttu-id="a5387-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a5387-172">ScrollBar</span></span>|<span data-ttu-id="a5387-173">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="a5387-173">Slider</span></span>|  
|<span data-ttu-id="a5387-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="a5387-174">msctls_trackbar32</span></span>|<span data-ttu-id="a5387-175">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="a5387-175">Slider</span></span>|  
|<span data-ttu-id="a5387-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="a5387-176">msctls_updown32</span></span>|<span data-ttu-id="a5387-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="a5387-177">Spinner</span></span>|  
|<span data-ttu-id="a5387-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="a5387-178">msctls_statusbar32</span></span>|<span data-ttu-id="a5387-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a5387-179">StatusBar</span></span>|  
|<span data-ttu-id="a5387-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a5387-180">SysTabControl32</span></span>|<span data-ttu-id="a5387-181">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="a5387-181">Tab</span></span>|  
|<span data-ttu-id="a5387-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a5387-182">SysTabControl32</span></span>|<span data-ttu-id="a5387-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="a5387-183">TabItem</span></span>|  
|<span data-ttu-id="a5387-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a5387-184">ToolbarWindow32</span></span>|<span data-ttu-id="a5387-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a5387-185">ToolBar</span></span>|  
|<span data-ttu-id="a5387-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a5387-186">ToolbarWindow32</span></span>|<span data-ttu-id="a5387-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a5387-187">MenuItem</span></span>|  
|<span data-ttu-id="a5387-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a5387-188">ToolbarWindow32</span></span>|<span data-ttu-id="a5387-189">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-189">Button</span></span>|  
|<span data-ttu-id="a5387-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a5387-190">ToolbarWindow32</span></span>|<span data-ttu-id="a5387-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a5387-191">CheckBox</span></span>|  
|<span data-ttu-id="a5387-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a5387-192">ToolbarWindow32</span></span>|<span data-ttu-id="a5387-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a5387-193">RadioButton</span></span>|  
|<span data-ttu-id="a5387-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a5387-194">ToolbarWindow32</span></span>|<span data-ttu-id="a5387-195">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="a5387-195">Separator</span></span>|  
|<span data-ttu-id="a5387-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="a5387-196">tooltips_class32</span></span>|<span data-ttu-id="a5387-197">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="a5387-197">ToolTip</span></span>|  
|<span data-ttu-id="a5387-198">#32774</span><span class="sxs-lookup"><span data-stu-id="a5387-198">#32774</span></span>|<span data-ttu-id="a5387-199">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="a5387-199">ToolTip</span></span>|  
|<span data-ttu-id="a5387-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="a5387-200">ReBarWindow32</span></span>|<span data-ttu-id="a5387-201">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="a5387-201">Toolbar</span></span>|  
|<span data-ttu-id="a5387-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a5387-202">SysTreeView32</span></span>|<span data-ttu-id="a5387-203">Struktur</span><span class="sxs-lookup"><span data-stu-id="a5387-203">Tree</span></span>|  
|<span data-ttu-id="a5387-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a5387-204">SysTreeView32</span></span>|<span data-ttu-id="a5387-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="a5387-205">TreeItem</span></span>|  
  
 <span data-ttu-id="a5387-206">**Hinweis** Das RichEdit-Steuerelement wird nur für Versionen unterstützt, die mit Windows Vista ausgeliefert wurden (in RichEd20.dll Version 3,1 und höher sowie MsftEdit.dll Version 4,1 und höher).</span><span class="sxs-lookup"><span data-stu-id="a5387-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="a5387-207">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a5387-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="a5387-208">Klassenname</span><span class="sxs-lookup"><span data-stu-id="a5387-208">Class name</span></span>|<span data-ttu-id="a5387-209">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="a5387-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a5387-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="a5387-210">SysAnimate32</span></span>|<span data-ttu-id="a5387-211">Image</span><span class="sxs-lookup"><span data-stu-id="a5387-211">Image</span></span>|  
|<span data-ttu-id="a5387-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="a5387-212">SysPager</span></span>|<span data-ttu-id="a5387-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="a5387-213">Spinner</span></span>|  
|<span data-ttu-id="a5387-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="a5387-214">SysDateTimePick32</span></span>|<span data-ttu-id="a5387-215">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="a5387-215">Custom</span></span>|  
|<span data-ttu-id="a5387-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="a5387-216">SysMonthCal32</span></span>|<span data-ttu-id="a5387-217">Kalender</span><span class="sxs-lookup"><span data-stu-id="a5387-217">Calendar</span></span>|  
|<span data-ttu-id="a5387-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="a5387-218">MS_WINNOTE</span></span>|<span data-ttu-id="a5387-219">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="a5387-219">Tooltip</span></span>|  
|<span data-ttu-id="a5387-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="a5387-220">VBBubble</span></span>|<span data-ttu-id="a5387-221">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="a5387-221">Tooltip</span></span>|  
|<span data-ttu-id="a5387-222">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="a5387-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="a5387-223">Schieberegler</span><span class="sxs-lookup"><span data-stu-id="a5387-223">Slider</span></span>|  
|<span data-ttu-id="a5387-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="a5387-224">SuperGrid</span></span>|<span data-ttu-id="a5387-225">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="a5387-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="a5387-226">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a5387-226">Windows Forms Controls</span></span>  
 <span data-ttu-id="a5387-227">Windows Forms-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über Client seitige Anbieter in UIAutomationClientsideProviders.dll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a5387-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a5387-228">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="a5387-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a5387-229">In der Regel werden Windows Forms Steuerelemente, die verwaltete Wrapper für allgemeine Win32-Steuerelemente sind, von unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5387-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a5387-230">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a5387-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a5387-231">Klassenname</span><span class="sxs-lookup"><span data-stu-id="a5387-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="a5387-232">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a5387-232">Button</span></span>|  
|<span data-ttu-id="a5387-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a5387-233">CheckBox</span></span>|  
|<span data-ttu-id="a5387-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="a5387-234">CheckedListBox</span></span>|  
|<span data-ttu-id="a5387-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="a5387-235">ColorDialog</span></span>|  
|<span data-ttu-id="a5387-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a5387-236">ComboBox</span></span>|  
|<span data-ttu-id="a5387-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="a5387-237">FolderBrowser</span></span>|  
|<span data-ttu-id="a5387-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="a5387-238">FontDialog</span></span>|  
|<span data-ttu-id="a5387-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="a5387-239">GroupBox</span></span>|  
|<span data-ttu-id="a5387-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="a5387-240">HscrollBar</span></span>|  
|<span data-ttu-id="a5387-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="a5387-241">ImageList</span></span>|  
|<span data-ttu-id="a5387-242">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="a5387-242">Label</span></span>|  
|<span data-ttu-id="a5387-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="a5387-243">ListBox</span></span>|  
|<span data-ttu-id="a5387-244">ListView</span><span class="sxs-lookup"><span data-stu-id="a5387-244">ListView</span></span>|  
|<span data-ttu-id="a5387-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a5387-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="a5387-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="a5387-246">MonthCalendar</span></span>|  
|<span data-ttu-id="a5387-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="a5387-247">NotifyIcon</span></span>|  
|<span data-ttu-id="a5387-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a5387-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="a5387-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="a5387-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="a5387-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a5387-250">PrintDialog</span></span>|  
|<span data-ttu-id="a5387-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a5387-251">ProgressBar</span></span>|  
|<span data-ttu-id="a5387-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a5387-252">RadioButton</span></span>|  
|<span data-ttu-id="a5387-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a5387-253">RichTextBox</span></span>|  
|<span data-ttu-id="a5387-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="a5387-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="a5387-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="a5387-255">ScrollableControl</span></span>|  
|<span data-ttu-id="a5387-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="a5387-256">SoundPlayer</span></span>|  
|<span data-ttu-id="a5387-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a5387-257">StatusBar</span></span>|  
|<span data-ttu-id="a5387-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="a5387-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="a5387-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="a5387-259">TextBox</span></span>|  
|<span data-ttu-id="a5387-260">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="a5387-260">Timer</span></span>|  
|<span data-ttu-id="a5387-261">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="a5387-261">Toolbar</span></span>|  
|<span data-ttu-id="a5387-262">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="a5387-262">ToolTip</span></span>|  
|<span data-ttu-id="a5387-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="a5387-263">TrackBar</span></span>|  
|<span data-ttu-id="a5387-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="a5387-264">TreeView</span></span>|  
|<span data-ttu-id="a5387-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="a5387-265">VscrollBar</span></span>|  
|<span data-ttu-id="a5387-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="a5387-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="a5387-267">Die folgenden Steuerelemente sind nur für die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung von Microsoft Active Accessibility verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a5387-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="a5387-268">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a5387-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="a5387-269">Name des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="a5387-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="a5387-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="a5387-270">BindingSource</span></span>|  
|<span data-ttu-id="a5387-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a5387-271">DataGrid</span></span>|  
|<span data-ttu-id="a5387-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="a5387-272">DataGridView</span></span>|  
|<span data-ttu-id="a5387-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="a5387-273">DataNavigator</span></span>|  
|<span data-ttu-id="a5387-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="a5387-274">DomainUpDown</span></span>|  
|<span data-ttu-id="a5387-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="a5387-275">ErrorProvider</span></span>|  
|<span data-ttu-id="a5387-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a5387-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="a5387-277">Formular</span><span class="sxs-lookup"><span data-stu-id="a5387-277">Form</span></span>|  
|<span data-ttu-id="a5387-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="a5387-278">LinkLabel</span></span>|  
|<span data-ttu-id="a5387-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="a5387-279">HelpProvider</span></span>|  
|<span data-ttu-id="a5387-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="a5387-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="a5387-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a5387-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="a5387-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="a5387-282">NumericUpDown</span></span>|  
|<span data-ttu-id="a5387-283">Bereich</span><span class="sxs-lookup"><span data-stu-id="a5387-283">Panel</span></span>|  
|<span data-ttu-id="a5387-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="a5387-284">PictureBox</span></span>|  
|<span data-ttu-id="a5387-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="a5387-285">PrintDocument</span></span>|  
|<span data-ttu-id="a5387-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="a5387-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="a5387-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="a5387-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="a5387-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="a5387-288">PropertyGrid</span></span>|  
|<span data-ttu-id="a5387-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="a5387-289">UserControl</span></span>|  
|<span data-ttu-id="a5387-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a5387-290">ToolStrip</span></span>|  
|<span data-ttu-id="a5387-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a5387-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="a5387-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="a5387-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="a5387-293">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="a5387-293">Splitter</span></span>|  
|<span data-ttu-id="a5387-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="a5387-294">RaftingContainer</span></span>|  
|<span data-ttu-id="a5387-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="a5387-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5387-296">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5387-296">See also</span></span>

- [<span data-ttu-id="a5387-297">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="a5387-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
