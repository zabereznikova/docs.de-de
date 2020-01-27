---
title: 'Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746518"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms
Wenn Sie in einem <xref:System.Windows.Forms.DataGridView> Steuerelement sehr große Mengen an tabellarischen Daten anzeigen möchten, können Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft auf `true` festlegen und die Interaktion des Steuer Elements mit seinem Datenspeicher explizit verwalten. Auf diese Weise können Sie die Leistung des Steuer Elements in dieser Situation optimieren.  
  
 Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, um mit einem benutzerdefinierten Datenspeicher zu interagieren. Diese exemplarische Vorgehensweise führt Sie durch den Prozess der Implementierung dieser Ereignishandler. Das Codebeispiel in diesem Thema verwendet zur Veranschaulichung eine sehr einfache Datenquelle. In einer Produktionseinstellung laden Sie in der Regel nur die Zeilen, die Sie in einem Cache anzeigen müssen, und behandeln <xref:System.Windows.Forms.DataGridView> Ereignisse, um mit dem Cache zu interagieren und ihn zu aktualisieren. Weitere Informationen finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten in das Windows Forms DataGridView-Steuer](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md) Element.  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)Element.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-implement-virtual-mode"></a>So implementieren Sie den virtuellen Modus  
  
1. Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und ein <xref:System.Windows.Forms.DataGridView> Steuerelement enthält.  
  
     Der folgende Code enthält eine grundlegende Initialisierung. Er deklariert einige Variablen, die in späteren Schritten verwendet werden, stellt eine `Main` Methode bereit und stellt ein einfaches Formularlayout im-Klassenkonstruktor bereit.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars, das das <xref:System.Windows.Forms.DataGridView>-Steuerelement initialisiert und den Datenspeicher mit Beispiel Werten füllt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignis, das den angeforderten Zellwert aus dem Datenspeicher abruft, oder das `Customer` Objekt, das gerade bearbeitet wird.  
  
     Dieses Ereignis tritt auf, wenn das <xref:System.Windows.Forms.DataGridView>-Steuerelement eine Zelle zeichnen muss.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValuePushed>-Ereignis, das einen bearbeiteten Zellwert im `Customer` Objekt speichert, das die bearbeitete Zeile darstellt. Dieses Ereignis tritt auf, wenn der Benutzer eine Änderung eines Zellen Werts durchführt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.NewRowNeeded>-Ereignis, das ein neues `Customer`-Objekt erstellt, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer die Zeile für neue Datensätze eingibt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowValidated>-Ereignis, das neue oder geänderte Zeilen im Datenspeicher speichert.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer die aktuelle Zeile ändert.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignis, das angibt, ob das <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis auftritt, wenn der Benutzer die Zeilen Neuversion durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus oder außerhalb des Bearbeitungsmodus signalisiert.  
  
     Standardmäßig erfolgt <xref:System.Windows.Forms.DataGridView.CancelRowEdit> bei der Zeilen Neuversion, wenn Zellen in der aktuellen Zeile geändert wurden, es sei denn, die <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>-Eigenschaft ist im <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignishandler auf `true` festgelegt. Dieses Ereignis ist hilfreich, wenn der Commit-Bereich zur Laufzeit bestimmt wird.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis, das die Werte des `Customer` Objekts verwirft, das die aktuelle Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer die Zeilen Neuversion durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus oder außerhalb des Bearbeitungsmodus signalisiert. Dieses Ereignis tritt nicht auf, wenn keine Zellen in der aktuellen Zeile geändert wurden oder wenn der Wert der <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>-Eigenschaft auf `false` in einem <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>-Ereignishandler festgelegt wurde.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.UserDeletingRow> Ereignis, das ein vorhandenes `Customer` Objekt aus dem Datenspeicher löscht, oder verwirft ein nicht gespeichertes `Customer` Objekt, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer eine Zeile durch Klicken auf einen Zeilen Header und durch Drücken der ENTF-Taste löscht.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementieren Sie eine einfache `Customers`-Klasse, die die Datenelemente darstellt, die in diesem Codebeispiel verwendet werden.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
- Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Es wird ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit drei Kundendatensätzen angezeigt. Sie können die Werte mehrerer Zellen in einer Zeile ändern und die ESC-Taste zweimal im Bearbeitungsmodus drücken und einmal außerhalb des Bearbeitungsmodus, um die gesamte Zeile auf ihre ursprünglichen Werte zurückzusetzen. Wenn Sie Zeilen im Steuerelement ändern, hinzufügen oder löschen, werden `Customer` Objekte im Datenspeicher ebenfalls geändert, hinzugefügt oder gelöscht.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung enthält grundlegende Kenntnisse über die Ereignisse, die Sie behandeln müssen, um den virtuellen Modus im <xref:System.Windows.Forms.DataGridView> Steuerelement zu implementieren. Sie können diese grundlegende Anwendung auf verschiedene Arten verbessern:  
  
- Implementieren Sie einen Datenspeicher, der Werte aus einer externen Datenbank zwischenspeichert. Der Cache sollte bei Bedarf Werte abrufen und verwerfen, sodass er nur die für die Anzeige erforderlichen Elemente enthält, während ein kleiner Speicherplatz auf dem Client Computer beansprucht wird.  
  
- Optimieren Sie die Leistung des Datenspeicher abhängig von Ihren Anforderungen. Beispielsweise möchten Sie möglicherweise langsame Netzwerkverbindungen anstelle der Arbeitsspeicher Beschränkungen von Client Computern kompensieren, indem Sie eine größere Cache Größe verwenden und die Anzahl der Datenbankabfragen minimieren.  
  
 Weitere Informationen zum Zwischenspeichern von Werten aus einer externen Datenbank finden [Sie unter Gewusst wie: Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten in das Windows Forms DataGridView-Steuer](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)Element.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [Gewusst wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
