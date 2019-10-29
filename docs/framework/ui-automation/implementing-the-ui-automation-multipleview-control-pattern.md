---
title: Implementieren des MultipleView-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: edef213c0f4d43a15b7c6842ef6c62e95544da66
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039498"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a>Implementieren des MultipleView-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, einschließlich Informationen über Ereignisse und Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.MultipleViewPattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die mehrere Darstellungen desselben Satzes von Informationen oder untergeordneten Steuerelementen bereitstellt und zwischen diesen wechseln kann.  
  
 Beispiele für Steuerelemente, die mehrere Ansichten darstellen können, sind die Listenansicht (die den Inhalt als Miniaturansichten, Kacheln, Symbole oder Details anzeigen kann), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] Diagrammen (Kreis, Linie, Balken, Zellwert mit einer Formel) [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] Dokumente (normal, Weblayout, Drucklayout, Lesen von Layout, Gliederung), Microsoft Outlook-Kalender (Jahr, Monat, Woche, Tag) und Microsoft Windows Media Player Skins. Die unterstützten Ansichten werden vom Steuerelemententwickler bestimmt und sind für jedes Steuerelement spezifisch.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Steuerelementmusters für mehrere Ansichten die folgenden Richtlinien und Konventionen:  
  
- <xref:System.Windows.Automation.Provider.IMultipleViewProvider> sollte auch für einen Container implementiert werden, der die aktuelle Ansicht verwaltet, wenn er sich von einem Steuerelement unterscheidet, das die aktuelle Ansicht bereitstellt. Windows Explorer enthält z. B. ein Listensteuerelement für den aktuellen Ordnerinhalt, während die Ansicht für das Steuerelement über die Windows Explorer-Anwendung verwaltet wird.  
  
- Ein Steuerelement, das seinen Inhalt sortieren kann, wird nicht als Steuerelement betrachtet, das mehrere Ansichten unterstützt.  
  
- Die Auflistung von Ansichten muss instanzenübergreifend identisch sein.  
  
- Die Namen von Ansichten müssen für die Sprachausgabe, Blindenschrift und andere lesbare Anwendungen geeignet sein.  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a>Erforderliche Member für IMultipleViewProvider  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von „IMultipleViewProvider“ erforderlich.  
  
|Erforderliche Member|Memberart|Notizen|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|property|Keiner|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|Methode|Keiner|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|Methode|Keiner|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|Methode|Keiner|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|Wenn entweder <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> oder <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> mit einem Parameter aufgerufen wird, der kein Member der unterstützten Ansichtenauflistung ist.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
