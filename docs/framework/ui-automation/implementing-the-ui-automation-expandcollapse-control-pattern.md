---
title: "Implementing the UI Automation ExpandCollapse Control Pattern | Microsoft Docs"
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
  - "UI Automation, ExpandCollapse control pattern"
  - "ExpandCollapse control pattern"
  - "control patterns, ExpandCollapse"
ms.assetid: 1dbabb8c-0d68-47c1-a35e-1c01cb01af26
caps.latest.revision: 25
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 25
---
# Implementing the UI Automation ExpandCollapse Control Pattern
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie auf der Seite zur [Windows\-Automatisierungs\-API: UI\-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Das <xref:System.Windows.Automation.ExpandCollapsePattern>\-Steuerelementmuster dient zur Unterstützung von Steuerelementen, die für das Anzeigen von mehr Inhalt erweitert bzw. für das Ausblenden von Inhalt reduziert werden. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Implementierungsrichtlinien und \-konventionen  
 Beachten Sie beim Implementieren des „ExpandCollapse“\-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   Aggregierte Steuerelemente \(mit untergeordneten Objekten erstellt, die die Benutzeroberfläche mit Funktionen zum Erweitern\/Reduzieren bereitstellen\) müssen das <xref:System.Windows.Automation.ExpandCollapsePattern>\-Steuerelementmuster unterstützen, während deren untergeordnete Elemente dies nicht müssen. Beispielsweise wird ein Kombinationsfeld\-Steuerelement mit einer Kombination aus einem Listenfeld, einer Schaltfläche und Bearbeitungssteuerelementen erstellt, aber es handelt es sich nur um das übergeordnete Kombinationsfeld, das <xref:System.Windows.Automation.ExpandCollapsePattern> unterstützen muss.  
  
    > [!NOTE]
    >  Eine Ausnahme stellt das Menüsteuerelement dar. Hierbei handelt es sich um ein Aggregat von einzelnen „MenuItem“\-Objekten. Die „MenuItem“\-Objekte können das <xref:System.Windows.Automation.ExpandCollapsePattern>\-Steuerelementmuster unterstützen, das übergeordnete Menüsteuerelement ist dazu jedoch nicht in der Lage. Eine ähnliche Ausnahme gilt für die Gesamtstruktur\- und Gesamtstrukturelement\-Steuerelemente.  
  
-   Wenn der <xref:System.Windows.Automation.ExpandCollapseState> eines Steuerelements auf <xref:System.Windows.Automation.ExpandCollapseState> festgelegt ist, sind die <xref:System.Windows.Automation.ExpandCollapsePattern>\-Funktionalitäten aktuell inaktiv für das Steuerelement, und <xref:System.Windows.Automation.ExpandCollapseState> sind die einzigen Informationen, die mithilfe dieses Steuerelementmusters abgerufen werden können. Wenn untergeordnete Objekte später hinzugefügt werden, wird <xref:System.Windows.Automation.ExpandCollapseState> geändert, und die <xref:System.Windows.Automation.ExpandCollapsePattern>\-Funktionalität wird aktiviert.  
  
-   <xref:System.Windows.Automation.ExpandCollapseState> verweist nur auf die Sichtbarkeit der unmittelbaren untergeordneten Objekte und nicht auf die Sichtbarkeit sämtlicher Nachfolgerobjekte.  
  
-   Die Funktionalität zum Erweitern und Reduzieren ist steuerelementspezifisch. Im Folgenden finden Sie Beispiele dieses Verhaltens.  
  
    -   Das persönliche Office\-Menü kann ein aus drei Status bestehendes „MenuItem“ \(<xref:System.Windows.Automation.ExpandCollapseState>, <xref:System.Windows.Automation.ExpandCollapseState> und <xref:System.Windows.Automation.ExpandCollapseState>\) sein, wobei das Steuerelement den zu verwendenden Status angibt, wenn eine <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A>\- oder <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>\-Funktion aufgerufen wird.  
  
    -   Durch das Aufrufen von <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> in einem „TreeItem“ werden möglicherweise alle Nachfolger oder nur das unmittelbar untergeordnete Element angezeigt.  
  
    -   Durch das Aufrufen von <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> oder <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> in einem Steuerelement wird der Status der entsprechenden Nachfolger beibehalten, es sollte ein Sichtbarkeitsänderungsereignis gesendet werden und kein Statusänderungsereignis. Wenn das übergeordnete Steuerelement den Status seiner Nachfolger nicht beibehalten kann, wenn es reduziert ist, zerstört das Steuerelement möglicherweise alle Nachfolger, die nicht mehr sichtbar sind und löst ein Ereignis über eine Zerstörung aus oder es ändert <xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A> für jeden Nachfolger und löst ein Sichtbarkeitsänderungsereignis aus.  
  
-   Zum Garantieren der Navigation ist es für ein Objekt wünschenswert, wenn es sich in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Gesamtstruktur \(mit dem entsprechenden Sichtbarkeitsstatus\) befindet, und zwar unabhängig von seinen übergeordneten <xref:System.Windows.Automation.ExpandCollapseState>. Wenn Nachfolger bedarfsgesteuert generiert werden, werden sie möglicherweise nur dann in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Gesamtstruktur angezeigt, nachdem sie das erste Mal angezeigt wurden, oder nur während sie sichtbar sind.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## Erforderliche Member für „IExpandCollapseProvider“  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IExpandCollapseProvider> erforderlich.  
  
|Erforderliche Member|Memberart|Notizen|  
|--------------------------|---------------|-------------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|Ereignis|Dieses Steuerelement verfügt über keine zugeordneten Ereignisse. Verwenden Sie diesen generischen Delegaten.|  
  
<a name="Exceptions"></a>   
## Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|-----------------|---------------|  
|<xref:System.InvalidOperationException>|Es wird <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> oder <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> aufgerufen, wenn <xref:System.Windows.Automation.ExpandCollapseState> \= <xref:System.Windows.Automation.ExpandCollapseState>.|  
  
## Siehe auch  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Navigate Among UI Automation Elements with TreeWalker](../../../docs/framework/ui-automation/navigate-among-ui-automation-elements-with-treewalker.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)