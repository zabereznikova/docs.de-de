---
title: Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28cb1b02e67d076f9190e2d8e36b72c20cc5c4e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement
In diesem Thema wird beschrieben, wie Benutzer mit interagieren können die <xref:System.Windows.Controls.DataGrid> -Steuerelement mithilfe der Tastatur und Maus.  
  
 Typische Interaktionen mit der <xref:System.Windows.Controls.DataGrid> gehören Navigation, Auswahl und bearbeiten. Das Verhalten der Funktionsauswahl hat Auswirkungen auf die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> Eigenschaften. Sind die Standardwerte, die in diesem Thema beschriebene Verhalten verursachen <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> und <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType>. Das Ändern dieser Werte möglicherweise Verhalten, das sich aus, die beschrieben. Wenn eine Zelle im Bearbeitungsmodus befindet, Bearbeitungssteuerelements möglicherweise außer Kraft setzen die Standardtastaturverhalten von der <xref:System.Windows.Controls.DataGrid>.  
  
## <a name="default-keyboard-behavior"></a>Standardverhalten der Tastatur  
 Die folgende Tabelle enthält die Tastatur-Standardverhalten für die <xref:System.Windows.Controls.DataGrid>.  
  
|Schlüssel oder eine Tastenkombination|Beschreibung|  
|----------------------------|-----------------|  
|NACH-UNTEN-TASTE|Verschiebt den Fokus auf die Zelle direkt unterhalb der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, wird die Drücken der nach-unten-Taste keine Aktion ausgeführt.|  
|NACH-OBEN-TASTE|Verschiebt den Fokus auf die Zelle direkt über der aktuellen Zelle. Wenn der Fokus in der ersten Zeile befindet, wird durch Drücken der nach-oben keine Aktion ausgeführt.|  
|NACH-LINKS|Verschiebt den Fokus auf die vorherige Zelle in der Zeile an. Wenn der Fokus in der ersten Zelle in der Zeile befindet, wird der links-Taste keine Aktion ausgeführt.|  
|NACH-RECHTS|Verschiebt den Fokus zur nächsten Zelle in der Zeile an. Wenn der Fokus in der letzten Zelle der Zeile befindet, wird durch Drücken der nach-rechts-keine Aktion ausgeführt.|  
|START|Verschiebt den Fokus zur ersten Zelle in der aktuellen Zeile.|  
|ENDE|Verschiebt den Fokus zur letzten Zelle in der aktuellen Zeile.|  
|BILD-AB|Wenn Zeilen nicht gruppiert werden, ermöglicht das Scrollen des Steuerelements nach unten durch die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf die letzte vollständig angezeigte Zeile ohne Spalten zu ändern.<br /><br /> Wenn Zeilen gruppiert werden, verschiebt den Fokus auf die letzte Zeile in der <xref:System.Windows.Controls.DataGrid> ohne Spalten zu ändern.|  
|BILD-AUF|Wenn Zeilen nicht gruppiert werden, verschiebt das Steuerelement nach oben durch die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf den ersten angezeigten Zeilen ohne Spalten zu ändern.<br /><br /> Wenn Zeilen gruppiert werden, verschiebt den Fokus auf die erste Zeile in der <xref:System.Windows.Controls.DataGrid> ohne Spalten zu ändern.|  
|TAB|Verschiebt den Fokus zur nächsten Zelle in der aktuellen Zeile. Wenn der Fokus in der letzten Zelle der Zeile ist, verschiebt den Fokus zur ersten Zelle in der nächsten Zeile. Wenn der Fokus in der letzten Zelle im Steuerelement ist, verschiebt den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Ist die aktuelle Zelle im Bearbeitungsmodus befindet, und drücken die Registerkarte Ursachen den Fokus auf den von der aktuellen Zeile verschieben, alle Änderungen, die auf die Zeile vorgenommen wurden werden ausgeführt vor der Fokus geändert wird.|  
|UMSCHALT+TAB|Verschiebt den Fokus auf die vorherige Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der ersten Zelle der Zeile ist, geht bis zur letzten Zelle in der vorherigen Zeile. Wenn der Fokus in der ersten Zelle im Steuerelement ist, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Ist die aktuelle Zelle im Bearbeitungsmodus befindet, und drücken die Registerkarte Ursachen den Fokus auf den von der aktuellen Zeile verschieben, alle Änderungen, die auf die Zeile vorgenommen wurden werden ausgeführt vor der Fokus geändert wird.|  
|STRG+NACH-UNTEN|Verschiebt den Fokus zur letzten Zelle in der aktuellen Spalte.|  
|STRG+NACH-OBEN|Verschiebt den Fokus zur ersten Zelle in der aktuellen Spalte.|  
|STRG+NACH-RECHTS|Verschiebt den Fokus zur letzten Zelle in der aktuellen Zeile.|  
|STRG+NACH-LINKS|Verschiebt den Fokus zur ersten Zelle in der aktuellen Zeile.|  
|STRG + POS1|Verschiebt den Fokus zur ersten Zelle im Steuerelement.|  
|STRG + ENDE|Verschiebt den Fokus zur letzten Zelle im Steuerelement.|  
|STRG+BILD-AB|Identisch mit Bild-ab.|  
|STRG+BILD-AUF|Identisch mit Bild-auf.|  
|F2|Wenn die <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> Eigenschaft ist `false` und <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> Eigenschaft ist `false` versetzt Sie die aktuelle Zelle in den Bearbeitungsmodus für die Zelle, für die aktuelle Spalte.|  
|EINGABETASTE|Führt einen Commit für Änderungen an der aktiven Zelle und die Zeile, und verschiebt den Fokus auf die Zelle direkt unterhalb der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, führt einen Commit für Änderungen ohne den Fokus zu verschieben.|  
|ESC|Wenn das Steuerelement im Bearbeitungsmodus befindet, die Bearbeitung abgebrochen, und die im Steuerelement vorgenommenen Änderungen wurden zurückgesetzt. Falls die zugrunde liegenden implementiert Datenquelle <xref:System.ComponentModel.IEditableObject>, ein zweites Mal Drücken von ESC bricht Bearbeitungsmodus für die gesamte Zeile ab.|  
|RÜCKTASTE|Löscht das Zeichen vor dem Cursor, beim Bearbeiten einer Zelle.|  
|DELETE|Löscht das Zeichen nach des Cursors an, beim Bearbeiten einer Zelle.|  
|STRG+EINGABE|Führt einen Commit für Änderungen an der aktuellen Zelle ohne den Fokus zu verschieben.|  
|STRG+A|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, wählt alle Zeilen in der <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="selection-keys"></a>Auswahl-Schlüssel  
 Wenn die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, das Verhalten ändert sich nicht, aber bei gedrückter Umschalttaste (einschließlich STRG + UMSCHALT) über die Tastatur navigiert wird die Auswahl mehrerer Zeile ändern. Vor der Navigation markiert das Steuerelement die aktuelle Zeile als eine Ankerzeile. Wenn Sie bei gedrückter Umschalttaste navigieren, umfasst die Auswahl aller Zeilen zwischen dem Anker und der aktuellen Zeile.  
  
 Die folgenden Tastenkombinationen mehrzeilige Auswahl zu ändern.  
  
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
  
