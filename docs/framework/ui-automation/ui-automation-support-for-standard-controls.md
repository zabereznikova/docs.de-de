---
title: "Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 71a5a2e4319debf1a4d8ddd08d7f0979443682b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="6917a-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="6917a-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="6917a-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6917a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6917a-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6917a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6917a-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6917a-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="6917a-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="6917a-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="6917a-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6917a-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="6917a-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="6917a-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="6917a-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="6917a-109">Win32 Controls</span></span>  
 <span data-ttu-id="6917a-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="6917a-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="6917a-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="6917a-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="6917a-112">Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).</span><span class="sxs-lookup"><span data-stu-id="6917a-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="6917a-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6917a-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="6917a-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="6917a-114">Class name</span></span>|<span data-ttu-id="6917a-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="6917a-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="6917a-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-116">Button</span></span>|<span data-ttu-id="6917a-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-117">Button</span></span>|  
|<span data-ttu-id="6917a-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-118">Button</span></span>|<span data-ttu-id="6917a-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="6917a-119">RadioButton</span></span>|  
|<span data-ttu-id="6917a-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-120">Button</span></span>|<span data-ttu-id="6917a-121">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="6917a-121">Group</span></span>|  
|<span data-ttu-id="6917a-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-122">Button</span></span>|<span data-ttu-id="6917a-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6917a-123">CheckBox</span></span>|  
|<span data-ttu-id="6917a-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-124">Button</span></span>|<span data-ttu-id="6917a-125">Link</span><span class="sxs-lookup"><span data-stu-id="6917a-125">Hyperlink</span></span>|  
|<span data-ttu-id="6917a-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-126">Button</span></span>|<span data-ttu-id="6917a-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="6917a-127">SplitButton</span></span>|  
|<span data-ttu-id="6917a-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-128">Button</span></span>|<span data-ttu-id="6917a-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6917a-129">CheckBox</span></span>|  
|<span data-ttu-id="6917a-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="6917a-130">ComboBoxEx32</span></span>|<span data-ttu-id="6917a-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6917a-131">ComboBox</span></span>|  
|<span data-ttu-id="6917a-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6917a-132">ComboBox</span></span>|<span data-ttu-id="6917a-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6917a-133">ComboBox</span></span>|  
|<span data-ttu-id="6917a-134">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="6917a-134">Edit</span></span>|<span data-ttu-id="6917a-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="6917a-135">Document</span></span>|  
|<span data-ttu-id="6917a-136">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="6917a-136">Edit</span></span>|<span data-ttu-id="6917a-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="6917a-137">Edit</span></span>|  
|<span data-ttu-id="6917a-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="6917a-138">SysLink</span></span>|<span data-ttu-id="6917a-139">Link</span><span class="sxs-lookup"><span data-stu-id="6917a-139">Hyperlink</span></span>|  
|<span data-ttu-id="6917a-140">Statisch</span><span class="sxs-lookup"><span data-stu-id="6917a-140">Static</span></span>|<span data-ttu-id="6917a-141">Text</span><span class="sxs-lookup"><span data-stu-id="6917a-141">Text</span></span>|  
|<span data-ttu-id="6917a-142">Statisch</span><span class="sxs-lookup"><span data-stu-id="6917a-142">Static</span></span>|<span data-ttu-id="6917a-143">Bild</span><span class="sxs-lookup"><span data-stu-id="6917a-143">Image</span></span>|  
|<span data-ttu-id="6917a-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="6917a-144">SysIPAddress32</span></span>|<span data-ttu-id="6917a-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="6917a-145">Custom</span></span>|  
|<span data-ttu-id="6917a-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="6917a-146">SysHeader32</span></span>|<span data-ttu-id="6917a-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="6917a-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="6917a-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="6917a-148">SysListView32</span></span>|<span data-ttu-id="6917a-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="6917a-149">DataGrid</span></span>|  
|<span data-ttu-id="6917a-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="6917a-150">SysListView32</span></span>|<span data-ttu-id="6917a-151">Liste</span><span class="sxs-lookup"><span data-stu-id="6917a-151">List</span></span>|  
|<span data-ttu-id="6917a-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="6917a-152">ListBox</span></span>|<span data-ttu-id="6917a-153">Liste</span><span class="sxs-lookup"><span data-stu-id="6917a-153">List</span></span>|  
|<span data-ttu-id="6917a-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="6917a-154">ListBox</span></span>|<span data-ttu-id="6917a-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="6917a-155">ListItem</span></span>|  
|<span data-ttu-id="6917a-156">#32768</span><span class="sxs-lookup"><span data-stu-id="6917a-156">#32768</span></span>|<span data-ttu-id="6917a-157">Menü</span><span class="sxs-lookup"><span data-stu-id="6917a-157">Menu</span></span>|  
|<span data-ttu-id="6917a-158">#32768</span><span class="sxs-lookup"><span data-stu-id="6917a-158">#32768</span></span>|<span data-ttu-id="6917a-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="6917a-159">MenuItem</span></span>|  
|<span data-ttu-id="6917a-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="6917a-160">msctls_progress32</span></span>|<span data-ttu-id="6917a-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="6917a-161">ProgressBar</span></span>|  
|<span data-ttu-id="6917a-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="6917a-162">RichEdit</span></span>|<span data-ttu-id="6917a-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="6917a-163">Document.</span></span> <span data-ttu-id="6917a-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="6917a-164">See note.</span></span>|  
|<span data-ttu-id="6917a-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="6917a-165">RichEdit20A</span></span>|<span data-ttu-id="6917a-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="6917a-166">Document</span></span>|  
|<span data-ttu-id="6917a-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="6917a-167">RichEdit20W</span></span>|<span data-ttu-id="6917a-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="6917a-168">Document</span></span>|  
|<span data-ttu-id="6917a-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="6917a-169">RichEdit50W</span></span>|<span data-ttu-id="6917a-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="6917a-170">Document</span></span>|  
|<span data-ttu-id="6917a-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="6917a-171">ScrollBar</span></span>|<span data-ttu-id="6917a-172">Slider</span><span class="sxs-lookup"><span data-stu-id="6917a-172">Slider</span></span>|  
|<span data-ttu-id="6917a-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="6917a-173">msctls_trackbar32</span></span>|<span data-ttu-id="6917a-174">Slider</span><span class="sxs-lookup"><span data-stu-id="6917a-174">Slider</span></span>|  
|<span data-ttu-id="6917a-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="6917a-175">msctls_updown32</span></span>|<span data-ttu-id="6917a-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="6917a-176">Spinner</span></span>|  
|<span data-ttu-id="6917a-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="6917a-177">msctls_statusbar32</span></span>|<span data-ttu-id="6917a-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="6917a-178">StatusBar</span></span>|  
|<span data-ttu-id="6917a-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="6917a-179">SysTabControl32</span></span>|<span data-ttu-id="6917a-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="6917a-180">Tab</span></span>|  
|<span data-ttu-id="6917a-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="6917a-181">SysTabControl32</span></span>|<span data-ttu-id="6917a-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="6917a-182">TabItem</span></span>|  
|<span data-ttu-id="6917a-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6917a-183">ToolbarWindow32</span></span>|<span data-ttu-id="6917a-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="6917a-184">ToolBar</span></span>|  
|<span data-ttu-id="6917a-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6917a-185">ToolbarWindow32</span></span>|<span data-ttu-id="6917a-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="6917a-186">MenuItem</span></span>|  
|<span data-ttu-id="6917a-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6917a-187">ToolbarWindow32</span></span>|<span data-ttu-id="6917a-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-188">Button</span></span>|  
|<span data-ttu-id="6917a-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6917a-189">ToolbarWindow32</span></span>|<span data-ttu-id="6917a-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6917a-190">CheckBox</span></span>|  
|<span data-ttu-id="6917a-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6917a-191">ToolbarWindow32</span></span>|<span data-ttu-id="6917a-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="6917a-192">RadioButton</span></span>|  
|<span data-ttu-id="6917a-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6917a-193">ToolbarWindow32</span></span>|<span data-ttu-id="6917a-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="6917a-194">Separator</span></span>|  
|<span data-ttu-id="6917a-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="6917a-195">tooltips_class32</span></span>|<span data-ttu-id="6917a-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="6917a-196">ToolTip</span></span>|  
|<span data-ttu-id="6917a-197">#32774</span><span class="sxs-lookup"><span data-stu-id="6917a-197">#32774</span></span>|<span data-ttu-id="6917a-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="6917a-198">ToolTip</span></span>|  
|<span data-ttu-id="6917a-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="6917a-199">ReBarWindow32</span></span>|<span data-ttu-id="6917a-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="6917a-200">Toolbar</span></span>|  
|<span data-ttu-id="6917a-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="6917a-201">SysTreeView32</span></span>|<span data-ttu-id="6917a-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="6917a-202">Tree</span></span>|  
|<span data-ttu-id="6917a-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="6917a-203">SysTreeView32</span></span>|<span data-ttu-id="6917a-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="6917a-204">TreeItem</span></span>|  
  
 <span data-ttu-id="6917a-205">**Hinweis** Das RichEdit-Steuerelement wird nur für mit [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] ausgelieferte Versionen unterstützt (in „RichEd20.dll“ ab Version 3.1 und „MsftEdit.dll“ ab Version 4.1).</span><span class="sxs-lookup"><span data-stu-id="6917a-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="6917a-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6917a-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="6917a-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="6917a-207">Class name</span></span>|<span data-ttu-id="6917a-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="6917a-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="6917a-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="6917a-209">SysAnimate32</span></span>|<span data-ttu-id="6917a-210">Bild</span><span class="sxs-lookup"><span data-stu-id="6917a-210">Image</span></span>|  
