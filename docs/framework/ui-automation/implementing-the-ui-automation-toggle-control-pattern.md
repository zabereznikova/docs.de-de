---
title: Implementieren des Toggle-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: 75659182fae64c548fe67090b13d43a212e6abae
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679033"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="610b6-102">Implementieren des Toggle-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="610b6-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="610b6-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="610b6-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="610b6-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="610b6-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="610b6-105">Dieses Thema enthält Richtlinien und Konventionen zum Implementieren von <xref:System.Windows.Automation.Provider.IToggleProvider>, einschließlich Informationen über Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="610b6-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="610b6-106">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="610b6-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="610b6-107">Das <xref:System.Windows.Automation.TogglePattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die eine Reihe von Zuständen durchlaufen und einen Zustand beibehalten, nachdem dieser festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="610b6-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="610b6-108">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="610b6-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="610b6-109">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="610b6-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="610b6-110">Beachten Sie beim Implementieren des Toggle-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="610b6-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="610b6-111">Steuerelemente, die ihren Zustand nach der Aktivierung nicht beibehalten, z. B. Schaltflächen, Symbolleistenschaltflächen und Links, müssen stattdessen <xref:System.Windows.Automation.Provider.IInvokeProvider> implementieren.</span><span class="sxs-lookup"><span data-stu-id="610b6-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
-   <span data-ttu-id="610b6-112">Ein Steuerelement muss seinen <xref:System.Windows.Automation.ToggleState> in der folgenden Reihenfolge durchlaufen: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> und <xref:System.Windows.Automation.ToggleState.Indeterminate>(sofern unterstützt).</span><span class="sxs-lookup"><span data-stu-id="610b6-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
-   <span data-ttu-id="610b6-113"><xref:System.Windows.Automation.TogglePattern> bietet aufgrund der Probleme im Rahmen der direkten Einstellung eines CheckBox-Steuerelements mit drei Zuständen ohne Durchlaufen seiner entsprechenden <xref:System.Windows.Automation.ToggleState> -Sequenz keine „SetState(newState)“-Methode.</span><span class="sxs-lookup"><span data-stu-id="610b6-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
-   <span data-ttu-id="610b6-114">Das RadioButton-Steuerelement implementiert <xref:System.Windows.Automation.Provider.IToggleProvider>nicht, da es seine gültigen Zustände nicht durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="610b6-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="610b6-115">Erforderliche Member für IToggleProvider</span><span class="sxs-lookup"><span data-stu-id="610b6-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="610b6-116">Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IToggleProvider>erforderlich.</span><span class="sxs-lookup"><span data-stu-id="610b6-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="610b6-117">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="610b6-117">Required member</span></span>|<span data-ttu-id="610b6-118">Memberart</span><span class="sxs-lookup"><span data-stu-id="610b6-118">Member type</span></span>|<span data-ttu-id="610b6-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="610b6-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="610b6-120">Methode</span><span class="sxs-lookup"><span data-stu-id="610b6-120">Method</span></span>|<span data-ttu-id="610b6-121">Keine</span><span class="sxs-lookup"><span data-stu-id="610b6-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="610b6-122">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="610b6-122">Property</span></span>|<span data-ttu-id="610b6-123">Keine</span><span class="sxs-lookup"><span data-stu-id="610b6-123">None</span></span>|  
  
 <span data-ttu-id="610b6-124">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="610b6-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="610b6-125">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="610b6-125">Exceptions</span></span>  
 <span data-ttu-id="610b6-126">Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="610b6-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610b6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="610b6-127">See also</span></span>
- [<span data-ttu-id="610b6-128">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="610b6-128">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="610b6-129">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="610b6-129">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="610b6-130">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="610b6-130">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="610b6-131">Abrufen des Umschaltstatus eines Kontrollkästchens mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="610b6-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="610b6-132">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="610b6-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="610b6-133">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="610b6-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
