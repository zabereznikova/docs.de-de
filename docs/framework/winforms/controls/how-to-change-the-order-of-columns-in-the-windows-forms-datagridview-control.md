---
title: Ändern der Reihenfolge von Spalten im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 2aef196e9544a81f42a563783ce6c357869aa247
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746544"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Ändern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms
Wenn Sie eine <xref:System.Windows.Forms.DataGridView> verwenden, um Daten aus einer Datenquelle anzuzeigen, werden die Spalten im Schema der Datenquelle manchmal nicht in der von Ihnen gewünschten Reihenfolge angezeigt. Sie können die Reihenfolge, in der die Spalten angezeigt werden, durch Verwenden der <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridViewColumn>-Klasse ändern.  
  
 Im folgenden Codebeispiel werden einige der Spalten neu angeordnet, die automatisch generiert werden, wenn Sie eine Bindung zur Customers-Tabelle in der Beispieldatenbank Northwind herstellen. Weitere Informationen zum Binden des <xref:System.Windows.Forms.DataGridView>-Steuer Elements an eine Datenbanktabelle finden Sie unter Gewusst [wie: Binden von Daten an das Windows Forms DataGridView-Steuer](how-to-bind-data-to-the-windows-forms-datagridview-control.md)Element.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch Gewusst [wie: Ändern der Reihenfolge von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `customersDataGridView`, das an eine Tabelle mit den angegebenen Spaltennamen gebunden ist, beispielsweise die `Customers`-Tabelle in der Beispieldatenbank Northwind.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> und <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
