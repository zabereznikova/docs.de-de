---
title: "Auswahlmodi im DataGridView-Steuerelement von Windows Forms | Microsoft Docs"
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
  - "DataGridView-Steuerelement [Windows Forms], Auswahlmodus"
  - "Auswahl, Modi im DataGridView-Steuerelement"
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Auswahlmodi im DataGridView-Steuerelement von Windows Forms
Zeitweise ist es erforderlich, dass eine Anwendung auf Benutzerauswahlen basierende Aktionen innerhalb eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements ausführt.  Abhängig von den Aktionen möchten Sie die möglichen Auswahlen vielleicht beschränken.  Angenommen, die Anwendung kann einen Bericht für den aktuell ausgewählten Datensatz ausgeben.  In diesem Fall können Sie das <xref:System.Windows.Forms.DataGridView>\-Steuerelement so konfigurieren, dass beim Klicken in eine Zeile immer die gesamte Zeile ausgewählt wird. Folglich kann immer nur diese eine Zeile ausgewählt werden.  
  
 Sie können die zulässigen Auswahlen angeben, indem Sie die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>\-Eigenschaft auf einen der folgenden <xref:System.Windows.Forms.DataGridViewSelectionMode>\-Enumerationswerte festlegen.  
  
|DataGridViewSelectionMode\-Wert|Beschreibung|  
|-------------------------------------|------------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Durch Klicken auf eine Zelle wird diese ausgewählt.  Zeilen\- und Spaltenheader können nicht zum Auswählen verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Durch Klicken auf eine Zelle wird diese ausgewählt.  Durch Klicken auf einen Spaltenheader wird die gesamte Spalte ausgewählt.  Spaltenheader können nicht zum Sortieren verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Durch Klicken auf eine Zelle oder einen Spaltenheader wird die gesamte Spalte ausgewählt.  Spaltenheader können nicht zum Sortieren verwendet werden.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Durch Klicken auf eine Zelle oder einen Zeilenheader wird die gesamte Zeile ausgewählt.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Standardauswahlmodus.  Durch Klicken auf eine Zelle wird diese ausgewählt.  Durch Klicken auf einen Zeilenheader wird die gesamte Zeile ausgewählt.|  
  
> [!NOTE]
>  Durch Änderung des Auswahlmodus zur Laufzeit wird die aktuelle Auswahl automatisch aufgehoben.  
  
 Benutzer können standardmäßig mehrere Zeilen, Spalten oder Zellen auswählen, indem sie den Mauszeiger ziehen und während der Auswahl die STRG\- oder UMSCHALTTASTE gedrückt halten, um die Auswahl zu erweitern bzw. zu ändern. Alternativ können sie auf die obere linke Headerzelle klicken, um sämtliche Zellen im Steuerelement auszuwählen.  Legen Sie die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>\-Eigenschaft auf den Wert `false` fest, um dieses Verhalten zu vermeiden.  
  
 Im <xref:System.Windows.Forms.DataGridViewSelectionMode>\-Modus und im <xref:System.Windows.Forms.DataGridViewSelectionMode>\-Modus können Benutzer Zeilen löschen, indem Sie sie auswählen und die ENTF\-TASTE drücken.  Benutzer können Zeilen nur dann löschen, wenn sich die aktuelle Zelle nicht im Bearbeitungsmodus befindet, die <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A>\-Eigenschaft auf `true` festgelegt ist und die zugrunde liegende Datenquelle das Löschen von Zeilen durch Benutzer unterstützt.  Beachten Sie, dass das programmgesteuerte Löschen von Zeilen durch diese Einstellungen nicht verhindert wird.  
  
## Programmgesteuerte Auswahl  
 Der aktuelle Auswahlmodus beschränkt das Verhalten bei der programmgesteuerten Auswahl sowie bei der Benutzerauswahl.  Sie können die aktuelle Auswahl programmgesteuert ändern, indem Sie die `Selected`\-Eigenschaft beliebiger Zellen, Zeilen oder Spalten im <xref:System.Windows.Forms.DataGridView>\-Steuerelement festlegen.  Außerdem können Sie abhängig vom Auswahlmodus alle im Steuerelement enthaltenen Zellen mithilfe der <xref:System.Windows.Forms.DataGridView.SelectAll%2A>\-Methode auswählen.  Um die Auswahl aufzuheben, verwenden Sie die <xref:System.Windows.Forms.DataGridView.ClearSelection%2A>\-Methode.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>\-Eigenschaft auf `true` festgelegt ist, können Sie der Auswahl <xref:System.Windows.Forms.DataGridView>\-Elemente hinzufügen oder diese daraus entfernen, indem Sie die `Selected`\-Eigenschaft des Elements ändern.  Wenn Sie die `Selected`\-Eigenschaft für ein Element in einem anderen Fall auf `true` festlegen, werden andere Elemente automatisch aus der Auswahl entfernt.  
  
 Beachten Sie, dass die aktuelle Auswahl durch eine Änderung des Werts der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>\-Eigenschaft nicht geändert wird.  
  
 Eine Auflistung der momentan ausgewählten Zellen, Zeilen oder Spalten können Sie über die Eigenschaften <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> des <xref:System.Windows.Forms.DataGridView>\-Steuerelements abrufen.  Der Zugriff auf diese Eigenschaften ist ineffizient, wenn jede Zelle im Steuerelement ausgewählt ist.  Um in diesem Fall Leistungseinbußen zu vermeiden, verwenden Sie zuerst die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>\-Methode.  Außerdem kann sich der Zugriff auf diese Auflistungen als ineffizient erweisen, wenn die Anzahl der ausgewählten Zellen, Zeilen oder Spalten ermittelt werden soll.  Sie sollten stattdessen die Methode <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A> oder <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> verwenden und den <xref:System.Windows.Forms.DataGridViewElementStates>\-Wert übergeben.  
  
> [!TIP]
>  Beispielcode zur Veranschaulichung der programmgesteuerten Verwendung ausgewählter Zellen finden Sie in der Übersicht über die <xref:System.Windows.Forms.DataGridView>\-Klasse.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridViewSelectionMode>   
 [Verwendung von Auswahl und Zwischenablage mit dem DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen des Auswahlmodus des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)