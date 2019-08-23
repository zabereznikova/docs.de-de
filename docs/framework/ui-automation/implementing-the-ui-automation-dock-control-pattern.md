---
title: Implementieren des Dock-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
ms.openlocfilehash: 9bc4f80569dc2bab68e3f65c9e99df72df372171
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968908"
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a>Implementieren des Dock-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IDockProvider>, einschließlich Informationen über Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.DockPattern> -Steuerelementmuster wird verwendet, um Andockeigenschaften eines Steuerelements in einem Dockingcontainer verfügbar zu machen. Ein Dockingcontainer ist ein Steuerelement, mit dem untergeordnete Elemente horizontal oder vertikal zueinander ausgerichtet werden können. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
 ![Andock Container mit zwei angedockten unter] geordneten Elementen. (../../../docs/framework/ui-automation/media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")  
Andockbeispiel aus Visual Studio, in dem das Fenster „Klassenansicht“ die DockPosition.Right und das Fenster „Fehlerliste“ die DockPosition.Bottom hat  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Dock-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- <xref:System.Windows.Automation.Provider.IDockProvider> macht keine Eigenschaften des Dockingcontainers bzw. der Steuerelemente verfügbar, die neben dem aktuellen Steuerelement im Dockingcontainer angedockt sind.  
  
- Steuerelemente werden relativ zueinander entsprechend ihrer aktuellen z-Reihenfolge angeordnet. Je höher ihre z-Reihenfolgenposition ist, desto weiter entfernt vom angegebenen Rand des Dockingcontainers werden sie platziert.  
  
- Wenn die Größe des Dockingcontainers geändert wird, werden alle angedockten Steuerelemente im Container bündig zu derselben Kante neu positioniert, an der sie ursprünglich angedockt waren. Die Größe der angedockten Steuerelemente wird ebenfalls geändert, um den Platz innerhalb des Containers entsprechend dem Andockverhalten ihrer <xref:System.Windows.Automation.DockPosition>auszufüllen. Wenn beispielsweise <xref:System.Windows.Automation.DockPosition.Top> angegeben ist, werden die linke und die rechte Seite des Steuerelements erweitert, um den verfügbaren Platz auszufüllen. Wenn <xref:System.Windows.Automation.DockPosition.Fill> angegeben ist, werden alle vier Seiten des Steuerelements erweitert, um den verfügbaren Platz auszufüllen.  
  
- Auf einem System mit mehreren Bildschirmen sollten Steuerelemente auf der linken oder rechten Seite des aktuellen Bildschirms andocken. Ist dies nicht möglich, sollten sie auf der linken Seite des am weitesten links stehenden Bildschirms bzw. auf der rechten Seite des am weitesten rechts stehenden Bildschirms angedockt werden.  
  
<a name="Required_Members_for_IDockProvider"></a>   
## <a name="required-members-for-idockprovider"></a>Erforderliche Member für IDockProvider  
 Zum Implementieren der IDockProvider-Schnittstelle werden die folgenden Eigenschaften und Methoden benötigt.  
  
|Erforderliche Member|Memberart|Hinweise|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|Eigenschaft|None|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|Methode|None|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> : Wenn ein Steuerelement nicht in der Lage ist, den angeforderten Andock Stil auszuführen.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
