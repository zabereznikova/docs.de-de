---
title: Standardverhalten von Tastatur und Maus im Windows Forms-DataGridView-Steuerelement
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
ms.openlocfilehash: 56585bf91a559844f15aede4519706674357a924
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011345"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Standardverhalten von Tastatur und Maus im Windows Forms-DataGridView-Steuerelement

Die folgende Tabelle beschreibt die Interaktion zwischen Benutzer und dem <xref:System.Windows.Forms.DataGridView> Steuerelement über eine Tastatur und Maus.  
  
> [!NOTE]
>  Um Tastaturverhalten anzupassen, können Sie z. B. standard Tastaturereignisse behandeln <xref:System.Windows.Forms.Control.KeyDown>. Im Bearbeitungsmodus befindet, empfängt das Bearbeitungssteuerelement jedoch die Tastatureingabe und die Tastaturereignisse treten nicht für die <xref:System.Windows.Forms.DataGridView> Steuerelement. Fügen Sie zum Bearbeiten der Steuerelementereignisse behandeln zu können, die Handler auf das Steuerelement zur Textbearbeitung in einer <xref:System.Windows.Forms.DataGridView.EditingControlShowing> -Ereignishandler. Alternativ können Sie anpassen, Tastaturverhalten in einem <xref:System.Windows.Forms.DataGridView> Unterklasse durch Überschreiben der <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> und <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> Methoden.  
  
## <a name="default-keyboard-handling"></a>Standardbehandlung von Tastatur  
  
### <a name="basic-navigation-and-entry-keys"></a>Grundlegende Navigations- und Eingabetasten  
  
|Taste oder Tastenkombination|Beschreibung|  
|----------------------------|-----------------|  
|NACH-UNTEN-TASTE|Verschiebt den Fokus auf die Zelle direkt unter der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, bleibt wirkungslos.|  
|NACH-LINKS|Verschiebt den Fokus auf die vorherige Zelle in der Zeile an. Wenn der Fokus in der ersten Zelle in der Zeile befindet, bleibt wirkungslos.|  
|NACH-RECHTS|Verschiebt den Fokus auf die nächste Zelle in der Zeile an. Wenn der Fokus in der letzten Zelle in der Zeile befindet, bleibt wirkungslos.|  
|NACH-OBEN-TASTE|Verschiebt den Fokus auf die Zelle direkt über der aktuellen Zelle. Wenn der Fokus in der ersten Zeile befindet, bleibt wirkungslos.|  
|START|Verschiebt den Fokus auf die erste Zelle in der aktuellen Zeile.|  
|ENDE|Verschiebt den Fokus auf die letzte Zelle in der aktuellen Zeile.|  
|BILD-AB|Führt einen Bildlauf des Steuerelements nach unten, um die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf die letzte vollständig angezeigte Zeile ohne Spalten zu ändern.|  
|BILD-AUF|Führt einen Bildlauf des Steuerelements nach oben, um die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf die erste angezeigte Zeile ohne Spalten zu ändern.|  
|TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus auf die nächste Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der letzten Zelle der Zeile ist, geht auf die erste Zelle in der nächsten Zeile. Wenn der Fokus in der letzten Zelle im Steuerelement ist, geht zum nächsten Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|UMSCHALT+TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus auf die vorherige Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der ersten Zelle der Zeile ist, geht bis zur letzten Zelle in der vorherigen Zeile. Wenn der Fokus in der ersten Zelle im Steuerelement ist, verschiebt den Fokus, um das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|STRG+TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus auf die nächste Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der letzten Zelle der Zeile ist, geht auf die erste Zelle in der nächsten Zeile. Wenn der Fokus in der letzten Zelle im Steuerelement ist, geht zum nächsten Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|STRG+UMSCHALT +TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus auf die vorherige Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der ersten Zelle der Zeile ist, geht bis zur letzten Zelle in der vorherigen Zeile. Wenn der Fokus in der ersten Zelle im Steuerelement ist, verschiebt den Fokus, um das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|STRG + PFEILTASTE|Verschiebt den Fokus auf die am weitesten entfernten Zelle in der Richtung des Pfeils.|  
|STRG + POS1|Verschiebt den Fokus zur ersten Zelle im Steuerelement.|  
|STRG + ENDE|Verschiebt den Fokus zur letzten Zelle im Steuerelement.|  
|STRG + BILD-AUF VERTIKALE|Identisch mit der Seite nach unten oder Bild-auf.|  
|F2|Versetzt die aktuelle Zelle in den Bearbeitungsmodus für die Zelle ein, wenn die <xref:System.Windows.Forms.DataGridView.EditMode%2A> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> oder <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|
|F3|Die aktuelle Spalte sortiert, wenn die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>. Es ist identisch mit den aktuellen Spaltenheader klicken. Seit .NET Framework 4.7.2 verfügbar. Um dieses Feature zu aktivieren, müssen Anwendungen als Ziel .NET Framework 4.7.2 oder höher oder explizit festlegen, Verbesserungen der Barrierefreiheit von AppContext-Schalter verwenden.|  
|F4|Wenn die aktuelle Zelle ist eine <xref:System.Windows.Forms.DataGridViewComboBoxCell>, wird für die Zelle in den Bearbeitungsmodus, und zeigt die Dropdown-Liste.|  
|ALT + NACH-OBEN/NACH-UNTEN|Wenn die aktuelle Zelle ist eine <xref:System.Windows.Forms.DataGridViewComboBoxCell>, wird für die Zelle in den Bearbeitungsmodus, und zeigt die Dropdown-Liste.|  
|LEERTASTE|Wenn die aktuelle Zelle ist eine <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>, oder <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, löst die <xref:System.Windows.Forms.DataGridView.CellClick> und <xref:System.Windows.Forms.DataGridView.CellContentClick> Ereignisse. Wenn die aktuelle Zelle ist eine <xref:System.Windows.Forms.DataGridViewButtonCell>, auch auf die Schaltfläche klickt. Wenn die aktuelle Zelle ist eine <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, ändert sich auch den Status überprüfen.|  
|EINGABETASTE|Übernimmt alle Änderungen an der aktuellen Zelle und die Zeile, und verschiebt den Fokus auf die Zelle direkt unter der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, übernimmt alle Änderungen, ohne den Fokus zu verschieben.|  
|ESC|Wenn das Steuerelement im Bearbeitungsmodus befindet, bricht die Bearbeitung ab. Ist das Steuerelement nicht im Bearbeitungsmodus befindet, stellt alle Änderungen, die mit der aktuellen Zeile vorgenommen wurden, wenn das Steuerelement an eine Datenquelle gebunden ist, die die Bearbeitung unterstützt wieder her, oder des Virtueller Modus mit auf Zeilenebene Commit-Bereich implementiert wurde.|  
|RÜCKTASTE|Löscht die Zeichen vor der Einfügemarke, beim Bearbeiten einer Zelle.|  
|DELETE|Löscht das Zeichen nach der Einfügemarke, wenn eine Zelle bearbeitet.|  
|STRG+EINGABE|Führt einen Commit für Änderungen an der aktuellen Zelle ohne den Fokus zu verschieben. Auch auf Zeilenebene Commits, die alle Änderungen an der aktuellen Zeile, wenn das Steuerelement an eine Datenquelle gebunden ist, die Bearbeitung oder der virtuelle Modus unterstützt wurde implementiert, mit Commit-Bereich.|  
|STRG+0|Gibt eine <xref:System.DBNull.Value?displayProperty=nameWithType> Wert in die aktuelle Zelle, wenn die Zelle bearbeitet werden kann. Wird standardmäßig der Anzeigewert für eine <xref:System.DBNull> Zellenwert ist der Wert des der <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellStyle> für die aktuelle Zelle.|  
  
