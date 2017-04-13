---
title: "Implementing the UI Automation Toggle Control Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Toggle control pattern"
  - "control patterns, Toggle"
  - "UI Automation, Toggle control pattern"
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Implementing the UI Automation Toggle Control Pattern
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie auf der Seite zur [Windows\-Automatisierungs\-API: UI\-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen zum Implementieren von <xref:System.Windows.Automation.Provider.IToggleProvider>, einschließlich Informationen über Methoden und Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.TogglePattern>\-Steuerelementmuster dient zur Unterstützung von Steuerelementen, die eine Reihe von Zuständen durchlaufen und einen Zustand beibehalten, nachdem dieser festgelegt wurde. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Implementierungsrichtlinien und \-konventionen  
 Beachten Sie beim Implementieren des Toggle\-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   Steuerelemente, die ihren Zustand nach der Aktivierung nicht beibehalten, z. B. Schaltflächen, Symbolleistenschaltflächen und Links, müssen stattdessen <xref:System.Windows.Automation.Provider.IInvokeProvider> implementieren.  
  
-   Ein Steuerelement muss seinen <xref:System.Windows.Automation.ToggleState> in der folgenden Reihenfolge durchlaufen: <xref:System.Windows.Automation.ToggleState>, <xref:System.Windows.Automation.ToggleState> und <xref:System.Windows.Automation.ToggleState> \(sofern unterstützt\).  
  
-   <xref:System.Windows.Automation.TogglePattern> bietet aufgrund der Probleme im Rahmen der direkten Einstellung eines CheckBox\-Steuerelements mit drei Zuständen ohne Durchlaufen seiner entsprechenden <xref:System.Windows.Automation.ToggleState>\-Sequenz keine „SetState\(newState\)“\-Methode.  
  
-   Das RadioButton\-Steuerelement implementiert <xref:System.Windows.Automation.Provider.IToggleProvider> nicht, da es seine gültigen Zustände nicht durchlaufen kann.  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## Erforderliche Member für IToggleProvider  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IToggleProvider> erforderlich.  
  
|Erforderliche Member|Memberart|Notizen|  
|--------------------------|---------------|-------------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|Eigenschaft|Keine|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## Ausnahmen  
 Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.  
  
## Siehe auch  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Get the Toggle State of a Check Box Using UI Automation](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)