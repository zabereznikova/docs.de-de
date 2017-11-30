---
title: 'Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms'
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
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b2e06298d0ead9a2dd9fa554af0c42df5d61d56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms
Ein Bild oder eine Grafik ist einer der Werte, die in eine Zeile mit Daten angezeigt werden können. In vielen Fällen sind diese Grafiken Foto eines Mitarbeiters oder ein Unternehmenslogo.  
  
 Integrieren von Bildern ist einfach, wenn Sie anzeigen, dass die Daten innerhalb der <xref:System.Windows.Forms.DataGridView> Steuerelement. Die <xref:System.Windows.Forms.DataGridView> Steuerelement behandelt systemintern alle Bildformat von unterstützt die <xref:System.Drawing.Image> Klasse als auch das OLE-Bild, das von einigen Datenbanken verwendet.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView> Datenquelle des Steuerelements besitzt eine Spalte vom Bildern, werden sie automatisch vom angezeigt werden die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein Symbol aus einer eingebetteten Ressource extrahiert und konvertieren Sie ihn in eine Bitmap für die Anzeige in jeder Zelle der Image-Spalte. Ein weiteres Beispiel, die Zellenwerte durch entsprechende Bilder ersetzt werden, finden Sie unter [wie: Anpassen der Datenformatierung im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Eine eingebettete Symbolressource mit dem Namen `tree.ico`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
