---
title: "Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Daten [Windows Forms], Anzeigemodi"
  - "Datenblätter, Anzeigemodi"
  - "DataGridView-Steuerelement [Windows Forms], Anzeigemodi"
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement kann Daten in drei verschiedenen Modi anzeigen: gebunden, ungebunden und virtuell.  Wählen Sie den für Ihre Anforderungen geeignetesten Modus aus.  
  
## Ungebunden  
 Der Ungebunden\-Modus eignet sich zur Anzeige relativ kleiner Datenmengen, die Sie programmgesteuert verwalten.  Sie fügen das <xref:System.Windows.Forms.DataGridView>\-Steuerelement nicht wie im Gebunden\-Modus direkt an eine Datenquelle an.  Stattdessen müssen Sie das Steuerelement selbst füllen. Hierfür verwenden Sie normalerweise die <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName>\-Methode.  
  
 Der Ungebunden\-Modus eignet sich insbesondere für statische, schreibgeschützte Daten oder wenn Sie Ihren eigenen Code bereitstellen möchten, der mit einem externen Datastore interagiert.  Wenn Sie den Benutzern die Interaktion mit einer externen Datenquelle ermöglichen möchten, verwenden Sie aber in der Regel den Gebunden\-Modus.  
  
 Ein Beispiel für eine schreibgeschützte, ungebundene <xref:System.Windows.Forms.DataGridView> finden Sie unter [Gewusst wie: Erstellen eines ungebundenen DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## Gebunden  
 Der Gebunden\-Modus eignet sich zur Verwaltung von Daten mithilfe der automatischen Interaktion mit dem Datenspeicher.  Sie können das <xref:System.Windows.Forms.DataGridView>\-Steuerelement direkt an seine Datenquelle anfügen, indem Sie die <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft festlegen.  Wenn das Steuerelement datengebunden ist, werden Datenzeilen ohne explizite Verwaltung Ihrerseits abgelegt und abgerufen.  Wenn die <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>\-Eigenschaft `true` lautet, wird für jede Spalte in der Datenquelle eine entsprechende Spalte im Steuerelement erstellt.  Wenn Sie lieber Ihre eigenen Spalten erstellen möchten, können Sie diese Eigenschaft auf `false` festlegen und mit der <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A>\-Eigenschaft jede Spalte beim Konfigurieren binden.  Dies ist hilfreich, wenn Sie einen anderen Spaltentyp verwenden möchten als die Typen, die standardmäßig generiert werden.  Weitere Informationen finden Sie unter [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).  
  
 Ein Beispiel für ein gebundenes <xref:System.Windows.Forms.DataGridView>\-Steuerelement finden Sie unter [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 Sie können einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement im Gebunden\-Modus auch ungebundene Spalten hinzufügen.  Dies empfiehlt sich, wenn Sie eine Spalte mit Schaltflächen oder Links anzeigen möchten, durch die Aktionen für bestimmte Zeilen ausgeführt werden können.  Außerdem ist es hilfreich, Spalten mit Werten anzuzeigen, die anhand von gebundenen Spalten berechnet wurden.  Sie können die Zellenwerte für berechnete Spalten in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis füllen.  Wenn Sie <xref:System.Data.DataSet> oder <xref:System.Data.DataTable> als Datenquelle verwenden, sollten Sie jedoch mit der <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName>\-Eigenschaft eine berechnete Spalte erstellen.  In diesem Fall behandelt das <xref:System.Windows.Forms.DataGridView>\-Steuerelement berechnete Spalten ebenso wie andere Spalten in der Datenquelle.  
  
 Das Sortieren nach ungebundenen Spalten im Gebunden\-Modus wird nicht unterstützt.  Wenn Sie im Gebunden\-Modus eine ungebundene Spalte erstellen, die vom Benutzer anpassbare Werte enthält, müssen Sie den virtuellen Modus implementieren, damit diese Werte erhalten bleiben, wenn das Steuerelement nach einer gebundenen Spalte sortiert wird.  
  
## Virtual  
 Mit dem virtuellen Modus können Sie Ihre eigenen Datenverwaltungsoperationen implementieren.  Dies ist erforderlich, um die Werte von ungebundenen Spalten im Gebunden\-Modus zu erhalten, wenn das Steuerelement nach gebundenen Spalten sortiert wird.  Der Hauptverwendungszweck des virtuellen Modus besteht jedoch darin, die Leistung bei der Interaktion mit großen Datenmengen zu optimieren.  
  
 Sie fügen das <xref:System.Windows.Forms.DataGridView>\-Steuerelement an einen von Ihnen verwalteten Cache an, und das Steuerelement bestimmt, wann Daten abgelegt und abgerufen werden.  Um die Speicherbeanspruchung gering zu halten, sollte der Cache eine ähnliche Größe wie die Anzahl der aktuelle angezeigten Zeilen haben.  Wenn der Benutzer per Bildlauf neue Zeilen anzeigt, fragt der Code neue Daten aus dem Cache ab, und löscht optional alte Daten aus dem Speicher.  
  
 Wenn Sie den virtuellen Modus implementieren, müssen Sie verfolgen, wann eine neue Zeile erforderlich ist und wann sie wieder entfernt werden kann.  Die genaue Implementierung dieser Funktion hängt von der Implementierung des Datenmodells und seiner Transaktionssemantik ab, d. h. ob sich der Commit\-Bereich auf Zellenebene oder Zeilenebene befindet.  
  
 Weitere Informationen zum virtuellen Modus finden Sie unter [Virtueller Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  Ein Beispiel, das zeigt, wie Ereignisse des virtuellen Modus verwendet werden, finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=fullName>   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)   
 [Gewusst wie: Binden von Daten an das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)   
 [Virtueller Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)