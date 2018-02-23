---
title: Standardbehandlung von Tastatur und Maus Behandlung in Windows Forms-DataGridView-Steuerelement
ms.date: 02/13/2018
ms.prod: .net-framework
ms.technology:
- dotnet-winforms
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 29e8afaefd35951288a4d8f5e5df2e3b5fbc4356
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2018
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Standardbehandlung von Tastatur und Maus Behandlung in Windows Forms-DataGridView-Steuerelement

Die folgende Tabelle beschreibt, wie Benutzer mit interagieren können die <xref:System.Windows.Forms.DataGridView> Steuerelement über eine Tastatur und Maus.  
  
> [!NOTE]
>  Um Tastaturverhalten anzupassen, können Sie z. B. Standardtastaturereignisse behandeln <xref:System.Windows.Forms.Control.KeyDown>. In den Bearbeitungsmodus wechseln, empfängt das Bearbeitungssteuerelement jedoch die Tastatureingaben und die Tastaturereignisse treten für die <xref:System.Windows.Forms.DataGridView> Steuerelement. Fügen Sie zum Bearbeiten der Steuerelementereignisse behandeln zu können, die Handler an das Bearbeitungssteuerelement in eine <xref:System.Windows.Forms.DataGridView.EditingControlShowing> -Ereignishandler. Alternativ können Sie anpassen, Tastaturverhalten in einer <xref:System.Windows.Forms.DataGridView> Unterklasse durch Überschreiben der <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> und <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> Methoden.  
  
## <a name="default-keyboard-handling"></a>Standardbehandlung von Tastatur  
  
### <a name="basic-navigation-and-entry-keys"></a>Grundlegende Navigations- und Schlüssel  
  
|Schlüssel oder eine Tastenkombination|Beschreibung|  
|----------------------------|-----------------|  
|NACH-UNTEN-TASTE|Verschiebt den Fokus auf die Zelle direkt unterhalb der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, wird keine Aktion ausgeführt.|  
|NACH-LINKS|Verschiebt den Fokus auf die vorherige Zelle in der Zeile an. Wenn der Fokus in der ersten Zelle in der Zeile ist, wird keine Aktion ausgeführt.|  
|NACH-RECHTS|Verschiebt den Fokus zur nächsten Zelle in der Zeile an. Wenn der Fokus in der letzten Zelle der Zeile befindet, wird keine Aktion ausgeführt.|  
|NACH-OBEN-TASTE|Verschiebt den Fokus auf die Zelle direkt über der aktuellen Zelle. Wenn der Fokus in der ersten Zeile befindet, wird keine Aktion ausgeführt.|  
|START|Verschiebt den Fokus zur ersten Zelle in der aktuellen Zeile.|  
|ENDE|Verschiebt den Fokus zur letzten Zelle in der aktuellen Zeile.|  
|BILD-AB|Ermöglicht das Scrollen des Steuerelements nach unten durch die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf die letzte vollständig angezeigte Zeile ohne Spalten zu ändern.|  
|BILD-AUF|Führt einen Bildlauf des Steuerelements nach oben, um die Anzahl der Zeilen, die vollständig angezeigt werden. Verschiebt den Fokus auf den ersten angezeigten Zeilen ohne Spalten zu ändern.|  
|TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus zur nächsten Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der letzten Zelle der Zeile ist, verschiebt den Fokus zur ersten Zelle in der nächsten Zeile. Wenn der Fokus in der letzten Zelle im Steuerelement ist, verschiebt den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|UMSCHALT+TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus auf die vorherige Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der ersten Zelle der Zeile ist, geht bis zur letzten Zelle in der vorherigen Zeile. Wenn der Fokus in der ersten Zelle im Steuerelement ist, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|STRG+TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus zur nächsten Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der letzten Zelle der Zeile ist, verschiebt den Fokus zur ersten Zelle in der nächsten Zeile. Wenn der Fokus in der letzten Zelle im Steuerelement ist, verschiebt den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|STRG+UMSCHALT +TAB|Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `false`, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.<br /><br /> Wenn die <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Eigenschaftswert ist `true`, verschiebt den Fokus auf die vorherige Zelle in der aktuellen Zeile. Wenn der Fokus bereits in der ersten Zelle der Zeile ist, geht bis zur letzten Zelle in der vorherigen Zeile. Wenn der Fokus in der ersten Zelle im Steuerelement ist, verschiebt den Fokus auf das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers.|  
|STRG + PFEILTASTE|Verschiebt den Fokus zur am weitesten entfernten Zelle in die Richtung des Pfeils.|  
|STRG + POS1|Verschiebt den Fokus zur ersten Zelle im Steuerelement.|  
|STRG + ENDE|Verschiebt den Fokus zur letzten Zelle im Steuerelement.|  
|STRG + BILD-AB/NACH-OBEN|Identisch mit der Seite nach unten oder Bild-auf.|  
|F2|Versetzt die aktuelle Zelle in den Bearbeitungsmodus für die Zelle ein, wenn die <xref:System.Windows.Forms.DataGridView.EditMode%2A> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> oder <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|
|F3|Die aktuelle Spalte sortiert, wenn die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>. Er ist der gleiche wie das Klicken auf den aktuellen Spaltenheader. Verfügbar seit .NET Framework 4.7.2. Zum Aktivieren dieser Funktion müssen Anwendungen als Ziel .NET Framework 4.7.2 oder höhere Versionen oder explizit Eingabehilfen-Verbesserungen mit AppContext Switches verwenden.|  
|F4|Wenn die aktuelle Zelle befindet sich eine <xref:System.Windows.Forms.DataGridViewComboBoxCell>, versetzt die Zelle in den Bearbeitungsmodus, und zeigt die Dropdown-Liste.|  
|ALT + NACH-OBEN/NACH-UNTEN|Wenn die aktuelle Zelle befindet sich eine <xref:System.Windows.Forms.DataGridViewComboBoxCell>, versetzt die Zelle in den Bearbeitungsmodus, und zeigt die Dropdown-Liste.|  
|LEERTASTE|Wenn die aktuelle Zelle befindet sich eine <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>, oder <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, löst die <xref:System.Windows.Forms.DataGridView.CellClick> und <xref:System.Windows.Forms.DataGridView.CellContentClick> Ereignisse. Wenn die aktuelle Zelle befindet sich eine <xref:System.Windows.Forms.DataGridViewButtonCell>, auch auf die Schaltfläche klickt. Wenn die aktuelle Zelle befindet sich eine <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, ändert sich auch auf den Aktivierungszustand.|  
|EINGABETASTE|Führt einen Commit für Änderungen an der aktiven Zelle und die Zeile, und verschiebt den Fokus auf die Zelle direkt unterhalb der aktuellen Zelle. Wenn der Fokus in der letzten Zeile befindet, führt einen Commit für Änderungen ohne den Fokus zu verschieben.|  
|ESC|Wenn das Steuerelement im Bearbeitungsmodus befindet, wird die Bearbeitung abgebrochen. Wenn das Steuerelement nicht im Bearbeitungsmodus befindet, wird zurückgesetzt, die mit der aktuellen Zeile vorgenommen wurden, wenn das Steuerelement an eine Datenquelle gebunden ist, die Bearbeitung unterstützt Änderungen oder des Virtueller Modus mit Commit auf Zeilenebene Bereich implementiert wurde.|  
|RÜCKTASTE|Löscht das Zeichen vor der Einfügemarke an, beim Bearbeiten einer Zelle.|  
|DELETE|Löscht das Zeichen nach der Einfügemarke an, beim Bearbeiten einer Zelle.|  
|STRG+EINGABE|Führt einen Commit für Änderungen an der aktuellen Zelle ohne den Fokus zu verschieben. Auch auf Zeilenebene Commits für Änderungen an der aktuellen Zeile, wenn das Steuerelement an eine Datenquelle gebunden ist, die Bearbeitung oder der virtuelle Modus unterstützt mit implementiert wurde Commit-Bereich.|  
|STRG+0|Gibt eine <xref:System.DBNull.Value?displayProperty=nameWithType> Wert in der aktiven Zelle, wenn die Zelle bearbeitet werden kann. Wird standardmäßig der Anzeigewert für eine <xref:System.DBNull> Zellwert ist der Wert des der <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridViewCellStyle> faktisch für die aktuelle Zelle.|  
  
