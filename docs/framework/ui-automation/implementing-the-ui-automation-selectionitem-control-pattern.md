---
title: "Implementing the UI Automation SelectionItem Control Pattern | Microsoft Docs"
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
  - "Selection Item control pattern"
  - "UI Automation, Selection Item control pattern"
  - "control patterns, Selection Item"
ms.assetid: 76b0949a-5b23-4cfc-84cc-154f713e2e12
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# Implementing the UI Automation SelectionItem Control Pattern
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie auf der Seite zur [Windows\-Automatisierungs\-API: UI\-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Das <xref:System.Windows.Automation.SelectionItemPattern>\-Steuerelementmuster dient zur Unterstützung von Steuerelementen, die als einzelne auswählbare untergeordnete Elemente von Containersteuerelementen fungieren, die <xref:System.Windows.Automation.Provider.ISelectionProvider> implementieren. Beispiele für Steuerelemente, die das SelectionItem\-Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Implementierungsrichtlinien und \-konventionen  
 Beachten Sie beim Implementieren des SelectionItem\-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   Steuerelemente mit Einfachauswahl, die untergeordnete Steuerelemente verwalten, die <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot> implementieren, z. B. der **Bildschirmauflösung**\-Schieberegler im Dialogfeld **Anzeigeeigenschaften**, sollten <xref:System.Windows.Automation.Provider.ISelectionProvider> implementieren. Deren untergeordnete Elemente sollten sowohl <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> als auch <xref:System.Windows.Automation.Provider.ISelectionItemProvider> implementieren.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## Erforderliche Member für ISelectionItemProvider  
 Die folgenden Eigenschaften, Methoden und Ereignisse sind für die <xref:System.Windows.Automation.Provider.ISelectionItemProvider>\-Implementierung erforderlich.  
  
|Erforderliche Member|Memberart|Notizen|  
|--------------------------|---------------|-------------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Ereignis|Dieses wird ausgelöst, wenn die Auswahl in einem Container maßgeblich geändert wurde und dies das Senden weiterer <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>\- und <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>\-Ereignisse erfordert, als die <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit>\-Konstante gestattet.|  
  
-   Wenn das Ergebnis von <xref:System.Windows.Automation.SelectionItemPattern.Select%2A>, <xref:System.Windows.Automation.SelectionItemPattern.AddToSelection%2A> oder <xref:System.Windows.Automation.SelectionItemPattern.RemoveFromSelection%2A> ein einzelnes ausgewähltes Element ist, muss ein <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> ausgelöst werden. Andernfalls senden Sie entsprechend <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>\/<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>.  
  
<a name="Exceptions"></a>   
## Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|-----------------|---------------|  
|<xref:System.InvalidOperationException>|Wenn einer der folgenden Schritte versucht wird:<br /><br /> -   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> wird für einen Einfachauswahlcontainer aufgerufen, für den <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> \= `true` gilt und bereits ein Element ausgewählt ist.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> wird für einen Mehrfachauswahlcontainer aufgerufen, für den <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> \= `true` gilt und nur ein Element ausgewählt ist.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.AddToSelection%2A> wird für einen Einfachauswahlcontainer aufgerufen, für den <xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty> \= `false` gilt und bereits ein weiteres Element ausgewählt ist.|  
  
## Siehe auch  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Implementing the UI Automation Selection Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-selection-control-pattern.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)   
 [Fragment Provider Sample](http://msdn.microsoft.com/de-de/778ef1bc-8610-4bc9-886e-aeff94a8a13e)