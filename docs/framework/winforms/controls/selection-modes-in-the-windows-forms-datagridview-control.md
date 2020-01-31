---
title: Auswahl Modi im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: e20bf6307d77bf189b698e847c6b855c249dc3c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743039"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Auswahlmodi im DataGridView-Steuerelement von Windows Forms

Manchmal möchten Sie, dass Ihre Anwendung Aktionen auf der Grundlage der Benutzer Auswahl in einem <xref:System.Windows.Forms.DataGridView> Steuerelement ausführt. Abhängig von den Aktionen können Sie die möglichen Auswahlmöglichkeiten einschränken. Nehmen Sie beispielsweise an, dass Ihre Anwendung einen Bericht für den aktuell ausgewählten Datensatz drucken kann. In diesem Fall empfiehlt es sich, das <xref:System.Windows.Forms.DataGridView>-Steuerelement so zu konfigurieren, dass bei jedem Klicken auf eine beliebige Stelle in einer Zeile immer die gesamte Zeile ausgewählt wird, sodass nur jeweils eine Zeile ausgewählt werden kann.

Sie können die zulässige Auswahl angeben, indem Sie die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>-Eigenschaft auf einen der folgenden <xref:System.Windows.Forms.DataGridViewSelectionMode> Enumerationswerte festlegen.

|DataGridViewSelectionMode-Wert|Beschreibung|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Durch Klicken auf eine Zelle wird Sie ausgewählt. Zeilen-und Spaltenheader können nicht zur Auswahl verwendet werden.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Durch Klicken auf eine Zelle wird Sie ausgewählt. Wenn Sie auf einen Spaltenheader klicken, wird die gesamte Spalte ausgewählt. Spaltenheader können nicht für die Sortierung verwendet werden.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Wenn Sie auf eine Zelle oder einen Spaltenheader klicken, wird die gesamte Spalte ausgewählt. Spaltenheader können nicht für die Sortierung verwendet werden.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Durch Klicken auf eine Zelle oder einen Zeilen Header wird die gesamte Zeile ausgewählt.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Standardauswahl Modus. Durch Klicken auf eine Zelle wird Sie ausgewählt. Durch Klicken auf einen Zeilen Header wird die gesamte Zeile ausgewählt.|

> [!NOTE]
> Wenn Sie den Auswahlmodus zur Laufzeit ändern, wird die aktuelle Auswahl automatisch gelöscht.

Standardmäßig können Benutzer mehrere Zeilen, Spalten oder Zellen auswählen, indem Sie Sie mit der Maus ziehen, die STRG-Taste oder die UMSCHALTTASTE gedrückt halten, um eine Auswahl zu erweitern oder zu ändern, oder indem Sie auf die obere linke Header Zelle klicken, um alle Zellen im Steuerelement auszuwählen. Um dieses Verhalten zu verhindern, legen Sie die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>-Eigenschaft auf `false`fest.

Mit den Modi <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> und <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> können Benutzer Zeilen löschen, indem Sie Sie auswählen und die ENTF-Taste drücken. Benutzer können Zeilen nur löschen, wenn sich die aktive Zelle nicht im Bearbeitungsmodus befindet, die <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A>-Eigenschaft auf `true`festgelegt ist und die zugrunde liegende Datenquelle das Löschen von Zeilen unterstützt. Beachten Sie, dass diese Einstellungen das programmgesteuerte Löschen von Zeilen nicht verhindern.

## <a name="programmatic-selection"></a>Programmgesteuerte Auswahl

Der aktuelle Auswahlmodus schränkt das Verhalten der programmgesteuerten Auswahl und der Benutzer Auswahl ein. Sie können die aktuelle Auswahlprogramm gesteuert ändern, indem Sie die `Selected`-Eigenschaft von Zellen, Zeilen oder Spalten festlegen, die im <xref:System.Windows.Forms.DataGridView>-Steuerelement vorhanden sind. Sie können auch alle Zellen im-Steuerelement durch die <xref:System.Windows.Forms.DataGridView.SelectAll%2A>-Methode auswählen, abhängig vom Auswahlmodus. Um die Auswahl zu löschen, verwenden Sie die <xref:System.Windows.Forms.DataGridView.ClearSelection%2A>-Methode.

Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>-Eigenschaft auf `true`festgelegt ist, können Sie <xref:System.Windows.Forms.DataGridView> Elemente hinzufügen oder aus der Auswahl entfernen, indem Sie die `Selected`-Eigenschaft des Elements ändern. Andernfalls werden beim Festlegen der `Selected`-Eigenschaft auf `true` für ein Element automatisch weitere Elemente aus der Auswahl entfernt.

Beachten Sie, dass das Ändern des Werts der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>-Eigenschaft die aktuelle Auswahl nicht ändert.

Sie können eine Sammlung der derzeit ausgewählten Zellen, Zeilen oder Spalten über die Eigenschaften <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> des <xref:System.Windows.Forms.DataGridView> Steuer Elements abrufen. Der Zugriff auf diese Eigenschaften ist ineffizient, wenn jede Zelle im Steuerelement ausgewählt wird. Um in diesem Fall eine Leistungs Einbuße zu vermeiden, verwenden Sie zuerst die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>-Methode. Außerdem kann der Zugriff auf diese Auflistungen zum Ermitteln der Anzahl ausgewählter Zellen, Zeilen oder Spalten ineffizient sein. Verwenden Sie stattdessen die <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>-, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>-oder <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A>-Methode, und übergeben Sie dabei den <xref:System.Windows.Forms.DataGridViewElementStates.Selected> Wert.

> [!TIP]
> Beispielcode, der die programmgesteuerte Verwendung ausgewählter Zellen veranschaulicht, finden Sie in der Übersicht über <xref:System.Windows.Forms.DataGridView>-Klasse.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Festlegen des Auswahlmodus des DataGridView-Steuerelements in Windows Forms](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
