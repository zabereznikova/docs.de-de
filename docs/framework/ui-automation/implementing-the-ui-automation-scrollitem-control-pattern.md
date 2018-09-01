---
title: Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0346b70b4400c5f7a8d282d945e029701973dad1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393467"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a>Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren der <xref:System.Windows.Automation.Provider.IScrollItemProvider>, einschließlich Informationen zu Eigenschaften, Methoden und Ereignisse. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Die <xref:System.Windows.Automation.ScrollItemPattern> -Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, implementieren <xref:System.Windows.Automation.Provider.IScrollProvider>. Dieses Steuerelementmuster dient als Kommunikationskanal zwischen einem untergeordneten Steuerelement und dessen Container, um sicherzustellen, dass der Container den aktuell sichtbaren Inhalt (oder die Region) innerhalb des Viewports ändern kann, um das untergeordnete Steuerelement anzuzeigen. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des ScrollItem-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   In einem Window- oder Canvas-Steuerelement enthaltene Elemente müssen die IScrollItemProvider-Schnittstelle nicht implementieren. Als Alternative können jedoch, sie müssen zur Verfügung stellen eines gültigen Speicherort für die <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>. Dadurch kann eine Benutzeroberflächenautomatisierungs-Clientanwendung verwendet die <xref:System.Windows.Automation.ScrollPattern> -steuerelementmustermethoden im Container auf das untergeordnete Element anzuzeigen.  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a>Erforderliche Member für IScrollItemProvider  
 Die folgende Methode ist zum Implementieren der IScrollProvider-Schnittstelle erforderlich.  
  
|Erforderliche Member|Memberart|Hinweise|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|-Methode|Keiner|  
  
 Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Wenn ein Element nicht in die Ansicht gescrollt werden kann:<br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
