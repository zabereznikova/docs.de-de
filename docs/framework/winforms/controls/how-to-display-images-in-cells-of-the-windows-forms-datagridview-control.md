---
title: Anzeigen von Bildern in Zellen des DataGridView-Steuer Elements
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
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740284"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms
Ein Bild oder eine Grafik ist einer der Werte, die in einer Daten Zeile angezeigt werden können. Häufig haben diese Grafiken das Foto eines Mitarbeiters oder ein Firmenlogo.  
  
 Das Einschließen von Bildern ist einfach, wenn Sie Daten innerhalb des <xref:System.Windows.Forms.DataGridView> Steuer Elements anzeigen. Das <xref:System.Windows.Forms.DataGridView>-Steuerelement behandelt alle Bildformate, die von der <xref:System.Drawing.Image>-Klasse unterstützt werden, und das von einigen Datenbanken verwendete OLE-Bildformat.  
  
 Wenn die Datenquelle des <xref:System.Windows.Forms.DataGridView> Steuer Elements über eine Spalte mit Bildern verfügt, werden diese automatisch vom <xref:System.Windows.Forms.DataGridView>-Steuerelement angezeigt.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein Symbol aus einer eingebetteten Ressource extrahieren und in eine Bitmap konvertieren, um Sie in jeder Zelle einer Bild Spalte anzuzeigen. Ein weiteres Beispiel, das Text Zellwerte durch entsprechende Bilder ersetzt, finden Sie unter Gewusst [wie: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuer](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Element.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Eine eingebettete Symbol Ressource mit dem Namen `tree.ico`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
