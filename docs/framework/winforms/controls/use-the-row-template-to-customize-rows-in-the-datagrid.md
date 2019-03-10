---
title: 'Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 3cd1e9af32cb47f5d81abfc92423ea30e2e599cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707572"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet die Zeilenvorlage als Grundlage für alle Zeilen, die es dem Steuerelement hinzugefügt, über die Datenbindung oder beim Aufrufen der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> Methode ohne Angabe einer vorhandenen Zeile verwenden.  
  
 Die Zeilenvorlage ermöglicht Ihnen größere Kontrolle über das Erscheinungsbild und Verhalten von Zeilen als die <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> Eigenschaft enthält. Mit der Zeilenvorlage können Sie alle festlegen <xref:System.Windows.Forms.DataGridViewRow> Eigenschaften, einschließlich <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Es gibt einige Situationen, in dem Sie die Zeilenvorlage verwenden müssen, um einen bestimmten Effekt zu erzielen. Z. B. Informationen über die Zeilenhöhe in gespeichert werden kann keiner <xref:System.Windows.Forms.DataGridViewCellStyle>, Sie eine Zeilenvorlage verwenden müssen, um die Standardhöhe aller Zeilen ein, zu ändern. Die Zeilenvorlage ist auch nützlich, bei der Erstellung eigener Klassen abgeleitet <xref:System.Windows.Forms.DataGridViewRow> und den benutzerdefinierten Typ verwendet, wenn dem Steuerelement neue Zeilen hinzugefügt werden sollen.  
  
> [!NOTE]
>  Die Zeilenvorlage wird verwendet, nur, wenn Zeilen hinzugefügt werden. Sie können keine vorhandene Zeilen ändern, durch Ändern der Zeilenvorlage.  
  
### <a name="to-use-the-row-template"></a>Verwenden die Zeilenvorlage  
  
-   Legen Sie Eigenschaften für das Objekt abgerufen, die von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> Eigenschaft.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
