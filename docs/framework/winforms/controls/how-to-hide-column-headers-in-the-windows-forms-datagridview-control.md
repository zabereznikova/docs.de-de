---
title: "Gewusst wie: Ausblenden von Spaltenheadern im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Spaltenheader, Ausblenden"
  - "Spalten [Windows Forms], Ausblenden von Spaltenheadern"
  - "DataGridView-Steuerelement [Windows Forms], Spaltenheader"
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Ausblenden von Spaltenheadern im DataGridView-Steuerelement in Windows Forms
Gelegentlich möchten Sie eine <xref:System.Windows.Forms.DataGridView> ohne Spaltenheader anzeigen.  Im <xref:System.Windows.Forms.DataGridView>\-Steuerelement bestimmt der <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>\-Eigenschaftswert, ob die Spaltenheader angezeigt werden.  
  
### So blenden Sie die Spaltenheader aus  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=fullName>\-Eigenschaft auf `false` fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=fullName>   
 [Grundlegende Spalten\-, Zeilen\- und Zellfeatures im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)