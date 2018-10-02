---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 68fa7753be76b0681c40e540e86b11c89e7a8ca1
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48037338"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="0864e-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="0864e-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="0864e-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0864e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0864e-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="0864e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="0864e-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0864e-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="0864e-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="0864e-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="0864e-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0864e-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="0864e-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="0864e-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="0864e-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0864e-109">Win32 Controls</span></span>  
 <span data-ttu-id="0864e-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="0864e-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="0864e-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="0864e-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="0864e-112">Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).</span><span class="sxs-lookup"><span data-stu-id="0864e-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="0864e-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0864e-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="0864e-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="0864e-114">Class name</span></span>|<span data-ttu-id="0864e-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="0864e-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="0864e-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-116">Button</span></span>|<span data-ttu-id="0864e-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-117">Button</span></span>|  
|<span data-ttu-id="0864e-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-118">Button</span></span>|<span data-ttu-id="0864e-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0864e-119">RadioButton</span></span>|  
|<span data-ttu-id="0864e-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-120">Button</span></span>|<span data-ttu-id="0864e-121">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="0864e-121">Group</span></span>|  
|<span data-ttu-id="0864e-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-122">Button</span></span>|<span data-ttu-id="0864e-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0864e-123">CheckBox</span></span>|  
|<span data-ttu-id="0864e-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-124">Button</span></span>|<span data-ttu-id="0864e-125">Link</span><span class="sxs-lookup"><span data-stu-id="0864e-125">Hyperlink</span></span>|  
|<span data-ttu-id="0864e-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-126">Button</span></span>|<span data-ttu-id="0864e-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="0864e-127">SplitButton</span></span>|  
|<span data-ttu-id="0864e-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-128">Button</span></span>|<span data-ttu-id="0864e-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0864e-129">CheckBox</span></span>|  
|<span data-ttu-id="0864e-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="0864e-130">ComboBoxEx32</span></span>|<span data-ttu-id="0864e-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0864e-131">ComboBox</span></span>|  
|<span data-ttu-id="0864e-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0864e-132">ComboBox</span></span>|<span data-ttu-id="0864e-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0864e-133">ComboBox</span></span>|  
|<span data-ttu-id="0864e-134">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="0864e-134">Edit</span></span>|<span data-ttu-id="0864e-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="0864e-135">Document</span></span>|  
|<span data-ttu-id="0864e-136">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="0864e-136">Edit</span></span>|<span data-ttu-id="0864e-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="0864e-137">Edit</span></span>|  
|<span data-ttu-id="0864e-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="0864e-138">SysLink</span></span>|<span data-ttu-id="0864e-139">Link</span><span class="sxs-lookup"><span data-stu-id="0864e-139">Hyperlink</span></span>|  
|<span data-ttu-id="0864e-140">Statisch</span><span class="sxs-lookup"><span data-stu-id="0864e-140">Static</span></span>|<span data-ttu-id="0864e-141">Text</span><span class="sxs-lookup"><span data-stu-id="0864e-141">Text</span></span>|  
|<span data-ttu-id="0864e-142">Statisch</span><span class="sxs-lookup"><span data-stu-id="0864e-142">Static</span></span>|<span data-ttu-id="0864e-143">Bild</span><span class="sxs-lookup"><span data-stu-id="0864e-143">Image</span></span>|  
|<span data-ttu-id="0864e-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="0864e-144">SysIPAddress32</span></span>|<span data-ttu-id="0864e-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="0864e-145">Custom</span></span>|  
|<span data-ttu-id="0864e-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="0864e-146">SysHeader32</span></span>|<span data-ttu-id="0864e-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="0864e-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="0864e-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="0864e-148">SysListView32</span></span>|<span data-ttu-id="0864e-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="0864e-149">DataGrid</span></span>|  
|<span data-ttu-id="0864e-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="0864e-150">SysListView32</span></span>|<span data-ttu-id="0864e-151">Liste</span><span class="sxs-lookup"><span data-stu-id="0864e-151">List</span></span>|  
|<span data-ttu-id="0864e-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="0864e-152">ListBox</span></span>|<span data-ttu-id="0864e-153">Liste</span><span class="sxs-lookup"><span data-stu-id="0864e-153">List</span></span>|  
|<span data-ttu-id="0864e-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="0864e-154">ListBox</span></span>|<span data-ttu-id="0864e-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="0864e-155">ListItem</span></span>|  
|<span data-ttu-id="0864e-156">#32768</span><span class="sxs-lookup"><span data-stu-id="0864e-156">#32768</span></span>|<span data-ttu-id="0864e-157">Menü</span><span class="sxs-lookup"><span data-stu-id="0864e-157">Menu</span></span>|  
|<span data-ttu-id="0864e-158">#32768</span><span class="sxs-lookup"><span data-stu-id="0864e-158">#32768</span></span>|<span data-ttu-id="0864e-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="0864e-159">MenuItem</span></span>|  
|<span data-ttu-id="0864e-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="0864e-160">msctls_progress32</span></span>|<span data-ttu-id="0864e-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="0864e-161">ProgressBar</span></span>|  
|<span data-ttu-id="0864e-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="0864e-162">RichEdit</span></span>|<span data-ttu-id="0864e-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="0864e-163">Document.</span></span> <span data-ttu-id="0864e-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="0864e-164">See note.</span></span>|  
|<span data-ttu-id="0864e-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="0864e-165">RichEdit20A</span></span>|<span data-ttu-id="0864e-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="0864e-166">Document</span></span>|  
|<span data-ttu-id="0864e-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="0864e-167">RichEdit20W</span></span>|<span data-ttu-id="0864e-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="0864e-168">Document</span></span>|  
|<span data-ttu-id="0864e-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="0864e-169">RichEdit50W</span></span>|<span data-ttu-id="0864e-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="0864e-170">Document</span></span>|  
|<span data-ttu-id="0864e-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0864e-171">ScrollBar</span></span>|<span data-ttu-id="0864e-172">Slider</span><span class="sxs-lookup"><span data-stu-id="0864e-172">Slider</span></span>|  
|<span data-ttu-id="0864e-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="0864e-173">msctls_trackbar32</span></span>|<span data-ttu-id="0864e-174">Slider</span><span class="sxs-lookup"><span data-stu-id="0864e-174">Slider</span></span>|  
|<span data-ttu-id="0864e-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="0864e-175">msctls_updown32</span></span>|<span data-ttu-id="0864e-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="0864e-176">Spinner</span></span>|  
|<span data-ttu-id="0864e-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="0864e-177">msctls_statusbar32</span></span>|<span data-ttu-id="0864e-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="0864e-178">StatusBar</span></span>|  
|<span data-ttu-id="0864e-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="0864e-179">SysTabControl32</span></span>|<span data-ttu-id="0864e-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="0864e-180">Tab</span></span>|  
|<span data-ttu-id="0864e-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="0864e-181">SysTabControl32</span></span>|<span data-ttu-id="0864e-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="0864e-182">TabItem</span></span>|  
|<span data-ttu-id="0864e-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0864e-183">ToolbarWindow32</span></span>|<span data-ttu-id="0864e-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="0864e-184">ToolBar</span></span>|  
|<span data-ttu-id="0864e-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0864e-185">ToolbarWindow32</span></span>|<span data-ttu-id="0864e-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="0864e-186">MenuItem</span></span>|  
|<span data-ttu-id="0864e-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0864e-187">ToolbarWindow32</span></span>|<span data-ttu-id="0864e-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-188">Button</span></span>|  
|<span data-ttu-id="0864e-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0864e-189">ToolbarWindow32</span></span>|<span data-ttu-id="0864e-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0864e-190">CheckBox</span></span>|  
|<span data-ttu-id="0864e-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0864e-191">ToolbarWindow32</span></span>|<span data-ttu-id="0864e-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0864e-192">RadioButton</span></span>|  
|<span data-ttu-id="0864e-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0864e-193">ToolbarWindow32</span></span>|<span data-ttu-id="0864e-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="0864e-194">Separator</span></span>|  
|<span data-ttu-id="0864e-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="0864e-195">tooltips_class32</span></span>|<span data-ttu-id="0864e-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0864e-196">ToolTip</span></span>|  
|<span data-ttu-id="0864e-197">#32774</span><span class="sxs-lookup"><span data-stu-id="0864e-197">#32774</span></span>|<span data-ttu-id="0864e-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0864e-198">ToolTip</span></span>|  
|<span data-ttu-id="0864e-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="0864e-199">ReBarWindow32</span></span>|<span data-ttu-id="0864e-200">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="0864e-200">Toolbar</span></span>|  
|<span data-ttu-id="0864e-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="0864e-201">SysTreeView32</span></span>|<span data-ttu-id="0864e-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="0864e-202">Tree</span></span>|  
|<span data-ttu-id="0864e-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="0864e-203">SysTreeView32</span></span>|<span data-ttu-id="0864e-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="0864e-204">TreeItem</span></span>|  
  
 <span data-ttu-id="0864e-205">**Hinweis** Das RichEdit-Steuerelement wird nur für mit [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] ausgelieferte Versionen unterstützt (in „RichEd20.dll“ ab Version 3.1 und „MsftEdit.dll“ ab Version 4.1).</span><span class="sxs-lookup"><span data-stu-id="0864e-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="0864e-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0864e-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="0864e-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="0864e-207">Class name</span></span>|<span data-ttu-id="0864e-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="0864e-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="0864e-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="0864e-209">SysAnimate32</span></span>|<span data-ttu-id="0864e-210">Bild</span><span class="sxs-lookup"><span data-stu-id="0864e-210">Image</span></span>|  
