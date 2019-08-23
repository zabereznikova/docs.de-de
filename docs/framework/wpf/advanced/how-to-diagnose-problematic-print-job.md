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
ms.openlocfilehash: 181248f69684860fd43648952ef4eb3cced1c0ba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944636"
---
# <a name="how-to-diagnose-problematic-print-job"></a>Vorgehensweise: Diagnose von Problemen mit Druckaufträgen
Netzwerkadministratoren erhalten oft Beschwerden von Benutzern über Druckaufträge, die gar nicht oder nur langsam gedruckt werden. Der umfangreiche Satz von Druckauftrags Eigenschaften, die in den APIs von Microsoft .NET Framework verfügbar gemacht werden, ermöglichen eine schnelle Remote Diagnose von Druckaufträgen.  
  
## <a name="example"></a>Beispiel  
 Die wichtigsten Schritte beim Erstellen dieses Hilfsprogramms sind die folgenden.  
  
1. Identifizieren Sie den Druckauftrag, über den sich der Benutzer beschwert. Benutzern ist dies häufig nicht genau möglich. Sie wissen möglicherweise den Namen des Druckerserver oder Druckers nicht. Sie können den Speicherort des Druckers in einer anderen Terminologie beschreiben, als beim Festlegen <xref:System.Printing.PrintQueue.Location%2A> der-Eigenschaft verwendet wurde. Daher ist es eine gute Idee, eine Liste der zuletzt übermittelten Druckaufträge des Benutzers zu erstellen. Wenn es mehr als einen Druckauftrag gibt, kann die Kommunikation zwischen dem Benutzer und dem Administrator des Drucksystems verwendet werden, um den Auftrag zu ermitteln, bei dem Probleme vorliegen. Die Teilschritte werden im Folgenden beschrieben.  
  
    1. Rufen Sie eine Liste aller Druckerserver ab.  
  
    2. Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.  
  
    3. Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, um die Aufträge abzufragen.  
  
    4. Durchlaufen Sie in jeder Phase der Serverschleife alle Aufträge und sammeln Sie bezeichnende Informationen über die Aufträge, die vom Benutzer übermittelt wurden, der die Beschwerde gestellt hat.  
  
2. Untersuchen Sie relevante Eigenschaften, wenn der Druckauftrag mit Problemen identifiziert wurde, um herauszufinden, wo das Problem liegen könnte. Befindet sich der Auftrag z.B. im Fehlerstatus oder ist der Drucker, der die Warteschleife wartet in den Offlinemodus gewechselt, bevor der Auftrag gedruckt werden konnte?  
  
 Im unteren Code finden Sie eine Reihe von Codebeispielen. Das erste Codebeispiel enthält das Durchlaufen der Druckerwarteschlangen. (Schritt 1c oben.) Die- `myPrintQueues` Variable ist <xref:System.Printing.PrintQueueCollection> das-Objekt für den aktuellen Druckserver.  
  
 Das Codebeispiel beginnt mit dem Aktualisieren des aktuellen druckwarteschlangenobjekts mit <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=nameWithType>. Dadurch wird sichergestellt, dass die Eigenschaften des Objekts den Status des physischen Druckers, den es repräsentiert, akkurat darstellen. Anschließend ruft die Anwendung die Auflistung der Druckaufträge, die sich derzeit in der Druck <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>Warteschlange befinden, mit ab.  
  
 Im nächsten Schritt durchläuft die <xref:System.Printing.PrintSystemJobInfo> Anwendung die Auflistung und <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> vergleicht jede Eigenschaft mit dem Alias des beanstandenden Benutzers. Wenn Sie übereinstimmen, fügt die Anwendung bezeichnende Informationen über den Auftrag zur Zeichenfolge hinzu, die dargestellt wird. (Die Variablen `userName` und `jobList` werden früher in der Anwendung initialisiert.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 Im nächsten Codebeispiel wird die Anwendung bei Schritt 2 aufgenommen. (Siehe oben.) Der problematische Auftrag wurde identifiziert, und die Anwendung fordert die Informationen an, die ihn identifizieren. Aus diesen Informationen werden- <xref:System.Printing.PrintServer>, <xref:System.Printing.PrintQueue>-und <xref:System.Printing.PrintSystemJobInfo> -Objekte erstellt.  
  
 Zu diesem Zeitpunkt enthält die Anwendung eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckauftrags zu überprüfen:  
  
- Sie können die Flags <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> der Eigenschaft lesen, die vom Typ <xref:System.Printing.PrintJobStatus>ist.  
  
- Sie können jede relevante Eigenschaft lesen, z <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> . <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>b. und.  
  
 In diesem Beispiel werden beide Methoden veranschaulicht. Daher wurde der Benutzer zuvor gefragt, welche Methode verwendet werden soll, und mit "Y" geantwortet, wenn er die Flags <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> der Eigenschaft verwenden wollte. Weitere Informationen zu den beiden Methoden finden Sie unten. Schließlich verwendet die Anwendung eine Methode namens **ReportQueueAndJobAvailability**, die meldet, ob der Auftrag zu dieser Tageszeit gedruckt werden kann. Diese Methode wird in [Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann](how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md) diskutiert.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Wenn Sie den Druckauftrags Status mithilfe der Flags <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> der Eigenschaft überprüfen möchten, überprüfen Sie jedes relevante Flag, um festzustellen, ob es festgelegt ist. Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist. Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist. Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen. Weitere Informationen finden <xref:System.Printing.PrintJobStatus>Sie unter, dem [&-OperatorC# (Verweis)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)und <xref:System.FlagsAttribute>.  
  
 Für jedes Attribut, dessen Bit festgelegt ist, meldet der Code dies im Konsolenfenster, und schlägt manchmal eine mögliche Reaktion vor. (Die Methode **HandlePausedJob**, die aufgerufen wird, wenn der Auftrag oder die Warteschlange wie oben beschrieben angehalten wird.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Sie müssen einfach jede Eigenschaft lesen, um den Status des Druckauftrags mithilfe verschiedener Eigenschaften zu überprüfen, und wenn die Eigenschaft `true` ist, an die Konsole berichten und eine mögliche Reaktion vorschlagen. (Die Methode **HandlePausedJob**, die aufgerufen wird, wenn der Auftrag oder die Warteschlange wie oben beschrieben angehalten wird.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 Die Methode **HandlePausedJob** ermöglicht dem Benutzer der Anwendung, angehaltene Druckaufträge Remote fortzusetzen. Da es vermutlich einen guten Grund gibt, warum die Druckerwarteschlange angehalten war, fordert die Methode den Benutzer zuerst zu einer Entscheidung auf, die Warteschlange fortzusetzen. Wenn die Antwort "Y" lautet, wird die <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=nameWithType> -Methode aufgerufen.  
  
 Als Nächstes wird der Benutzer aufgefordert, zu entscheiden, ob der Auftrag selbst fortgesetzt werden soll, falls er unabhängig von der Warteschlange angehalten wurde. (Vergleichen <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=nameWithType> Sie <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=nameWithType>und.) Wenn die Antwort "Y" lautet, <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=nameWithType> wird aufgerufen; andernfalls <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> wird aufgerufen.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Printing.PrintJobStatus>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintQueue>
- [&-OperatorC# (Referenz)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
