---
title: Formatieren von Daten im DataGridView-Steuerelement
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
ms.openlocfilehash: 9ee2869cf4085b5acfdf1f8c440151be506dbe3e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736790"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms
Die folgenden Prozeduren veranschaulichen die grundlegende Formatierung von Zellwerten mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>-Eigenschaft eines <xref:System.Windows.Forms.DataGridView> Steuer Elements und bestimmter Spalten in einem-Steuerelement. Weitere Informationen zur erweiterten Datenformatierung finden Sie unter Gewusst [wie: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuer](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Element.  
  
### <a name="to-format-currency-and-date-values"></a>So formatieren Sie Currency-und Date-Werte  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest. Im folgenden Codebeispiel wird das Format für bestimmte Spalten mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>-Eigenschaft der Spalten festgelegt. Werte in der Spalte `UnitPrice` werden im aktuellen Kultur abhängigen Währungs Format angezeigt, wobei negative Werte in Klammern eingeschlossen sind. Werte in der Spalte `ShipDate` werden im aktuellen kulturspezifischen kurzen Datumsformat angezeigt. Weitere Informationen zu <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Werten finden Sie unter [Formatieren von Typen](../../../standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>So passen Sie die Anzeige von NULL-Daten bankwerten an  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>-Eigenschaft verwendet, um in allen Zellen, die Werte gleich <xref:System.DBNull.Value?displayProperty=nameWithType>enthalten, den Eintrag No Entry anzuzeigen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>So aktivieren Sie WordWrap in textbasierten Zellen  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der <xref:System.Windows.Forms.DataGridViewTriState>-Enumerationswerte fest. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>-Eigenschaft verwendet, um den Umbruch Modus für das gesamte-Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>So geben Sie die Textausrichtung von DataGridView-Zellen an  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der <xref:System.Windows.Forms.DataGridViewContentAlignment>-Enumerationswerte fest. Im folgenden Codebeispiel wird die Ausrichtung für eine bestimmte Spalte mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>-Eigenschaft der Spalte festgelegt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Diese Beispiele erfordern Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem Namen `dataGridView1`, das eine Spalte mit dem Namen `UnitPrice`, eine Spalte mit dem Namen `ShipDate`und eine Spalte mit dem Namen `CustomerName`enthält.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Robuste Programmierung  
 Um maximale Skalierbarkeit zu ermöglichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte für mehrere Zeilen, Spalten oder Zellen freigeben, die dieselben Stile verwenden, anstatt die Stileigenschaften für jedes Element separat festzulegen. Weitere Informationen finden Sie unter [bewährte Methoden zum Skalieren des Windows Forms DataGridView-Steuer](best-practices-for-scaling-the-windows-forms-datagridview-control.md)Elements.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Datenformatierung im DataGridView-Steuerelement in Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [Formatierung von Typen](../../../standard/base-types/formatting-types.md)
