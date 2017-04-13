---
title: "Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datenblätter, Mausbehandlung"
  - "DataGridView-Steuerelement [Windows Forms], Tastaturbehandlung"
  - "DataGridView-Steuerelement [Windows Forms], Mausbehandlung"
  - "DataGridView-Steuerelement [Windows Forms], Navigationstasten"
  - "Tastaturen, Standardbehandlung in DataGridView-Steuerelementen"
  - "Maus, Standardbehandlung in DataGridView-Steuerelementen"
  - "Navigationstasten, DataGridView-Steuerelement"
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms
In den folgenden Tabellen wird beschrieben, wie Benutzer über eine Tastatur und eine Maus mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement interagieren können.  
  
> [!NOTE]
>  Sie können Standardtastaturereignisse behandeln, um das Tastaturverhalten anzupassen, beispielsweise <xref:System.Windows.Forms.Control.KeyDown>.  Im Bearbeitungsmodus treten für das <xref:System.Windows.Forms.DataGridView>\-Steuerelement keine Tastaturereignisse auf, da das Bearbeitungssteuerelement die Tastatureingaben entgegen nimmt.  Um Bearbeitungssteuerelementereignisse zu behandeln, fügen Sie die Handler dem Bearbeitungssteuerelement über einen<xref:System.Windows.Forms.DataGridView.EditingControlShowing>\-Ereignishandler hinzu.  Wahlweise können Sie das Tastaturverhalten auch in einer <xref:System.Windows.Forms.DataGridView>\-Unterklasse anpassen, indem Sie die <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A>\-Methode und die<xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A>\-Methode überschreiben.  
  
## Standardtastaturbehandlung  
  
### Grundlegende Navigations\- und Eingabetasten  
  
