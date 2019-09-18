---
title: Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: cfd8e5dbe34df7b947646c714a360cf56b0435a4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043863"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
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
|Schaltfläche|None|Aufrufen, Ein-/ausschalten, Erweitern Reduzieren|None|  
|Kalender|Raster, Tabelle|Auswahl, Scroll|Wert|  
|Kontrollkästchen|Ein-/ausschalten|None|None|  
|Kombinationsfeld|Erweitern Reduzieren|Auswahl, Wert|Scroll|  
|DataGrid|Raster|Scroll, Auswahl, Tabelle|None|  
|Datenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Scroll-Element, Tabelle, Ein-/ausschalten, Wert|None|  
|Dokument|Text|Scroll, Wert|None|  
|Bearbeiten|None|Text, Bereichswert, Wert|None|  
|Gruppieren|None|Erweitern Reduzieren|None|  
|Header|None|Transformation|None|  
|Headerelement|None|Transformation, Aufrufen|None|  
|Link|Aufrufen|Wert|None|  
|Bild|None|Rasterelement, Tabellenelement|Aufrufen, Auswahlelement|  
|Liste|None|Raster, mehrere Ansichten, Scroll, Auswahl|Tabelle|  
|Listenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Aufrufen, Ein-/ausschalten, Wert|None|  
|Menü|None|Keiner|None|  
|Menüleiste|None|Erweitern Reduzieren, Andocken, Transformation|None|  
|Menübefehl|None|Erweitern Reduzieren, Aufrufen, Auswahlelement, Ein-/ausschalten|None|  
|Bereich|None|Andocken Scroll, Transformation|Fenster|  
|Statusanzeige|None|Bereichswert, Wert|None|  
|Radio Button|SelectionItem|None|Ein-/ausschalten|  
|Bildlaufleiste|None|Bereichswert|Scroll|  
|Trennzeichen|None|Keiner|None|  
|Slider|None|Bereichswert, Auswahl, Wert|None|  
|Spinner|None|Bereichswert, Auswahl, Wert|None|  
|Unterteilte Schaltfläche|Aufrufen, Erweitern Reduzieren|None|None|  
|Statusleiste|None|Raster|None|  
|Registerkarte|Auswahl|Scroll|None|  
|TabItem|SelectionItem|None|Aufrufen|  
|Tabelle|Raster, Rasterelement, Tabelle, Tabellenelement|None|None|  
|Text|None|Rasterelement, Tabellenelement, Text|Wert|  
|Ziehpunkt|Transformation|None|None|  
|Titelleiste|None|Keiner|None|  
|Symbolleiste|None|Andocken, Erweitern Reduzieren, Transformation|None|  
|QuickInfo|None|Text, Fenster|None|  
|Struktur|None|Scroll, Auswahl|None|  
|Strukturelement|Erweitern Reduzieren|Aufrufen, Scroll-Element, Auswahlelement, Ein-/ausschalten|None|  
|Fenster|Transformation, Fenster|Andocken|None|  
  
> [!NOTE]
> Wenn für einen Steuerelementtyp keine unterstützten Steuerelementmuster aufgeführt sind, es aber über mindestens ein bedingt unterstütztes Steuerelementmuster verfügt, dann wird eines dieser bedingten Steuerelementmuster jederzeit unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
