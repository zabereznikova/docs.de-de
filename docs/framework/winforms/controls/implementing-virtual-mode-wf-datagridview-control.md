---
title: 'Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31806d3ed13776e26634914b48bc887297ea4dab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms
Wenn sehr große Mengen von Tabellendaten in angezeigt werden soll eine <xref:System.Windows.Forms.DataGridView> -Steuerelements legen Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und das Steuerelement Interaktion mit dem Datenspeicher explizit verwalten. So können Sie beim Optimieren der Leistung des Steuerelements in dieser Situation.  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, um einen benutzerdefinierten Datenspeicher interagieren. Diese exemplarische Vorgehensweise führt Sie durch den Prozess der Implementierung dieser Ereignishandler. Das Codebeispiel in diesem Thema wird eine sehr einfache Datenquelle zur Veranschaulichung verwendet. In einer produktionsumgebung, in der Regel nur die Zeilen, die Sie in den Cache anzuzeigen und zu behandeln müssen laden <xref:System.Windows.Forms.DataGridView> Ereignisse zur Interaktion und zum Aktualisieren des Caches. Weitere Informationen finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-implement-virtual-mode"></a>Zum Implementieren virtuellen Modus  
  
1.  Erstellen Sie eine Klasse, die abgeleitet <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
     Der folgende Code enthält einige grundlegende Initialisierung. Es einige Variablen deklariert, die in späteren Schritten verwendet werden, bietet eine `Main` -Methode, und bietet ein einfaches Formularlayout im Klassenkonstruktor.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  Implementieren Sie einen Handler für Ihr Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> steuern und der Datenspeicher mit Beispieldaten gefüllt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignis, das den angeforderten Zellenwert aus dem Datenspeicher abruft oder die `Customer` Objekt derzeit in Bearbeitung.  
  
     Dieses Ereignis tritt auf, wenn die <xref:System.Windows.Forms.DataGridView> Steuerelement eine Zelle gezeichnet werden muss.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValuePushed> Ereignis, das einen bearbeitete Zellenwert in speichert die `Customer` Objekt, das die bearbeitete Zeile darstellt. Dieses Ereignis tritt auf, wenn der Benutzer eine Änderung in der Zelle Wert ein Commit ausgeführt wird.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.NewRowNeeded> Ereignis, das eine neue erstellt `Customer` Objekt, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer die Zeile für neue Datensätze eingibt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowValidated> Ereignis, das neue oder geänderte Zeilen im Datenspeicher gespeichert.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer die aktuelle Zeile ändert.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignis, das angibt, ob die <xref:System.Windows.Forms.DataGridView.CancelRowEdit> -Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken von ESC zweimal im Bearbeitungsmodus befindet oder einmal außerhalb Bearbeitungsmodus signalisiert.  
  
     Standardmäßig <xref:System.Windows.Forms.DataGridView.CancelRowEdit> beim Zurücksetzen von Zeilen tritt auf, wenn keine Zellen in der aktuellen Zeile geändert wurden, sofern die <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> -Eigenschaftensatz auf `true` in der <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler. Dieses Ereignis ist nützlich, wenn der Commit-Bereich zur Laufzeit bestimmt wird.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis, das die Werte der verwirft die `Customer` Objekt, das die aktuelle Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken von ESC zweimal im Bearbeitungsmodus befindet oder einmal außerhalb Bearbeitungsmodus signalisiert. Dieses Ereignis tritt nicht auf, wenn keine Zellen in der aktuellen Zeile geändert wurden oder wenn der Wert des der <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> Eigenschaft auf festgelegt wurde `false` in einen <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.UserDeletingRow> Ereignis, das ein vorhandenes löscht `Customer` Objekt aus dem Datenspeicher zusammen oder verwirft eine ungespeicherte `Customer` Objekt, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt auf, wenn der Benutzer eine Zeile gelöscht wird, indem Sie auf einen Zeilenkopf, und drücken die ENTF-Taste.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementieren Sie eine einfache `Customers` Klasse, um die Datenelemente, die von diesem Codebeispiel verwendeten darzustellen.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit drei Kundendatensätze aufgefüllt. Sie können ändern Sie die Werte aus mehreren Zellen in einer Zeile, und drücken Sie ESC, zweimal im Bearbeitungsmodus befindet und einmal außerhalb Bearbeitungsmodus wechseln, um die gesamte Zeile auf die ursprünglichen Werte zurückgesetzt. Wenn Sie ändern, hinzufügen oder Löschen von Zeilen im Steuerelement `Customer` Objekte im Datenspeicher geändert, hinzugefügt oder ebenfalls gelöscht werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung bietet Ihnen ein grundlegendes Verständnis der Ereignisse müssen Sie zum Implementieren des virtuellen Modus im behandeln die <xref:System.Windows.Forms.DataGridView> Steuerelement. Sie können diese grundlegenden Anwendung auf vielfältige Weise verbessern:  
  
-   Implementieren Sie einen Datenspeicher, der Werte aus einer externen Datenbank zwischenspeichert. Der Cache sollte abrufen und Werte nach Bedarf zu verwerfen, sodass sie nur enthält, was für die Anzeige Anspruch eine kleine Menge an Arbeitsspeicher auf dem Clientcomputer erforderlich ist.  
  
-   Optimieren der Leistung des Datenspeichers je nach Ihren Anforderungen. Sie möchten z. B. mithilfe von Cache zu einem größeren und Minimieren der Anzahl der Datenbankabfragen für langsame Verbindungen anstelle der Clientcomputer Memory-Einschränkungen zu kompensieren.  
  
 Weitere Informationen zum Zwischenspeichern von Werten aus einer externen Datenbank finden Sie unter [wie: Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [Gewusst wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
