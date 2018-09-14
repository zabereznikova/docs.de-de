---
title: Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, grid
- grid control pattern
- UI Automation, grid control pattern
ms.assetid: 234d11a0-7ce7-4309-8989-2f4720e02f78
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 036680ea908f2cbe58db398dc315fccd997c4148
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45529302"
---
# <a name="implementing-the-ui-automation-grid-control-pattern"></a>Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IGridProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Das <xref:System.Windows.Automation.GridPattern> -Steuerelementmuster wird zur Unterstützung von Steuerelementen verwendet, die als Container für eine Auflistung von untergeordneten Elementen dienen. Die untergeordneten Elemente dieses Elements müssen <xref:System.Windows.Automation.Provider.IGridItemProvider> implementieren und in einem zweidimensionalen logischen Koordinatensystem angeordnet sein, das zeilen- und spaltenweise durchlaufen werden kann. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Grid-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   Grid-Koordinaten sind nullbasiert, wobei die obere linke Zelle (oder die obere rechte Zelle, je nach Gebietsschema) die Koordinaten (0,0) aufweist.  
  
-   Auch wenn eine Zelle leer ist, muss ein Benutzeroberflächenautomatisierungs-Element zurückgegeben werden, um die <xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A> -Eigenschaft dieser Zelle zu unterstützen. Dies ist möglich, wenn das Layout von untergeordneten Elementen im Raster dem eines unregelmäßigen Arrays entspricht (siehe folgendes Beispiel).  
  
 ![Windows Explorer-Ansicht mit Flatterlayout. ](../../../docs/framework/ui-automation/media/uia-gridpattern-ragged-array.PNG "UIA_GridPattern_Ragged_Array")  
Beispiel für ein Grid-Steuerelement mit leeren Koordinaten  
  
-   Ein Raster mit einem einzelnen Element muss weiterhin <xref:System.Windows.Automation.Provider.IGridProvider> implementieren, wenn es logisch als Raster gilt. Die Anzahl untergeordneter Elemente im Raster ist unwesentlich.  
  
-   Ausgeblendete Zeilen und Spalten können je nach der Anbieterimplementierung in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur geladen werden. Daher werden sie in den Eigenschaften <xref:System.Windows.Automation.GridPattern.GridPatternInformation.RowCount%2A> und <xref:System.Windows.Automation.GridPattern.GridPatternInformation.ColumnCount%2A> angegeben. Wenn die ausgeblendeten Zeilen und Spalten noch nicht geladen wurden, sollten sie nicht gezählt werden.  
  
-   <xref:System.Windows.Automation.Provider.IGridProvider> ermöglicht keine aktive Bearbeitung eines Rasters. <xref:System.Windows.Automation.Provider.ITransformProvider> muss implementiert werden, um diese Funktionalität zu aktivieren.  
  
-   Verwenden Sie einen <xref:System.Windows.Automation.StructureChangedEventHandler> , um Änderungen an der Struktur oder am Layout des Raster zu erfassen, z. B. Zellen, die hinzugefügt, entfernt oder zusammengeführt wurden.  
  
-   Verwenden Sie einen <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> , um den Durchlauf durch die Elemente oder Zellen eines Rasters zu verfolgen.  
  
<a name="Required_Members_for_IGridProvider"></a>   
## <a name="required-members-for-igridprovider"></a>Erforderliche Member für IGridProvider  
 Zum Implementieren der IGridProvider-Schnittstelle werden die folgenden Eigenschaften und Methoden benötigt.  
  
|Erforderliche Member|Typ|Hinweise|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A>|Methode|Keiner|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> -Wenn die angeforderte Zeilenkoordinate größer als die <xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A> oder die Spaltenkoordinate ist größer als die <xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> – Wenn Sie entweder von der angeforderten Zeilen- oder Spaltenkoordinaten kleiner als 0 (null).|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
