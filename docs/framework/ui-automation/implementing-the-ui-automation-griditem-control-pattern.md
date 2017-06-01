---
title: "Implementieren des GridItem-Steuerelementmusters der Benutzeroberfl&#228;chenautomatisierung | Microsoft Docs"
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
  - "Steuerelementmuster GridItem"
  - "Benutzeroberflächenautomatisierungs-GridItem-Steuerelementmuster"
  - "GridItem-Steuerelementmuster"
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# Implementieren des GridItem-Steuerelementmusters der Benutzeroberfl&#228;chenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler, die die verwaltete verwenden möchten vorgesehen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Klassen, die in der <xref:System.Windows.Automation> Namespace. Die neuesten Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows Automation API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen zum Implementieren von <xref:System.Windows.Automation.Provider.IGridItemProvider>, sowie Informationen über Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Die <xref:System.Windows.Automation.GridItemPattern> -Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, implementieren <xref:System.Windows.Automation.Provider.IGridProvider>. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Bei der Implementierung <xref:System.Windows.Automation.Provider.IGridProvider>, beachten Sie die folgenden Richtlinien und Konventionen:  
  
-   Rasterkoordinaten (Grid-Koordinaten) sind nullbasiert, wobei die obere linke Zelle die Koordinaten (0, 0) hat.  
  
-   Zusammengeführte Zellen ihre <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> und <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> Eigenschaften basierend auf der zugrunde liegenden Ankerzelle von Benutzeroberflächenautomatisierungs-Anbieter definiert. In der Regel sind dies die oberste Zeile und die am weitesten links liegende Spalte.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider> bietet keine aktive Manipulation des Rasters z. B. zusammenführen oder Teilen von Zellen.  
  
-   Steuert, implementieren <xref:System.Windows.Automation.Provider.IGridItemProvider> in der Regel durchlaufen werden kann (d. h. Benutzeroberflächenautomatisierungs-Client kann zu benachbarten Steuerelementen wechseln) mithilfe der Tastatur.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>Erforderliche Member für IGridItemProvider  
 Die folgenden Eigenschaften und Methoden für die Implementierung erforderlich sind <xref:System.Windows.Automation.Provider.IGridItemProvider>.  
  
|Erforderliche Member|Memberart|Notizen|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|Eigenschaft|Keine|  
  
 Diesem Steuerelementmuster sind keine Methoden oder Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Implementieren die Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)   
 [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Zwischenspeichern Sie in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)