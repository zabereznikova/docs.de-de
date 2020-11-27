---
title: Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Überprüfen Sie die Richtlinien und Konventionen, um das Fenster Steuerelement Muster in der Benutzeroberflächen Automatisierung Sie müssen erforderliche Member für die IWindowProvider-Schnittstelle kennen.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: b43884393974e6f2863da6a4a5ca8f305e5a160c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286096"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a>Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IWindowProvider>, einschließlich Informationen über <xref:System.Windows.Automation.WindowPattern> -Eigenschaften, -Methoden und -Ereignisse. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das- <xref:System.Windows.Automation.WindowPattern> Steuerelement Muster wird zur Unterstützung von Steuerelementen verwendet, die grundlegende fensterbasierte Funktionen in einer herkömmlichen grafischen Benutzeroberfläche (GUI) bereitstellen. Beispiele für Steuerelemente, die dieses Steuerelement Muster implementieren müssen, sind u. a. Anwendungsfenster der obersten Ebene, untergeordnete MDI-Fenster (Multiple Document Interface), in der Größe umsetzbare Steuerelemente für geteilte Bereiche, Modale Dialoge und  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  

 Beachten Sie beim Implementieren des Window-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- Damit ein Steuerelement in der Lage ist, Fenstergröße und Bildschirmposition über Benutzeroberflächenautomatisierung zu ändern, muss es <xref:System.Windows.Automation.Provider.ITransformProvider> zusätzlich zu <xref:System.Windows.Automation.Provider.IWindowProvider>implementieren.  
  
- Für Steuerelemente, die Titelleisten und Titelleistenelemente enthalten, mit denen das Steuerelement verschoben, maximiert, minimiert, geschlossen oder in der Größe verändert werden kann, muss üblicherweise <xref:System.Windows.Automation.Provider.IWindowProvider>implementiert werden.  
  
- Für Steuerelemente wie QuickInfo-Popups und Dropdown-Kombinationsfelder oder -Menüs muss <xref:System.Windows.Automation.Provider.IWindowProvider>normalerweise nicht implementiert werden.  
  
- Hilfefenster in Sprechblasenform unterscheiden sich von normalen QuickInfo-Popups darin, dass sie eine wie für Fenster verwendete Schaltfläche zum Schließen bereitstellen.  
  
- Der Vollbildmodus wird von IWindowProvider nicht unterstützt, da er featurespezifisch für eine Anwendung und kein typisches Fensterverhalten ist.  
  
<a name="Required_Members_for_IWindowProvider"></a>

## <a name="required-members-for-iwindowprovider"></a>Erforderliche Member für IWindowProvider  

 Die folgenden Eigenschaften, Methoden und Ereignisse sind für die IWindowProvider-Schnittstelle erforderlich.  
  
|Erforderlicher Member|Memberart|Hinweise|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|Ereignis|Keine|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|Ereignis|Keine|  
|<xref:System.Windows.Automation.WindowInteractionState>|Ereignis|<xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction>|  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a>Ausnahmen  

 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> : Wenn ein Steuerelement ein angefordertes Verhalten nicht unterstützt.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> -Wenn der-Parameter keine gültige Zahl ist.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
