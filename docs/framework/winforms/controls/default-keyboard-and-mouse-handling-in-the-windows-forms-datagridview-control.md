---
title: Standardbehandlung von Tastatur und Maus im Windows Forms DataGridView-Steuerelement
ms.date: 02/13/2018
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
ms.openlocfilehash: 97b8c8c3e418586bbc0053c358a2924484115a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969132"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Standardbehandlung von Tastatur und Maus im Windows Forms DataGridView-Steuerelement

In den folgenden Tabellen wird beschrieben, wie Benutzer über <xref:System.Windows.Forms.DataGridView> eine Tastatur und eine Maus mit dem Steuerelement interagieren können.  
  
> [!NOTE]
> Wenn <xref:System.Windows.Forms.Control.KeyDown>Sie das Tastatur Verhalten anpassen möchten, können Sie Standardtastatur Ereignisse wie z. b. verarbeiten. Im Bearbeitungsmodus empfängt das Steuerelement für die gehostete Bearbeitung jedoch die Tastatureingabe, und die Tastatur Ereignisse treten nicht <xref:System.Windows.Forms.DataGridView> für das Steuerelement auf. Fügen Sie die Handler an das Bearbeitungs Steuerelement in einem <xref:System.Windows.Forms.DataGridView.EditingControlShowing> Ereignishandler an, um Bearbeitungs Steuerelement-Ereignisse zu behandeln. Alternativ können Sie das Tastatur Verhalten in einer <xref:System.Windows.Forms.DataGridView> Unterklasse anpassen, indem Sie die-Methode und die <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> - <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> Methode überschreiben.  
  
## <a name="default-keyboard-handling"></a>Standardtastatur Behandlung  
  
### <a name="basic-navigation-and-entry-keys"></a>Grundlegende Navigations-und Eintrags Schlüssel  
  
