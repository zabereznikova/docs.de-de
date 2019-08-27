---
title: Auswahlmodi im DataGridView-Steuerelement von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: cfe80d5ccb73208f1c61a2ac6c9963343d398bcb
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046423"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Auswahlmodi im DataGridView-Steuerelement von Windows Forms

Manchmal möchten Sie, dass Ihre Anwendung Aktionen auf der Grundlage der Benutzer Auswahl <xref:System.Windows.Forms.DataGridView> in einem Steuerelement ausführt. Abhängig von den Aktionen können Sie die möglichen Auswahlmöglichkeiten einschränken. Nehmen Sie beispielsweise an, dass Ihre Anwendung einen Bericht für den aktuell ausgewählten Datensatz drucken kann. In diesem Fall empfiehlt es sich, das <xref:System.Windows.Forms.DataGridView> Steuerelement so zu konfigurieren, dass bei jedem Klicken auf eine beliebige Stelle in einer Zeile immer die gesamte Zeile ausgewählt wird, sodass jeweils nur eine Zeile ausgewählt werden kann.

Sie können die zulässige Auswahl angeben, indem Sie <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> die-Eigenschaft auf einen der <xref:System.Windows.Forms.DataGridViewSelectionMode> folgenden Enumerationswerte festlegen.

|DataGridViewSelectionMode-Wert|Beschreibung|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Durch Klicken auf eine Zelle wird Sie ausgewählt. Zeilen-und Spaltenheader können nicht zur Auswahl verwendet werden.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Durch Klicken auf eine Zelle wird Sie ausgewählt. Wenn Sie auf einen Spaltenheader klicken, wird die gesamte Spalte ausgewählt. Spaltenheader können nicht für die Sortierung verwendet werden.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Wenn Sie auf eine Zelle oder einen Spaltenheader klicken, wird die gesamte Spalte ausgewählt. Spaltenheader können nicht für die Sortierung verwendet werden.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Durch Klicken auf eine Zelle oder einen Zeilen Header wird die gesamte Zeile ausgewählt.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Standardauswahl Modus. Durch Klicken auf eine Zelle wird Sie ausgewählt. Durch Klicken auf einen Zeilen Header wird die gesamte Zeile ausgewählt.|

> [!NOTE]
> Wenn Sie den Auswahlmodus zur Laufzeit ändern, wird die aktuelle Auswahl automatisch gelöscht.

Standardmäßig können Benutzer mehrere Zeilen, Spalten oder Zellen auswählen, indem Sie Sie mit der Maus ziehen, die STRG-Taste oder die UMSCHALTTASTE gedrückt halten, um eine Auswahl zu erweitern oder zu ändern, oder indem Sie auf die obere linke Header Zelle klicken, um alle Zellen im Steuerelement auszuwählen. Um dieses Verhalten zu verhindern, legen <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> Sie die `false`-Eigenschaft auf fest.

Mit <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> den <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> Modi und können Benutzer Zeilen löschen, indem Sie Sie auswählen und die ENTF-Taste drücken. Benutzer können Zeilen nur löschen, wenn sich die aktuelle Zelle nicht im Bearbeitungsmodus befindet <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> , die-Eigenschaft `true`auf festgelegt ist und die zugrunde liegende Datenquelle das Löschen von Zeilen unterstützt. Beachten Sie, dass diese Einstellungen das programmgesteuerte Löschen von Zeilen nicht verhindern.

## <a name="programmatic-selection"></a>Programmgesteuerte Auswahl

Der aktuelle Auswahlmodus schränkt das Verhalten der programmgesteuerten Auswahl und der Benutzer Auswahl ein. Sie können die aktuelle Auswahlprogramm gesteuert ändern, indem Sie `Selected` die-Eigenschaft von Zellen, Zeilen oder Spalten festlegen, die <xref:System.Windows.Forms.DataGridView> im-Steuerelement vorhanden sind. Sie können auch alle Zellen im-Steuerelement über die <xref:System.Windows.Forms.DataGridView.SelectAll%2A> -Methode auswählen, abhängig vom Auswahlmodus. Verwenden Sie die <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> -Methode, um die Auswahl zu löschen.

Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaft auf `true`festgelegt ist, können <xref:System.Windows.Forms.DataGridView> Sie Elemente hinzufügen oder aus der Auswahl entfernen, indem `Selected` Sie die-Eigenschaft des-Elements ändern. Andernfalls werden durch das `Selected` Festlegen der `true` -Eigenschaft auf für ein Element automatisch weitere Elemente aus der Auswahl entfernt.

Beachten Sie, dass das Ändern des <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Werts der-Eigenschaft die aktuelle Auswahl nicht ändert.

Sie können eine Auflistung der aktuell ausgewählten Zellen, Zeilen oder <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>Spalten über die Eigenschaften, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>und des <xref:System.Windows.Forms.DataGridView> - <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> Steuer Elements abrufen. Der Zugriff auf diese Eigenschaften ist ineffizient, wenn jede Zelle im Steuerelement ausgewählt wird. Um in diesem Fall eine Leistungs Einbuße zu vermeiden, <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> verwenden Sie zuerst die-Methode. Außerdem kann der Zugriff auf diese Auflistungen zum Ermitteln der Anzahl ausgewählter Zellen, Zeilen oder Spalten ineffizient sein. Verwenden <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>Sie stattdessen die Methode, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>oder <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> , und übergeben Sie den <xref:System.Windows.Forms.DataGridViewElementStates.Selected> Wert.

> [!TIP]
> Beispielcode, der die programmgesteuerte Verwendung ausgewählter Zellen veranschaulicht, finden Sie in <xref:System.Windows.Forms.DataGridView> der Übersicht über die-Klasse.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen des Auswahlmodus des Windows Forms DataGridView-Steuer Elements](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