|Taste oder Tastenkombination|Beschreibung|  
|----------------------------------|------------------|  
|NACH\-UNTEN\-TASTE|Verschiebt den Fokus in die Zelle direkt unter der aktuellen Zelle.  Wenn sich der Fokus in der letzten Zeile befindet, bewirkt diese Taste nichts.|  
|NACH\-LINKS|Verschiebt den Fokus in die vorherige Zelle der Zeile.  Wenn sich der Fokus in der ersten Zelle der Zeile befindet, bewirkt diese Taste nichts.|  
|NACH\-RECHTS|Verschiebt den Fokus in die nächste Zelle der Zeile.  Wenn sich der Fokus in der letzten Zelle der Zeile befindet, bewirkt diese Taste nichts.|  
|NACH\-OBEN\-TASTE|Verschiebt den Fokus in die Zelle direkt über der aktuellen Zelle.  Wenn sich der Fokus in der ersten Zeile befindet, bewirkt diese Taste nichts.|  
|POS1|Verschiebt den Fokus in die erste Zelle der aktuellen Zeile.|  
|ENDE|Verschiebt den Fokus in die letzte Zelle der aktuellen Zeile.|  
|BILD\-AB|Führt für das Steuerelement einen Bildlauf nach unten um die Anzahl Zeilen durch, die vollständig angezeigt werden.  Verschiebt den Fokus in die letzte vollständig angezeigte Zeile, ohne Spalten zu ändern.|  
|BILD\-AUF|Führt für das Steuerelement einen Bildlauf nach oben um die Anzahl Zeilen durch, die vollständig angezeigt werden.  Verschiebt den Fokus in die erste angezeigte Zeile, ohne Spalten zu ändern.|  
|TAB|Verschiebt den Fokus in die nächste Zelle der aktuellen Zeile, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `false` lautet.  Wenn sich der Fokus bereits in der letzten Zelle der Zeile befindet, wird der Fokus in die erste Zelle der nächsten Zeile verschoben.  Befindet sich der Fokus in der letzten Zelle des Steuerelements, wird der Fokus in das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers verschoben.<br /><br /> Verschiebt den Fokus in das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `true` lautet.|  
|UMSCHALT\+TAB|Verschiebt den Fokus in die vorherige Zelle der aktuellen Zeile, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `false` lautet.  Wenn sich der Fokus bereits in der ersten Zelle der Zeile befindet, wird der Fokus in die letzte Zelle der nächsten Zeile verschoben.  Befindet sich der Fokus in der ersten Zelle des Steuerelements, wird der Fokus in das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers verschoben.<br /><br /> Verschiebt den Fokus in das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `true` lautet.|  
|STRG\+TAB|Verschiebt den Fokus in das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `false` lautet.<br /><br /> Verschiebt den Fokus in die nächste Zelle der aktuellen Zeile, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `true` lautet.  Wenn sich der Fokus bereits in der letzten Zelle der Zeile befindet, wird der Fokus in die erste Zelle der nächsten Zeile verschoben.  Befindet sich der Fokus in der letzten Zelle des Steuerelements, wird der Fokus in das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers verschoben.|  
|STRG\+UMSCHALT \+TAB|Verschiebt den Fokus in das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `false` lautet.<br /><br /> Verschiebt den Fokus in die vorherige Zelle der aktuellen Zeile, wenn der <xref:System.Windows.Forms.DataGridView.StandardTab%2A>\-Eigenschaftswert `true` lautet.  Wenn sich der Fokus bereits in der ersten Zelle der Zeile befindet, wird der Fokus in die letzte Zelle der nächsten Zeile verschoben.  Befindet sich der Fokus in der ersten Zelle des Steuerelements, wird der Fokus in das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers verschoben.|  
|STRG\+PFEILTASTE|Verschiebt den Fokus zur am weitesten entfernten Zelle in Richtung des Pfeils.|  
|STRG\+POS1|Verschiebt den Fokus in die erste Zelle im Steuerelement.|  
|STRG\+ENDE|Verschiebt den Fokus in die letzte Zelle im Steuerelement.|  
|STRG\+BILD\-AUF\/AB|Siehe BILD\-AUF oder BILD\-AB.|  
|F2|Legt für die aktuelle Zelle den Zellenbearbeitungsmodus fest, wenn der <xref:System.Windows.Forms.DataGridView.EditMode%2A>\-Eigenschaftswert <xref:System.Windows.Forms.DataGridViewEditMode> oder <xref:System.Windows.Forms.DataGridViewEditMode> lautet.|  
|F4|Wenn die aktuelle Zelle eine <xref:System.Windows.Forms.DataGridViewComboBoxCell> ist, wird für die Zelle der Bearbeitungsmodus festgelegt und die Dropdownliste angezeigt.|  
|ALT\+NACH\-OBEN\/UNTEN|Wenn die aktuelle Zelle eine <xref:System.Windows.Forms.DataGridViewComboBoxCell> ist, wird für die Zelle der Bearbeitungsmodus festgelegt und die Dropdownliste angezeigt.|  
|LEERTASTE|Wenn die aktuelle Zelle eine <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell> oder <xref:System.Windows.Forms.DataGridViewCheckBoxCell> ist, werden das <xref:System.Windows.Forms.DataGridView.CellClick>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellContentClick>\-Ereignis ausgelöst.  Wenn die aktuelle Zelle eine <xref:System.Windows.Forms.DataGridViewButtonCell> ist, wird zudem die Schaltfläche gedrückt.  Wenn die aktuelle Zelle eine <xref:System.Windows.Forms.DataGridViewCheckBoxCell> ist, wird zudem der Aktivierungszustand geändert.|  
|EINGABETASTE|Speichert Änderungen an der aktuellen Zelle und Zeile und verschiebt den Fokus in die Zelle direkt unter der aktuellen Zelle.  Wenn sich der Fokus in der letzten Zeile befindet, werden alle Änderungen gespeichert, ohne den Fokus zu verschieben.|  
|ESC|Wenn sich das Steuerelement im Bearbeitungsmodus befindet, wird die Bearbeitung abgebrochen.  Befindet sich das Steuerelement nicht im Bearbeitungsmodus, werden Änderungen an der aktuellen Zeile zurückgenommen, wenn das Steuerelement an eine Datenquelle gebunden ist, die Bearbeitung unterstützt, oder ein virtueller Modus mit Speicherbereich auf Zeilenebene implementiert ist.|  
|RÜCKTASTE|Löscht das Zeichen vor der Einfügemarke beim Bearbeiten einer Zelle.|  
|ENTFERNEN|Löscht das Zeichen nach der Einfügemarke beim Bearbeiten einer Zelle.|  
|STRG\+EINGABE|Speichert sämtliche Änderungen an der aktuellen Zelle, ohne den Fokus zu verschieben.  Es werden auch Änderungen an der aktuellen Zeile gespeichert, wenn das Steuerelement an eine Datenquelle gebunden ist, die Bearbeitung unterstützt, oder ein virtueller Modus mit Speicherbereich auf Zeilenebene implementiert ist.|  
|CTRL\+0|Gibt einen <xref:System.DBNull.Value?displayProperty=fullName>\-Wert in die aktuelle Zelle ein, wenn die Zelle bearbeitet werden kann.  Standardmäßig entspricht der Anzeigewert für einen <xref:System.DBNull>\-Zellenwert dem Wert der <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>\-Eigenschaft des für die aktuelle Zelle gültigen <xref:System.Windows.Forms.DataGridViewCellStyle>.|  
  
