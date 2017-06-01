---
title: "Gewusst wie: Diagnose von Problemen mit Druckauftr&#228;gen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Druckaufträge, Problemdiagnose"
  - "Druckaufträge, Problembehandlung"
  - "Beheben von Druckauftragsproblemen"
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Diagnose von Problemen mit Druckauftr&#228;gen
Netzwerkadministratoren erhalten oft Klagen von Benutzern über Druckaufträge, die gar nicht oder nur langsam gedruckt werden.  Die zahlreichen Eigenschaften für Druckaufträge, die in den [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] verfügbar gemacht werden, ermöglichen eine schnelle Remotediagnose von Druckaufträgen.  
  
## Beispiel  
 Die wichtigsten Schritte beim Erstellen dieses Dienstprogramms sind die folgenden.  
  
1.  Identifizieren Sie den Druckauftrag, über den sich der Benutzer beklagt.  Benutzer können diesen häufig nicht präzise identifizieren.  Möglicherweise kennen sie die Namen der Druckerserver oder Drucker nicht.  Unter Umständen beschreiben sie den Speicherort des Druckers mit einer anderen Terminologie als der beim Einrichten der <xref:System.Printing.PrintQueue.Location%2A>\-Eigenschaft verwendeten Terminologie.  Daher ist es eine gute Idee, eine Liste der derzeit vom Benutzer übermittelten Aufträge zu generieren.  Wenn mehrere Aufträge vorhanden sind, können Benutzer und Drucksystemadministrator gemeinsam den Auftrag isolieren, der die Probleme verursacht.  Die Teilschritte lauten wie folgt:  
  
    1.  Rufen Sie eine Liste aller Druckerserver ab.  
  
    2.  Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.  
  
    3.  Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, um ihre Aufträge abzufragen.  
  
    4.  Durchlaufen Sie in jeder Phase der Warteschlangenschleife ihre Aufträge, und sammeln Sie Informationen, die zur Identifizierung der Aufträge beitragen, die von dem sich beschwerenden Benutzer übermittelt wurden.  
  