### <a name="selection-keys"></a>Auswahl-Schlüssel

 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaftensatz auf `false` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, Ändern der aktiven Zelle die Tasten für die Navigation mit die Auswahl in die neue Zelle ändert. Die UMSCHALTTASTE, STRG und ALT-Tasten wirken sich nicht auf dieses Verhalten aus.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, das gleiche Verhalten tritt auf, jedoch mit den folgenden Ergänzungen.  
  
|Schlüssel oder eine Tastenkombination|Beschreibung|  
|----------------------------|-----------------|  
|UMSCHALT + LEERTASTE|Wählt die vollständige Zeile oder Spalte (identisch mit der Zeilen- oder Spaltenüberschrift klicken).|  
|Navigationstaste (-Taste, Seite nach oben/unten, POS1, Ende)|Wenn eine vollständige Zeile oder Spalte ausgewählt ist, wird die aktive Zelle in einer neuen Zeile oder Spalte ändern die Auswahl, die vollständig neue Zeile oder Spalte (je nach Auswahlmodus) verschoben.|  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> festgelegt ist, um `false` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, ändern die aktive Zelle in einer neuen Zeile oder Spalte mithilfe der Tastatur, die vollständig neue Zeile oder Spalte wird die Auswahl verschoben. Die UMSCHALTTASTE, STRG und ALT-Tasten wirken sich nicht auf dieses Verhalten aus.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> festgelegt ist, um `true`, das Verhalten ändert sich nicht, aber bei gedrückter Umschalttaste (einschließlich STRG + UMSCHALT) über die Tastatur navigiert, wird eine Auswahl von mehreren Zelle ändern. Vor der Navigation markiert das Steuerelement die aktuelle Zelle als Ankerzelle an. Wenn Sie bei gedrückter Umschalttaste navigieren, umfasst die Auswahl aller Zellen zwischen der Ankerzelle und der aktuellen Zelle. Andere Zellen im Steuerelement bleibt ausgewählt, wenn sie bereits ausgewählt wurden, aber sie nicht ausgewählt sind können, die Tastaturnavigation sie vorübergehend zwischen der Ankerzelle und der aktuellen Zelle versetzt.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> festgelegt ist, um `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, das Verhalten der Ankerzelle und der aktuellen Zelle ist identisch, aber nur ganze Zeilen oder Spalten aktiviert oder deaktiviert werden.  
  
## <a name="default-mouse-handling"></a>Standardbehandlung von Maus
  
### <a name="basic-mouse-handling"></a>Grundlegende Mausbehandlung
  
> [!NOTE]
>  Klicken auf eine Zelle mit der linken Maustaste immer ändert die aktuelle Zelle. Auf eine Zelle mit der rechten Maustaste klicken wird ein Kontextmenü geöffnet, wenn ein solcher verfügbar ist.  
  
|Mausaktionen|Beschreibung|  
|------------------|-----------------|  
|Linke Maustaste unten|Macht der angeklickte Zelle die aktiven Zelle, und löst die <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> Ereignis.|  
|Linke Maustaste oben|Löst das <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>-Ereignis aus.|  
|Linken Maustaste klicken|Löst das <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> und <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> Ereignisse|  
|Linke Maustaste, und ziehen Sie auf eine Spaltenheaderzelle|Wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> Eigenschaft `true`, verschiebt die Spalte, damit sie eine neue Position abgelegt werden kann.|  
  
### <a name="mouse-selection"></a>Auswahl der Maus

 Ohne das Verhalten der Funktionsauswahl bezieht sich auf die mittlere Maustaste oder das Mausrad.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> -Eigenschaftensatz auf `false` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, tritt das folgende Verhalten auf.  
  
|Mausaktionen|Beschreibung|  
|------------------|-----------------|  
|Klicken Sie auf die linke Maustaste gedrückt|Wählt nur die aktive Zelle aus, wenn der Benutzer auf eine Zelle klickt. Kein Auswahlverhalten, wenn der Benutzer eine Zeile oder einen Spaltenheader klickt.|  
|Klicken Sie auf die rechte Maustaste|Wird ein Kontextmenü angezeigt, sofern verfügbar.|  
  
 Das gleiche Verhalten tritt auf, wenn die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, außer dass, je nach Auswahlmodus, klicken auf einen Zeilen- oder Spaltenüberschrift wird die ganze Zeile oder Spalte auswählen und legen Sie die aktive Zelle zur ersten Zelle in der Zeile oder Spalte.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, klicken auf eine beliebige Zelle in einer Zeile oder Spalte wird die ganze Zeile oder Spalte ausgewählt.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> festgelegt ist, um `true`, auf eine Zelle bei gedrückter STRG- bzw. Umschalttaste Klicken, wird eine Auswahl mehrerer Zelle ändern.  
  
 Wenn Sie eine Zelle klicken, während Sie die STRG-Taste drücken, ändert sich der Auswahlzustand die Zelle, während alle anderen Zellen mit den aktuellen Auswahlzustand beibehalten.  
  
 Wenn Sie einer Zelle oder von einer Reihe von Zellen klicken bei gedrückter UMSCHALTTASTE, umfasst die Auswahl zwischen der aktuellen Zelle und einer Ankerzelle befindet sich an der Position der aktuellen Zelle vor der ersten auf alle Zellen aus. Wenn Sie klicken und ziehen Sie den Mauszeiger über mehrere Zellen, ist die Ankerzelle die Zelle geklickt haben, am Anfang des Ziehvorgangs. Nachfolgende Klicken bei gedrückter Umschalttaste Ändern der aktiven Zelle, aber nicht die Ankerzelle. Andere Zellen im Steuerelement bleibt ausgewählt, wenn sie bereits ausgewählt wurden, aber möglicherweise nicht ausgewählte werden Maus Navigation sie vorübergehend zwischen der Ankerzelle und der aktuellen Zelle versetzt.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> festgelegt ist, um `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf festgelegt ist <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, auf einen Zeilen- oder Spaltenüberschrift (je nach Auswahlmodus) bei gedrückter UMSCHALTTASTE wird eine vorhandene Auswahl ganzer Zeilen oder Spalten ändern, wenn eine solche ein Auswahl vorhanden ist. Andernfalls wird es heben Sie die Auswahl und starten eine neue Auswahl ganzer Zeilen oder Spalten. Auf einen Zeilen- oder Spaltenüberschrift beim Drücken von STRG, jedoch wird hinzufügen oder entfernen, die Sie geklickt haben, Zeile oder Spalte in der aktuellen Auswahl ohne Weise Bearbeiten der aktuellen Auswahl.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> festgelegt ist, um `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> festgelegt ist, um <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, auf eine Zelle klicken, während der STRG-oder UMSCHALTTASTE verhält sich genauso außer, dass nur vollständige Zeilen und Spalten sind betroffen.  
  
## <a name="see-also"></a>Siehe auch

<xref:System.Windows.Forms.DataGridView>  
 [DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
