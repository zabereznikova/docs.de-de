---
title: "Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataGrid [WPF], Tastaturverhalten"
  - "DataGrid [WPF], Mausverhalten"
  - "Tastaturverhalten [WPF], DataGrid"
  - "Mausverhalten [WPF], DataGrid"
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Standardverhalten von Tastatur und Maus im DataGrid-Steuerelement
In diesem Thema wird beschrieben, wie Benutzer über eine Tastatur und eine Maus mit dem <xref:System.Windows.Controls.DataGrid>\-Steuerelement interagieren können.  
  
 Typische Interaktionen mit <xref:System.Windows.Controls.DataGrid> umfassen die Navigation, Auswahl und das Bearbeiten.  Das Auswahlverhalten wird durch die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>\- und <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>\-Eigenschaften beeinflusst.  Die Standardwerte, die das Verhalten verursachen, das in diesem Thema beschrieben wird, sind <xref:System.Windows.Controls.DataGridSelectionMode?displayProperty=fullName> und <xref:System.Windows.Controls.DataGridSelectionUnit?displayProperty=fullName>.  Das Ändern dieser Werte kann zu Verhalten führen, das vom beschriebenen abweicht.  Wenn sich eine Zelle im Bearbeitungsmodus befindet, überschreibt das Bearbeitungssteuerelement möglicherweise das Standardtastaturverhalten von <xref:System.Windows.Controls.DataGrid>.  
  
## Standardtastaturverhalten  
 In der folgenden Tabelle wird das Standardtastaturverhalten für das <xref:System.Windows.Controls.DataGrid> dargestellt.  
  
