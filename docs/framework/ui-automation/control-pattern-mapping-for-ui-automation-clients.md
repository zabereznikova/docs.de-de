---
title: Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 48298cb8d89958c701d7150aeb497e82d565bde1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433858"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema werden Steuerelementtypen und ihre zugeordneten Steuerelementmuster aufgeführt.  
  
 In der folgenden Tabelle sind die Steuerelementmuster in folgende Kategorien unterteilt:  
  
- Unterstützt. Das Steuerelement muss dieses Steuerelementmuster unterstützen.  
  
- Bedingte Unterstützung. Dieses Steuerelement unterstützt das Steuerelementmuster in Abhängigkeit vom Zustand des Steuerelements.  
  
- Nicht unterstützt. Das Steuerelement unterstützt dieses Steuerelementmuster nicht. Benutzerdefinierte Steuerelemente können dieses Steuerelementmuster unterstützen.  
  
> [!NOTE]
> Einige Steuerelemente verfügen je nach Funktionalität des Steuerelements über die bedingte Unterstützung für verschiedene Steuerelementmuster. Das MenuItem-Steuerelement verfügt beispielsweise über die bedingte Unterstützung für die <xref:System.Windows.Automation.InvokePattern>-, <xref:System.Windows.Automation.ExpandCollapsePattern>-, <xref:System.Windows.Automation.TogglePattern>- oder <xref:System.Windows.Automation.SelectionItemPattern> -Steuerelementmuster. Dies hängt von seiner Funktion im Menüsteuerelement ab.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients  
  
|Steuerelementtyp|Unterstützt|Bedingte Unterstützung|Nicht unterstützt|  
|------------------|---------------|-------------------------|-------------------|  
|Schaltfläche|Keine|Aufrufen, Ein-/ausschalten, Erweitern Reduzieren|Keine|  
|Kalender|Raster, Tabelle|Auswahl, Scroll|Wert|  
|Kontrollkästchen|Ein-/ausschalten|Keine|Keine|  
|Kombinationsfeld|Erweitern Reduzieren|Auswahl, Wert|Scroll|  
|DataGrid|Raster|Scroll, Auswahl, Tabelle|Keine|  
|Datenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Scroll-Element, Tabelle, Ein-/ausschalten, Wert|Keine|  
|Dokument|Text|Scroll, Wert|Keine|  
|Bearbeiten|Keine|Text, Bereichswert, Wert|Keine|  
|Gruppe|Keine|Erweitern Reduzieren|Keine|  
|Header|Keine|Transformieren|Keine|  
|Headerelement|Keine|Transformation, Aufrufen|Keine|  
|Link|Aufrufen|Wert|Keine|  
|Bild|Keine|Rasterelement, Tabellenelement|Aufrufen, Auswahlelement|  
|Liste|Keine|Raster, mehrere Ansichten, Scroll, Auswahl|Table|  
|Listenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Aufrufen, Ein-/ausschalten, Wert|Keine|  
|Menü|Keine|Keine|Keine|  
|Menüleiste|Keine|Erweitern Reduzieren, Andocken, Transformation|Keine|  
|Menüelement|Keine|Erweitern Reduzieren, Aufrufen, Auswahlelement, Ein-/ausschalten|Keine|  
|Bereich|Keine|Andocken Scroll, Transformation|Fenster|  
|Statusanzeige|Keine|Bereichswert, Wert|Keine|  
|Optionsfeld|SelectionItem|Keine|Ein-/ausschalten|  
|Bildlaufleiste|Keine|Bereichswert|Scroll|  
|Trennzeichen|Keine|Keine|Keine|  
|Schieberegler|Keine|Bereichswert, Auswahl, Wert|Keine|  
|Spinner|Keine|Bereichswert, Auswahl, Wert|Keine|  
|Unterteilte Schaltfläche|Aufrufen, Erweitern Reduzieren|Keine|Keine|  
|Statusleiste|Keine|Raster|Keine|  
|Registerkarte|Markierung|Scroll|Keine|  
|TabItem|SelectionItem|Keine|Aufrufen|  
|Table|Raster, Rasterelement, Tabelle, Tabellenelement|Keine|Keine|  
|Text|Keine|Rasterelement, Tabellenelement, Text|Wert|  
|Miniatur|Transformieren|Keine|Keine|  
|Titelleiste|Keine|Keine|Keine|  
|Symbolleiste|Keine|Andocken, Erweitern Reduzieren, Transformation|Keine|  
|QuickInfo|Keine|Text, Fenster|Keine|  
|Struktur|Keine|Scroll, Auswahl|Keine|  
|Strukturelement|Erweitern Reduzieren|Aufrufen, Scroll-Element, Auswahlelement, Ein-/ausschalten|Keine|  
|Fenster|Transformation, Fenster|Andocken|Keine|  
  
> [!NOTE]
> Wenn für einen Steuerelementtyp keine unterstützten Steuerelementmuster aufgeführt sind, es aber über mindestens ein bedingt unterstütztes Steuerelementmuster verfügt, dann wird eines dieser bedingten Steuerelementmuster jederzeit unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
