---
title: Festlegen von Standardzellen Formaten für das DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: 6b2d7de671e48ae8f55987c262e15717138b3fb4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744869"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a>Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms
Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie Standardzellenstile für das gesamte Steuerelement und für bestimmte Spalten und Zeilen angeben. Diese Standardeinstellungen werden von der Steuerelementebene bis herunter auf die Spaltenebene, dann auf die Zeilenebene und anschließend auf die Zellenebene gefiltert. Wenn eine bestimmte Eigenschaft <xref:System.Windows.Forms.DataGridViewCellStyle> nicht auf Zellenebene festgelegt ist, wird die standardmäßige Eigenschafteneinstellung auf Zeilenebene verwendet. Wenn die Eigenschaft auf Zeilenebene ebenfalls nicht festgelegt ist, wird die Standardspalteneinstellung verwendet. Wenn die Eigenschaft schließlich auf Spaltenebene ebenfalls nicht festgelegt ist, wird die <xref:System.Windows.Forms.DataGridView>-Standardeinstellung verwendet. Mit dieser Einstellung können Sie vermeiden, die Eigenschafteneinstellungen auf mehreren Ebenen duplizieren zu müssen. Geben Sie einfach auf jeder Ebene die Stile an, die sich von den darüber liegenden Ebenen unterscheiden. Weitere Informationen finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  Siehe auch Gewusst [wie: Festlegen von Standardzellen Stilen und Datenformaten für das Windows Forms DataGridView-Steuerelement mithilfe des Designers](default-cell-styles-datagridview.md).  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a>Die legen Sie Standardzellenstile programmgesteuert fest  
  
1. Legen Sie die Eigenschaften des <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekts fest, das über die Eigenschaft <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> abgerufen wurde.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. Erstellen und initialisieren Sie neue <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte für die Verwendung durch mehreren Zeilen und Spalten.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. Legen Sie die Eigenschaft `DefaultCellStyle` bestimmter Zeilen und Spalten fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Robuste Programmierung  
 Um maximale Skalierbarkeit zu erreichen, wenn Sie mit sehr großen Datenmengen arbeiten, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte für mehrere Zeilen, Spalten oder Zellen freigeben, die dieselben Stile verwenden, anstatt die Stileigenschaften für einzelne Elemente separat festzulegen. Darüber hinaus sollten Sie freigegebene Zeilen erstellen und auf diese zugreifen, indem Sie die Eigenschaft <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> verwenden. Weitere Informationen finden Sie unter [bewährte Methoden zum Skalieren des Windows Forms DataGridView-Steuer](best-practices-for-scaling-the-windows-forms-datagridview-control.md)Elements.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