|Taste oder Tastenkombination|Beschreibung|  
|----------------------------------|------------------|  
|NACH\-UNTEN\-TASTE|Verschiebt den Fokus in die Zelle direkt unter der aktuellen Zelle.  Wenn sich der Fokus in der letzten Zeile befindet, hat das Drücken der NACH\-UNTEN\-TASTE keine Auswirkungen.|  
|NACH\-OBEN\-TASTE|Verschiebt den Fokus in die Zelle direkt über der aktuellen Zelle.  Wenn sich der Fokus in der ersten Zeile befindet, hat das Drücken der NACH\-OBEN\-TASTE keine Auswirkungen.|  
|NACH\-LINKS|Verschiebt den Fokus in die vorherige Zelle der Zeile.  Wenn sich der Fokus in der ersten Zelle der Zeile befindet, hat das Drücken der NACH\-LINKS\-TASTE keine Auswirkungen.|  
|NACH\-RECHTS|Verschiebt den Fokus in die nächste Zelle der Zeile.  Wenn sich der Fokus in der letzten Zelle der Zeile befindet, hat das Drücken der NACH\-RECHTS\-TASTE keine Auswirkungen.|  
|POS1|Verschiebt den Fokus in die erste Zelle der aktuellen Zeile.|  
|ENDE|Verschiebt den Fokus in die letzte Zelle der aktuellen Zeile.|  
|BILD\-AB|Wenn Zeilen nicht gruppiert werden, wird für das Steuerelement einen Bildlauf nach unten um die Anzahl Zeilen durchgeführt, die vollständig angezeigt werden.  Verschiebt den Fokus in die letzte vollständig angezeigte Zeile, ohne Spalten zu ändern.<br /><br /> Wenn Zeilen gruppiert werden, wird der Fokus in die letzte Zeile im <xref:System.Windows.Controls.DataGrid> verschoben, ohne Spalten zu ändern.|  
|BILD\-AUF|Wenn Zeilen nicht gruppiert werden, wird für das Steuerelement einen Bildlauf nach oben um die Anzahl Zeilen durchgeführt, die vollständig angezeigt werden.  Verschiebt den Fokus in die erste angezeigte Zeile, ohne Spalten zu ändern.<br /><br /> Wenn Zeilen gruppiert werden, wird der Fokus in die erste Zeile im <xref:System.Windows.Controls.DataGrid> verschoben, ohne Spalten zu ändern.|  
|TAB|Verschiebt den Fokus in die nächste Zelle der aktuellen Zeile.  Wenn sich der Fokus in der letzten Zelle der Zeile befindet, wird der Fokus in die erste Zelle der nächsten Zeile verschoben.  Befindet sich der Fokus in der letzten Zelle des Steuerelements, wird der Fokus in das nächste Steuerelement in der Aktivierreihenfolge des übergeordneten Containers verschoben.<br /><br /> Wenn sich die aktuelle Zelle im Bearbeitungsmodus befindet und durch Drücken der TAB\-TASTE der Fokus von der aktuellen Zeile weg verschoben wird, werden alle Änderungen der Zeile übernommen, bevor der Fokus geändert wird.|  
|UMSCHALT\+TAB|Verschiebt den Fokus in die vorherige Zelle der aktuellen Zeile.  Wenn sich der Fokus bereits in der ersten Zelle der Zeile befindet, wird der Fokus in die letzte Zelle der nächsten Zeile verschoben.  Befindet sich der Fokus in der ersten Zelle des Steuerelements, wird der Fokus in das vorherige Steuerelement in der Aktivierreihenfolge des übergeordneten Containers verschoben.<br /><br /> Wenn sich die aktuelle Zelle im Bearbeitungsmodus befindet und durch Drücken der TAB\-TASTE der Fokus von der aktuellen Zeile weg verschoben wird, werden alle Änderungen der Zeile übernommen, bevor der Fokus geändert wird.|  
|STRG\+NACH\-UNTEN|Verschiebt den Fokus in die letzte Zelle der aktuellen Spalte.|  
|STRG\+NACH\-OBEN|Verschiebt den Fokus in die erste Zelle der aktuellen Spalte.|  
|STRG\+NACH\-RECHTS|Verschiebt den Fokus in die letzte Zelle der aktuellen Zeile.|  
|STRG\+NACH\-LINKS|Verschiebt den Fokus in die erste Zelle der aktuellen Zeile.|  
|STRG\+POS1|Verschiebt den Fokus in die erste Zelle im Steuerelement.|  
|STRG\+ENDE|Verschiebt den Fokus in die letzte Zelle im Steuerelement.|  
|STRG\+BILD\-AB|Siehe BILD\-AB|  
|STRG\+BILD\-AUF|Siehe BILD\-AUF.|  
|F2|Legt für die aktuelle Zelle den Zellenbearbeitungsmodus fest, wenn die <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=fullName>\-Eigenschaft für die aktuelle Spalte `false` und die <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=fullName>\-Eigenschaft `false` ist.|  
|EINGABETASTE|Speichert Änderungen an der aktuellen Zelle und Zeile und verschiebt den Fokus in die Zelle direkt unter der aktuellen Zelle.  Wenn sich der Fokus in der letzten Zeile befindet, werden alle Änderungen gespeichert, ohne den Fokus zu verschieben.|  
|ESC|Bricht die Bearbeitung ab und macht alle Änderungen am Steuerelement rückgängig, wenn sich das Steuerelement im Bearbeitungsmodus befindet.  Wenn <xref:System.ComponentModel.IEditableObject> von der zugrunde liegenden Datenquelle implementiert wird, wird der Bearbeitungsmodus für die gesamte Zeile durch erneutes Drücken von ESC abgebrochen.|  
|RÜCKTASTE|Löscht das Zeichen vor dem Cursor beim Bearbeiten einer Zelle.|  
|ENTFERNEN|Löscht das Zeichen nach dem Cursor beim Bearbeiten einer Zelle.|  
|STRG\+EINGABE|Speichert sämtliche Änderungen an der aktuellen Zelle, ohne den Fokus zu verschieben.|  
|STRG\+A|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> auf <xref:System.Windows.Controls.DataGridSelectionMode> festgelegt ist, werden alle Zeilen in <xref:System.Windows.Controls.DataGrid> ausgewählt.|  
  
## Auswahltasten  
 Wenn die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>\-Eigenschaft auf <xref:System.Windows.Controls.DataGridSelectionMode> festgelegt ist, ändert sich das Navigationsverhalten nicht. Wenn Sie jedoch mit der Tastatur navigieren und dabei die UMSCHALTTASTE \(bzw. STRG\+UMSCHALT\) drücken, können Sie die Auswahl mehrerer Zeilen ändern.  Vor der Navigation markiert das Steuerelement die aktuelle Zeile als Ankerzeile.  Wenn Sie navigieren und dabei die UMSCHALTTASTE drücken, schließt die Auswahl alle Zeilen zwischen der Ankerzeile und der aktuellen Zeile ein.  
  
 Die folgenden Tastenkombinationen ändern die Auswahl für mehrere Zeilen.  
  
-   UMSCHALT\+NACH\-UNTEN  
  
-   UMSCHALT\+NACH\-OBEN  
  
-   UMSCHALT\+BILD\-AB  
  
-   UMSCHALT\+BILD\-AUF  
  
-   STRG\+UMSCHALT\+NACH\-UNTEN  
  
-   STRG\+UMSCHALT\+NACH\-OBEN  
  
-   STRG\+UMSCHALT\+POS1  
  
-   STRG\+UMSCHALT\+ENDE  
  
## Standardmausverhalten  
 In der folgenden Tabelle wird das Standardmausverhalten für das <xref:System.Windows.Controls.DataGrid> dargestellt.  
  
