---
title: Implementieren des Transform-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: 5643bc85972ea33cc31b1a83ecf7615dbb275bc2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180050"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a>Implementieren des Transform-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ITransformProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.TransformPattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die in einem zweidimensionalen Raum verschoben, verkleinert, vergrößert oder gedreht werden können. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Transform-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- Die Unterstützung für dieses Steuerelementmuster ist nicht auf Objekte auf dem Desktop beschränkt. Dieses Steuerelementmuster muss auch von den untergeordneten Elementen eines Containerobjekts unterstützt werden, wenn die untergeordneten Elemente verschoben, vergrößert, verkleinert oder innerhalb der Grenzen des Containers frei gedreht werden können.  
  
- Ein Objekt kann nicht so verschoben, vergrößert, verkleinert oder gedreht werden, dass seine resultierende Bildschirmposition vollständig außerhalb der Koordinaten des Containers liegt und daher nicht über die Tastatur oder Maus zugänglich ist (wenn z. B. ein Fenster auf oberster Ebene außerhalb des Bildschirms oder ein untergeordnetes Objekt außerhalb der Viewportgrenzen des Containers verschoben wird). In diesen Fällen wird das Objekt so nahe wie möglich bei den angeforderten Bildschirmkoordinaten platziert, wobei die oberen oder linken Koordinaten außer Kraft gesetzt werden, damit sich die Koordinaten innerhalb der Containergrenzen befinden.  
  
- Für Systeme mit mehreren Monitoren wird ein Objekt so nahe wie möglich bei den angeforderten Koordinaten auf dem primären Monitor platziert, wenn das Objekt vollständig außerhalb der Bildschirmkoordinaten des kombinierten Desktops verschoben, vergrößert, verkleinert oder gedreht wird.  
  
- Alle Parameter und Eigenschaftswerte sind absolute Angaben und unabhängig vom Gebietsschema.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>
## <a name="required-members-for-itransformprovider"></a>Erforderliche Member für ITransformProvider  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.ITransformProvider>erforderlich.  
  
|Erforderliche Member|Memberart|Notizen|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|Methode|Keine|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> - Wenn <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> der falsch ist.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> - Wenn <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> der falsch ist.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> - Wenn <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> der falsch ist.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
