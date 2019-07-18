---
title: 'Vorgehensweise: Automatisches Anpassen der Zellengröße bei Änderungen des Inhalts im DataGridView-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 3411b68b4dcc64dba86cd9fa8804e0a487cec76d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586634"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Automatisches Anpassen der Zellengröße bei Änderungen des Inhalts im DataGridView-Steuerelement von Windows Forms
Sie können das <xref:System.Windows.Forms.DataGridView> -Steuerelement für das automatische Ändern der Größe der Zeilen, Spalten und Header konfigurieren, wenn sich die Inhalte ändern, damit die Zellen immer groß genug sind, um die Werte anzuzeigen, ohne dass diese abgeschnitten werden.  
  
 Sie können auf verschiedene Weise einschränken, welche Zellen verwendet werden, um die neue Größe zu bestimmen. Beispielsweise können Sie das Steuerelement so konfigurieren, dass die Breite der Spalten automatisch nur anhand der Werte in den aktuell angezeigten Zeilen angepasst wird. Mit dieser Option können Sie Ineffizienz bei der Arbeit mit einer großen Anzahl von Zeilen vermeiden. In diesem Fall können Sie jedoch wahlweise auch Größenänderungsmethoden wie z. B. <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> verwenden, um die Größe anzupassen.  
  
 Weitere Informationen zur automatischen Größenänderung finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 Im folgenden Codebeispiel werden die Optionen veranschaulicht, die für die automatische Größenänderung verfügbar sind.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Programmgesteuertes Ändern der Größe Zellen an Inhalt im DataGridView-Steuerelement in Windows Forms](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
