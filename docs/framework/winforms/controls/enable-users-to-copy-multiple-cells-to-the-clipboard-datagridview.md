---
title: 'Vorgehensweise: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden können'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: b220603adcaeae6f3380a2e3c10ea524c9a61f24
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591924"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a>Vorgehensweise: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden können
Wenn Sie das Kopieren von Zellen aktivieren, stellen Sie die Daten in Ihrem <xref:System.Windows.Forms.DataGridView>-Steuerelement problemlos für andere Anwendungen über <xref:System.Windows.Forms.Clipboard> zur Verfügung. Die Werte der ausgewählten Zellen werden in Zeichenfolgen konvertiert und als durch Tabstopp getrennte Textwerte zur Zwischenablage hinzugefügt, damit sie in Anwendungen wie Notepad und Excel eingefügt sowie als HTML-formatierte Tabelle zum Einfügen in Anwendungen wie Word verwendet werden können.  
  
 Sie können das Kopieren von Zellen konfigurieren, sodass nur Zellwerte kopiert werden, damit der Text von Zeilen- und Spaltenüberschriften in die Zwischenablagedaten einbezogen wird. Sie können den Headertext auch nur für den Fall einbeziehen, dass Benutzer ganze Zeilen oder Spalten auswählen.  
  
 Je nach Auswahlmodus können Benutzer mehrere getrennte Gruppen von Zellen auswählen. Wenn ein Benutzer Zellen in die Zwischenablage kopiert, werden Zeilen und Spalten ohne ausgewählte Zellen nicht kopiert. Alle anderen Zeilen oder Spalten werden zu Zeilen und Spalten in der Tabelle der Daten, die in die Zwischenablage kopiert wurden. Nicht ausgewählte Zellen in diesen Zeilen oder Spalten werden als leere Platzhalter in die Zwischenablage kopiert.  
  
### <a name="to-enable-cell-copying"></a>So aktivieren Sie das Kopieren von Zellen  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>-Eigenschaft fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden vollständigen Codebeispiel wird veranschaulicht, wie die Zellen in die Zwischenablage kopiert werden. Dieses Beispiel enthält eine Schaltfläche, die ausgewählte Zellen mithilfe der <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType>-Methode in die Zwischenablage kopiert und den Inhalt der Zwischenablage in einem Textfeld anzeigt.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieser Code erfordert:  
  
- Verweise auf die Assemblys "N:System" und "N:System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
