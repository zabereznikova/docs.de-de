---
title: "Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms | Microsoft Docs"
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
  - "Zellen, Anpassen im DataGridView-Steuerelement"
  - "Datenblätter, Anpassen von Zellen"
  - "DataGridView-Steuerelement [Windows Forms], Anpassen von Zellen"
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms
Sie können die Darstellung einer beliebigen Zelle anpassen, indem Sie das <xref:System.Windows.Forms.DataGridView.CellPainting>\-Ereignis des <xref:System.Windows.Forms.DataGridView>\-Steuerelements behandeln.  Sie können die <xref:System.Drawing.Graphics> des <xref:System.Windows.Forms.DataGridView>\-Steuerelements aus der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> extrahieren.  Mit diesen <xref:System.Drawing.Graphics> können Sie die Darstellung des gesamten <xref:System.Windows.Forms.DataGridView>\-Steuerelements beeinflussen. Für gewöhnlich möchten Sie jedoch nur die Darstellung der Zelle ändern, die momentan gezeichnet wird.  Die <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> ermöglicht es Ihnen, die Zeichenvorgänge auf die Zelle zu beschränken, die momentan gezeichnet wird.  
  
 Im folgenden Codebeispiel zeichnen Sie alle Zellen in einer `ContactName`\-Spalte mithilfe des Farbschemas des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  Der Textinhalt aller Zellen wird in <xref:System.Drawing.Color.Crimson%2A> gezeichnet, und ein abgesenktes Rechteck wird in derselben Farbe wie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGridView>\-Steuerelements gezeichnet.  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen `dataGridView1` mit einer `ContactName`\-Spalte wie die in der Tabelle Customers der Beispieldatenbank Northwind.  
  
-   Verweise auf die Assemblys System, System.Drawing und System.Windows.Forms.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellPainting>   
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)