2.  Wenn der problematische Druckauftrag identifiziert wurde, überprüfen Sie die relevanten Eigenschaften, um das Problem zu ermitteln.  Befindet sich der Auftrag beispielsweise in einem Fehlerstatus, oder hat der die Warteschlange bearbeitende Drucker vor dem Drucken des Auftrags in den Offlinemodus gewechselt?  
  
 Der folgende Code besteht aus einer Reihe von Codebeispielen.  Das erste Codebeispiel enthält das Durchlaufen der Druckwarteschlangen.  \(Schritt 1c oben.\) Die Variable `myPrintQueues` ist das <xref:System.Printing.PrintQueueCollection>\-Objekt für den aktuellen Druckerserver.  
  
 Das Codebeispiel beginnt mit der Aktualisierung des aktuellen Druckwarteschlangenobjekts mit <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=fullName>.  Auf diese Weise wird sichergestellt, dass die Eigenschaften des Objekts den Zustand des physischen Druckers, den es darstellt, genau darstellen.  Anschließend ruft die Anwendung durch Verwendung von <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A> die Auflistung der Druckaufträge ab, die sich gerade in der Druckwarteschlange befinden.  
  
 Danach durchläuft die Anwendung die <xref:System.Printing.PrintSystemJobInfo>\-Auflistung und vergleicht jede <xref:System.Printing.PrintSystemJobInfo.Submitter%2A>\-Eigenschaft mit dem Alias des Benutzers, der sich beschwert hat.  Bei einer Übereinstimmung fügt die Anwendung Identifizierungsinformationen über den Auftrag zur Zeichenfolge hinzu, die dargestellt wird.  \(Die `userName`\-Variable und die `jobList`\-Variable werden vorher in der Anwendung initialisiert.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 Im nächsten Codebeispiel wird die Anwendung bei Schritt 2 aufgegriffen.  \(Siehe oben.\) Der problematische Auftrag wurde identifiziert, und die Anwendung fordert zur Eingabe der Informationen auf, die ihn identifizieren.  Aus diesen Informationen werden <xref:System.Printing.PrintServer>\-Objekte, <xref:System.Printing.PrintQueue>\-Objekte und <xref:System.Printing.PrintSystemJobInfo>\-Objekte erstellt.  
  
 Jetzt enthält die Anwendung eine Verzweigungsstruktur, die den zwei Möglichkeiten entspricht, den Status eines Druckauftrags zu überprüfen:  
  
-   Sie können die Flags der <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>\-Eigenschaft lesen, die vom Typ <xref:System.Printing.PrintJobStatus> ist.  
  
-   Sie können jede relevante Eigenschaft, z. B. <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> und <xref:System.Printing.PrintSystemJobInfo.IsInError%2A> lesen.  
  
 In diesem Beispiel werden beide Methoden veranschaulicht. Daher wurde der Benutzer zuvor zur Eingabe der zu verwendenden Methode aufgefordert und hat "Y" eingegeben, um die Flags der <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>\-Eigenschaft zu verwenden.  Weitere Informationen zu den beiden Methoden finden Sie unten.  Abschließend verwendet die Anwendung eine Methode namens **ReportQueueAndJobAvailability**, um zu melden, ob der Auftrag zu dieser Tageszeit gedruckt werden kann.  Diese Methode wird in [Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann](../../../../docs/framework/wpf/advanced/how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md) erläutert.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Um den Status des Druckauftrags mit den Flags der <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>\-Eigenschaft zu überprüfen, müssen Sie für jedes relevante Flag überprüfen, ob es festgelegt ist.  Standardmäßig wird durch Ausführen eines logischen AND\-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweitem Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist.  Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND\-Vorgang lediglich, dass dasselbe Bit festgelegt ist.  Um herauszufinden, ob das Bit festgelegt ist, brauchen Sie das Ergebnis des logischen AND\-Vorgangs nur mit dem Flag selbst zu vergleichen.  Weitere Informationen finden Sie unter <xref:System.Printing.PrintJobStatus>, [Operator & \(C\#\-Referenz\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) und <xref:System.FlagsAttribute>.  
  
 Für jedes Attribut, dessen Bit festgelegt ist, wird dies vom Code an den Konsolenbildschirm gemeldet. Manchmal wird auch eine mögliche Reaktion vorgeschlagen.  \(Die **HandlePausedJob**\-Methode, die aufgerufen wird, wenn der Auftrag oder die Warteschlange angehalten wird, wird unten erläutert.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Um den Status des Druckauftrags mit separaten Eigenschaften zu überprüfen, lesen Sie einfach jede Eigenschaft und melden sie, sofern die Eigenschaft auf `true` festgelegt ist, an den Konsolenbildschirm und schlagen unter Umständen eine mögliche Reaktion vor.  \(Die **HandlePausedJob**\-Methode, die aufgerufen wird, wenn der Auftrag oder die Warteschlange angehalten wird, wird unten erläutert.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 Die **HandlePausedJob**\-Methode ermöglicht es dem Benutzer der Anwendung, angehaltene Aufträge remote fortzusetzen.  Da für das Anhalten der Druckwarteschlange ein triftiger Grund vorliegen kann, fordert die Methode den Benutzer zunächst zur Entscheidung auf, ob der Auftrag fortgesetzt werden soll.  Wenn die Antwort "Y" ist, wird die <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=fullName>\-Methode aufgerufen.  
  
 Anschließend muss der Benutzer entscheiden, ob der Auftrag selbst fortgesetzt werden soll, falls dieser unabhängig von der Druckwarteschlange angehalten wurde.  \(Vergleichen Sie <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=fullName> und <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=fullName>.\) Wenn die Antwort "Y" ist, wird die <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=fullName>\-Methode aufgerufen. Andernfalls wird <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> aufgerufen.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## Siehe auch  
 <xref:System.Printing.PrintJobStatus>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.FlagsAttribute>   
 <xref:System.Printing.PrintQueue>   
 [Operator & \(C\#\-Referenz\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)