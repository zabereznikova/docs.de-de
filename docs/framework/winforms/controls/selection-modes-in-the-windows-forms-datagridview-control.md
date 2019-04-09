---
title: Auswahlmodi im DataGridView-Steuerelement von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: 79e13e65938252015e43b59a962d40f20963a5df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097277"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Auswahlmodi im DataGridView-Steuerelement von Windows Forms
Manchmal möchten Sie Ihre Anwendung für Aktionen basierend auf der Auswahl des Benutzers innerhalb einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Je nach den Aktionen empfiehlt es sich um die Arten der Auswahl zu beschränken, die möglich sind. Nehmen wir beispielsweise an, dass Ihre Anwendung für den aktuell ausgewählten Datensatz einen Bericht drucken kann. In diesem Fall sollten Sie so konfigurieren Sie die <xref:System.Windows.Forms.DataGridView> Steuerelement, damit an einer beliebigen Stelle innerhalb einer Zeile immer auf die gesamte Zeile ausgewählt, und so, dass nur eine Zeile zu einem Zeitpunkt ausgewählt werden kann.  
  
 Sie können angeben, die durch Festlegen von zulässigen Auswahlen der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> -Eigenschaft auf einen der folgenden <xref:System.Windows.Forms.DataGridViewSelectionMode> -Enumerationswerte fest.  
  
|DataGridViewSelectionMode-Wert|Beschreibung|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Klicken Sie auf eine Zelle wird ausgewählt. Zeilen- und Spaltenüberschriften können nicht für die Auswahl verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Klicken Sie auf eine Zelle wird ausgewählt. Klicken Sie auf eine Spaltenüberschrift, wählt die gesamte Spalte. Spaltenüberschriften können nicht für die Sortierung verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Klicken Sie auf eine Zelle oder einen Spaltenheader, wählt die gesamte Spalte. Spaltenüberschriften können nicht für die Sortierung verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Klicken Sie auf eine Zelle oder einen Zeilenheader wird die gesamte Zeile ausgewählt.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Auswahl-Standardmodus. Klicken Sie auf eine Zelle wird ausgewählt. Klicken Sie auf einen Zeilenheader wird die gesamte Zeile ausgewählt.|  
  
> [!NOTE]
>  Ändern den Auswahlmodus zur Laufzeit automatisch löscht die aktuelle Auswahl.  
  
 Standardmäßig können Benutzer auswählen mehrerer Zeilen, Spalten oder Zellen durch Ziehen mit der Maus durch Drücken von STRG-Taste oder UMSCHALTTASTE beim Erweitern oder ändern eine Auswahl auswählen, oder klicken Sie auf der linken oberen Headerzelle um alle Zellen im Steuerelement zu markieren. Um dieses Verhalten zu verhindern, legen die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> Eigenschaft `false`.  
  
 Die <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> und <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> Modi können Benutzer Zeilen löschen, indem Sie sie auswählen, und drücken die ENTF-Taste. Benutzer können die Zeilen löschen, nur, wenn die aktuelle Zelle sich nicht im Bearbeitungsmodus befindet, ist die <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> -Eigenschaftensatz auf `true`, und die zugrunde liegenden Datenquelle unterstützt benutzergesteuerte Zeile löschen. Beachten Sie, dass diese Einstellungen nicht programmgesteuerte Zeile löschen verhindern.  
  
## <a name="programmatic-selection"></a>Programmgesteuerte Auswahl  
 Der aktuellen Auswahlmodus schränkt das Verhalten der programmgesteuerte Auswahl als auch der Benutzerauswahl. Sie können die aktuelle Auswahl programmgesteuert ändern, durch Festlegen der `Selected` Eigenschaft alle Zellen, Zeilen oder Spalten in der <xref:System.Windows.Forms.DataGridView> Steuerelement. Sie können auch alle Zellen im Steuerelement durch Auswählen der <xref:System.Windows.Forms.DataGridView.SelectAll%2A> -Methode, entsprechend dem Auswahlmodus. Verwenden Sie zum Aufheben der Auswahl der <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> Methode.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaftensatz auf `true`, hinzufügbaren <xref:System.Windows.Forms.DataGridView> Elemente, oder entfernen Sie sie aus der Auswahl durch Ändern der `Selected` -Eigenschaft des Elements. Andernfalls werden beim Festlegen der `Selected` Eigenschaft `true` für ein Element automatisch auf andere Elemente aus der Auswahl entfernt.  
  
 Beachten Sie, dass den Wert der Änderungen der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft ändert sich nicht auf die aktuelle Auswahl.  
  
 Sie können eine Auflistung von der aktuell ausgewählten Zellen, Zeilen oder Spalten durch Abrufen der <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> Eigenschaften der <xref:System.Windows.Forms.DataGridView> Steuerelement. Zugriff auf diese Eigenschaften ist ineffizient, wenn jede Zelle im Steuerelement ausgewählt ist. Um in diesem Fall eine Leistungseinbuße zu vermeiden, verwenden die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode zuerst. Darüber hinaus können den Zugriff auf diese Auflistungen zum Ermitteln der Anzahl der ausgewählten Zellen, Zeilen oder Spalten ineffizient sein. Sie sollten stattdessen die <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, oder <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> Methode und übergeben die <xref:System.Windows.Forms.DataGridViewElementStates.Selected> Wert.  
  
> [!TIP]
>  Beispielcode, der die programmgesteuerte Verwendung der ausgewählten Zellen wird veranschaulicht, finden Sie in der <xref:System.Windows.Forms.DataGridView> Übersicht über die Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen des Auswahlmodus des DataGridView-Steuerelements in Windows Forms](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