|Schlüssel-oder Schlüssel Kombination|Beschreibung|  
|----------------------------|-----------------|  
|NACH-UNTEN-TASTE|Verschiebt den Fokus direkt unterhalb der aktuellen Zelle in die Zelle. Wenn sich der Fokus in der letzten Zeile befindet, führt keine Aktion aus.|  
|NACH-LINKS|Verschiebt den Fokus auf die vorherige Zelle in der Zeile. Wenn sich der Fokus in der ersten Zelle in der Zeile befindet, führt keine Aktion aus.|  
|NACH-RECHTS|Verschiebt den Fokus auf die nächste Zelle in der Zeile. Wenn sich der Fokus in der letzten Zelle in der Zeile befindet, führt keine Aktion aus.|  
|NACH-OBEN-TASTE|Verschiebt den Fokus direkt oberhalb der aktuellen Zelle in die Zelle. Wenn sich der Fokus in der ersten Zeile befindet, führt keine Aktion aus.|  
|START|Verschiebt den Fokus auf die erste Zelle in der aktuellen Zeile.|  
|ENDE|Verschiebt den Fokus auf die letzte Zelle in der aktuellen Zeile.|  
|BILD-AB|Führt einen Bildlauf nach unten um die Anzahl der Zeilen aus, die vollständig angezeigt werden. Verschiebt den Fokus auf die letzte vollständig angezeigte Zeile, ohne die Spalten zu ändern.|  
|BILD-AUF|Führt einen Bildlauf nach oben um die Anzahl der Zeilen aus, die vollständig angezeigt werden. Verschiebt den Fokus auf die erste angezeigte Zeile, ohne die Spalten zu ändern.|  
|TAB|Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `false`Wert ist, wird der Fokus auf die nächste Zelle in der aktuellen Zeile verschoben. Wenn sich der Fokus bereits in der letzten Zelle der Zeile befindet, verschiebt den Fokus auf die erste Zelle in der nächsten Zeile. Wenn sich der Fokus in der letzten Zelle im-Steuerelement befindet, verschiebt den Fokus auf das nächste Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.<br /><br /> Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `true`Wert ist, verschiebt den Fokus auf das nächste Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.|  
|UMSCHALT+TAB|Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `false`Wert ist, wird der Fokus auf die vorherige Zelle in der aktuellen Zeile verschoben. Wenn sich der Fokus bereits in der ersten Zelle der Zeile befindet, verschiebt den Fokus auf die letzte Zelle in der vorherigen Zeile. Wenn sich der Fokus in der ersten Zelle im-Steuerelement befindet, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.<br /><br /> Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `true`Wert ist, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.|  
|STRG+TAB|Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `false`Wert ist, verschiebt den Fokus auf das nächste Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.<br /><br /> Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `true`Wert ist, wird der Fokus auf die nächste Zelle in der aktuellen Zeile verschoben. Wenn sich der Fokus bereits in der letzten Zelle der Zeile befindet, verschiebt den Fokus auf die erste Zelle in der nächsten Zeile. Wenn sich der Fokus in der letzten Zelle im-Steuerelement befindet, verschiebt den Fokus auf das nächste Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.|  
|STRG+UMSCHALT +TAB|Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `false`Wert ist, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.<br /><br /> Wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A> -Eigenschafts `true`Wert ist, wird der Fokus auf die vorherige Zelle in der aktuellen Zeile verschoben. Wenn sich der Fokus bereits in der ersten Zelle der Zeile befindet, verschiebt den Fokus auf die letzte Zelle in der vorherigen Zeile. Wenn sich der Fokus in der ersten Zelle im-Steuerelement befindet, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivier Reihenfolge des übergeordneten Containers.|  
|STRG + PFEIL|Verschiebt den Fokus in Richtung des Pfeils in die am weitesten entfernte Zelle.|  
|STRG + STARTSEITE|Verschiebt den Fokus auf die erste Zelle im-Steuerelement.|  
|STRG + ENDE|Verschiebt den Fokus auf die letzte Zelle im-Steuerelement.|  
|STRG + BILD-AB/NACH-OBEN|Identisch mit Bild-ab oder Bild-auf.|  
|F2|Versetzt die aktuelle Zelle in den Bearbeitungsmodus der Zelle <xref:System.Windows.Forms.DataGridView.EditMode%2A> , wenn der <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> - <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>Eigenschafts Wert oder ist.|
|F3|Sortiert die aktuelle Spalte, wenn <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> der-Eigenschafts Wert ist. <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> Dies entspricht dem Klicken auf den aktuellen Spaltenheader. Verfügbar seit .NET Framework 4.7.2. Um dieses Feature zu aktivieren, müssen Anwendungen auf .NET Framework 4.7.2 oder höhere Versionen abzielen oder die Barrierefreiheits Verbesserungen mithilfe von appContext-Switches explizit abonnieren.|  
|F4|Wenn die aktive Zelle eine <xref:System.Windows.Forms.DataGridViewComboBoxCell>ist, wird die Zelle in den Bearbeitungsmodus versetzt, und die Dropdown Liste wird angezeigt.|  
|ALT + NACH-OBEN/NACH-UNTEN|Wenn die aktive Zelle eine <xref:System.Windows.Forms.DataGridViewComboBoxCell>ist, wird die Zelle in den Bearbeitungsmodus versetzt, und die Dropdown Liste wird angezeigt.|  
|LEERTASTE|Wenn die aktive Zelle <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>oder <xref:System.Windows.Forms.DataGridViewCheckBoxCell>ist, löst das-Ereignis <xref:System.Windows.Forms.DataGridView.CellClick> und <xref:System.Windows.Forms.DataGridView.CellContentClick> das-Ereignis aus. Wenn die aktive Zelle eine <xref:System.Windows.Forms.DataGridViewButtonCell>ist, wird auch die Schaltfläche gedrückt. Wenn es sich bei der aktuellen <xref:System.Windows.Forms.DataGridViewCheckBoxCell>Zelle um handelt, ändert auch den Prüf Zustand.|  
|EINGABETASTE|Führt einen Commit für alle Änderungen an der aktuellen Zelle und Zeile aus und verschiebt den Fokus direkt unterhalb der aktuellen Zelle in die Zelle. Wenn sich der Fokus in der letzten Zeile befindet, führt einen Commit für alle Änderungen aus, ohne den Fokus zu verschieben.|  
|ESC|Wenn sich das Steuerelement im Bearbeitungsmodus befindet, wird der Bearbeitungsvorgang abgebrochen. Wenn sich das Steuerelement nicht im Bearbeitungsmodus befindet, werden alle Änderungen, die an der aktuellen Zeile vorgenommen wurden, zurückgesetzt, wenn das Steuerelement an eine Datenquelle gebunden ist, die die Bearbeitung unterstützt, oder der virtuelle Modus wurde mit einem commitbereich auf Zeilenebene implementiert.|  
|RÜCKTASTE|Löscht das Zeichen vor der Einfügemarke, wenn eine Zelle bearbeitet wird.|  
|DELETE|Löscht das Zeichen nach der Einfügemarke, wenn eine Zelle bearbeitet wird.|  
|STRG+EINGABE|Führt einen Commit für alle Änderungen an der aktuellen Zelle aus, ohne den Fokus zu verschieben. Führt außerdem einen Commit für alle Änderungen an der aktuellen Zeile aus, wenn das Steuerelement an eine Datenquelle gebunden ist, die die Bearbeitung unterstützt, oder der virtuelle Modus mit einem commitbereich auf Zeilenebene implementiert wurde.|  
|STRG+0|Gibt einen <xref:System.DBNull.Value?displayProperty=nameWithType> Wert in die aktuelle Zelle ein, wenn die Zelle bearbeitet werden kann. Standardmäßig entspricht der Anzeige Wert für einen <xref:System.DBNull> Zellwert dem Wert <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> der-Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellStyle> -Eigenschaft für die aktuelle Zelle.|  
  
