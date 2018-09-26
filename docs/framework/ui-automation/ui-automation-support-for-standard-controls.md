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
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157024"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="7cffa-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="7cffa-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="7cffa-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7cffa-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7cffa-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="7cffa-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7cffa-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7cffa-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="7cffa-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="7cffa-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="7cffa-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cffa-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="7cffa-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="7cffa-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="7cffa-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="7cffa-109">Win32 Controls</span></span>  
 <span data-ttu-id="7cffa-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="7cffa-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="7cffa-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="7cffa-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="7cffa-112">Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).</span><span class="sxs-lookup"><span data-stu-id="7cffa-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="7cffa-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7cffa-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="7cffa-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="7cffa-114">Class name</span></span>|<span data-ttu-id="7cffa-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="7cffa-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="7cffa-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-116">Button</span></span>|<span data-ttu-id="7cffa-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-117">Button</span></span>|  
|<span data-ttu-id="7cffa-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-118">Button</span></span>|<span data-ttu-id="7cffa-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7cffa-119">RadioButton</span></span>|  
|<span data-ttu-id="7cffa-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-120">Button</span></span>|<span data-ttu-id="7cffa-121">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="7cffa-121">Group</span></span>|  
|<span data-ttu-id="7cffa-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-122">Button</span></span>|<span data-ttu-id="7cffa-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-123">CheckBox</span></span>|  
|<span data-ttu-id="7cffa-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-124">Button</span></span>|<span data-ttu-id="7cffa-125">Link</span><span class="sxs-lookup"><span data-stu-id="7cffa-125">Hyperlink</span></span>|  
|<span data-ttu-id="7cffa-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-126">Button</span></span>|<span data-ttu-id="7cffa-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="7cffa-127">SplitButton</span></span>|  
|<span data-ttu-id="7cffa-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-128">Button</span></span>|<span data-ttu-id="7cffa-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-129">CheckBox</span></span>|  
|<span data-ttu-id="7cffa-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="7cffa-130">ComboBoxEx32</span></span>|<span data-ttu-id="7cffa-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-131">ComboBox</span></span>|  
|<span data-ttu-id="7cffa-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-132">ComboBox</span></span>|<span data-ttu-id="7cffa-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-133">ComboBox</span></span>|  
|<span data-ttu-id="7cffa-134">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="7cffa-134">Edit</span></span>|<span data-ttu-id="7cffa-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="7cffa-135">Document</span></span>|  
|<span data-ttu-id="7cffa-136">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="7cffa-136">Edit</span></span>|<span data-ttu-id="7cffa-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="7cffa-137">Edit</span></span>|  
|<span data-ttu-id="7cffa-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="7cffa-138">SysLink</span></span>|<span data-ttu-id="7cffa-139">Link</span><span class="sxs-lookup"><span data-stu-id="7cffa-139">Hyperlink</span></span>|  
|<span data-ttu-id="7cffa-140">Statisch</span><span class="sxs-lookup"><span data-stu-id="7cffa-140">Static</span></span>|<span data-ttu-id="7cffa-141">Text</span><span class="sxs-lookup"><span data-stu-id="7cffa-141">Text</span></span>|  
|<span data-ttu-id="7cffa-142">Statisch</span><span class="sxs-lookup"><span data-stu-id="7cffa-142">Static</span></span>|<span data-ttu-id="7cffa-143">Bild</span><span class="sxs-lookup"><span data-stu-id="7cffa-143">Image</span></span>|  
|<span data-ttu-id="7cffa-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="7cffa-144">SysIPAddress32</span></span>|<span data-ttu-id="7cffa-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="7cffa-145">Custom</span></span>|  
|<span data-ttu-id="7cffa-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="7cffa-146">SysHeader32</span></span>|<span data-ttu-id="7cffa-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="7cffa-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="7cffa-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="7cffa-148">SysListView32</span></span>|<span data-ttu-id="7cffa-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="7cffa-149">DataGrid</span></span>|  
|<span data-ttu-id="7cffa-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="7cffa-150">SysListView32</span></span>|<span data-ttu-id="7cffa-151">Liste</span><span class="sxs-lookup"><span data-stu-id="7cffa-151">List</span></span>|  
|<span data-ttu-id="7cffa-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-152">ListBox</span></span>|<span data-ttu-id="7cffa-153">Liste</span><span class="sxs-lookup"><span data-stu-id="7cffa-153">List</span></span>|  
|<span data-ttu-id="7cffa-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-154">ListBox</span></span>|<span data-ttu-id="7cffa-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="7cffa-155">ListItem</span></span>|  
|<span data-ttu-id="7cffa-156">#32768</span><span class="sxs-lookup"><span data-stu-id="7cffa-156">#32768</span></span>|<span data-ttu-id="7cffa-157">Menü</span><span class="sxs-lookup"><span data-stu-id="7cffa-157">Menu</span></span>|  
|<span data-ttu-id="7cffa-158">#32768</span><span class="sxs-lookup"><span data-stu-id="7cffa-158">#32768</span></span>|<span data-ttu-id="7cffa-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="7cffa-159">MenuItem</span></span>|  
|<span data-ttu-id="7cffa-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="7cffa-160">msctls_progress32</span></span>|<span data-ttu-id="7cffa-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-161">ProgressBar</span></span>|  
|<span data-ttu-id="7cffa-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="7cffa-162">RichEdit</span></span>|<span data-ttu-id="7cffa-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="7cffa-163">Document.</span></span> <span data-ttu-id="7cffa-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="7cffa-164">See note.</span></span>|  
|<span data-ttu-id="7cffa-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="7cffa-165">RichEdit20A</span></span>|<span data-ttu-id="7cffa-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="7cffa-166">Document</span></span>|  
|<span data-ttu-id="7cffa-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="7cffa-167">RichEdit20W</span></span>|<span data-ttu-id="7cffa-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="7cffa-168">Document</span></span>|  
|<span data-ttu-id="7cffa-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="7cffa-169">RichEdit50W</span></span>|<span data-ttu-id="7cffa-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="7cffa-170">Document</span></span>|  
|<span data-ttu-id="7cffa-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-171">ScrollBar</span></span>|<span data-ttu-id="7cffa-172">Slider</span><span class="sxs-lookup"><span data-stu-id="7cffa-172">Slider</span></span>|  
|<span data-ttu-id="7cffa-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="7cffa-173">msctls_trackbar32</span></span>|<span data-ttu-id="7cffa-174">Slider</span><span class="sxs-lookup"><span data-stu-id="7cffa-174">Slider</span></span>|  
|<span data-ttu-id="7cffa-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="7cffa-175">msctls_updown32</span></span>|<span data-ttu-id="7cffa-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="7cffa-176">Spinner</span></span>|  
|<span data-ttu-id="7cffa-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="7cffa-177">msctls_statusbar32</span></span>|<span data-ttu-id="7cffa-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-178">StatusBar</span></span>|  
|<span data-ttu-id="7cffa-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="7cffa-179">SysTabControl32</span></span>|<span data-ttu-id="7cffa-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="7cffa-180">Tab</span></span>|  
|<span data-ttu-id="7cffa-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="7cffa-181">SysTabControl32</span></span>|<span data-ttu-id="7cffa-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="7cffa-182">TabItem</span></span>|  
|<span data-ttu-id="7cffa-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7cffa-183">ToolbarWindow32</span></span>|<span data-ttu-id="7cffa-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-184">ToolBar</span></span>|  
|<span data-ttu-id="7cffa-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7cffa-185">ToolbarWindow32</span></span>|<span data-ttu-id="7cffa-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="7cffa-186">MenuItem</span></span>|  
|<span data-ttu-id="7cffa-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7cffa-187">ToolbarWindow32</span></span>|<span data-ttu-id="7cffa-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-188">Button</span></span>|  
|<span data-ttu-id="7cffa-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7cffa-189">ToolbarWindow32</span></span>|<span data-ttu-id="7cffa-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-190">CheckBox</span></span>|  
|<span data-ttu-id="7cffa-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7cffa-191">ToolbarWindow32</span></span>|<span data-ttu-id="7cffa-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7cffa-192">RadioButton</span></span>|  
|<span data-ttu-id="7cffa-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7cffa-193">ToolbarWindow32</span></span>|<span data-ttu-id="7cffa-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="7cffa-194">Separator</span></span>|  
|<span data-ttu-id="7cffa-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="7cffa-195">tooltips_class32</span></span>|<span data-ttu-id="7cffa-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="7cffa-196">ToolTip</span></span>|  
|<span data-ttu-id="7cffa-197">#32774</span><span class="sxs-lookup"><span data-stu-id="7cffa-197">#32774</span></span>|<span data-ttu-id="7cffa-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="7cffa-198">ToolTip</span></span>|  
|<span data-ttu-id="7cffa-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="7cffa-199">ReBarWindow32</span></span>|<span data-ttu-id="7cffa-200">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="7cffa-200">Toolbar</span></span>|  
|<span data-ttu-id="7cffa-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="7cffa-201">SysTreeView32</span></span>|<span data-ttu-id="7cffa-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="7cffa-202">Tree</span></span>|  
|<span data-ttu-id="7cffa-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="7cffa-203">SysTreeView32</span></span>|<span data-ttu-id="7cffa-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="7cffa-204">TreeItem</span></span>|  
  
 <span data-ttu-id="7cffa-205">**Hinweis** Das RichEdit-Steuerelement wird nur für mit [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] ausgelieferte Versionen unterstützt (in „RichEd20.dll“ ab Version 3.1 und „MsftEdit.dll“ ab Version 4.1).</span><span class="sxs-lookup"><span data-stu-id="7cffa-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="7cffa-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7cffa-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="7cffa-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="7cffa-207">Class name</span></span>|<span data-ttu-id="7cffa-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="7cffa-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="7cffa-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="7cffa-209">SysAnimate32</span></span>|<span data-ttu-id="7cffa-210">Bild</span><span class="sxs-lookup"><span data-stu-id="7cffa-210">Image</span></span>|  