|<span data-ttu-id="0864e-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="0864e-211">SysPager</span></span>|<span data-ttu-id="0864e-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="0864e-212">Spinner</span></span>|  
|<span data-ttu-id="0864e-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="0864e-213">SysDateTimePick32</span></span>|<span data-ttu-id="0864e-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="0864e-214">Custom</span></span>|  
|<span data-ttu-id="0864e-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="0864e-215">SysMonthCal32</span></span>|<span data-ttu-id="0864e-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="0864e-216">Calendar</span></span>|  
|<span data-ttu-id="0864e-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="0864e-217">MS_WINNOTE</span></span>|<span data-ttu-id="0864e-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0864e-218">Tooltip</span></span>|  
|<span data-ttu-id="0864e-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="0864e-219">VBBubble</span></span>|<span data-ttu-id="0864e-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0864e-220">Tooltip</span></span>|  
|<span data-ttu-id="0864e-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="0864e-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="0864e-222">Slider</span><span class="sxs-lookup"><span data-stu-id="0864e-222">Slider</span></span>|  
|<span data-ttu-id="0864e-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="0864e-223">SuperGrid</span></span>|<span data-ttu-id="0864e-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="0864e-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="0864e-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0864e-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="0864e-226">Windows Forms-Steuerelemente werden verfügbar gemacht, um [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über clientseitige Anbieter in "UIAutomationClientsideProviders.dll".</span><span class="sxs-lookup"><span data-stu-id="0864e-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="0864e-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="0864e-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="0864e-228">Windows Forms-Steuerelemente, die Sie in der Regel die verwaltete Wrapper für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] allgemeine Steuerelemente werden von unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0864e-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="0864e-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0864e-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="0864e-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="0864e-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="0864e-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0864e-231">Button</span></span>|  
|<span data-ttu-id="0864e-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0864e-232">CheckBox</span></span>|  
|<span data-ttu-id="0864e-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="0864e-233">CheckedListBox</span></span>|  
|<span data-ttu-id="0864e-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="0864e-234">ColorDialog</span></span>|  
|<span data-ttu-id="0864e-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0864e-235">ComboBox</span></span>|  
|<span data-ttu-id="0864e-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="0864e-236">FolderBrowser</span></span>|  
|<span data-ttu-id="0864e-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="0864e-237">FontDialog</span></span>|  
|<span data-ttu-id="0864e-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="0864e-238">GroupBox</span></span>|  
|<span data-ttu-id="0864e-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="0864e-239">HscrollBar</span></span>|  
|<span data-ttu-id="0864e-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="0864e-240">ImageList</span></span>|  
|<span data-ttu-id="0864e-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="0864e-241">Label</span></span>|  
|<span data-ttu-id="0864e-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="0864e-242">ListBox</span></span>|  
|<span data-ttu-id="0864e-243">ListView</span><span class="sxs-lookup"><span data-stu-id="0864e-243">ListView</span></span>|  
|<span data-ttu-id="0864e-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0864e-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="0864e-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="0864e-245">MonthCalendar</span></span>|  
|<span data-ttu-id="0864e-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="0864e-246">NotifyIcon</span></span>|  
|<span data-ttu-id="0864e-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="0864e-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="0864e-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="0864e-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="0864e-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="0864e-249">PrintDialog</span></span>|  
|<span data-ttu-id="0864e-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="0864e-250">ProgressBar</span></span>|  
|<span data-ttu-id="0864e-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0864e-251">RadioButton</span></span>|  
|<span data-ttu-id="0864e-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0864e-252">RichTextBox</span></span>|  
|<span data-ttu-id="0864e-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="0864e-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="0864e-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="0864e-254">ScrollableControl</span></span>|  
|<span data-ttu-id="0864e-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="0864e-255">SoundPlayer</span></span>|  
|<span data-ttu-id="0864e-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="0864e-256">StatusBar</span></span>|  
|<span data-ttu-id="0864e-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="0864e-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="0864e-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="0864e-258">TextBox</span></span>|  
|<span data-ttu-id="0864e-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="0864e-259">Timer</span></span>|  
|<span data-ttu-id="0864e-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="0864e-260">Toolbar</span></span>|  
|<span data-ttu-id="0864e-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0864e-261">ToolTip</span></span>|  
|<span data-ttu-id="0864e-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="0864e-262">TrackBar</span></span>|  
|<span data-ttu-id="0864e-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="0864e-263">TreeView</span></span>|  
|<span data-ttu-id="0864e-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="0864e-264">VscrollBar</span></span>|  
|<span data-ttu-id="0864e-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="0864e-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="0864e-266">Die folgenden Steuerelemente sind für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] nur über ihre Unterstützung für [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0864e-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="0864e-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0864e-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="0864e-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="0864e-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="0864e-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="0864e-269">BindingSource</span></span>|  
|<span data-ttu-id="0864e-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="0864e-270">DataGrid</span></span>|  
|<span data-ttu-id="0864e-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="0864e-271">DataGridView</span></span>|  
|<span data-ttu-id="0864e-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="0864e-272">DataNavigator</span></span>|  
|<span data-ttu-id="0864e-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="0864e-273">DomainUpDown</span></span>|  
|<span data-ttu-id="0864e-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="0864e-274">ErrorProvider</span></span>|  
|<span data-ttu-id="0864e-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0864e-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="0864e-276">Formular</span><span class="sxs-lookup"><span data-stu-id="0864e-276">Form</span></span>|  
|<span data-ttu-id="0864e-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="0864e-277">LinkLabel</span></span>|  
|<span data-ttu-id="0864e-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="0864e-278">HelpProvider</span></span>|  
|<span data-ttu-id="0864e-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="0864e-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="0864e-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="0864e-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="0864e-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="0864e-281">NumericUpDown</span></span>|  
|<span data-ttu-id="0864e-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="0864e-282">Panel</span></span>|  
|<span data-ttu-id="0864e-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="0864e-283">PictureBox</span></span>|  
|<span data-ttu-id="0864e-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="0864e-284">PrintDocument</span></span>|  
|<span data-ttu-id="0864e-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="0864e-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="0864e-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="0864e-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="0864e-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="0864e-287">PropertyGrid</span></span>|  
|<span data-ttu-id="0864e-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="0864e-288">UserControl</span></span>|  
|<span data-ttu-id="0864e-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0864e-289">ToolStrip</span></span>|  
|<span data-ttu-id="0864e-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0864e-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="0864e-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="0864e-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="0864e-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="0864e-292">Splitter</span></span>|  
|<span data-ttu-id="0864e-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="0864e-293">RaftingContainer</span></span>|  
|<span data-ttu-id="0864e-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="0864e-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0864e-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0864e-295">See Also</span></span>  
 [<span data-ttu-id="0864e-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="0864e-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