### <a name="selection-keys"></a>Auswahl-Schlüssel

 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaftensatz auf `false` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, ändern die aktuelle Zelle mithilfe von Navigationstasten ändert die Auswahl in die neue Zelle. Die UMSCHALTTASTE, STRG und ALT-Taste wirken sich nicht auf dieses Verhalten aus.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, tritt das gleiche Verhalten auf, aber mit den folgenden Ergänzungen.  
  
|Taste oder Tastenkombination|Beschreibung|  
|----------------------------|-----------------|  
|UMSCHALT + LEERTASTE|Wählt die ganze Zeile oder Spalte (dasselbe wie das Klicken mit der die Zeilen- oder Spaltenüberschrift).|  
|Navigationstaste (-Taste, Seite nach oben/unten, Start, Ende)|Wenn eine vollständige Zeile oder Spalte ausgewählt ist, verschiebt die aktuelle Zelle in einer neuen Zeile oder Spalte ändern die Auswahl, die vollständig neue Zeile oder Spalte (je nach der Auswahlmodus).|  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> nastaven NA hodnotu `false` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, ändern die aktuelle Zelle in einer neuen Zeile oder Spalte mithilfe der Tastatur, die vollständig neue Zeile oder Spalte wird die Auswahl verschoben. Die UMSCHALTTASTE, STRG und ALT-Taste wirken sich nicht auf dieses Verhalten aus.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> nastaven NA hodnotu `true`, das Navigationsverhalten nicht geändert, doch bei gedrückter Umschalttaste (einschließlich STRG + UMSCHALT) über die Tastatur navigiert, wird eine Auswahl von mehreren Zelle ändern. Vor Beginn der Navigation, markiert das Steuerelement die aktuelle Zelle als Ankerzelle an. Wenn Sie sich bei gedrückter Umschalttaste navigieren, umfasst die Auswahl aller Zellen zwischen die Ankerzelle und der aktuellen Zelle. Andere Zellen im Steuerelement bleibt ausgewählt, wenn bereits ausgewählt waren, aber sie nicht ausgewählt werden können, wenn die Navigation per Tastatur sie vorübergehend zwischen der Ankerzelle und die aktuelle Zelle legt.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> nastaven NA hodnotu `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, das Verhalten der Ankerzelle und der aktuellen Zelle ist identisch, aber nur vollständige Zeilen oder Spalten aktiviert oder deaktiviert werden.  
  
## <a name="default-mouse-handling"></a>Standardbehandlung für Maus
  
### <a name="basic-mouse-handling"></a>Grundlegende Mausbehandlung
  
> [!NOTE]
>  Klicken auf eine Zelle mit der linken Maustaste immer ändert die aktuelle Zelle. Klicken Sie auf eine Zelle mit der rechten Maustaste wird ein Kontextmenü geöffnet, wenn eines verfügbar ist.  
  
|Mausaktion|Beschreibung|  
|------------------|-----------------|  
|Linken Maustaste|Stellt der angeklickte Zelle die aktiven Zelle, und löst die <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> Ereignis.|  
|Linke Maustaste oben|Löst das <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>-Ereignis aus.|  
|Klick mit der linken Maustaste|Löst die <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> und <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> Ereignisse|  
|Linken Maustaste, und ziehen Sie auf eine Spaltenheaderzelle|Wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> Eigenschaft `true`, verschiebt Sie die Spalte, damit sie auf eine neue Position abgelegt werden kann.|  
  
### <a name="mouse-selection"></a>Mausaus

 Es ist kein Auswahlverhalten der mittleren Maustaste oder des Mausrads zugeordnet.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaftensatz auf `false` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, tritt das folgende Verhalten auf.  
  
|Mausaktion|Beschreibung|  
|------------------|-----------------|  
|Klicken Sie auf die linke Maustaste|Wählt nur die aktuelle Zelle an, wenn der Benutzer eine Zelle klickt. Keine Auswahlverhalten, wenn der Benutzer auf einen Zeilen- oder Spaltenüberschrift klickt.|  
|Klicken Sie auf die rechte Maustaste|Wird ein Kontextmenü angezeigt, sofern verfügbar.|  
  
 Das gleiche Verhalten tritt auf, wenn die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, außer dass entsprechend dem Auswahlmodus, klicken Sie auf einen Zeilen- oder Spaltenüberschrift wird wählen Sie die gesamte Zeile oder Spalte und die aktuelle Zelle in die erste Zelle in der Zeile oder Spalte festlegen.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, durch Klicken auf eine beliebige Zelle in einer Zeile oder Spalte ausgewählt wird, die gesamte Zeile oder Spalte.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> nastaven NA hodnotu `true`, auf eine Zelle bei gedrückter STRG-Taste oder Umschalttaste Klicken eine Auswahl von mehreren Zelle ändern.  
  
 Wenn Sie eine Zelle klicken, während Sie die STRG-Taste drücken, wird die Zelle den Auswahlzustand ändern, während alle anderen Zellen mit den aktuellen Auswahlzustand beibehalten.  
  
 Wenn Sie eine Zelle oder eine Reihe von Zellen klicken bei gedrückter UMSCHALTTASTE, umfasst die Auswahl aller Zellen zwischen der aktuellen Zelle und befindet sich an der Position der aktuellen Zelle vor dem ersten Klick Ankerzelle an. Wenn Sie klicken und ziehen Sie den Mauszeiger über mehrere Zellen, ist die Ankerzelle der Zelle geklickt haben, die zu Beginn des Ziehvorgangs an. Nachfolgende Klicken bei gedrückter Umschalttaste Ändern der aktiven Zelle, aber nicht die Ankerzelle an. Andere Zellen im Steuerelement bleibt ausgewählt, wenn bereits ausgewählt waren, aber sie nicht ausgewählt werden können, wenn Navigation mit der Maus sie vorübergehend zwischen der Ankerzelle und die aktuelle Zelle legt.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> nastaven NA hodnotu `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, klicken auf einen Zeilen- oder Spaltenüberschrift (entsprechend dem Auswahlmodus) bei gedrückter Umschalttaste ändern eine vorhandene Auswahl ganzer Zeilen oder Spalten, wenn solche ein eine Auswahl vorhanden ist. Andernfalls wird es heben Sie die Auswahl, und starten eine neue Auswahl ganzer Zeilen oder Spalten. Auf einen Zeilen- oder Spaltenüberschrift klicken bei gedrückter STRG, allerdings wird hinzufügen oder Entfernen der geklickt wurde Zeile oder Spalte aus der aktuellen Auswahl ohne Weise die aktuelle Auswahl zu ändern.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> nastaven NA hodnotu `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> nastaven NA hodnotu <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, auf eine Zelle klicken, während Sie die STRG-oder UMSCHALTTASTE verhält sich genauso mit der Ausnahme, dass nur vollständige Zeilen und Spalten sind betroffen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
