---
title: Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: 4f11f82b628ac020cbda70d65adf7813291c60a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168037"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a>Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IWindowProvider>, einschließlich Informationen über <xref:System.Windows.Automation.WindowPattern> -Eigenschaften, -Methoden und -Ereignisse. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.WindowPattern> -Steuerelementmuster wird zur Unterstützung von Steuerelementen verwendet, die grundlegende fensterbasierte Funktionen in einer herkömmlichen [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]bereitstellen. Beispiele für Steuerelemente, für die dieses Steuerelementmuster implementiert werden muss, sind Anwendungsfenster der obersten Ebene, untergeordnete [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] -Fenster, Teilbereichs-Steuerelemente, deren Größe geändert werden kann, modale Dialogfelder und Hilfefenster in Sprechblasenform.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Window-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   Damit ein Steuerelement in der Lage ist, Fenstergröße und Bildschirmposition über Benutzeroberflächenautomatisierung zu ändern, muss es <xref:System.Windows.Automation.Provider.ITransformProvider> zusätzlich zu <xref:System.Windows.Automation.Provider.IWindowProvider>implementieren.  
  
-   Für Steuerelemente, die Titelleisten und Titelleistenelemente enthalten, mit denen das Steuerelement verschoben, maximiert, minimiert, geschlossen oder in der Größe verändert werden kann, muss üblicherweise <xref:System.Windows.Automation.Provider.IWindowProvider>implementiert werden.  
  
-   Für Steuerelemente wie QuickInfo-Popups und Dropdown-Kombinationsfelder oder -Menüs muss <xref:System.Windows.Automation.Provider.IWindowProvider>normalerweise nicht implementiert werden.  
  
-   Hilfefenster in Sprechblasenform unterscheiden sich von normalen QuickInfo-Popups darin, dass sie eine wie für Fenster verwendete Schaltfläche zum Schließen bereitstellen.  
  
-   Der Vollbildmodus wird von IWindowProvider nicht unterstützt, da er featurespezifisch für eine Anwendung und kein typisches Fensterverhalten ist.  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## <a name="required-members-for-iwindowprovider"></a>Erforderliche Member für IWindowProvider  
 Die folgenden Eigenschaften, Methoden und Ereignisse sind für die IWindowProvider-Schnittstelle erforderlich.  
  
|Erforderlicher Member|Memberart|Hinweise|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|Eigenschaft|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|Methode|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|Methode|Keiner|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|Methode|Keiner|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|event|Keiner|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|event|Keiner|  
|<xref:System.Windows.Automation.WindowInteractionState>|event|Ist nicht garantiert <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> – Wenn ein Steuerelement ein gefordertes Verhalten nicht unterstützt.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> – Wenn der Parameter keine gültige Zahl ist.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
