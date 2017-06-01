---
title: "Gewusst wie: Festlegen der Sortierungsmodi f&#252;r Spalten im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Sortieren von Daten"
  - "DataGridView-Steuerelement [Windows Forms], Sortiermodus"
  - "Sortieren, Datenblätter"
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Festlegen der Sortierungsmodi f&#252;r Spalten im DataGridView-Steuerelement in Windows Forms
Im <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwenden Textfeldspalten standardmäßig die automatische Sortierung, während andere Spaltentypen nicht automatisch sortiert werden.  Gelegentlich möchten Sie diese Vorgaben überschreiben.  Beispielsweise können Sie Bilder anstelle von Text, Zahlen oder Enumerationszellenwerten anzeigen.  Die Bilder können zwar nicht sortiert werden, die zugrunde liegenden Werte, die sie darstellen, aber schon.  
  
 Im <xref:System.Windows.Forms.DataGridView>\-Steuerelement bestimmt der <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>\-Eigenschaftswert einer Spalte ihr Sortierverhalten.  
  
 In der folgenden Prozedur wird die `Priority`\-Spalte aus [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md) gezeigt.  Diese Spalte ist eine Bildspalte und wird standardmäßig nicht sortiert.  Sie enthält eigentliche Zellenwerte, die jedoch Zeichenfolgen sind und somit automatisch sortiert werden können.  
  
### So legen Sie den Sortiermodus für eine Spalte fest  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>\-Eigenschaft fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte mit dem Namen `Priority` enthält.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 [Sortieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Spaltenssortiermodi im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Anpassen der Sortierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)