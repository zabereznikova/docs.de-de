---
title: 'Vorgehensweise: Programmgesteuertes Ändern der Größe Zellen an Inhalt im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: 09ac5e43653a3389737777258db3bb5e0ed4c0a1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722918"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Programmgesteuertes Ändern der Größe Zellen an Inhalt im DataGridView-Steuerelement in Windows Forms
Sie können die <xref:System.Windows.Forms.DataGridView>-Steuerelementmethoden verwenden, um die Größen von Zeilen, Spalten und Headern zu ändern, sodass die darin enthaltenen Werte ungekürzt angezeigt werden. Mit diesen Methoden können Sie die Größen der <xref:System.Windows.Forms.DataGridView>-Elemente zu von Ihnen gewählten Zeitpunkten ändern. Alternativ können Sie das Steuerelement so konfigurieren, dass diese Elemente automatisch angepasst werden, sobald sich der Inhalt ändert. Dies kann jedoch ineffizient sein, wenn Sie mit großen Datenmengen arbeiten oder wenn sich Ihre Daten häufig ändern. Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 In der Regel passen Sie <xref:System.Windows.Forms.DataGridView>-Elemente nur dann programmgesteuert an ihren Inhalt an, wenn Sie neue Daten aus einer Datenquelle laden oder der Benutzer einen Wert bearbeitet hat. Dies ist nützlich, um die Leistung zu optimieren, ist aber auch nützlich, wenn Sie Ihren Benutzern ermöglichen möchten, die Größen von Zeilen und Spalten manuell mit der Maus ändern zu können.  
  
 Im folgenden Codebeispiel werden die Optionen veranschaulicht, die zur programmgesteuerten Größenanpassung verfügbar sind.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Größe automatisch Zellen aus, wenn Inhalt geändert wird, in das DataGridView-Steuerelement in Windows Forms](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
