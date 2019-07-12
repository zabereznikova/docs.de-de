---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 641fc3f8dfca3ff6506354c076b98cc88073a1b7
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802116"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="9e9ae-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="9e9ae-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="9e9ae-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9e9ae-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="9e9ae-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="9e9ae-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e9ae-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="9e9ae-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="9e9ae-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="9e9ae-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e9ae-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="9e9ae-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="9e9ae-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="9e9ae-109">Win32 Controls</span></span>  
 <span data-ttu-id="9e9ae-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="9e9ae-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="9e9ae-112">Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).</span><span class="sxs-lookup"><span data-stu-id="9e9ae-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="9e9ae-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9e9ae-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="9e9ae-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="9e9ae-114">Class name</span></span>|<span data-ttu-id="9e9ae-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="9e9ae-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="9e9ae-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-116">Button</span></span>|<span data-ttu-id="9e9ae-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-117">Button</span></span>|  
|<span data-ttu-id="9e9ae-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-118">Button</span></span>|<span data-ttu-id="9e9ae-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="9e9ae-119">RadioButton</span></span>|  
|<span data-ttu-id="9e9ae-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-120">Button</span></span>|<span data-ttu-id="9e9ae-121">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="9e9ae-121">Group</span></span>|  
|<span data-ttu-id="9e9ae-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-122">Button</span></span>|<span data-ttu-id="9e9ae-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-123">CheckBox</span></span>|  
|<span data-ttu-id="9e9ae-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-124">Button</span></span>|<span data-ttu-id="9e9ae-125">Link</span><span class="sxs-lookup"><span data-stu-id="9e9ae-125">Hyperlink</span></span>|  
|<span data-ttu-id="9e9ae-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-126">Button</span></span>|<span data-ttu-id="9e9ae-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="9e9ae-127">SplitButton</span></span>|  
|<span data-ttu-id="9e9ae-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-128">Button</span></span>|<span data-ttu-id="9e9ae-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-129">CheckBox</span></span>|  
|<span data-ttu-id="9e9ae-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-130">ComboBoxEx32</span></span>|<span data-ttu-id="9e9ae-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-131">ComboBox</span></span>|  
|<span data-ttu-id="9e9ae-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-132">ComboBox</span></span>|<span data-ttu-id="9e9ae-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-133">ComboBox</span></span>|  
|<span data-ttu-id="9e9ae-134">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="9e9ae-134">Edit</span></span>|<span data-ttu-id="9e9ae-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="9e9ae-135">Document</span></span>|  
|<span data-ttu-id="9e9ae-136">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="9e9ae-136">Edit</span></span>|<span data-ttu-id="9e9ae-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="9e9ae-137">Edit</span></span>|  
|<span data-ttu-id="9e9ae-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="9e9ae-138">SysLink</span></span>|<span data-ttu-id="9e9ae-139">Link</span><span class="sxs-lookup"><span data-stu-id="9e9ae-139">Hyperlink</span></span>|  
|<span data-ttu-id="9e9ae-140">Statisch</span><span class="sxs-lookup"><span data-stu-id="9e9ae-140">Static</span></span>|<span data-ttu-id="9e9ae-141">Text</span><span class="sxs-lookup"><span data-stu-id="9e9ae-141">Text</span></span>|  
|<span data-ttu-id="9e9ae-142">Statisch</span><span class="sxs-lookup"><span data-stu-id="9e9ae-142">Static</span></span>|<span data-ttu-id="9e9ae-143">Bild</span><span class="sxs-lookup"><span data-stu-id="9e9ae-143">Image</span></span>|  
|<span data-ttu-id="9e9ae-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-144">SysIPAddress32</span></span>|<span data-ttu-id="9e9ae-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="9e9ae-145">Custom</span></span>|  
|<span data-ttu-id="9e9ae-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-146">SysHeader32</span></span>|<span data-ttu-id="9e9ae-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="9e9ae-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="9e9ae-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-148">SysListView32</span></span>|<span data-ttu-id="9e9ae-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="9e9ae-149">DataGrid</span></span>|  
|<span data-ttu-id="9e9ae-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-150">SysListView32</span></span>|<span data-ttu-id="9e9ae-151">Liste</span><span class="sxs-lookup"><span data-stu-id="9e9ae-151">List</span></span>|  
|<span data-ttu-id="9e9ae-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-152">ListBox</span></span>|<span data-ttu-id="9e9ae-153">Liste</span><span class="sxs-lookup"><span data-stu-id="9e9ae-153">List</span></span>|  
|<span data-ttu-id="9e9ae-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-154">ListBox</span></span>|<span data-ttu-id="9e9ae-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="9e9ae-155">ListItem</span></span>|  
|<span data-ttu-id="9e9ae-156">#32768</span><span class="sxs-lookup"><span data-stu-id="9e9ae-156">#32768</span></span>|<span data-ttu-id="9e9ae-157">Menü</span><span class="sxs-lookup"><span data-stu-id="9e9ae-157">Menu</span></span>|  
|<span data-ttu-id="9e9ae-158">#32768</span><span class="sxs-lookup"><span data-stu-id="9e9ae-158">#32768</span></span>|<span data-ttu-id="9e9ae-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="9e9ae-159">MenuItem</span></span>|  
|<span data-ttu-id="9e9ae-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-160">msctls_progress32</span></span>|<span data-ttu-id="9e9ae-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-161">ProgressBar</span></span>|  
|<span data-ttu-id="9e9ae-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="9e9ae-162">RichEdit</span></span>|<span data-ttu-id="9e9ae-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-163">Document.</span></span> <span data-ttu-id="9e9ae-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-164">See note.</span></span>|  
|<span data-ttu-id="9e9ae-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="9e9ae-165">RichEdit20A</span></span>|<span data-ttu-id="9e9ae-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="9e9ae-166">Document</span></span>|  
|<span data-ttu-id="9e9ae-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="9e9ae-167">RichEdit20W</span></span>|<span data-ttu-id="9e9ae-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="9e9ae-168">Document</span></span>|  
|<span data-ttu-id="9e9ae-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="9e9ae-169">RichEdit50W</span></span>|<span data-ttu-id="9e9ae-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="9e9ae-170">Document</span></span>|  
|<span data-ttu-id="9e9ae-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-171">ScrollBar</span></span>|<span data-ttu-id="9e9ae-172">Slider</span><span class="sxs-lookup"><span data-stu-id="9e9ae-172">Slider</span></span>|  
|<span data-ttu-id="9e9ae-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-173">msctls_trackbar32</span></span>|<span data-ttu-id="9e9ae-174">Slider</span><span class="sxs-lookup"><span data-stu-id="9e9ae-174">Slider</span></span>|  
|<span data-ttu-id="9e9ae-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-175">msctls_updown32</span></span>|<span data-ttu-id="9e9ae-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="9e9ae-176">Spinner</span></span>|  
|<span data-ttu-id="9e9ae-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-177">msctls_statusbar32</span></span>|<span data-ttu-id="9e9ae-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-178">StatusBar</span></span>|  
|<span data-ttu-id="9e9ae-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-179">SysTabControl32</span></span>|<span data-ttu-id="9e9ae-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="9e9ae-180">Tab</span></span>|  
|<span data-ttu-id="9e9ae-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-181">SysTabControl32</span></span>|<span data-ttu-id="9e9ae-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="9e9ae-182">TabItem</span></span>|  
|<span data-ttu-id="9e9ae-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-183">ToolbarWindow32</span></span>|<span data-ttu-id="9e9ae-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-184">ToolBar</span></span>|  
|<span data-ttu-id="9e9ae-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-185">ToolbarWindow32</span></span>|<span data-ttu-id="9e9ae-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="9e9ae-186">MenuItem</span></span>|  
|<span data-ttu-id="9e9ae-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-187">ToolbarWindow32</span></span>|<span data-ttu-id="9e9ae-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-188">Button</span></span>|  
|<span data-ttu-id="9e9ae-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-189">ToolbarWindow32</span></span>|<span data-ttu-id="9e9ae-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-190">CheckBox</span></span>|  
|<span data-ttu-id="9e9ae-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-191">ToolbarWindow32</span></span>|<span data-ttu-id="9e9ae-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="9e9ae-192">RadioButton</span></span>|  
|<span data-ttu-id="9e9ae-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-193">ToolbarWindow32</span></span>|<span data-ttu-id="9e9ae-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="9e9ae-194">Separator</span></span>|  
|<span data-ttu-id="9e9ae-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-195">tooltips_class32</span></span>|<span data-ttu-id="9e9ae-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9e9ae-196">ToolTip</span></span>|  
|<span data-ttu-id="9e9ae-197">#32774</span><span class="sxs-lookup"><span data-stu-id="9e9ae-197">#32774</span></span>|<span data-ttu-id="9e9ae-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9e9ae-198">ToolTip</span></span>|  
|<span data-ttu-id="9e9ae-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-199">ReBarWindow32</span></span>|<span data-ttu-id="9e9ae-200">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="9e9ae-200">Toolbar</span></span>|  
|<span data-ttu-id="9e9ae-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-201">SysTreeView32</span></span>|<span data-ttu-id="9e9ae-202">trEE</span><span class="sxs-lookup"><span data-stu-id="9e9ae-202">Tree</span></span>|  
|<span data-ttu-id="9e9ae-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-203">SysTreeView32</span></span>|<span data-ttu-id="9e9ae-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="9e9ae-204">TreeItem</span></span>|  
  
 <span data-ttu-id="9e9ae-205">**Hinweis** Das RichEdit-Steuerelement wird nur für mit [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] ausgelieferte Versionen unterstützt (in „RichEd20.dll“ ab Version 3.1 und „MsftEdit.dll“ ab Version 4.1).</span><span class="sxs-lookup"><span data-stu-id="9e9ae-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="9e9ae-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9e9ae-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="9e9ae-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="9e9ae-207">Class name</span></span>|<span data-ttu-id="9e9ae-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="9e9ae-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="9e9ae-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-209">SysAnimate32</span></span>|<span data-ttu-id="9e9ae-210">Bild</span><span class="sxs-lookup"><span data-stu-id="9e9ae-210">Image</span></span>|  
