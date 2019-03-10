---
title: 'Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 280f274a0957f098add7fbf2e3b919c33c4c5233
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704401"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelement von Windows Forms
Ein Bild oder eine Grafik ist einer der Werte, die in eine Zeile mit Daten angezeigt werden können. In vielen Fällen haben diese Grafiken der Form Foto eines Mitarbeiters oder einem Logo des Unternehmens.  
  
 Integrieren von Bildern ist einfach, wenn Sie anzeigen, dass die Daten in die <xref:System.Windows.Forms.DataGridView> Steuerelement. Die <xref:System.Windows.Forms.DataGridView> -Steuerelement behandelt jedes Bildformat, das unterstützt durch die <xref:System.Drawing.Image> -Klasse als auch das OLE-Bild, das von einigen Datenbanken verwendet.  
  
 Wenn die <xref:System.Windows.Forms.DataGridView> Datenquelle des Steuerelements verfügt über eine Spalte mit Bildern, werden sie automatisch vom angezeigt der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein Symbol aus einer eingebetteten Ressource extrahiert, und konvertieren Sie ihn in eine Bitmap für die Anzeige in jeder Zelle der Image-Spalte. Ein weiteres Beispiel, das durch entsprechende Bilder Zellenwerte ersetzt werden, finden Sie unter [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Eine eingebettete Symbolressource mit dem Namen `tree.ico`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
