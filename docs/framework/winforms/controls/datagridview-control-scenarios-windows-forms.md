---
title: Szenarien für das DataGridView-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 882b210a19f1ec5515bd7f37ccc55343f84767bc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721307"
---
# <a name="datagridview-control-scenarios-windows-forms"></a>Szenarien für das DataGridView-Steuerelement (Windows Forms)
Mit der <xref:System.Windows.Forms.DataGridView> -Steuerelement, können Sie Tabellendaten aus einer Vielzahl von Datenquellen anzeigen. Sie können manuell auffüllen, für die einfache verwendet, eine <xref:System.Windows.Forms.DataGridView> und die Daten direkt über das Steuerelement bearbeiten. In der Regel jedoch werden Ihre Daten in einer externen Datenquelle zu speichern und Binden des Steuerelements mit einem <xref:System.Windows.Forms.BindingSource> Komponente.  
  
 Dieses Thema beschreibt einige häufige Szenarien, bei denen die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>Szenario 1: Anzeige kleiner Mengen von Daten  
 Sie müssen keine Speichern von Daten in einer externen Datenquelle angezeigt, in der <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn Sie mit einer geringeren Menge an Daten arbeiten, können Sie füllen Sie das Steuerelement selbst und die Daten über das Steuerelement bearbeiten. Dies wird als bezeichnet *ungebundenen Modus*. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines ungebundenen Windows Forms-DataGridView-Steuerelements](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario die wichtigsten Punkte  
  
-   Ungebunden-Modus füllen Sie das Steuerelement manuell.  
  
-   Ungebunden-Modus eignet sich besonders für kleine Mengen von schreibgeschützten Daten.  
  
-   Ungebunden-Modus ist auch für Tabellen-ähnliche oder platzsparend gefüllten Tabellen geeignet.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>Szenario 2: Anzeigen und Aktualisieren von Daten in einer externen Datenquelle  
 Sie können die <xref:System.Windows.Forms.DataGridView> als Benutzeroberfläche (UI) zu steuern, über welche Benutzer die Daten, die in einer Datenquelle, z. B. eine Datenbanktabelle oder eine Auflistung von Geschäftsobjekten zugreifen können. Weitere Informationen finden Sie unter [Vorgehensweise: Binden von Daten an die Windows Forms-DataGridView-Steuerelement](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario die wichtigsten Punkte  
  
-   Gebundene Modus können Sie die Verbindung mit einer Datenquelle, Spalten, die anhand der Eigenschaften der Datenquelle oder die Spalten der Datenbank automatisch zu generieren und füllen Sie das Steuerelement automatisch.  
  
-   Gebundene Modus eignet sich für intensive Benutzerinteraktion mit Daten. Daten können für die Anzeige formatiert werden, und die benutzerdefinierten Daten analysiert werden können, in dem von der Datenquelle erwarteten Format. Formatieren von Fehlern und Einschränkung Datenbankfehler Dateneingabe kann erkannt werden, damit Benutzer gewarnt werden können und fehlerhafte Zellen korrigiert werden können.  
  
-   Zusätzliche Funktionen, z. B. die spaltensortierung, Einfrieren und Neuanordnen von ermöglichen Benutzern, Daten in die Möglichkeit, die am einfachsten für ihren Workflow anzuzeigen.  
  
-   Unterstützung der Zwischenablage kann Benutzer Daten aus Ihrer Anwendung in andere Anwendungen zu kopieren.  
  
## <a name="scenario-3-advanced-data"></a>Szenario 3: Erweiterte Daten  
 Wenn Sie besondere Anforderungen, die das standard-Datenbindungsmodell verwendet nicht beheben lässt verfügen, können Sie die Interaktion zwischen dem Steuerelement und Ihre Daten verwalten, durch die Implementierung *des virtuellen Modus*. Implementieren des virtuellen Modus bedeutet, dass eine oder mehrere Ereignishandler, mit die die Steuerelement Anforderungsinformationen zu Zellen, wie die Informationen können implementiert ist erforderlich.  
  
 Z. B. Wenn Sie mit großen Datenmengen arbeiten, sollten Sie zum Implementieren des virtuellen Modus befindet, um sicherzustellen, dass eine optimale Effizienz. Virtueller Modus eignet sich auch für die Verwaltung der Werte von ungebundenen Spalten, die angezeigt werden zusammen mit einer Spalte aus einer anderen Datenquelle abgerufen.  
  
 Weitere Informationen zu virtuellen Modus befindet, finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](implementing-virtual-mode-wf-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario die wichtigsten Punkte  
  
-   Virtueller Modus eignet sich für große Mengen an Daten anzeigen, wenn Sie die Leistung optimieren möchten.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>Szenario 4: Automatische Größenänderung von Zeilen und Spalten  
 Wenn Sie Daten, die regelmäßig aktualisiert wird anzeigen, können Sie automatisch ändern, Zeilen und Spalten, um sicherzustellen, dass der gesamte Inhalt sichtbar ist. Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet mehrere Optionen, mit denen Sie aktivieren oder deaktivieren manuell zu skalieren, zu bestimmten Zeitpunkten Programmgesteuertes Ändern der Größe, oder Ändern der Größe automatisch jedes Mal, wenn der Inhalt ändert. Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario die wichtigsten Punkte  
  
-   Manuelles Ändern der Größe ermöglicht Benutzern, die Zelle Höhen und Breiten anpassen.  
  
-   Automatische Größenänderung, können Sie Zellengrößen unterhalten, Zellinhalt nie abgeschnitten wird.  
  
-   Programmgesteuerten größenanpassung, können Sie passen Sie Zellen zu bestimmten Zeitpunkten, die Leistungseinbußen durch kontinuierliche automatische Größenänderung zu vermeiden.  
  
## <a name="scenario-5-simple-customization"></a>Szenario 5: Einfache Anpassung  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet viele Möglichkeiten, die grundlegende Darstellung und Verhalten zu ändern. Weitere Informationen finden Sie unter [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### <a name="scenario-key-points"></a>Szenario die wichtigsten Punkte  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte können Sie die Farbe, Schriftart, Formatierung und Positionierung von Informationen auf mehreren Ebenen und für die einzelnen Elemente des Steuerelements angeben.  
  
-   Zellstile können schichtweise strukturiert und von mehreren Elementen, sodass Sie die Wiederverwendung von Code gemeinsam verwendet werden.  
  
## <a name="scenario-6-advanced-customization"></a>Szenario 6: Erweiterte Anpassung  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet viele Möglichkeiten, dessen Darstellung und Verhalten anpassen.  
  
### <a name="scenario-key-points"></a>Szenario die wichtigsten Punkte  
  
-   Sie können Ihren eigenen Code zum Zeichnen von Zelle bereitstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md).  
  
-   Sie können eine eigene Zeile zeichnen bereitstellen. Dies ist beispielsweise nützlich, um Zeilen mit Inhalt zu erstellen, die mehrere Spalten umfasst. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen die Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms](customize-the-appearance-of-rows-in-the-datagrid.md).  
  
-   Sie können Ihre eigenen Klassen Zellen- und Spaltentyps zum Anpassen der zellendarstellung implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Zellen und Spalten in der Windows Forms-DataGridView-Steuerelement durch Erweitern Aussehens und Verhaltens](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
-   Sie können Ihre eigenen Klassen Zellen- und Spaltentyps zum Hosten von Steuerelementen als den angebotenen, die von den integrierten Typen implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Hosten von Steuerelementen in Windows Forms DataGridView-Zellen](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- [Übersicht über das DataGridView-Steuerelement](datagridview-control-overview-windows-forms.md)
