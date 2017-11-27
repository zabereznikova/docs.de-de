---
title: "Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
caps.latest.revision: "18"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 31beb7ab9a978f5bb379a3c1d61c90c19c26ca6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
|Schaltfläche|Keine|Aufrufen, Ein-/ausschalten, Erweitern Reduzieren|Keine|  
|Kalender|Raster, Tabelle|Auswahl, Scroll|Wert|  
|Kontrollkästchen|Ein-/ausschalten|Keine|Keine|  
|Kombinationsfeld|Erweitern Reduzieren|Auswahl, Wert|Scroll|  
|DataGrid|Raster|Scroll, Auswahl, Tabelle|Keine|  
|Datenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Scroll-Element, Tabelle, Ein-/ausschalten, Wert|Keine|  
|Dokument|Text|Scroll, Wert|Keine|  
|Bearbeiten|Keine|Text, Bereichswert, Wert|Keine|  
|Gruppieren|Keine|Erweitern Reduzieren|Keine|  
|Header|Keine|Transformation|Keine|  
|Headerelement|Keine|Transformation, Aufrufen|Keine|  
|Link|Aufrufen|Wert|Keine|  
|Bild|Keine|Rasterelement, Tabellenelement|Aufrufen, Auswahlelement|  
|Liste|Keine|Raster, mehrere Ansichten, Scroll, Auswahl|Tabelle|  
|Listenelement|SelectionItem|Erweitern Reduzieren, Rasterelement, Aufrufen, Ein-/ausschalten, Wert|Keine|  
|Menü|Keine|Keine|Keine|  
|Menüleiste|Keine|Erweitern Reduzieren, Andocken, Transformation|Keine|  
|Menübefehl|Keine|Erweitern Reduzieren, Aufrufen, Auswahlelement, Ein-/ausschalten|Keine|  
|Bereich|Keine|Andocken Scroll, Transformation|Fenster|  
|Statusanzeige|Keine|Bereichswert, Wert|Keine|  
|Radio Button|SelectionItem|Keine|Ein-/ausschalten|  
|Bildlaufleiste|Keine|Bereichswert|Scroll|  
|Trennzeichen|Keine|Keine|Keine|  
|Slider|Keine|Bereichswert, Auswahl, Wert|Keine|  
|Spinner|Keine|Bereichswert, Auswahl, Wert|Keine|  
|Unterteilte Schaltfläche|Aufrufen, Erweitern Reduzieren|Keine|Keine|  
|Statusleiste|Keine|Raster|Keine|  
|Registerkarte|Auswahl|Scroll|Keine|  
|TabItem|SelectionItem|Keine|Aufrufen|  
|Tabelle|Raster, Rasterelement, Tabelle, Tabellenelement|Keine|Keine|  
|Text|Keine|Rasterelement, Tabellenelement, Text|Wert|  
|Ziehpunkt|Transformation|Keine|Keine|  
|Titelleiste|Keine|Keine|Keine|  
|Symbolleiste|Keine|Andocken, Erweitern Reduzieren, Transformation|Keine|  
|QuickInfo|Keine|Text, Fenster|Keine|  
|Struktur|Keine|Scroll, Auswahl|Keine|  
|Strukturelement|Erweitern Reduzieren|Aufrufen, Scroll-Element, Auswahlelement, Ein-/ausschalten|Keine|  
|Fenster|Transformation, Fenster|Andocken|Keine|  
  
> [!NOTE]
>  Wenn für einen Steuerelementtyp keine unterstützten Steuerelementmuster aufgeführt sind, es aber über mindestens ein bedingt unterstütztes Steuerelementmuster verfügt, dann wird eines dieser bedingten Steuerelementmuster jederzeit unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
