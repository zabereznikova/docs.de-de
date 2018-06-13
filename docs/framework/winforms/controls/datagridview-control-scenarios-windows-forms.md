---
title: Szenarien für das DataGridView-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: a320b40664e4fe2254109183731db346a5d7d0b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529037"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Szenarien für das DataGridView-Steuerelement (Windows Forms)
Mit der <xref:System.Windows.Forms.DataGridView> -Steuerelement, Sie können Tabellendaten aus einer Vielzahl von Datenquellen anzeigen. Für einfache verwendet wird, können Sie manuell Auffüllen einer <xref:System.Windows.Forms.DataGridView> und bearbeiten Sie die Daten nicht direkt über das Steuerelement. In der Regel jedoch Sie Speichern Ihrer Daten in einer externen Datenquelle und Binden des Steuerelements an ihn über eine <xref:System.Windows.Forms.BindingSource> Komponente.  
  
 Dieses Thema beschreibt einige allgemeine Szenarien, bei denen, die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Szenario 1: Anzeige kleiner Mengen von Daten  
 Sie müssen keine Speichern Ihrer Daten in einer externen Datenquelle, um es im Bereich der <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn Sie eine kleine Menge von Daten arbeiten, können Sie füllen Sie das Steuerelement selbst und die Daten über das Steuerelement bearbeiten. Hierbei spricht *ungebundenen Modus*. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario wesentliche Punkte  
  
-   Ungebunden-Modus füllen Sie das Steuerelement manuell.  
  
-   Ungebunden-Modus eignet sich besonders für kleine Mengen von schreibgeschützten Daten.  
  
-   Ungebunden-Modus ist für die Kalkulationstabelle ähnelt oder gefüllten Tabellen geeignet ist.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Szenario 2: Anzeigen und Aktualisieren von Daten in einer externen Datenquelle gespeichert  
 Sie können die <xref:System.Windows.Forms.DataGridView> als Benutzeroberfläche (UI) zu steuern, über welche Benutzer Daten in einer Datenquelle, z. B. einer Datenbanktabelle oder eine Auflistung von Geschäftsobjekten beibehalten zugreifen können. Weitere Informationen finden Sie unter [Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario wesentliche Punkte  
  
-   Gebundenen Modus können Sie eine Verbindung mit einer Datenquelle herstellen, automatisch auf Grundlage des Datenquelleneigenschaften oder Datenbankspalten Spalten generieren und füllen Sie das Steuerelement automatisch.  
  
-   Gebundene Modus eignet sich für intensive Benutzerinteraktion mit Daten. Daten können für die Anzeige formatiert werden, und Benutzer angegebenen Daten analysiert werden können, in dem von der Datenquelle erwarteten Format. Dateneingabe Formatieren von Fehlern und Einschränkung Datenbankfehler kann erkannt werden, damit Benutzer darüber informiert werden können und fehlerhafte Zellen korrigiert werden können.  
  
-   Zusätzliche Funktionen wie z. B. den Spalte sortieren, aktivieren Sie fixieren und Neuanordnen von Benutzern, Daten in die Möglichkeit, die am einfachsten für ihren Workflow anzuzeigen.  
  
-   Unterstützung der Zwischenablage ermöglicht Benutzern das Kopieren von Daten aus Ihrer Anwendung in andere Anwendungen.  
  
## <a name="scenario-3-advanced-data"></a>Szenario 3: Erweiterte Daten  
 Wenn Sie besondere Anforderungen, die nicht das standard-Datenbindungsmodell berücksichtigt wird verfügen, können Sie die Interaktion zwischen dem Steuerelement und Ihre Daten verwalten, durch die Implementierung *Virtueller Modus*. Implementieren des virtuellen Modus bedeutet, dass implementieren eine oder mehrere Ereignishandler, mit die das Steuerelement Anfordern von Informationen zu den Zellen als die Informationen können ist erforderlich.  
  
 Wenn Sie mit großen Datenmengen arbeiten, sollten Sie z. B. Implementieren des virtuellen Modus um optimaler Effizienz sicherzustellen. Virtueller Modus eignet sich auch für die Verwaltung der Werte von ungebundenen Spalten, die Sie zusammen mit einer Spalte abgerufen, die aus einer anderen Datenquelle anzeigen.  
  
 Weitere Informationen zum virtuellen Modus finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario wesentliche Punkte  
  
-   Virtueller Modus eignet sich für sehr große Mengen von Daten anzeigen, wenn Sie die Leistung optimieren müssen.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Szenario 4: Automatische Größenänderung von Zeilen und Spalten  
 Wenn Sie Daten, die regelmäßig aktualisiert wird anzeigen, können Sie automatisch ändern, Zeilen und Spalten, um sicherzustellen, dass der gesamte Inhalt sichtbar ist. Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet mehrere Optionen, mit denen Sie aktivieren oder deaktivieren Sie manuelle Ändern der Größe, programmgesteuert zu bestimmten Zeitpunkten Ändern der Größe oder skalieren Inhalte automatisch bei jedem ändern. Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario wesentliche Punkte  
  
-   Manuelles Ändern der Größe ermöglicht Benutzern das Anpassen der Zelle Höhe und Breite.  
  
-   Automatische Größenänderung ermöglicht Zellengrößen zu behalten, sodass Zelleninhalt nie abgeschnitten wird.  
  
-   Programmgesteuerten größenanpassung ermöglicht es Ihnen, um die Größe von Zellen zu bestimmten Zeiten von kontinuierlichen automatische Größenänderung Leistungseinbußen zu vermeiden.  
  
## <a name="scenario-5-simple-customization"></a>Szenario 5: Einfache Anpassung  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet viele Möglichkeiten, die grundlegende Darstellung und Verhalten zu ändern. Weitere Informationen finden Sie unter [Zellstile im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario wesentliche Punkte  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte können Sie die Farbe, Schriftart, Formatierung und Positionierung von Informationen auf mehreren Ebenen und für einzelne Elemente des Steuerelements angeben.  
  
-   Zellstile im Protokollstapel zugeordnet, und von mehreren Elementen, da Sie die Wiederverwendung von Code dar, sondern gemeinsam genutzt werden können.  
  
## <a name="scenario-6-advanced-customization"></a>Szenario 6: Erweiterte Anpassung  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet viele Methoden für die Darstellung und Verhalten anpassen.  
  
### <a name="scenario-key-points"></a>Szenario wesentliche Punkte  
  
-   Sie können Ihren eigenen Code zum Zeichnen von Zelle bereitstellen. Weitere Informationen finden Sie unter [wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).  
  
-   Sie können eine eigene Zeile zeichnen bereitstellen. Dies ist nützlich, z. B. Zeilen mit Inhalt zu erstellen, die mehrere Spalten umfasst. Weitere Informationen finden Sie unter [wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).  
  
-   Sie können Ihren eigenen Zellen- und Spaltentyps Klassen zum Anpassen der Darstellung Zelle implementieren. Weitere Informationen finden Sie unter [wie: Anpassen von Zellen und Spalten in Windows Forms-DataGridView-Steuerelements durch Erweitern von deren Verhalten und Aussehen](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
-   Sie können Ihren eigenen Klassen Zellen- und Spaltentyps an Hoststeuerelemente als diejenigen, die von der integrierten Spaltentypen bereitgestellten implementieren. Weitere Informationen finden Sie unter [wie: Hosten-Steuerelementen in Windows Forms-DataGridView-Zellen](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Übersicht über das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