### <a name="selection-keys"></a>Auswahl Schlüssel

 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaft auf `false` festgelegt ist <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> und die-Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>auf festgelegt ist, wird durch das Ändern der aktuellen Zelle mithilfe der Navigationstasten die Auswahl in die neue Zelle geändert. Die UMSCHALT-, STRG-und Alt-Taste wirken sich nicht auf dieses Verhalten aus.  
  
 Wenn auf oder <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> festgelegtist,trittdasgleicheVerhaltenauf,abermit<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>den folgenden Ergänzungen.  
  
|Schlüssel-oder Schlüssel Kombination|Beschreibung|  
|----------------------------|-----------------|  
|UMSCHALT + LEERTASTE|Wählt die vollständige Zeile oder Spalte aus (identisch mit dem Klicken auf die Zeilen-oder Spalten Kopfzeile).|  
|Navigations Taste (Pfeiltaste, Seite nach oben/unten, Startseite, Ende)|Wenn eine vollständige Zeile oder Spalte ausgewählt ist, wird die Auswahl durch Ändern der aktuellen Zelle in eine neue Zeile oder Spalte in die vollständige neue Zeile oder Spalte verschoben (abhängig vom Auswahlmodus).|  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `false` und auf<xref:System.Windows.Forms.DataGridView.SelectionMode%2A> oderfest<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>gelegt ist, wird durch das Ändern der aktuellen Zelle in eine neue Zeile oder Spalte mithilfe der Tastatur die Auswahl zur vollständigen neuen Zeile oder Spalte verschoben. <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> Die UMSCHALT-, STRG-und Alt-Taste wirken sich nicht auf dieses Verhalten aus.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf`true`festgelegt ist, ändert sich das Navigationsverhalten nicht, aber die Navigation mit der Tastatur beim Drücken der Umschalttaste (einschließlich STRG + UMSCHALT) ändert eine Auswahl aus mehreren Zellen. Vor Beginn der Navigation markiert das Steuerelement die aktuelle Zelle als Anker Zelle. Wenn Sie beim Drücken der UMSCHALTTASTE navigieren, schließt die Auswahl alle Zellen zwischen der Anker Zelle und der aktuellen Zelle ein. Andere Zellen im Steuerelement bleiben aktiviert, wenn Sie bereits ausgewählt wurden. Sie werden jedoch möglicherweise deaktiviert, wenn Sie von der Tastaturnavigation vorübergehend zwischen der Anker Zelle und der aktuellen Zelle platziert werden.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` und auf<xref:System.Windows.Forms.DataGridView.SelectionMode%2A> oderfest<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>gelegt ist, ist das Verhalten der Anker Zelle und der aktuellen Zelle identisch, aber nur vollständige Zeilen oder Spalten werden ausgewählt oder nicht ausgewählt. <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>  
  
## <a name="default-mouse-handling"></a>Standard Maus Behandlung
  
### <a name="basic-mouse-handling"></a>Einfache Maus Behandlung
  
> [!NOTE]
> Wenn Sie mit der linken Maustaste auf eine Zelle klicken, wird die aktuelle Zelle immer geändert. Wenn Sie mit der rechten Maustaste auf eine Zelle klicken, wird ein Kontextmenü geöffnet, wenn eine Zelle verfügbar ist.  
  
|Maus Aktion|Beschreibung|  
|------------------|-----------------|  
|Linke Maustaste nach unten|Macht die angeklickte Zelle zur aktuellen Zelle und löst <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> das-Ereignis aus.|  
|Linke Maustaste nach oben|Löst das <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>-Ereignis aus.|  
|Mausklick mit der linken Maustaste|Löst die <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> Ereignisse <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> und aus.|  
|Linke Maustaste nach unten und ziehen auf eine Spaltenheader Zelle|Wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> -Eigenschaft `true`ist, wird die Spalte verschoben, sodass Sie an einer neuen Position abgelegt werden kann.|  
  
### <a name="mouse-selection"></a>Maus Auswahl

 Der mittleren Maustaste oder dem Mausrad ist kein Auswahl Verhalten zugeordnet.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaft auf `false` festgelegt ist <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> und die-Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>auf festgelegt ist, tritt das folgende Verhalten auf.  
  
|Maus Aktion|Beschreibung|  
|------------------|-----------------|  
|Klicken Sie mit der linken Maustaste.|Wählt nur die aktuelle Zelle aus, wenn der Benutzer auf eine Zelle klickt. Kein Auswahl Verhalten, wenn der Benutzer auf einen Zeilen-oder Spaltenheader klickt.|  
|Klicken Sie auf die Rechte Maustaste.|Zeigt ein Kontextmenü an, wenn eine verfügbar ist.|  
  
 Das gleiche Verhalten tritt auf, <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> wenn auf <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>festgelegt wird, mit der Ausnahme, dass das Klicken auf einen Zeilen-oder Spaltenheader abhängig vom Auswahlmodus die vollständige Zeile oder Spalte auswählt und die aktuelle Zelle auf die erste Zelle in der Zeile oder Spalte festgelegt wird.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>festgelegt ist, wird durch Klicken auf eine beliebige Zelle in einer Zeile oder Spalte die vollständige Zeile oder Spalte ausgewählt.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf festgelegt `true`ist, wird durch Klicken auf eine Zelle beim Drücken von STRG oder UMSCHALT eine Auswahl aus mehreren Zellen geändert.  
  
 Wenn Sie beim Drücken der STRG-Taste auf eine Zelle klicken, wird der Auswahl Zustand der Zelle geändert, während alle anderen Zellen ihren aktuellen Auswahl Zustand beibehalten.  
  
 Wenn Sie beim Drücken der UMSCHALTTASTE auf eine Zelle oder eine Reihe von Zellen klicken, umfasst die Auswahl alle Zellen zwischen der aktuellen Zelle und einer Anker Zelle, die sich an der Position der aktuellen Zelle vor dem ersten Klick befindet. Wenn Sie auf mehrere Zellen klicken und den Mauszeiger ziehen, ist die Anker Zelle die Zelle, auf die Sie am Anfang des Zieh Vorgangs geklickt haben. Nachfolgende Klicks beim Drücken der Umschalttaste ändern die aktuelle Zelle, jedoch nicht die Anker Zelle. Andere Zellen im Steuerelement bleiben aktiviert, wenn Sie bereits ausgewählt wurden. Sie werden jedoch möglicherweise deaktiviert, wenn Sie von der Maus Navigation vorübergehend zwischen der Anker Zelle und der aktuellen Zelle platziert werden.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` und auf<xref:System.Windows.Forms.DataGridView.SelectionMode%2A> oderfest<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>gelegt ist, wird beim Klicken auf einen Zeilen-oder Spaltenheader (abhängig vom Auswahlmodus) beim Drücken der Umschalttaste eine vorhandene Auswahl vollständiger Zeilen oder Spalten geändert, wenn dies der Fall ist. <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> die Auswahl ist vorhanden. Andernfalls wird die Auswahl gelöscht und eine neue Auswahl vollständiger Zeilen oder Spalten gestartet. Wenn Sie beim Drücken von STRG auf eine Zeilen-oder Spaltenüberschrift klicken, wird die angeklickte Zeile oder Spalte aus der aktuellen Auswahl hinzugefügt oder entfernt, ohne die aktuelle Auswahl anderweitig zu ändern.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` und <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> auf oder fest<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>gelegt ist, verhält sich das Klicken auf eine Zelle beim Drücken der UMSCHALTTASTE oder STRG auf die gleiche Weise, außer dass nur vollständige Zeilen und Spalten betroffen sind. <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
