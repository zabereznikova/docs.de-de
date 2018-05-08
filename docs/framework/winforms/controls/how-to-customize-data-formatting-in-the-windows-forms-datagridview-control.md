---
title: 'Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: 79b13d85fdb18e057ac1f16bc3c458b12ae1b8d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms
Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>-Ereignis implementieren, durch den geändert wird, wie Zellen in Abhängigkeit von ihren Spalten und Werten angezeigt werden.  
  
 Zellen in der Spalte `Balance`, die negative Zahlen enthalten, erhalten einen roten Hintergrund. Sie können diese Zellen auch als Währungszellen formatieren, sodass negative Werte in Klammern angezeigt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
 Zellen in der Spalte `Priority` zeigen Bilder anstelle entsprechender Textzellenwerte an. Die <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>-Instanz wird verwendet, um sowohl den Textzellenwert abzurufen als auch den entsprechenden Bildanzeigewert festzulegen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
-   <xref:System.Drawing.Bitmap>-Bilder mit den Namen `highPri.bmp`, `mediumPri.bmp` und `lowPri.bmp`, die sich im selben Verzeichnis befinden wie die ausführbare Datei.  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Drawing.Bitmap>  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
