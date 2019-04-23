---
title: Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
ms.openlocfilehash: 6be464ce85bd3ba91dd6e6cc810ec7d04edc0c3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083321"
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement
In diesem Thema wird beschrieben, wie Benutzer interagieren können, mit der <xref:System.Windows.Controls.DataGrid> -Steuerelement unter Verwendung der Tastatur und Maus.  
  
 Typische Interaktionen mit der <xref:System.Windows.Controls.DataGrid> enthalten, Navigation, Auswahl und bearbeiten. Verhalten der Funktionsauswahl wird von beeinflusst die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> Eigenschaften. Die Standardwerte, die dazu führen, das beschriebene Verhalten in diesem Thema dass sind <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> und <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType>. Das Ändern dieser Werte kann zu Verhalten führen, die sich beschrieben. Wenn eine Zelle im Bearbeitungsmodus befindet, das Steuerelement zur Textbearbeitung möglicherweise außer Kraft gesetzt die Standardtastaturverhalten der <xref:System.Windows.Controls.DataGrid>.  
  
## <a name="default-keyboard-behavior"></a>Standardmäßige Tastaturverhalten  
 Die folgende Tabelle enthält das standardmäßige Tastaturverhalten für die <xref:System.Windows.Controls.DataGrid>.  
  
|Taste oder Tastenkombination|Beschreibung|  
|----------------------------|-----------------|  
|NACH-UNTEN-TASTE|Verschiebt den Fokus auf die Zelle direkt unter der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, wird durch Drücken der nach-unten "nothing".|  
|NACH-OBEN-TASTE|Verschiebt den Fokus auf die Zelle direkt über der aktuellen Zelle. Wenn der Fokus in der ersten Zeile befindet, wird durch Drücken der nach-oben "nothing".|  
|NACH-LINKS|Verschiebt den Fokus auf die vorherige Zelle in der Zeile an. Wenn der Fokus in der ersten Zelle in der Zeile befindet, wird durch Drücken der nach-links "nothing".|  
|NACH-RECHTS|Verschiebt den Fokus auf die nächste Zelle in der Zeile an. Wenn der Fokus in der letzten Zelle in der Zeile befindet, nichts mit der rechten Taste.|  
|START|Verschiebt den Fokus auf die erste Zelle in der aktuellen Zeile.|  
|ENDE|Verschiebt den Fokus auf die letzte Zelle in der aktuellen Zeile.|  
|BILD-AB|Wenn keine Zeilen gruppiert werden, führt einen Bildlauf des Steuerelements nach unten, um die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf die letzte vollständig angezeigte Zeile ohne Spalten zu ändern.<br /><br /> Wenn Zeilen gruppiert werden, verschiebt den Fokus auf die letzte Zeile in der <xref:System.Windows.Controls.DataGrid> ohne Spalten zu ändern.|  
|BILD-AUF|Wenn keine Zeilen gruppiert werden, verschiebt das Steuerelement nach oben durch die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf die erste angezeigte Zeile ohne Spalten zu ändern.<br /><br /> Wenn Zeilen gruppiert werden, verschiebt den Fokus auf die erste Zeile in der <xref:System.Windows.Controls.DataGrid> ohne Spalten zu ändern.|  
|TAB|Verschiebt den Fokus auf die nächste Zelle in der aktuellen Zeile. Wenn der Fokus in der letzten Zelle der Zeile befindet, geht auf die erste Zelle in der nächsten Zeile. Wenn der Fokus in der letzten Zelle im Steuerelement ist, geht zum nächsten Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Ist die aktuelle Zelle im Bearbeitungsmodus befindet, und drücken die Registerkarte Ursachen Fokus weg von der aktuellen Zeile verschoben, alle Änderungen, die auf die Zeile vorgenommen wurden, sind ein Commit ausgeführt vor der Fokus geändert wird.|  
|UMSCHALT+TAB|Verschiebt den Fokus auf die vorherige Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der ersten Zelle der Zeile ist, geht bis zur letzten Zelle in der vorherigen Zeile. Wenn der Fokus in der ersten Zelle im Steuerelement ist, verschiebt den Fokus, um das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Ist die aktuelle Zelle im Bearbeitungsmodus befindet, und drücken die Registerkarte Ursachen Fokus weg von der aktuellen Zeile verschoben, alle Änderungen, die auf die Zeile vorgenommen wurden, sind ein Commit ausgeführt vor der Fokus geändert wird.|  
|STRG+NACH-UNTEN|Verschiebt den Fokus auf die letzte Zelle in der aktuellen Spalte.|  
|STRG+NACH-OBEN|Verschiebt den Fokus auf die erste Zelle in der aktuellen Spalte.|  
|STRG+NACH-RECHTS|Verschiebt den Fokus auf die letzte Zelle in der aktuellen Zeile.|  
|STRG+NACH-LINKS|Verschiebt den Fokus auf die erste Zelle in der aktuellen Zeile.|  
|STRG + POS1|Verschiebt den Fokus zur ersten Zelle im Steuerelement.|  
|STRG + ENDE|Verschiebt den Fokus zur letzten Zelle im Steuerelement.|  
|STRG+BILD-AB|Identisch mit Bild-ab.|  
|STRG+BILD-AUF|Identisch mit Bild-auf.|  
|F2|Wenn die <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> -Eigenschaft ist `false` und <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> Eigenschaft `false` für die aktuelle Spalte wird für die aktuelle Zelle in den Bearbeitungsmodus für die Zelle.|  
|EINGABETASTE|Übernimmt alle Änderungen an der aktuellen Zelle und die Zeile, und verschiebt den Fokus auf die Zelle direkt unter der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, übernimmt alle Änderungen, ohne den Fokus zu verschieben.|  
|ESC|Wenn das Steuerelement im Bearbeitungsmodus befindet, bricht den Bearbeitungsvorgang ab und setzt alle Änderungen, die im Steuerelement vorgenommen wurden. Wenn die zugrunde liegende implementiert Datenquelle <xref:System.ComponentModel.IEditableObject>, Drücken von ESC ein zweites Mal Bearbeitungsmodus für die gesamte Zeile abgebrochen.|  
|RÜCKTASTE|Löscht das Zeichen vor dem Cursor, wenn eine Zelle zu bearbeiten.|  
|DELETE|Löscht das Zeichen nach dem Cursor, beim Bearbeiten einer Zelle.|  
|STRG+EINGABE|Führt einen Commit für Änderungen an der aktuellen Zelle ohne den Fokus zu verschieben.|  
|STRG+A|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, wählt alle Zeilen in der <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="selection-keys"></a>Auswahl-Schlüssel  
 Wenn die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, das Navigationsverhalten nicht geändert, doch bei gedrückter Umschalttaste (einschließlich STRG + UMSCHALT) über die Tastatur navigiert, wird eine mehrzeilige Auswahl ändern. Vor Beginn der Navigation, markiert das Steuerelement die aktuelle Zeile als Ankerzeile. Wenn Sie sich bei gedrückter Umschalttaste navigieren, finden Sie die Auswahl aller Zeilen zwischen dem Anker und die aktuelle Zeile.  
  
 Die folgenden Tastenkombinationen ändern Sie mehrzeilige Auswahl.  
  
