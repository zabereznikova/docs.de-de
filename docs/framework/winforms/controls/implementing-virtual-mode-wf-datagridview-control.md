---
title: 'Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 7f6bf1703a6536f4d22b3a2fbe412579c59d39dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973770"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms
Bei sehr große Mengen von Tabellendaten in angezeigt werden soll eine <xref:System.Windows.Forms.DataGridView> -Steuerelements legen Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und explizit die Interaktion mit dem Datenspeicher des Steuerelements verwalten. Dadurch können Sie die Leistung des Steuerelements in diesem Fall optimieren.  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, für die Interaktion mit einem benutzerdefinierten Datenspeicher. Diese exemplarische Vorgehensweise führt Sie durch den Prozess der Implementierung von diesen Ereignishandlern. Das Codebeispiel in diesem Thema wird eine sehr einfache Datenquelle zur Veranschaulichung verwendet. In einer produktionsumgebung werden Sie in der Regel Laden nur die Zeilen, die Sie in einen Cache anzuzeigen und zu behandeln müssen <xref:System.Windows.Forms.DataGridView> Ereignisse interagieren und den Cache zu aktualisieren. Weitere Informationen finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-implement-virtual-mode"></a>Implementieren des virtuellen Modus  
  
1. Erstellen Sie eine abgeleitete Klasse <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
     Der folgende Code enthält einige grundlegende Initialisierung. Diese einige Variablen deklariert, die in späteren Schritten verwendet werden, und bietet eine `Main` -Methode, und bietet ein einfaches Formularlayout im Konstruktor Klasse.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. Implementieren Sie einen Handler für Ihres Formulars <xref:System.Windows.Forms.Form.Load> -Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> steuern und der Datenspeicher mit Beispieldaten gefüllt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellValueNeeded> -Ereignis, das den angeforderten Zelle-Wert aus dem Datenspeicher abruft oder `Customer` Objekt derzeit in Bearbeitung.  
  
     Dieses Ereignis tritt auf, wenn die <xref:System.Windows.Forms.DataGridView> Steuerelement eine Zelle gezeichnet werden muss.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellValuePushed> -Ereignis, das einen bearbeitete Zellenwert in speichert die `Customer` Objekt, das die bearbeitete Zeile darstellt. Dieses Ereignis tritt auf, wenn der Benutzer die Änderung eines Zelle ein Commit ausgeführt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.NewRowNeeded> -Ereignis, ein neues erstellt `Customer` Objekt, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer die Zeile für neue Datensätze eingibt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.RowValidated> Ereignis, neue oder geänderte Zeilen im Datenspeicher gespeichert.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer die aktuelle Zeile ändert.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignis, das angibt, ob die <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus befindet oder einmal außerhalb des Bearbeitungsmodus signalisiert.  
  
     In der Standardeinstellung <xref:System.Windows.Forms.DataGridView.CancelRowEdit> tritt auf, beim Zurücksetzen von Zeilen, wenn keine Zellen in der aktuellen Zeile geändert wurden, wenn die <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> -Eigenschaftensatz auf `true` in die <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler. Dieses Ereignis ist nützlich, wenn der Commit-Bereich zur Laufzeit bestimmt wird.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CancelRowEdit> -Ereignis, das die Werte der verwirft die `Customer` Objekt, das die aktuelle Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus befindet oder einmal außerhalb des Bearbeitungsmodus signalisiert. Dieses Ereignis tritt nicht auf, wenn keine Zellen in der aktuellen Zeile geändert wurden oder wenn der Wert des der <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> eingestellt wurde `false` in einer <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.UserDeletingRow> -Ereignis, das Löscht eine vorhandene `Customer` Objekt aus dem Datenspeicher, zusammen oder verwirft eine ungespeicherte `Customer` Objekt, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer eine Zeile löscht, indem Sie auf einen Zeilenheader und die ENTF-Taste.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementieren Sie eine einfache `Customers` Klasse darstellen, die die Datenelemente, die von diesem Codebeispiel wird verwendet.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
- Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sie sehen eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit drei Kundendatensätze aufgefüllt. Sie können ändern Sie die Werte aus mehreren Zellen in einer Zeile, und drücken Sie ESC, zweimal im Bearbeitungsmodus befindet und einmal außerhalb Bearbeitungszustand versetzt, damit die gesamte Zeile auf die ursprünglichen Werte zurückgesetzt. Wenn Sie ändern, hinzufügen oder Löschen von Zeilen im Steuerelement `Customer` Objekte im Datenspeicher geändert, hinzugefügt oder ebenfalls gelöscht werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung verfügt über einen grundlegenden Überblick über die Ereignisse müssen Sie zum Implementieren virtuellen Modus im behandeln die <xref:System.Windows.Forms.DataGridView> Steuerelement. Sie können diese einfache vorlagenanwendung auf vielfältige Weise verbessern:  
  
- Implementieren Sie einen Datenspeicher, der Werte aus einer externen Datenbank speichert. Der Cache sollte abrufen und die Werte nach Bedarf zu verwerfen, sodass sie nur enthält, was für die Anzeige während der Verarbeitung von einem kleinen Teil des Arbeitsspeichers auf dem Clientcomputer erforderlich ist.  
  
- Optimieren Sie die Leistung des Datenspeichers je nach Ihren Anforderungen. Beispielsweise empfiehlt es sich um für langsame Netzwerkverbindungen anstelle von Client-Computer-Memory-Einschränkungen zu kompensieren, indem Sie einen größeren Cache und Verringerung der Anzahl von Abfragen.  
  
 Weitere Informationen zum Zwischenspeichern von Werten aus einer externen Datenbank finden Sie unter [Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Daten laden in das Windows Forms-DataGridView-Steuerelement](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
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
- [Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
