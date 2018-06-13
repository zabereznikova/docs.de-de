---
title: Auswahlmodi im DataGridView-Steuerelement von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: 43f3648a9c7d64fb4fb900c7df3f01bc18d729b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539571"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Auswahlmodi im DataGridView-Steuerelement von Windows Forms
In einigen Fällen soll Ihre Anwendung für Aktionen, die basierend auf der Auswahl des Benutzers innerhalb einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Abhängig von der Aktionen empfiehlt es sich um die Arten der Auswahl zu beschränken, die möglich sind. Nehmen Sie beispielsweise an, dass Ihre Anwendung für den aktuell ausgewählten Datensatz einen Bericht drucken kann. In diesem Fall sollten Sie so konfigurieren Sie die <xref:System.Windows.Forms.DataGridView> Steuerelement, damit an einer beliebigen Stelle innerhalb einer Zeile immer auf die gesamte Zeile ausgewählt, und so, dass nur eine Zeile zu einem Zeitpunkt ausgewählt werden kann.  
  
 Sie können angeben, dass die Auswahl zulässig durch Festlegen der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> -Eigenschaft auf einen der folgenden <xref:System.Windows.Forms.DataGridViewSelectionMode> Enumerationswerte.  
  
|DataGridViewSelectionMode-Wert|Beschreibung|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Klicken auf eine Zelle ausgewählt. Zeilen- und Spaltenköpfe können nicht für die Auswahl verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Klicken auf eine Zelle ausgewählt. Klicken auf eine Spaltenüberschrift, wählt die gesamte Spalte aus. Spaltenüberschriften können nicht für die Sortierung verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Klicken Sie auf eine Zelle oder eine Spaltenüberschrift, wählt die gesamte Spalte aus. Spaltenüberschriften können nicht für die Sortierung verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Klicken Sie auf eine Zelle oder einen Zeilenheader wird die gesamte Zeile ausgewählt.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Standardmäßig den Mehrfachauswahlmodus aufweist. Klicken auf eine Zelle ausgewählt. Auf einen Zeilenkopf klicken, wird die gesamte Zeile ausgewählt.|  
  
> [!NOTE]
>  Ändern den Auswahlmodus zur Laufzeit automatisch löscht die aktuelle Auswahl.  
  
 Standardmäßig können Benutzer auswählen mehrere Zeilen, Spalten oder Zellen durch Ziehen mit der Maus, drücken STRG-Taste oder UMSCHALTTASTE beim Erweitern oder ändern eine Auswahl auswählen, oder klicken Sie auf der linken oberen Headerzelle um alle Zellen im Steuerelement auszuwählen. Um dieses Verhalten zu verhindern, legen die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> Eigenschaft `false`.  
  
 Die <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> und <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> Modi ermöglichen Benutzern die Zeilen zu löschen, indem Sie sie auswählen und die ENTF-Taste drücken. Benutzer können Zeilen löschen, nur, wenn die aktuelle Zelle nicht in den Bearbeitungsmodus wechseln, ist die <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> -Eigenschaftensatz auf `true`, und die zugrunde liegenden Datenquelle unterstützt anwendergesteuerte Zeile löschen. Beachten Sie, dass diese Einstellungen nicht programmgesteuerte Zeile löschen verhindern.  
  
## <a name="programmatic-selection"></a>Programmgesteuerte Auswahl  
 Der aktuelle Auswahlmodus schränkt das Verhalten der programmgesteuerte Auswahl sowie die Auswahl des Benutzers. Sie können die aktuelle Auswahl programmgesteuert ändern, indem Sie festlegen der `Selected` Eigenschaft alle Zellen, Zeilen oder Spalten in der <xref:System.Windows.Forms.DataGridView> Steuerelement. Sie können auch alle Zellen im Steuerelement durch Auswählen der <xref:System.Windows.Forms.DataGridView.SelectAll%2A> -Methode, je nach Auswahlmodus. Verwenden Sie zum Aufheben der Auswahl der <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> Methode.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaftensatz auf `true`, können Sie hinzufügen <xref:System.Windows.Forms.DataGridView> Elemente, oder entfernen Sie sie aus der Auswahl durch Ändern der `Selected` -Eigenschaft des Elements. Andernfalls werden beim Festlegen der `Selected` Eigenschaft `true` für ein Element automatisch auf andere Elemente aus der Auswahl entfernt.  
  
 Beachten Sie, dass den Wert der Änderungen der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft wird die aktuelle Auswahl nicht verändert.  
  
 Sie können eine Auflistung von der gerade ausgewählten Zellen, Zeilen oder Spalten durch Abrufen der <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> Eigenschaften der <xref:System.Windows.Forms.DataGridView> Steuerelement. Zugriff auf diese Eigenschaften ist ineffizient, wenn jede Zelle im Steuerelement ausgewählt ist. Um in diesem Fall eine Leistungseinbuße zu vermeiden, verwenden die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode erste. Darüber hinaus können den Zugriff auf diese Auflistungen zum Ermitteln der Anzahl der ausgewählten Zellen, Zeilen oder Spalten ineffizient sein. Stattdessen sollten Sie verwenden die <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, oder <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> -Methode auf und übergibt die <xref:System.Windows.Forms.DataGridViewElementStates.Selected> Wert.  
  
> [!TIP]
>  Beispielcode, der veranschaulicht, die programmgesteuerte Verwendung der ausgewählten Zellen Schemadokumentation in der <xref:System.Windows.Forms.DataGridView> -Klassenübersicht.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Festlegen des Auswahlmodus des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
