---
title: Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Lesen Sie die Richtlinien und Konventionen zum Implementieren des Table-Steuerelement Musters in der Benutzeroberflächen Automatisierung Sie müssen erforderliche Member für die ITableProvider-Schnittstelle kennen.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 9c1d57e46aed9ec2441a95544d26244d2dfa9496
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265751"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a>Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ITableProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Das <xref:System.Windows.Automation.TablePattern> -Steuerelementmuster wird zur Unterstützung von Steuerelementen verwendet, die als Container für eine Auflistung von untergeordneten Elementen dienen. Die untergeordneten Elemente dieses Elements müssen <xref:System.Windows.Automation.Provider.ITableItemProvider> implementieren und in einem zweidimensionalen logischen Koordinatensystem angeordnet sein, das zeilen- und spaltenweise durchlaufen werden kann. Dieses Steuerelementmuster entspricht dem <xref:System.Windows.Automation.Provider.IGridProvider>, mit dem Unterschied, dass jedes <xref:System.Windows.Automation.Provider.ITableProvider> implementierende Steuerelement für jedes untergeordnete Element auch eine Beziehung zwischen Spalten- und/oder Zeilenüberschriften verfügbar machen muss. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  

 Beachten Sie beim Implementieren des Table-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- Der Zugriff auf den Inhalt der einzelnen Zellen erfolgt über ein zweidimensionales logisches Koordinatensystem oder über ein Array, das von der erforderlichen gleichzeitigen Implementierung von <xref:System.Windows.Automation.Provider.IGridProvider> bereitgestellt wird.  
  
- Eine Spalten- oder Zeilenüberschrift kann in einem Tabellenobjekt enthalten sein oder ein separates Headerobjekt darstellen, das einem Tabellenobjekt zugeordnet ist.  
  
- Spalten- und Zeilenüberschriften können sowohl eine primäre als auch beliebige unterstützende Überschriften enthalten.  
  
> [!NOTE]
> Dieses Konzept wird in einer Microsoft Excel-Tabelle ersichtlich, in der ein Benutzer eine "Vorname"-Spalte definiert hat. Diese Spalte verfügt jetzt über zwei Überschriften. Die vom Benutzer definierte Überschrift „Vorname“ und die alphanumerische Bezeichnung der Spalte, die von der Anwendung zugewiesen wird.  
  
- Weitere Informationen finden Sie [unter Implementieren des Grid-Steuerelement Musters der Benutzeroberflächen Automatisierung](implementing-the-ui-automation-grid-control-pattern.md) .  
  
 ![Tabelle mit komplexen Headerelementen](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")  
Beispiel für eine Tabelle mit komplexen Spaltenüberschriften  
  
 ![Tabelle mit mehrdeutiger RowOrColumnMajor-Eigenschaft.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")  
Beispiel für eine Tabelle mit mehrdeutiger RowOrColumnMajor-Eigenschaft  
  
<a name="Required_Members_for_ITableProvider"></a>

## <a name="required-members-for-itableprovider"></a>Erforderliche Member für ITableProvider  

 Für die ITableProvider-Schnittstelle werden die folgenden Eigenschaften und Methoden benötigt.  
  
|Erforderliche Member|Memberart|Hinweise|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|Methode|Keine|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a>Ausnahmen  

 Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung](implementing-the-ui-automation-tableitem-control-pattern.md)
- [Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung](implementing-the-ui-automation-grid-control-pattern.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
