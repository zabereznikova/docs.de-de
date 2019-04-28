---
title: 'Vorgehensweise: Ändern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 90d262e738f092215e88e38e31169d74059e4401
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781224"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Ändern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms
Wenn Sie eine <xref:System.Windows.Forms.DataGridView> verwenden, um Daten aus einer Datenquelle anzuzeigen, werden die Spalten im Schema der Datenquelle manchmal nicht in der von Ihnen gewünschten Reihenfolge angezeigt. Sie können die Reihenfolge, in der die Spalten angezeigt werden, durch Verwenden der <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridViewColumn>-Klasse ändern.  
  
 Im folgenden Codebeispiel werden einige der Spalten neu angeordnet, die automatisch generiert werden, wenn Sie eine Bindung zur Customers-Tabelle in der Beispieldatenbank Northwind herstellen. Weitere Informationen über das Binden der <xref:System.Windows.Forms.DataGridView> in einer Datenbanktabelle zu steuern, finden Sie unter [Vorgehensweise: Binden von Daten an die Windows Forms-DataGridView-Steuerelement](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Ändern der Reihenfolge der Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `customersDataGridView`, das an eine Tabelle mit den angegebenen Spaltennamen gebunden ist, beispielsweise die `Customers`-Tabelle in der Beispieldatenbank Northwind.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> und <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
