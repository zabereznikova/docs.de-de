---
title: Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: 832a53e072afc5533f2eeb7feb0cc326771cf23d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435255"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a>Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IGridItemProvider>, einschließlich Informationen über Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Das <xref:System.Windows.Automation.GridItemPattern>-Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, in denen <xref:System.Windows.Automation.Provider.IGridProvider> implementiert ist. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie bei der Implementierung von <xref:System.Windows.Automation.Provider.IGridProvider> die folgenden Richtlinien und Konventionen:  
  
- Rasterkoordinaten (Grid-Koordinaten) sind nullbasiert, wobei die obere linke Zelle die Koordinaten (0, 0) hat.  
  
- Zusammengeführte Zellen geben ihre <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>-Eigenschaft und <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>-Eigenschaft entsprechend ihrer zugrunde liegenden Ankerzelle an, wie sie vom Benutzeroberflächenautomatisierungs-Anbieter definiert ist. In der Regel sind dies die oberste Zeile und die am weitesten links liegende Spalte.  
  
- <xref:System.Windows.Automation.Provider.IGridItemProvider> bietet keine aktive Bearbeitung des Rasters, z. b. das Zusammenführen oder aufteilen von Zellen.  
  
- Steuerelemente, die <xref:System.Windows.Automation.Provider.IGridItemProvider> implementieren, können meist mithilfe der Tastatur durchlaufen werden (d. h., ein Benutzeroberflächenautomatisierungs-Client kann zu benachbarten Steuerelementen wechseln).  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>Erforderliche Member für IGridItemProvider  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IGridItemProvider>erforderlich.  
  
|Erforderliche Member|Elementtyp|Hinweise|  
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

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [UI Automation Control Patterns for Clients](ui-automation-control-patterns-for-clients.md)
- [Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung](implementing-the-ui-automation-grid-control-pattern.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
