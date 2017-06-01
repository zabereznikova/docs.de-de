---
title: "Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Daten [Windows Forms], Verwalten von großen Datasets"
  - "DataGridView-Steuerelement [Windows Forms], Große Datasets"
  - "DataGridView-Steuerelement [Windows Forms], Virtueller Modus"
  - "Virtueller Modus, Exemplarische Vorgehensweisen"
  - "Exemplarische Vorgehensweisen [Windows Forms], DataGridView-Steuerelement"
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms
Wenn Sie sehr umfangreiche Tabellendaten in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement anzeigen möchten, können Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft auf `true` festlegen und die Interaktion des Steuerelements mit dem Datenspeicher explizit verwalten.  Auf diese Weise können Sie die Leistung des Steuerelements in dieser Situation feiner abstimmen.  
  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt mehrere Ereignisse bereit, die Sie für die Interaktion mit einem benutzerdefinierten Datenspeicher behandeln können.  Diese exemplarische Vorgehensweise führt Sie durch die Schritte zum Implementieren dieser Ereignishandler.  Im Codebeispiel in diesem Thema wird eine sehr einfache Datenquelle zu Illustrationszwecken verwendet.  In einer Produktionsumgebung werden normalerweise nur die anzuzeigenden Zeilen in einen Cache geladen und <xref:System.Windows.Forms.DataGridView>\-Ereignisse behandelt, um mit dem Cache zu interagieren und diesen zu aktualisieren.  Weitere Informationen finden Sie unter [Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter [Gewusst wie: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## Erstellen des Formulars  
  
#### So implementieren Sie den virtuellen Modus  
  
1.  Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet wird und ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  
  
     Der folgende Code enthält einigen Code für die grundlegende Initialisierung.  In der Initialisierung werden einige Variablen deklariert, die in nachfolgenden Schritten verwendet werden. Außerdem wird eine `Main`\-Methode sowie das Layout für ein einfaches Formular im Klassenkonstruktor bereitgestellt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars, durch den das <xref:System.Windows.Forms.DataGridView>\-Steuerelement initialisiert und der Datenspeicher mit Beispieldaten gefüllt wird.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueNeeded>\-Ereignis, durch den der angeforderte Zellwert vom Datenspeicher oder vom derzeit bearbeiteten `Customer`\-Objekt abgerufen wird.  
  
     Dieses Ereignis tritt ein, wenn eine Zelle vom <xref:System.Windows.Forms.DataGridView>\-Steuerelement gezeichnet werden muss.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValuePushed>\-Ereignis, durch den ein bearbeiteter Zellwert im `Customer`\-Objekt gespeichert wird, das die bearbeitete Zeile darstellt.  Dieses Ereignis tritt ein, wenn der Benutzer für einen geänderten Zellwert einen Commit ausführt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.NewRowNeeded>\-Ereignis, durch den ein neues `Customer`\-Objekt erstellt wird, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt ein, wenn der Benutzer in die Zeile für neue Datensätze klickt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowValidated>\-Ereignis, durch den neue oder geänderte Zeilen im Datenspeicher gespeichert werden.  
  
     Dieses Ereignis tritt ein, wenn der Benutzer die aktuelle Zeile ändert.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>\-Ereignis, durch den angegeben wird, ob das <xref:System.Windows.Forms.DataGridView.CancelRowEdit>\-Ereignis auftritt, sobald der Benutzer das Zurücksetzen einer Zeile signalisiert, indem er im Bearbeitungsmodus zweimal oder außerhalb des Bearbeitungsmodus einmal die ESC\-TASTE drückt.  
  
     <xref:System.Windows.Forms.DataGridView.CancelRowEdit> tritt beim Zurücksetzen von Zeilen standardmäßig ein, wenn Zellen in der aktuellen Zeile geändert wurden. Wenn die <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName>\-Eigenschaft im <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>\-Ereignishandler auf `true` festgelegt wurde, gilt dies allerdings nicht.  Dieses Ereignis ist hilfreich, wenn der Commit\-Bereich zur Laufzeit bestimmt wird.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CancelRowEdit>\-Ereignis, durch den die Werte des `Customer`\-Objekts verworfen werden, das die aktuelle Zeile darstellt.  
  
     Dieses Ereignis tritt ein, sobald der Benutzer das Zurücksetzen einer Zeile signalisiert, indem er im Bearbeitungsmodus zweimal oder außerhalb des Bearbeitungsmodus einmal die ESC\-TASTE drückt.  Das Ereignis tritt nicht ein, wenn in der aktuellen Zeile keine Zellen geändert wurden oder der Wert der <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName>\-Eigenschaft in einem <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>\-Ereignishandler auf `false` festgelegt wurde.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.UserDeletingRow>\-Ereignis, durch den ein vorhandenes `Customer`\-Objekt aus dem Datenspeicher gelöscht oder ein nicht gespeichertes `Customer`\-Objekt verworfen wird, das eine neu erstellte Zeile darstellt.  
  
     Dieses Ereignis tritt ein, wenn der Benutzer eine Zeile löscht, indem er auf einen Zeilenheader klickt und die ENTF\-TASTE drückt.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementieren Sie eine einfache `Customers`\-Klasse, um die von diesem Codebeispiel verwendeten Datenelemente darzustellen.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## Testen der Anwendung  
 Sie können das Formular jetzt testen und prüfen, ob es sich wie wie erwartet verhält.  
  
#### So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sie sehen ein mit drei Kundendatensätzen gefülltes <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  Sie können die Werte mehrerer Zellen in einer Zeile ändern und im Bearbeitungsmodus zweimal sowie außerhalb des Bearbeitungsmodus einmal die ESC\-Taste drücken, um die gesamte Zeile wieder auf die ursprünglichen Werte zurückzusetzen.  Beim Ändern, Hinzufügen oder Löschen von Zeilen im Steuerelement werden ebenfalls die `Customer`\-Objekte im Datenspeicher geändert, hinzugefügt oder gelöscht.  
  
## Nächste Schritte  
 Diese Anwendung vermittelt grundlegende Kenntnisse zu den Ereignissen, die zur Implementierung des virtuellen Modus im <xref:System.Windows.Forms.DataGridView>\-Steuerelement behandelt werden müssen.  Sie können diese Basisanwendung auf vielfältige Weise verbessern:  
  
-   Implementieren Sie einen Datenspeicher, der Werte von einer externen Datenbank zwischenspeichert.  Der Cache sollte Werte ggf. abrufen und verwerfen, sodass er nur die Daten enthält, die für die Anzeige erforderlich sind, und möglichst wenig Speicherplatz auf dem Clientcomputer belegt.  
  
-   Sie sollten die Leistung des Datenspeichers optimal an Ihre Anforderungen anpassen.  Beispielsweise können Sie langsame Netzwerkverbindungen kompensieren, indem Sie eine höhere Cachekapazität verwenden und die Anzahl der Datenbankabfragen reduzieren. Speicherbeschränkungen auf dem Clientcomputer bleiben dabei jedoch unberücksichtigt.  
  
 Weitere Informationen zum Zwischenspeichern von Werten von einer externen Datenbank finden Sie unter [Gewusst wie: Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>   
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>   
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>   
 <xref:System.Windows.Forms.DataGridView.RowValidated>   
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>   
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>   
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>   
 [Leistungsoptimierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)   
 [Gewusst wie: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)