-   UMSCHALT+NACH-UNTEN  
  
-   UMSCHALT+NACH-OBEN  
  
-   UMSCHALT+BILD-AB  
  
-   UMSCHALT+BILD-AUF  
  
-   STRG+UMSCHALT+NACH-UNTEN  
  
-   STRG+UMSCHALT+NACH-OBEN  
  
-   STRG + UMSCHALT + POS1  
  
-   STRG + UMSCHALT + ENDE  
  
## <a name="default-mouse-behavior"></a>Standardverhalten für Maus  
 Die folgende Tabelle enthält die Maus-Standardverhalten für die <xref:System.Windows.Controls.DataGrid>.  
  
|Mausaktion|Beschreibung|  
|------------------|-----------------|  
|Klicken Sie auf eine nicht ausgewählte Zeile|Ist das der aktuellen Zeile und die angeklickte Zelle die aktuelle Zelle der Zeile, auf die geklickt wurde.|  
|Klicken Sie auf der aktuellen Zelle|Legt die aktuelle Zelle in den Bearbeitungsmodus.|  
|Ziehen Sie eine Spaltenheaderzelle|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> -Eigenschaft ist `true` und <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> Eigenschaft `true` verschiebt Sie für die aktuelle Spalte, die Spalte, damit sie auf eine neue Position abgelegt werden kann.|  
|Ziehen Sie ein Spaltentrennzeichen für die header|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> -Eigenschaft ist `true` und <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> Eigenschaft `true` für die aktuelle Spalte, die Größe der Spalte ändert.|  
|Doppelklicken Sie auf Header Spaltentrennzeichen|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> Eigenschaft `true` und die <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> -Eigenschaft ist `true` für die aktuelle Spalte, die automatische die Spalte mit der <xref:System.Windows.Controls.DataGridLength.Auto%2A> Größenänderungsmodus.|  
|Klicken Sie auf eine Spaltenheaderzelle|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> Eigenschaft `true` und die <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> Eigenschaft `true` für die aktuelle Spalte, die Spalte sortiert.<br /><br /> Durch das Klicken auf eine Spalte, die bereits sortiert ist, wird die Sortierreihenfolge der Spalte umgekehrt.<br /><br /> Drücken die UMSCHALTTASTE gedrückt, während Sie auf die Spaltenüberschriften nach mehreren Spalten in der Reihenfolge geklickt sortiert.|  
|STRG + Klicken Sie auf eine Zeile|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, nicht zusammenhängende Auswahl mehrerer Zeile ändert.<br /><br /> Wenn die Zeile bereits ausgewählt ist, hebt die Auswahl der zeilenupdates.|  
|UMSCHALT + Klicken Sie auf eine Zeile|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, zusammenhängende Auswahl mehrerer Zeile ändert.|  
|Klicken Sie auf einer Zeilengruppen-Kopfzeile|Erweitert oder reduziert die Gruppe.|  
|Klicken Sie auf die Schaltfläche "Alle auswählen" auf der oberen linken Ecke des der <xref:System.Windows.Controls.DataGrid>|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, wählt alle Zeilen in der <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="mouse-selection"></a>Mausaus  
 Wenn die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, auf eine Zeile beim Drücken von STRG oder UMSCHALT Auswahl mehrerer Zeile ändern.  
  
 Wenn Sie eine Zeile klicken, während Sie die STRG-Taste drücken, ändert sich den Auswahlzustand die Zeile, während alle anderen Zeilen den aktuellen Auswahlzustand beibehalten. Führen Sie diese Option, um nicht benachbarte Zeilen auszuwählen.  
  
 Wenn Sie bei gedrückter Umschalttaste auf eine Zeile klicken, umfasst die Auswahl aller Zeilen zwischen der aktuellen Zeile und einer Ankerzeile befindet sich an der Position der aktuellen Zeile vor dem klicken. Nachfolgende Klicken bei gedrückter Umschalttaste Ändern der aktuellen Zeile, jedoch nicht der Ankerzeile. Führen Sie diese Option, um einen Bereich von angrenzenden Zeilen auszuwählen.  
  
 STRG + UMSCHALT können kombiniert werden, um nicht benachbarte Bereiche von angrenzenden Zeilen auszuwählen. Zu diesem Zweck wählen Sie den ersten Bereich, indem Sie mithilfe der UMSCHALTTASTE, und klicken Sie auf wie zuvor beschrieben. Nachdem der erste Bereich von Zeilen ausgewählt wird, verwenden Sie STRG + Klicken Sie auf, um die erste Zeile in den nächsten Bereich auszuwählen, und klicken Sie dann auf die letzte Zeile in den nächsten Bereich bei gedrückter STRG + UMSCHALT.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