|<span data-ttu-id="6917a-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="6917a-211">SysPager</span></span>|<span data-ttu-id="6917a-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="6917a-212">Spinner</span></span>|  
|<span data-ttu-id="6917a-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="6917a-213">SysDateTimePick32</span></span>|<span data-ttu-id="6917a-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="6917a-214">Custom</span></span>|  
|<span data-ttu-id="6917a-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="6917a-215">SysMonthCal32</span></span>|<span data-ttu-id="6917a-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="6917a-216">Calendar</span></span>|  
|<span data-ttu-id="6917a-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="6917a-217">MS_WINNOTE</span></span>|<span data-ttu-id="6917a-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="6917a-218">Tooltip</span></span>|  
|<span data-ttu-id="6917a-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="6917a-219">VBBubble</span></span>|<span data-ttu-id="6917a-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="6917a-220">Tooltip</span></span>|  
|<span data-ttu-id="6917a-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="6917a-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="6917a-222">Slider</span><span class="sxs-lookup"><span data-stu-id="6917a-222">Slider</span></span>|  
|<span data-ttu-id="6917a-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="6917a-223">SuperGrid</span></span>|<span data-ttu-id="6917a-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="6917a-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="6917a-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="6917a-225">Windows Forms Controls</span></span>  
 [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)]<span data-ttu-id="6917a-226"> -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="6917a-226"> controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="6917a-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="6917a-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="6917a-228">[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] -Steuerelemente, die verwaltete Wrapper für allgemeine [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente sind, werden von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]in der Regel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6917a-228">Typically, [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="6917a-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6917a-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="6917a-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="6917a-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="6917a-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="6917a-231">Button</span></span>|  