|Mausaktionen|Beschreibung|  
|------------------|-----------------|  
|Klicken Sie auf eine nicht ausgewählte Zeile|Macht die geklickt wurde Zeile an, die aktuelle Zeile und die angeklickte Zelle der aktuellen Zelle.|  
|Klicken Sie auf der aktuellen Zelle|Versetzt die aktuelle Zelle in den Bearbeitungsmodus.|  
|Ziehen Sie eine Spaltenheaderzelle|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> Eigenschaft ist `true` und <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> Eigenschaft ist `true` für die aktuelle Spalte verschiebt die Spalte, damit sie eine neue Position abgelegt werden kann.|  
|Ziehen Sie ein Spaltentrennzeichen-header|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> Eigenschaft `true` und <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> Eigenschaft ist `true` für die aktuelle Spalte ändert die Größe der Spalte.|  
|Doppelklicken Sie auf einen Header Spaltentrennzeichen|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> Eigenschaft ist `true` und die <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> Eigenschaft ist `true` für die aktuelle Spalte automatisch Größen der Spalte unter Verwendung der <xref:System.Windows.Controls.DataGridLength.Auto%2A> Größenanpassungsmodus.|  
|Klicken Sie auf eine Spaltenheaderzelle|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> Eigenschaft `true` und <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> Eigenschaft ist `true` für die aktuelle Spalte die Spalte sortiert.<br /><br /> Durch das Klicken auf eine Spalte, die bereits sortiert sind, wird die Sortierreihenfolge der Spalte umgekehrt.<br /><br /> Drücken die UMSCHALTTASTE gedrückt, während auf die Spaltenüberschriften sortieren nach mehreren Spalten in der Reihenfolge geklickt wird.|  
|STRG + Klicken Sie auf eine Zeile|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, nicht zusammenhängende Auswahl mehrerer Zeile ändert.<br /><br /> Wenn die Zeile bereits ausgewählt ist, hebt die Auswahl der zeilenupdates.|  
|UMSCHALT + Klicken Sie auf eine Zeile|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, eine zusammenhängende Auswahl von mehreren Zeile bestehenden ändert.|  
|Klicken Sie auf einer Zeilengruppen-Kopfzeile|Erweitert oder reduziert die Gruppe.|  
|Klicken Sie auf die Schaltfläche "Alle auswählen" in der oberen linken Ecke des der<xref:System.Windows.Controls.DataGrid>|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, wählt alle Zeilen in der <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="mouse-selection"></a>Mausauswahl  
 Wenn die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, auf eine Zeile beim Drücken der STRG-Taste oder UMSCHALTTASTE Auswahl mehrerer Zeile ändern.  
  
 Wenn Sie eine Zeile klicken, während Sie die STRG-Taste drücken, ändert sich der Auswahlzustand die Zeile, während alle anderen Zeilen den aktuellen Auswahlzustand beibehalten. Führen Sie diese Option, um nicht benachbarte Zeilen auszuwählen.  
  
 Wenn Sie bei gedrückter Umschalttaste auf eine Zeile klicken, umfasst die Auswahl zwischen der aktuellen Zeile und einen Anker befindet sich an der Position der aktuellen Zeile vor der auf alle Zeilen aus. Nachfolgende Klicken bei gedrückter Umschalttaste Ändern der aktuellen Zeile, aber nicht in der Ankerzeile. Führen Sie diese Option, um einen Bereich aufeinander folgender Zeilen auszuwählen.  
  
 STRG + UMSCHALT können kombiniert werden, um nicht benachbarte Bereiche von benachbarten Zeilen auszuwählen. Zu diesem Zweck wählen Sie den ersten Bereich, indem Sie mithilfe der Umschalttaste aus, und klicken Sie, wie zuvor beschrieben. Nach der erste Bereich von Zeilen ausgewählt wird, verwenden Sie STRG + Klicken Sie auf, um die erste Zeile in den nächsten Bereich auszuwählen, und klicken Sie dann auf die letzte Zeile in den nächsten Bereich beim Drücken von STRG + UMSCHALT.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
