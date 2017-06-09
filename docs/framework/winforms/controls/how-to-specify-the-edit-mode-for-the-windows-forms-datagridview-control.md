---
title: "Gewusst wie: Festlegen des Bearbeitungsmodus f&#252;r das DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Bearbeitungsmodus"
  - "DataGridView-Steuerelement [Windows Forms], Bearbeitungsmodus"
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Festlegen des Bearbeitungsmodus f&#252;r das DataGridView-Steuerelement in Windows Forms
Standardmäßig können Benutzer den Inhalt der aktuellen <xref:System.Windows.Forms.DataGridView>\-Textfeldzelle bearbeiten, indem Sie Eingaben darin vornehmen oder F2 drücken.  Dadurch wird für die Zelle der Bearbeitungsmodus aktiviert, sofern alle der folgenden Bedingungen erfüllt sind:  
  
-   Die zugrunde liegende Datenquelle unterstützt Bearbeitungen.  
  
-   Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ist aktiviert.  
  
-   Der <xref:System.Windows.Forms.DataGridView.EditMode%2A>\-Eigenschaftswert lautet nicht <xref:System.Windows.Forms.DataGridViewEditMode>.  
  
-   Die `ReadOnly`\-Eigenschaften von Zelle, Zeile, Spalte und Steuerelement sind alle auf `false` festgelegt.  
  
 Im Bearbeitungsmodus kann der Benutzer den Zellenwert ändern und die EINGABETASTE drücken, um die Änderung zu übernehmen, oder die ESC\-TASTE drücken, um den ursprünglichen Zellenwert wiederherzustellen.  
  
 Sie können ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement so konfigurieren, dass für die Zelle der Bearbeitungsmodus aktiviert wird, sobald sie aktiv ist.  In diesem Fall ist das Verhalten der EINGABETASTE und der ESC\-TASTE unverändert. Die Zelle bleibt jedoch auch dann noch im Bearbeitungsmodus, wenn der Wert übernommen oder zurückgesetzt wurde.  Sie können das Steuerelement auch so konfigurieren, dass für die Zelle nur dann der Bearbeitungsmodus aktiviert wird, wenn etwas in die Zelle eingegeben oder F2 gedrückt wird.  Schließlich können Sie verhindern, dass für Zellen der Bearbeitungsmodus aktiviert wird, außer beim Aufrufen der <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>\-Methode.  
  
### So ändern Sie den Bearbeitungsmodus eines DataGridView\-Steuerelements  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName>\-Eigenschaft auf die geeignete <xref:System.Windows.Forms.DataGridViewEditMode>\-Enumeration fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Verweise auf die <xref:System>\-Assembly und die <xref:System.Windows.Forms>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName>   
 [Dateneingabe im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)