|Mausaktion|Beschreibung|  
|----------------|------------------|  
|Klicken Sie auf eine nicht ausgewählte Zeile.|Macht die Zeile, in die geklickt wird, zur aktuellen Zeile und die Zelle, in die geklickt wird, zur aktuellen Zelle.|  
|Klicken auf die aktive Zelle|Versetzt die aktuelle Zelle in den Bearbeitungsmodus.|  
|Ziehen einer Spaltenheaderzelle|Verschiebt die Spalte, sodass sie an einer neuen Position abgelegt werden kann, wenn die <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=fullName>\-Eigenschaft für die aktuelle Spalte `true` und die <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=fullName>\-Eigenschaft `true` ist.|  
|Ziehen eines Spaltenheadertrennzeichens|Ändert die Größe der Spalte, wenn die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName>\-Eigenschaft für die aktuelle Spalte `true` und die <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName>\-Eigenschaft `true` ist.|  
|Doppelklick auf ein Spaltenheadertrennzeichen|Wenn die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName>\-Eigenschaft `true` ist und die <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName>\-Eigenschaft für die aktuelle Spalte `true` ist, wird die Größe der Spalte mit dem <xref:System.Windows.Controls.DataGridLength.Auto%2A>\-Größenanpassungsmodus automatisch angepasst.|  
|Klicken auf eine Spaltenheaderzelle|Sortiert die Spalte, wenn die <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=fullName>\-Eigenschaft für die aktuelle Spalte `true` und die <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=fullName>\-Eigenschaft `true` ist.<br /><br /> Wenn Sie auf den Header einer Spalte klicken, die bereits sortiert wurde, wird die Sortierreihenfolge der Spalte umgekehrt.<br /><br /> Wenn Sie die UMSCHALTTASTE drücken, während Sie auf mehrere Spaltenheader klicken, werden die entsprechenden Spalten in die Reihenfolge sortiert, in der auf sie geklickt wurde.|  
|STRG \+ Klicken auf eine Zeile|Ändert die Auswahl mehrerer nicht zusammenhängender Zeilen, wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> auf <xref:System.Windows.Controls.DataGridSelectionMode> festgelegt wird.<br /><br /> Wenn die Zeile bereits ausgewählt wurde, wird die Auswahl aufgehoben.|  
|UMSCHALT \+ Klicken auf eine Zeile|Ändert die Auswahl mehrerer zusammenhängender Zeilen, wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> auf <xref:System.Windows.Controls.DataGridSelectionMode> festgelegt wird.|  
|Klicken auf einen Zeilengruppenheader|Erweitert oder reduziert die Gruppe.|  
|Klicken Sie auf die Schaltfläche "Alle auswählen" in der linken oberen Ecke von <xref:System.Windows.Controls.DataGrid>|Wenn <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> auf <xref:System.Windows.Controls.DataGridSelectionMode> festgelegt ist, werden alle Zeilen in <xref:System.Windows.Controls.DataGrid> ausgewählt.|  
  
## Mausauswahl  
 Wenn die <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>\-Eigenschaft auf <xref:System.Windows.Controls.DataGridSelectionMode> festgelegt ist und Sie bei gedrückter STRG\- oder UMSCHALTTASTE auf eine Zeile klicken, wird die Auswahl mehrerer Zeilen geändert.  
  
 Wenn Sie bei gedrückter STRG\-TASTE auf eine Zeile klicken, ändert sich der Auswahlzustand dieser Zeile, während alle anderen Zeilen den aktuellen Auswahlzustand beibehalten.  Wählen Sie auf diese Weise nicht benachbarte Zeilen aus.  
  
 Wenn Sie bei gedrückter UMSCHALTTASTE auf eine Zeile klicken, umfasst die Auswahl alle Zeilen zwischen der aktuellen Zeile und einer Ankerzeile, die sich an der Position der aktuellen Zeile vor dem Klicken befindet.  Durch anschließendes Klicken bei gedrückter UMSCHALTTASTE ändert sich die aktuelle Zeile, nicht jedoch die Ankerzeile.  Wählen Sie auf diese Weise einen Bereich von benachbarten Zeilen aus.  
  
 STRG\+UMSCHALT kann nicht kombiniert werden, um nicht benachbarte Bereiche von benachbarten Zeilen auszuwählen.  Hierzu wählen Sie den ersten Bereich aus, indem Sie beim Auswählen STRG gedrückt halten, wie weiter oben erläutert.  Verwenden Sie nach dem Auswählen des ersten Bereichs von Zeilen STRG\+Klicken, um die erste Zeile im folgenden Bereich auszuwählen, und klicken Sie dann bei gedrückter STRG\- und UMSCHALTTASTE auf die letzte Zeile im folgenden Bereich.  
  
## Siehe auch  
 <xref:System.Windows.Controls.DataGrid>   
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>