|<span data-ttu-id="7cffa-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="7cffa-211">SysPager</span></span>|<span data-ttu-id="7cffa-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="7cffa-212">Spinner</span></span>|  
|<span data-ttu-id="7cffa-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="7cffa-213">SysDateTimePick32</span></span>|<span data-ttu-id="7cffa-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="7cffa-214">Custom</span></span>|  
|<span data-ttu-id="7cffa-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="7cffa-215">SysMonthCal32</span></span>|<span data-ttu-id="7cffa-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="7cffa-216">Calendar</span></span>|  
|<span data-ttu-id="7cffa-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="7cffa-217">MS_WINNOTE</span></span>|<span data-ttu-id="7cffa-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="7cffa-218">Tooltip</span></span>|  
|<span data-ttu-id="7cffa-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="7cffa-219">VBBubble</span></span>|<span data-ttu-id="7cffa-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="7cffa-220">Tooltip</span></span>|  
|<span data-ttu-id="7cffa-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="7cffa-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="7cffa-222">Slider</span><span class="sxs-lookup"><span data-stu-id="7cffa-222">Slider</span></span>|  
|<span data-ttu-id="7cffa-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="7cffa-223">SuperGrid</span></span>|<span data-ttu-id="7cffa-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="7cffa-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="7cffa-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="7cffa-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="7cffa-226">Windows Forms-Steuerelemente werden verfügbar gemacht, um [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über clientseitige Anbieter in "UIAutomationClientsideProviders.dll".</span><span class="sxs-lookup"><span data-stu-id="7cffa-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="7cffa-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="7cffa-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="7cffa-228">Windows Forms-Steuerelemente, die Sie in der Regel die verwaltete Wrapper für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] allgemeine Steuerelemente werden von unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cffa-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="7cffa-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7cffa-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="7cffa-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="7cffa-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="7cffa-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="7cffa-231">Button</span></span>|  
|<span data-ttu-id="7cffa-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-232">CheckBox</span></span>|  
|<span data-ttu-id="7cffa-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-233">CheckedListBox</span></span>|  
|<span data-ttu-id="7cffa-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="7cffa-234">ColorDialog</span></span>|  
|<span data-ttu-id="7cffa-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-235">ComboBox</span></span>|  
|<span data-ttu-id="7cffa-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="7cffa-236">FolderBrowser</span></span>|  
|<span data-ttu-id="7cffa-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="7cffa-237">FontDialog</span></span>|  
|<span data-ttu-id="7cffa-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-238">GroupBox</span></span>|  
|<span data-ttu-id="7cffa-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-239">HscrollBar</span></span>|  
|<span data-ttu-id="7cffa-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="7cffa-240">ImageList</span></span>|  
|<span data-ttu-id="7cffa-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="7cffa-241">Label</span></span>|  
|<span data-ttu-id="7cffa-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-242">ListBox</span></span>|  
|<span data-ttu-id="7cffa-243">ListView</span><span class="sxs-lookup"><span data-stu-id="7cffa-243">ListView</span></span>|  
|<span data-ttu-id="7cffa-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="7cffa-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="7cffa-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="7cffa-245">MonthCalendar</span></span>|  
|<span data-ttu-id="7cffa-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="7cffa-246">NotifyIcon</span></span>|  
|<span data-ttu-id="7cffa-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="7cffa-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="7cffa-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="7cffa-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="7cffa-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="7cffa-249">PrintDialog</span></span>|  
|<span data-ttu-id="7cffa-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-250">ProgressBar</span></span>|  
|<span data-ttu-id="7cffa-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7cffa-251">RadioButton</span></span>|  
|<span data-ttu-id="7cffa-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-252">RichTextBox</span></span>|  
|<span data-ttu-id="7cffa-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="7cffa-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="7cffa-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="7cffa-254">ScrollableControl</span></span>|  
|<span data-ttu-id="7cffa-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="7cffa-255">SoundPlayer</span></span>|  
|<span data-ttu-id="7cffa-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-256">StatusBar</span></span>|  
|<span data-ttu-id="7cffa-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="7cffa-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="7cffa-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-258">TextBox</span></span>|  
|<span data-ttu-id="7cffa-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="7cffa-259">Timer</span></span>|  
|<span data-ttu-id="7cffa-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-260">Toolbar</span></span>|  
|<span data-ttu-id="7cffa-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="7cffa-261">ToolTip</span></span>|  
|<span data-ttu-id="7cffa-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-262">TrackBar</span></span>|  
|<span data-ttu-id="7cffa-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="7cffa-263">TreeView</span></span>|  
|<span data-ttu-id="7cffa-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="7cffa-264">VscrollBar</span></span>|  
|<span data-ttu-id="7cffa-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="7cffa-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="7cffa-266">Die folgenden Steuerelemente sind für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] nur über ihre Unterstützung für [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7cffa-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="7cffa-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7cffa-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="7cffa-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="7cffa-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="7cffa-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="7cffa-269">BindingSource</span></span>|  
|<span data-ttu-id="7cffa-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="7cffa-270">DataGrid</span></span>|  
|<span data-ttu-id="7cffa-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="7cffa-271">DataGridView</span></span>|  
|<span data-ttu-id="7cffa-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="7cffa-272">DataNavigator</span></span>|  
|<span data-ttu-id="7cffa-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="7cffa-273">DomainUpDown</span></span>|  
|<span data-ttu-id="7cffa-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="7cffa-274">ErrorProvider</span></span>|  
|<span data-ttu-id="7cffa-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7cffa-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="7cffa-276">Formular</span><span class="sxs-lookup"><span data-stu-id="7cffa-276">Form</span></span>|  
|<span data-ttu-id="7cffa-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="7cffa-277">LinkLabel</span></span>|  
|<span data-ttu-id="7cffa-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="7cffa-278">HelpProvider</span></span>|  
|<span data-ttu-id="7cffa-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="7cffa-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="7cffa-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="7cffa-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="7cffa-281">NumericUpDown</span></span>|  
|<span data-ttu-id="7cffa-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="7cffa-282">Panel</span></span>|  
|<span data-ttu-id="7cffa-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="7cffa-283">PictureBox</span></span>|  
|<span data-ttu-id="7cffa-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="7cffa-284">PrintDocument</span></span>|  
|<span data-ttu-id="7cffa-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="7cffa-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="7cffa-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="7cffa-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="7cffa-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="7cffa-287">PropertyGrid</span></span>|  
|<span data-ttu-id="7cffa-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="7cffa-288">UserControl</span></span>|  
|<span data-ttu-id="7cffa-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7cffa-289">ToolStrip</span></span>|  
|<span data-ttu-id="7cffa-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7cffa-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="7cffa-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="7cffa-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="7cffa-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="7cffa-292">Splitter</span></span>|  
|<span data-ttu-id="7cffa-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="7cffa-293">RaftingContainer</span></span>|  
|<span data-ttu-id="7cffa-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="7cffa-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7cffa-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cffa-295">See Also</span></span>  
 [<span data-ttu-id="7cffa-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="7cffa-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