### Auswahltasten  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>\-Eigenschaft auf `false` und die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist, wird durch Ändern der aktuellen Zelle mit den Navigationstasten die neue Zelle ausgewählt.  Die Tasten UMSCHALT, STRG und ALT beeinflussen dieses Verhalten nicht.  
  
 Wenn der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist, tritt das gleiche Verhalten auf, jedoch mit folgenden Besonderheiten.  
  
|Taste oder Tastenkombination|Beschreibung|  
|----------------------------------|------------------|  
|UMSCHALT\+LEERTASTE|Wählt die ganze Zeile oder Spalte aus \(identisch mit dem Klicken in die Zeile oder den Spaltenheader\).|  
|Navigationstaste \(Pfeiltaste, BILD\-AUF\/AB, POS1, ENDE\)|Wenn eine ganze Zeile oder Spalte ausgewählt ist, wird durch Ändern der aktuellen Zelle in eine neue Zeile oder Spalte die ganze neue Zeile oder Spalte ausgewählt \(je nach Auswahlmodus\).|  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `false` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist, wird durch Ändern der aktuellen Zelle in eine neue Zelle oder Spalte mithilfe der Tastatur die ganze neue Zeile oder Spalte ausgewählt.  Die Tasten UMSCHALT, STRG und ALT beeinflussen dieses Verhalten nicht.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` festgelegt ist, ändert sich das Navigationsverhalten nicht. Wenn Sie aber mit der Tastatur navigieren und dabei die UMSCHALTTASTE \(bzw. STRG\+UMSCHALT\) drücken, können Sie die Auswahl mehrerer Zellen ändern.  Vor der Navigation markiert das Steuerelement die aktuelle Zelle als Ankerzelle.  Wenn Sie navigieren und dabei die UMSCHALTTASTE drücken, schließt die Auswahl alle Zellen zwischen der Ankerzelle und der aktuellen Zelle ein.  Andere Zellen im Steuerelement, die bereits ausgewählt waren, bleiben ausgewählt. Wenn sich diese aber durch die Navigation mit der Tastatur vorübergehend zwischen der Ankerzelle und der aktuellen Zelle befinden, wird ihre Auswahl möglicherweise aufgehoben.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist, ist das Verhalten der Ankerzelle und der aktuellen Zelle gleich, aber es werden nur ganze Zeilen oder Spalten ausgewählt bzw. aus der Auswahl entfernt.  
  
## Standardmausbehandlung  
  
### Grundlegende Mausbehandlung  
  
> [!NOTE]
>  Wenn Sie mit der linken Maustaste in eine Zelle klicken, wird die aktuelle Zelle stets geändert.  Wenn Sie mit der rechten Maustaste in eine Zelle klicken, öffnet sich ein Kontextmenü, sofern verfügbar.  
  
|Mausaktion|Beschreibung|  
|----------------|------------------|  
|Linke Maustaste unten|Macht die Zelle, in die geklickt wird, zur aktuellen Zelle und löst das <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=fullName>\-Ereignis aus.|  
|Linke Maustaste oben|Löst das <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=fullName>\-Ereignis aus.|  
|Linke Maustaste gedrückt|Löst das <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=fullName>\-Ereignis aus.|  
|Linke Maustaste unten und Ziehen in eine Spaltenheaderzelle|Wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName>\-Eigenschaft auf `true` festgelegt ist, wird die Spalte verschoben, sodass sie an einer neuen Position abgelegt werden kann.|  
  
### Mausauswahl  
 Der mittleren Maustaste oder dem Mausrad ist kein Auswahlverhalten zugeordnet.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>\-Eigenschaft auf `false` und die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist, tritt das folgende Verhalten auf.  
  
|Mausaktion|Beschreibung|  
|----------------|------------------|  
|Klicken mit linker Maustaste|Wählt nur die aktuelle Zelle aus, wenn der Benutzer in eine Zelle klickt.  Kein Auswahlverhalten, wenn der Benutzer in eine Zeile oder einen Spaltenheader klickt.|  
|Klicken mit rechter Maustaste|Zeigt ein Kontextmenü an, sofern verfügbar.|  
  
 Das gleiche Verhalten tritt auf, wenn <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist. Die einzige Ausnahme besteht darin, dass beim Klicken in eine Zeile oder einen Spaltenheader je nach Auswahlmodus die ganze Zeile oder Spalte ausgewählt und die aktuelle Zelle auf die erste Zelle in der Zelle oder Spalte festgelegt wird.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist, wird durch Klicken in eine beliebige Zelle in einer Zeile oder Spalte die ganze Zeile oder Spalte ausgewählt.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` festgelegt ist und Sie bei gedrückter STRG\- oder UMSCHALTTASTE in eine Zelle klicken, wird die Auswahl mehrerer Zellen geändert.  
  
 Wenn Sie bei gedrückter STRG\-TASTE in eine Zelle klicken, ändert sich der Auswahlzustand dieser Zelle, während alle anderen Zellen den aktuellen Auswahlzustand beibehalten.  
  
 Wenn Sie bei gedrückter UMSCHALTTASTE in eine Zelle oder eine Abfolge von Zellen klicken, umfasst die Auswahl alle Zellen zwischen der aktuellen Zelle und einer Ankerzelle, die sich an der Position der aktuellen Zelle vor dem ersten Klick befindet.  Wenn Sie den Mauszeiger bei gedrückter Maustaste über mehrere Zellen ziehen, ist die Ankerzelle die Zelle, in die Sie zu Beginn des Ziehvorgangs klicken.  Anschließende Klicks bei gedrückter UMSCHALTTASTE ändern die aktuelle Zelle, aber nicht die Ankerzelle.  Andere Zellen im Steuerelement, die bereits ausgewählt waren, bleiben ausgewählt. Wenn sich diese aber durch die Navigation mit der Maus vorübergehend zwischen der Ankerzelle und der aktuellen Zelle befinden, wird ihre Auswahl möglicherweise aufgehoben.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist und Sie bei gedrückter UMSCHALTTASTE in eine Zeile oder einen Spaltenheader \(je nach Auswahlmodus\) klicken, wird eine vorhandene Auswahl ganzer Zeilen oder Spalten geändert, sofern vorhanden.  Andernfalls wird die Auswahl gelöscht und eine neue Auswahl ganzer Zeilen oder Spalten vorgenommen.  Wenn Sie jedoch bei gedrückter STRG\-TASTE in eine Zeile oder einen Spaltenheader klicken, wird die Zeile oder Spalte, in die Sie geklickt haben, der aktuellen Auswahl hinzugefügt bzw. daraus entfernt, ohne die aktuelle Auswahl auf andere Weise zu ändern.  
  
 Wenn <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> auf `true` und <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festgelegt ist, ruft das Klicken in eine Zelle bei gedrückter STRG\- oder UMSCHALTTASTE das gleiche Verhalten hervor, abgesehen davon, dass nur ganze Zeilen und Spalten betroffen sind.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)