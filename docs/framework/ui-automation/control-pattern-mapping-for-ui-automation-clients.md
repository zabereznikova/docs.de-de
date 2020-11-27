---
title: Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients
description: Anzeigen einer Steuerelement Muster-Mapping-Tabelle für Benutzeroberflächenautomatisierungs-Clients Aktionen für bestimmte Steuerelement Typen werden möglicherweise unterstützt, bedingt unterstützt oder nicht unterstützt.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: aaab4639a7573dd090af2e6d9bb06f896c4728f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276554"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema werden Steuerelementtypen und ihre zugeordneten Steuerelementmuster aufgeführt.  
  
 In der folgenden Tabelle sind die Steuerelementmuster in folgende Kategorien unterteilt:  
  
- Unterstützt. Das Steuerelement muss dieses Steuerelementmuster unterstützen.  
  
- Bedingte Unterstützung. Dieses Steuerelement unterstützt das Steuerelementmuster in Abhängigkeit vom Zustand des Steuerelements.  
  
- Wird nicht unterstützt. Das Steuerelement unterstützt dieses Steuerelementmuster nicht. Benutzerdefinierte Steuerelemente können dieses Steuerelementmuster unterstützen.  
  
> [!NOTE]
> Einige Steuerelemente verfügen je nach Funktionalität des Steuerelements über die bedingte Unterstützung für verschiedene Steuerelementmuster. Das MenuItem-Steuerelement verfügt beispielsweise über die bedingte Unterstützung für die <xref:System.Windows.Automation.InvokePattern>-, <xref:System.Windows.Automation.ExpandCollapsePattern>-, <xref:System.Windows.Automation.TogglePattern>- oder <xref:System.Windows.Automation.SelectionItemPattern> -Steuerelementmuster. Dies hängt von seiner Funktion im Menüsteuerelement ab.  
  
<a name="control_mapping_clients"></a>

## <a name="ui-automation-control-patterns-for-clients"></a>Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients  
  
|Steuerelementtyp|Unterstützt|Bedingte Unterstützung|Nicht unterstützt|  
|------------------|---------------|-------------------------|-------------------|  
|Schaltfläche|Keine|Aufrufen, Ein-/ausschalten, Erweitern Reduzieren|Keine|  
|Kalender|Raster, Tabelle|Auswahl, Scroll|Wert|  
|Kontrollkästchen|Ein-/Ausschalten|Keine|Keine|  
|Kombinationsfeld|Erweitern Reduzieren|Auswahl, Wert|Scroll|  
|Datentabelle|Raster|Scroll, Auswahl, Tabelle|Keine|  
|Datenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Scroll-Element, Tabelle, Ein-/ausschalten, Wert|Keine|  
|Dokument|Text|Scroll, Wert|Keine|  
|Bearbeiten|Keine|Text, Bereichswert, Wert|Keine|  
|Group|Keine|Erweitern Reduzieren|Keine|  
|Header|Keine|Transformieren|Keine|  
|Headerelement|Keine|Transformation, Aufrufen|Keine|  
|Hyperlink|Invoke|Wert|Keine|  
|Image|Keine|Rasterelement, Tabellenelement|Aufrufen, Auswahlelement|  
|List|Keine|Raster, mehrere Ansichten, Scroll, Auswahl|Tabelle|  
|Listenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Aufrufen, Ein-/ausschalten, Wert|Keine|  
|Menü|Keine|Keine|Keine|  
|Menüleiste|Keine|Erweitern Reduzieren, Andocken, Transformation|Keine|  
|Menübefehl|Keine|Erweitern Reduzieren, Aufrufen, Auswahlelement, Ein-/ausschalten|Keine|  
|Bereich|Keine|Andocken Scroll, Transformation|Fenster|  
|Statusanzeige|Keine|Bereichswert, Wert|Keine|  
|Radio Button|SelectionItem|Keine|Ein-/Ausschalten|  
|Bildlaufleiste|Keine|Bereichswert|Scroll|  
|Trennzeichen|Keine|Keine|Keine|  
|Schieberegler|Keine|Bereichswert, Auswahl, Wert|Keine|  
|Spinner|Keine|Bereichswert, Auswahl, Wert|Keine|  
|Unterteilte Schaltfläche|Aufrufen, Erweitern Reduzieren|Keine|Keine|  
|Statusleiste|Keine|Raster|Keine|  
|Registerkarte|Auswahl|Scroll|Keine|  
|TabItem|SelectionItem|Keine|Invoke|  
|Tabelle|Raster, Rasterelement, Tabelle, Tabellenelement|Keine|Keine|  
|Text|Keine|Rasterelement, Tabellenelement, Text|Wert|  
|Ziehpunkt|Transformieren|Keine|Keine|  
|Titelleiste|Keine|Keine|Keine|  
|Symbolleiste|Keine|Andocken, Erweitern Reduzieren, Transformation|Keine|  
|QuickInfo|Keine|Text, Fenster|Keine|  
|Struktur|Keine|Scroll, Auswahl|Keine|  
|Strukturelement|Erweitern Reduzieren|Aufrufen, Scroll-Element, Auswahlelement, Ein-/ausschalten|Keine|  
|Fenster|Transformation, Fenster|Dock|Keine|  
  
> [!NOTE]
> Wenn für einen Steuerelementtyp keine unterstützten Steuerelementmuster aufgeführt sind, es aber über mindestens ein bedingt unterstütztes Steuerelementmuster verfügt, dann wird eines dieser bedingten Steuerelementmuster jederzeit unterstützt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
