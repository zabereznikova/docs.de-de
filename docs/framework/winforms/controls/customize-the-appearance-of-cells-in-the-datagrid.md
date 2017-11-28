---
title: 'Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 545a3bff5e810f9c0a995366e7f6460930f9e936
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms
Sie können die Darstellung der eine beliebige Zelle anpassen, indem die Behandlung der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis. Sie extrahieren die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Drawing.Graphics> aus der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Mit diesem <xref:System.Drawing.Graphics>, Sie können die Darstellung des gesamten beeinflussen <xref:System.Windows.Forms.DataGridView> -Steuerelement, aber Sie werden in der Regel möchte nur die Darstellung der Zelle zu beeinflussen, die gerade gezeichnet wird. Die <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> ermöglicht es Ihnen, Ihre Zeichenvorgänge auf die Zelle zu beschränken, die gerade gezeichnet wird.  
  
 Im folgenden Codebeispiel zeichnen Sie alle Zellen in einem `ContactName` Spalte unter Verwendung der <xref:System.Windows.Forms.DataGridView> Farbschema des Steuerelements. Jede Zelle Text-Inhalt gezeichnet wird <xref:System.Drawing.Color.Crimson%2A>, und eine abgesenktes Rechteck gezeichnet wird, in die gleiche Farbe wie der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.GridColor%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView> Steuerelement namens `dataGridView1` mit einem `ContactName` Spalte wie in der Customers-Tabelle in der Northwind-Beispieldatenbank.  
  
-   Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
