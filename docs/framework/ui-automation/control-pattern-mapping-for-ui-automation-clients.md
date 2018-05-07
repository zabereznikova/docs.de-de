---
title: Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 571d94c7654038c7ea47721caa35c41d31983016
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema werden Steuerelementtypen und ihre zugeordneten Steuerelementmuster aufgeführt.  
  
 In der folgenden Tabelle sind die Steuerelementmuster in folgende Kategorien unterteilt:  
  
-   Unterstützt. Das Steuerelement muss dieses Steuerelementmuster unterstützen.  
  
-   Bedingte Unterstützung. Dieses Steuerelement unterstützt das Steuerelementmuster in Abhängigkeit vom Zustand des Steuerelements.  
  
-   Wird nicht unterstützt. Das Steuerelement unterstützt dieses Steuerelementmuster nicht. Benutzerdefinierte Steuerelemente können dieses Steuerelementmuster unterstützen.  
  
> [!NOTE]
>  Einige Steuerelemente verfügen je nach Funktionalität des Steuerelements über die bedingte Unterstützung für verschiedene Steuerelementmuster. Das MenuItem-Steuerelement verfügt beispielsweise über die bedingte Unterstützung für die <xref:System.Windows.Automation.InvokePattern>-, <xref:System.Windows.Automation.ExpandCollapsePattern>-, <xref:System.Windows.Automation.TogglePattern>- oder <xref:System.Windows.Automation.SelectionItemPattern> -Steuerelementmuster. Dies hängt von seiner Funktion im Menüsteuerelement ab.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients  
  
|Steuerelementtyp|Unterstützt|Bedingte Unterstützung|Nicht unterstützt|  
|------------------|---------------|-------------------------|-------------------|  
|Schaltfläche|Keiner|Aufrufen, Ein-/ausschalten, Erweitern Reduzieren|Keiner|  
|Kalender|Raster, Tabelle|Auswahl, Scroll|Wert|  
|Kontrollkästchen|Ein-/ausschalten|Keiner|Keiner|  
|Kombinationsfeld|Erweitern Reduzieren|Auswahl, Wert|Scroll|  
|DataGrid|Raster|Scroll, Auswahl, Tabelle|Keiner|  
|Datenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Scroll-Element, Tabelle, Ein-/ausschalten, Wert|Keiner|  
|Dokument|Text|Scroll, Wert|Keiner|  
|Bearbeiten|Keiner|Text, Bereichswert, Wert|Keiner|  
|Gruppieren|Keiner|Erweitern Reduzieren|Keiner|  
|Header|Keiner|Transformation|Keiner|  
|Headerelement|Keiner|Transformation, Aufrufen|Keiner|  
|Link|Aufrufen|Wert|Keiner|  
|Bild|Keiner|Rasterelement, Tabellenelement|Aufrufen, Auswahlelement|  
|Liste|Keiner|Raster, mehrere Ansichten, Scroll, Auswahl|Tabelle|  
|Listenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Aufrufen, Ein-/ausschalten, Wert|Keiner|  
|Menü|Keiner|Keine|Keiner|  
|Menüleiste|Keiner|Erweitern Reduzieren, Andocken, Transformation|Keiner|  
|Menübefehl|Keiner|Erweitern Reduzieren, Aufrufen, Auswahlelement, Ein-/ausschalten|Keiner|  
|Bereich|Keiner|Andocken Scroll, Transformation|Fenster|  
|Statusanzeige|Keiner|Bereichswert, Wert|Keiner|  
|Radio Button|SelectionItem|Keiner|Ein-/ausschalten|  
|Bildlaufleiste|Keiner|Bereichswert|Scroll|  
|Trennzeichen|Keiner|Keine|Keiner|  
|Slider|Keiner|Bereichswert, Auswahl, Wert|Keiner|  
|Spinner|Keiner|Bereichswert, Auswahl, Wert|Keiner|  
|Unterteilte Schaltfläche|Aufrufen, Erweitern Reduzieren|Keiner|Keiner|  
|Statusleiste|Keiner|Raster|Keiner|  
|Registerkarte|Auswahl|Scroll|Keiner|  
|TabItem|SelectionItem|Keiner|Aufrufen|  
|Tabelle|Raster, Rasterelement, Tabelle, Tabellenelement|Keiner|Keiner|  
|Text|Keiner|Rasterelement, Tabellenelement, Text|Wert|  
|Ziehpunkt|Transformation|Keiner|Keiner|  
|Titelleiste|Keiner|Keine|Keiner|  
|Symbolleiste|Keiner|Andocken, Erweitern Reduzieren, Transformation|Keiner|  
|QuickInfo|Keiner|Text, Fenster|Keiner|  
|Struktur|Keiner|Scroll, Auswahl|Keiner|  
|Strukturelement|Erweitern Reduzieren|Aufrufen, Scroll-Element, Auswahlelement, Ein-/ausschalten|Keiner|  
|Fenster|Transformation, Fenster|Andocken|Keiner|  
  
> [!NOTE]
>  Wenn für einen Steuerelementtyp keine unterstützten Steuerelementmuster aufgeführt sind, es aber über mindestens ein bedingt unterstütztes Steuerelementmuster verfügt, dann wird eines dieser bedingten Steuerelementmuster jederzeit unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