|<span data-ttu-id="9e9ae-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="9e9ae-211">SysPager</span></span>|<span data-ttu-id="9e9ae-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="9e9ae-212">Spinner</span></span>|  
|<span data-ttu-id="9e9ae-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-213">SysDateTimePick32</span></span>|<span data-ttu-id="9e9ae-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="9e9ae-214">Custom</span></span>|  
|<span data-ttu-id="9e9ae-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="9e9ae-215">SysMonthCal32</span></span>|<span data-ttu-id="9e9ae-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="9e9ae-216">Calendar</span></span>|  
|<span data-ttu-id="9e9ae-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="9e9ae-217">MS_WINNOTE</span></span>|<span data-ttu-id="9e9ae-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9e9ae-218">Tooltip</span></span>|  
|<span data-ttu-id="9e9ae-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="9e9ae-219">VBBubble</span></span>|<span data-ttu-id="9e9ae-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9e9ae-220">Tooltip</span></span>|  
|<span data-ttu-id="9e9ae-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="9e9ae-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="9e9ae-222">Slider</span><span class="sxs-lookup"><span data-stu-id="9e9ae-222">Slider</span></span>|  
|<span data-ttu-id="9e9ae-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="9e9ae-223">SuperGrid</span></span>|<span data-ttu-id="9e9ae-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="9e9ae-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="9e9ae-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="9e9ae-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="9e9ae-226">Windows Forms-Steuerelemente werden verfügbar gemacht, um [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über clientseitige Anbieter in "UIAutomationClientsideProviders.dll".</span><span class="sxs-lookup"><span data-stu-id="9e9ae-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="9e9ae-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="9e9ae-228">Windows Forms-Steuerelemente, die Sie in der Regel die verwaltete Wrapper für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] allgemeine Steuerelemente werden von unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e9ae-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="9e9ae-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9e9ae-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="9e9ae-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="9e9ae-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="9e9ae-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9e9ae-231">Button</span></span>|  
|<span data-ttu-id="9e9ae-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-232">CheckBox</span></span>|  
|<span data-ttu-id="9e9ae-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-233">CheckedListBox</span></span>|  
|<span data-ttu-id="9e9ae-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="9e9ae-234">ColorDialog</span></span>|  
|<span data-ttu-id="9e9ae-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-235">ComboBox</span></span>|  
|<span data-ttu-id="9e9ae-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="9e9ae-236">FolderBrowser</span></span>|  
|<span data-ttu-id="9e9ae-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="9e9ae-237">FontDialog</span></span>|  
|<span data-ttu-id="9e9ae-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-238">GroupBox</span></span>|  
|<span data-ttu-id="9e9ae-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-239">HscrollBar</span></span>|  
|<span data-ttu-id="9e9ae-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="9e9ae-240">ImageList</span></span>|  
|<span data-ttu-id="9e9ae-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="9e9ae-241">Label</span></span>|  
|<span data-ttu-id="9e9ae-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-242">ListBox</span></span>|  
|<span data-ttu-id="9e9ae-243">ListView</span><span class="sxs-lookup"><span data-stu-id="9e9ae-243">ListView</span></span>|  
|<span data-ttu-id="9e9ae-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="9e9ae-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="9e9ae-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-245">MonthCalendar</span></span>|  
|<span data-ttu-id="9e9ae-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="9e9ae-246">NotifyIcon</span></span>|  
|<span data-ttu-id="9e9ae-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="9e9ae-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="9e9ae-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="9e9ae-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="9e9ae-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="9e9ae-249">PrintDialog</span></span>|  
|<span data-ttu-id="9e9ae-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-250">ProgressBar</span></span>|  
|<span data-ttu-id="9e9ae-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="9e9ae-251">RadioButton</span></span>|  
|<span data-ttu-id="9e9ae-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-252">RichTextBox</span></span>|  
|<span data-ttu-id="9e9ae-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="9e9ae-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="9e9ae-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="9e9ae-254">ScrollableControl</span></span>|  
|<span data-ttu-id="9e9ae-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="9e9ae-255">SoundPlayer</span></span>|  
|<span data-ttu-id="9e9ae-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-256">StatusBar</span></span>|  
|<span data-ttu-id="9e9ae-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="9e9ae-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="9e9ae-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-258">TextBox</span></span>|  
|<span data-ttu-id="9e9ae-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="9e9ae-259">Timer</span></span>|  
|<span data-ttu-id="9e9ae-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-260">Toolbar</span></span>|  
|<span data-ttu-id="9e9ae-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9e9ae-261">ToolTip</span></span>|  
|<span data-ttu-id="9e9ae-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-262">TrackBar</span></span>|  
|<span data-ttu-id="9e9ae-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="9e9ae-263">TreeView</span></span>|  
|<span data-ttu-id="9e9ae-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="9e9ae-264">VscrollBar</span></span>|  
|<span data-ttu-id="9e9ae-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="9e9ae-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="9e9ae-266">Die folgenden Steuerelemente sind verfügbar, um [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] nur über ihre Unterstützung für Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="9e9ae-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e9ae-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="9e9ae-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="9e9ae-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="9e9ae-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="9e9ae-269">BindingSource</span></span>|  
|<span data-ttu-id="9e9ae-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="9e9ae-270">DataGrid</span></span>|  
|<span data-ttu-id="9e9ae-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="9e9ae-271">DataGridView</span></span>|  
|<span data-ttu-id="9e9ae-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="9e9ae-272">DataNavigator</span></span>|  
|<span data-ttu-id="9e9ae-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="9e9ae-273">DomainUpDown</span></span>|  
|<span data-ttu-id="9e9ae-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="9e9ae-274">ErrorProvider</span></span>|  
|<span data-ttu-id="9e9ae-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e9ae-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="9e9ae-276">Formular</span><span class="sxs-lookup"><span data-stu-id="9e9ae-276">Form</span></span>|  
|<span data-ttu-id="9e9ae-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="9e9ae-277">LinkLabel</span></span>|  
|<span data-ttu-id="9e9ae-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="9e9ae-278">HelpProvider</span></span>|  
|<span data-ttu-id="9e9ae-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="9e9ae-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="9e9ae-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="9e9ae-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="9e9ae-281">NumericUpDown</span></span>|  
|<span data-ttu-id="9e9ae-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="9e9ae-282">Panel</span></span>|  
|<span data-ttu-id="9e9ae-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="9e9ae-283">PictureBox</span></span>|  
|<span data-ttu-id="9e9ae-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="9e9ae-284">PrintDocument</span></span>|  
|<span data-ttu-id="9e9ae-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="9e9ae-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="9e9ae-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="9e9ae-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="9e9ae-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="9e9ae-287">PropertyGrid</span></span>|  
|<span data-ttu-id="9e9ae-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="9e9ae-288">UserControl</span></span>|  
|<span data-ttu-id="9e9ae-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9e9ae-289">ToolStrip</span></span>|  
|<span data-ttu-id="9e9ae-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e9ae-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="9e9ae-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="9e9ae-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="9e9ae-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="9e9ae-292">Splitter</span></span>|  
|<span data-ttu-id="9e9ae-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="9e9ae-293">RaftingContainer</span></span>|  
|<span data-ttu-id="9e9ae-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="9e9ae-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e9ae-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e9ae-295">See also</span></span>

- [<span data-ttu-id="9e9ae-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="9e9ae-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
