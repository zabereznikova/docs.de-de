---
title: 'Vorgehensweise: Diagnose von Problemen mit Druckaufträgen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- troubleshooting print job problems [WPF]
- print jobs [WPF], troubleshooting
- print jobs [WPF], diagnosing problems
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
ms.openlocfilehash: 7a2f6cd76cf44a3a6bd431e53ba0c10d3438037e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665798"
---
# <a name="how-to-diagnose-problematic-print-job"></a>Vorgehensweise: Diagnose von Problemen mit Druckaufträgen
Netzwerkadministratoren erhalten oft Beschwerden von Benutzern über Druckaufträge, die gar nicht oder nur langsam gedruckt werden. Den umfassenden Satz an Eigenschaften eines Druckauftrags verfügbar gemacht werden, der [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von Microsoft .NET Framework ermöglichen eine schnelle remote-Diagnose von Druckaufträgen ausführen.  
  
## <a name="example"></a>Beispiel  
 Die wichtigsten Schritte beim Erstellen dieses Hilfsprogramms sind die folgenden.  
  
1.  Identifizieren Sie den Druckauftrag, über den sich der Benutzer beschwert. Benutzern ist dies häufig nicht genau möglich. Sie wissen möglicherweise den Namen des Druckerserver oder Druckers nicht. Sie können den Speicherort des Druckers in anderer Terminologie verwendet als bei der Einstellung beschreiben die <xref:System.Printing.PrintQueue.Location%2A> Eigenschaft. Daher ist es eine gute Idee, eine Liste der zuletzt übermittelten Druckaufträge des Benutzers zu erstellen. Wenn es mehr als einen Druckauftrag gibt, kann die Kommunikation zwischen dem Benutzer und dem Administrator des Drucksystems verwendet werden, um den Auftrag zu ermitteln, bei dem Probleme vorliegen. Die Teilschritte werden im Folgenden beschrieben.  
  
    1.  Rufen Sie eine Liste aller Druckerserver ab.  
  
    2.  Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.  
  
    3.  Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, um die Aufträge abzufragen.  
  
    4.  Durchlaufen Sie in jeder Phase der Serverschleife alle Aufträge und sammeln Sie bezeichnende Informationen über die Aufträge, die vom Benutzer übermittelt wurden, der die Beschwerde gestellt hat.  
  
2.  Untersuchen Sie relevante Eigenschaften, wenn der Druckauftrag mit Problemen identifiziert wurde, um herauszufinden, wo das Problem liegen könnte. Befindet sich der Auftrag z.B. im Fehlerstatus oder ist der Drucker, der die Warteschleife wartet in den Offlinemodus gewechselt, bevor der Auftrag gedruckt werden konnte?  
  
 Im unteren Code finden Sie eine Reihe von Codebeispielen. Das erste Codebeispiel enthält das Durchlaufen der Druckerwarteschlangen. (Schritt 1c oben.) Die Variable `myPrintQueues` ist die <xref:System.Printing.PrintQueueCollection> -Objekt für den aktuellen Druckerserver.  
  
 Das Codebeispiel beginnt durch Aktualisieren der aktuellen druckerwarteschlangenobjekts mit <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=nameWithType>. Dadurch wird sichergestellt, dass die Eigenschaften des Objekts den Status des physischen Druckers, den es repräsentiert, akkurat darstellen. Und dann die Anwendung die Auflistung von Druckaufträgen derzeit in der Druckwarteschlange mit erhält <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>.  
  
 Neben die Anwendung durchläuft die <xref:System.Printing.PrintSystemJobInfo> -Auflistung und vergleicht jede <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> Eigenschaft mit dem Alias des Benutzers Beschwerde gestellt. Wenn Sie übereinstimmen, fügt die Anwendung bezeichnende Informationen über den Auftrag zur Zeichenfolge hinzu, die dargestellt wird. (Die Variablen `userName` und `jobList` werden früher in der Anwendung initialisiert.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 Im nächsten Codebeispiel wird die Anwendung bei Schritt 2 aufgenommen. (Siehe oben.) Der problematische Auftrag wurde identifiziert, und die Anwendung fordert die Informationen an, die ihn identifizieren. Aus diesen Informationen erstellt er <xref:System.Printing.PrintServer>, <xref:System.Printing.PrintQueue>, und <xref:System.Printing.PrintSystemJobInfo> Objekte.  
  
 Zu diesem Zeitpunkt enthält die Anwendung eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckauftrags zu überprüfen:  
  
-   Sie können die Flags der Lesen der <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> Eigenschaft, die vom Typ <xref:System.Printing.PrintJobStatus>.  
  
-   Sie können jede relevante Eigenschaft wie z. B. Lesen <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> und <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>.  
  
 In diesem Beispiel werden beide Methoden veranschaulicht, damit der Benutzer zuvor hinsichtlich der zu verwendenden Methode aufgefordert und hat "Y", wenn er die Flags der verwenden die <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> Eigenschaft. Weitere Informationen zu den beiden Methoden finden Sie unten. Schließlich verwendet die Anwendung eine Methode namens **ReportQueueAndJobAvailability**, die meldet, ob der Auftrag zu dieser Tageszeit gedruckt werden kann. Diese Methode wird in [Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann](../../../../docs/framework/wpf/advanced/how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md) diskutiert.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Überprüfen des Status des Druckauftrags mit den Flags der der <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> -Eigenschaft, zu überprüfen jedes relevante Flag überprüfen, ob es festgelegt ist. Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist. Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist. Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen. Weitere Informationen finden Sie unter <xref:System.Printing.PrintJobStatus>, [&-Operator (C# Verweis)](~/docs/csharp/language-reference/operators/and-operator.md), und <xref:System.FlagsAttribute>.  
  
 Für jedes Attribut, dessen Bit festgelegt ist, meldet der Code dies im Konsolenfenster, und schlägt manchmal eine mögliche Reaktion vor. (Die Methode **HandlePausedJob**, die aufgerufen wird, wenn der Auftrag oder die Warteschlange wie oben beschrieben angehalten wird.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Sie müssen einfach jede Eigenschaft lesen, um den Status des Druckauftrags mithilfe verschiedener Eigenschaften zu überprüfen, und wenn die Eigenschaft `true` ist, an die Konsole berichten und eine mögliche Reaktion vorschlagen. (Die Methode **HandlePausedJob**, die aufgerufen wird, wenn der Auftrag oder die Warteschlange wie oben beschrieben angehalten wird.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 Die Methode **HandlePausedJob** ermöglicht dem Benutzer der Anwendung, angehaltene Druckaufträge Remote fortzusetzen. Da es vermutlich einen guten Grund gibt, warum die Druckerwarteschlange angehalten war, fordert die Methode den Benutzer zuerst zu einer Entscheidung auf, die Warteschlange fortzusetzen. Wenn die Antwort "Y", und klicken Sie dann die <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=nameWithType> Methode wird aufgerufen.  
  
 Als Nächstes wird der Benutzer aufgefordert, zu entscheiden, ob der Auftrag selbst fortgesetzt werden soll, falls er unabhängig von der Warteschlange angehalten wurde. (Vergleichen <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=nameWithType> und <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=nameWithType>.) Wenn die Antwort "Y", klicken Sie dann <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=nameWithType> aufgerufen wird; andernfalls <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> aufgerufen wird.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Printing.PrintJobStatus>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintQueue>
- [&-Operator (C# Verweis)](~/docs/csharp/language-reference/operators/and-operator.md)
- [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)
