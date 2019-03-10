---
title: 'Vorgehensweise: Formatieren von Daten in der Windows Forms-DataGridView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 0699aec73c0a48efe88fc2901ef11c70d6f639d7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721280"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Formatieren von Daten in der Windows Forms-DataGridView-Steuerelement
Die folgenden Prozeduren veranschaulichen grundlegende Formatierung von Zellenwerten durch die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> Eigenschaft eine <xref:System.Windows.Forms.DataGridView> Steuerelement sowie von bestimmten Spalten in einem Steuerelement. Weitere Informationen über die Erweiterte Formatierung finden Sie unter [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-format-currency-and-date-values"></a>Formatieren von Währung und Datumswerte  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest. Das folgende Codebeispiel legt das Format für bestimmte Spalten mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> -Eigenschaft der Spalten. Werte in der `UnitPrice` Spalte in der aktuellen kulturspezifische Währungsformat angezeigt werden, mit negativen Werten, die in Klammern eingeschlossen sind. Werte in der `ShipDate` Spalte in der aktuellen kulturspezifische kurzen Datumsformat angezeigt werden. Weitere Informationen zu <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Werte finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>Die Anzeige der Datenbank-Nullwerte anpassen  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> Eigenschaft "keinen Eintrag" in allen Zellen mit Werten, die gleich angezeigt <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>Wordwrap in textbasierten Zellen aktivieren  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> Eigenschaft eine <xref:System.Windows.Forms.DataGridViewCellStyle> eines der <xref:System.Windows.Forms.DataGridViewTriState> Enumerationswerte. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> Eigenschaft, um den Umbruchmodus für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>Die Ausrichtung des Texts von DataGridView-Zellen an  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> Eigenschaft eine <xref:System.Windows.Forms.DataGridViewCellStyle> eines der <xref:System.Windows.Forms.DataGridViewContentAlignment> Enumerationswerte. Das folgende Codebeispiel legt die Ausrichtung für eine bestimmte Spalte mit dem <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> -Eigenschaft der Spalte.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Diese Beispiele erfordern Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem Namen `dataGridView1` , enthält eine Spalte namens `UnitPrice`, eine Spalte namens `ShipDate`, und eine Spalte mit dem Namen `CustomerName`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Sie sollten für maximale Skalierbarkeit gibt freigeben <xref:System.Windows.Forms.DataGridViewCellStyle> Objekten über mehrere Zeilen, Spalten oder Zellen, die dieselben Stile, anstatt die Stileigenschaften für jedes Element einzeln zu verwenden. Weitere Informationen finden Sie unter [Best Practices für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Datenformatierung im DataGridView-Steuerelement in Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [Formatierung von Typen](../../../standard/base-types/formatting-types.md)
