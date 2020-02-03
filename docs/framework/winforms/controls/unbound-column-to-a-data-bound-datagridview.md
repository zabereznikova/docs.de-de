---
title: Hinzufügen einer ungebundenen Spalte zu einem Daten gebundenen DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 807bbc121f33c35d70068571e76637c078ecb3da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747067"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>Gewusst wie: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms
Die Daten, die Sie im <xref:System.Windows.Forms.DataGridView>-Steuerelement anzeigen, stammen normalerweise aus einer Datenquelle einer bestimmten Art, aber möglicherweise möchten Sie eine Spalte mit Daten anzeigen, die nicht aus der Datenquelle stammen. Diese Art von Spalte wird als ungebundene Spalte bezeichnet. Ungebundene Spalten können viele Formen annehmen. Häufig werden sie verwendet, um Zugriff auf die Details einer Datenzeile bereitzustellen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine ungebundene Spalte mit **Detail** Schaltflächen erstellt wird, um eine untergeordnete Tabelle anzuzeigen, die sich auf eine bestimmte Zeile in einer übergeordneten Tabelle bezieht, wenn Sie ein Master/Detail-Szenario implementieren. Um auf Klicks auf Schaltflächen zu reagieren, implementieren Sie einen <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>-Ereignishandler, der ein Formular mit der untergeordneten Tabelle anzeigt.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch Gewusst [wie: Hinzufügen und Entfernen von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