|<span data-ttu-id="6917a-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6917a-232">CheckBox</span></span>|  
|<span data-ttu-id="6917a-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="6917a-233">CheckedListBox</span></span>|  
|<span data-ttu-id="6917a-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="6917a-234">ColorDialog</span></span>|  
|<span data-ttu-id="6917a-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6917a-235">ComboBox</span></span>|  
|<span data-ttu-id="6917a-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="6917a-236">FolderBrowser</span></span>|  
|<span data-ttu-id="6917a-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="6917a-237">FontDialog</span></span>|  
|<span data-ttu-id="6917a-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="6917a-238">GroupBox</span></span>|  
|<span data-ttu-id="6917a-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="6917a-239">HscrollBar</span></span>|  
|<span data-ttu-id="6917a-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="6917a-240">ImageList</span></span>|  
|<span data-ttu-id="6917a-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="6917a-241">Label</span></span>|  
|<span data-ttu-id="6917a-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="6917a-242">ListBox</span></span>|  
|<span data-ttu-id="6917a-243">ListView</span><span class="sxs-lookup"><span data-stu-id="6917a-243">ListView</span></span>|  
|<span data-ttu-id="6917a-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="6917a-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="6917a-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="6917a-245">MonthCalendar</span></span>|  
|<span data-ttu-id="6917a-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="6917a-246">NotifyIcon</span></span>|  
|<span data-ttu-id="6917a-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="6917a-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="6917a-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="6917a-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="6917a-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="6917a-249">PrintDialog</span></span>|  
|<span data-ttu-id="6917a-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="6917a-250">ProgressBar</span></span>|  
|<span data-ttu-id="6917a-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="6917a-251">RadioButton</span></span>|  
|<span data-ttu-id="6917a-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="6917a-252">RichTextBox</span></span>|  
|<span data-ttu-id="6917a-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="6917a-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="6917a-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="6917a-254">ScrollableControl</span></span>|  
|<span data-ttu-id="6917a-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="6917a-255">SoundPlayer</span></span>|  
|<span data-ttu-id="6917a-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="6917a-256">StatusBar</span></span>|  
|<span data-ttu-id="6917a-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="6917a-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="6917a-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="6917a-258">TextBox</span></span>|  
|<span data-ttu-id="6917a-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="6917a-259">Timer</span></span>|  
|<span data-ttu-id="6917a-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="6917a-260">Toolbar</span></span>|  
|<span data-ttu-id="6917a-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="6917a-261">ToolTip</span></span>|  
|<span data-ttu-id="6917a-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="6917a-262">TrackBar</span></span>|  
|<span data-ttu-id="6917a-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="6917a-263">TreeView</span></span>|  
|<span data-ttu-id="6917a-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="6917a-264">VscrollBar</span></span>|  
|<span data-ttu-id="6917a-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="6917a-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="6917a-266">Die folgenden Steuerelemente sind für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] nur über ihre Unterstützung für [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6917a-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="6917a-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6917a-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="6917a-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="6917a-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="6917a-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="6917a-269">BindingSource</span></span>|  
|<span data-ttu-id="6917a-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="6917a-270">DataGrid</span></span>|  
|<span data-ttu-id="6917a-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="6917a-271">DataGridView</span></span>|  
|<span data-ttu-id="6917a-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="6917a-272">DataNavigator</span></span>|  
|<span data-ttu-id="6917a-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="6917a-273">DomainUpDown</span></span>|  
|<span data-ttu-id="6917a-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="6917a-274">ErrorProvider</span></span>|  
|<span data-ttu-id="6917a-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6917a-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="6917a-276">Formular</span><span class="sxs-lookup"><span data-stu-id="6917a-276">Form</span></span>|  
|<span data-ttu-id="6917a-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="6917a-277">LinkLabel</span></span>|  
|<span data-ttu-id="6917a-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="6917a-278">HelpProvider</span></span>|  
|<span data-ttu-id="6917a-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="6917a-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="6917a-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="6917a-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="6917a-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="6917a-281">NumericUpDown</span></span>|  
|<span data-ttu-id="6917a-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="6917a-282">Panel</span></span>|  
|<span data-ttu-id="6917a-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="6917a-283">PictureBox</span></span>|  
|<span data-ttu-id="6917a-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="6917a-284">PrintDocument</span></span>|  
|<span data-ttu-id="6917a-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="6917a-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="6917a-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="6917a-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="6917a-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="6917a-287">PropertyGrid</span></span>|  
|<span data-ttu-id="6917a-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="6917a-288">UserControl</span></span>|  
|<span data-ttu-id="6917a-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6917a-289">ToolStrip</span></span>|  
|<span data-ttu-id="6917a-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6917a-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="6917a-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="6917a-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="6917a-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="6917a-292">Splitter</span></span>|  
|<span data-ttu-id="6917a-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="6917a-293">RaftingContainer</span></span>|  
|<span data-ttu-id="6917a-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="6917a-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6917a-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6917a-295">See Also</span></span>  
 [<span data-ttu-id="6917a-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="6917a-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
