---
title: "Implementieren des SelectionItem-Steuerelementmusters der Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Selection Item control pattern
- UI Automation, Selection Item control pattern
- control patterns, Selection Item
ms.assetid: 76b0949a-5b23-4cfc-84cc-154f713e2e12
caps.latest.revision: "22"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4ec9ee61973adacfc44c5fa7d8f1e6812e9950fd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="implementing-the-ui-automation-selectionitem-control-pattern"></a>Implementieren des SelectionItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Das <xref:System.Windows.Automation.SelectionItemPattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die als einzelne auswählbare untergeordnete Elemente von Containersteuerelementen fungieren, die <xref:System.Windows.Automation.Provider.ISelectionProvider>implementieren. Beispiele für Steuerelemente, die das SelectionItem-Steuerelementmuster implementieren, finden Sie unter [Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des SelectionItem-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   Steuerelemente mit Einfachauswahl, die untergeordnete Steuerelemente verwalten, die <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>implementieren, z. B. der **Bildschirmauflösung** -Schieberegler im Dialogfeld **Anzeigeeigenschaften** , sollten <xref:System.Windows.Automation.Provider.ISelectionProvider> implementieren. Deren untergeordnete Elemente sollten sowohl <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> als auch <xref:System.Windows.Automation.Provider.ISelectionItemProvider>implementieren.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-iselectionitemprovider"></a>Erforderliche Member für ISelectionItemProvider  
 Die folgenden Eigenschaften, Methoden und Ereignisse sind für die <xref:System.Windows.Automation.Provider.ISelectionItemProvider>-Implementierung erforderlich.  
  
|Erforderliche Member|Memberart|Hinweise|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Methode|Keiner|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|event|Dieses wird ausgelöst, wenn die Auswahl in einem Container maßgeblich geändert wurde und dies das Senden weiterer <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> - und <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> -Ereignisse erfordert, als die <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> -Konstante gestattet.|  
  
-   Wenn das Ergebnis von <xref:System.Windows.Automation.SelectionItemPattern.Select%2A>, <xref:System.Windows.Automation.SelectionItemPattern.AddToSelection%2A>oder <xref:System.Windows.Automation.SelectionItemPattern.RemoveFromSelection%2A> ein einzelnes ausgewähltes Element ist, muss ein <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> ausgelöst werden. Andernfalls senden Sie entsprechend <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>/ <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> .  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Wenn einer der folgenden Schritte versucht wird:<br /><br /> -   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A>für einen einfachauswahlcontainer aufgerufen wird, in denen <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty>  =  `true` und bereits ein Element ausgewählt ist.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> wird für einen Mehrfachauswahlcontainer aufgerufen, für den <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> = `true` gilt und nur ein Element ausgewählt ist.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.AddToSelection%2A> wird für einen Einfachauswahlcontainer aufgerufen, für den <xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty> = `false` gilt und bereits ein weiteres Element ausgewählt ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Implementieren des Selection-Steuerelementmusters der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/implementing-the-ui-automation-selection-control-pattern.md)  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [Beispiel für einen Fragmentanbieter](http://msdn.microsoft.com/library/778ef1bc-8610-4bc9-886e-aeff94a8a13e)
