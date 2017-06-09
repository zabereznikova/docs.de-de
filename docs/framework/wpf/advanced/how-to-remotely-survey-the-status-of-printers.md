---
title: "Gewusst wie: Remote&#252;berwachung des Druckerstatus | Microsoft Docs"
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
  - "Druckerstatus, Remoteüberwachung"
  - "Remoteüberwachung des Druckerstatus"
  - "Status, Drucker, Remoteüberwachung"
  - "Remoteüberwachung des Druckerstatus"
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Remote&#252;berwachung des Druckerstatus
In mittleren und großen Unternehmen kann es jederzeit dazu kommen, dass mehrere Drucker wegen eines Papierstaus oder fehlenden Papiers oder anderer problematischer Situationen ausfallen.  Die zahlreichen Druckeigenschaften, die in den [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] verfügbar gemacht werden, ermöglichen eine schnelle Überwachung der Druckerzustände.  
  
## Beispiel  
 Die wichtigsten Schritte beim Erstellen dieses Dienstprogramms sind die folgenden.  
  
1.  Rufen Sie eine Liste aller Druckerserver ab.  
  
2.  Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.  
  
3.  Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, und lesen Sie jede Eigenschaft, die auf eine nicht ordnungsgemäß funktionierende Warteschlange hinweisen könnte.  
  
 Der folgende Code ist eine Reihe von Ausschnitten.  Der Einfachheit halber wird in diesem Beispiel davon ausgegangen, dass eine CRLF\-getrennte Liste der Druckerserver vorhanden ist.  Die `fileOfPrintServers`\-Variable ist ein <xref:System.IO.StreamReader>\-Objekt für diese Datei.  Da sich jeder Servername in einer eigenen Zeile befindet, wird durch jeden Aufruf von <xref:System.IO.StreamReader.ReadLine%2A> der Name des nächsten Servers abgerufen und der Cursor von <xref:System.IO.StreamReader> an den Anfang der nächsten Zeile verschoben.  
  
 In der äußeren Schleife wird durch den Code ein <xref:System.Printing.PrintServer>\-Objekt für den letzten Druckerserver erstellt und angegeben, dass die Anwendung über Administratorrechte für den Server verfügen muss.  
  
> [!NOTE]
>  Wenn sehr viele Server vorhanden sind, können Sie die Leistung mithilfe von [PrintServer\(String, String\<xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29>\-Konstruktoren verbessern, die nur die tatsächlich erforderlichen Eigenschaften initialisieren.  
  
 Im Beispiel wird dann mithilfe von <xref:System.Printing.PrintServer.GetPrintQueues%2A> eine Auflistung aller Serverwarteschlangen erstellt, die alle durchlaufen werden.  Diese innere Schleife enthält eine Verzweigungsstruktur, die den zwei Möglichkeiten entspricht, den Status eines Druckers zu überprüfen:  
  
-   Sie können die Flags der <xref:System.Printing.PrintQueue.QueueStatus%2A>\-Eigenschaft lesen, die vom Typ <xref:System.Printing.PrintQueueStatus> ist.  
  
-   Sie können jede relevante Eigenschaft, z. B. <xref:System.Printing.PrintQueue.IsOutOfPaper%2A> und <xref:System.Printing.PrintQueue.IsPaperJammed%2A> lesen.  
  
 In diesem Beispiel werden beide Methoden veranschaulicht. Daher wurde der Benutzer zuvor zur Eingabe der zu verwendenden Methode aufgefordert und hat "y" eingegeben, um die Flags der <xref:System.Printing.PrintQueue.QueueStatus%2A>\-Eigenschaft zu verwenden.  Weitere Informationen zu den beiden Methoden finden Sie unten.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Um den Status des Druckers mit den Flags der <xref:System.Printing.PrintQueue.QueueStatus%2A>\-Eigenschaften zu überprüfen, müssen Sie für jedes relevante Flag überprüfen, ob es festgelegt ist.  Standardmäßig wird durch Ausführen eines logischen AND\-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweitem Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist.  Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND\-Vorgang lediglich, dass dasselbe Bit festgelegt ist.  Um herauszufinden, ob das Bit festgelegt ist, brauchen Sie das Ergebnis des logischen AND\-Vorgangs nur mit dem Flag selbst zu vergleichen.  Weitere Informationen finden Sie unter <xref:System.Printing.PrintQueueStatus>, [Operator & \(C\#\-Referenz\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) und <xref:System.FlagsAttribute>.  
  
 Für jedes Attribut, dessen Bit festgelegt ist, fügt der Code einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird.  \(Die **ReportAvailabilityAtThisTime**\-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.\)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Um den Status des Druckers mit jeder Eigenschaft zu überprüfen, lesen Sie einfach jede Eigenschaft und fügen einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird, sofern die Eigenschaft auf `true` festgelegt ist.  \(Die **ReportAvailabilityAtThisTime**\-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.\)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Die **ReportAvailabilityAtThisTime**\-Methode wurde für die Fälle erstellt, bei denen Sie bestimmen müssen, ob die Warteschlange zum aktuellen Zeitpunkt zur Verfügung steht.  
  
 Die Methode ist wirkungslos, wenn die Eigenschaften <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> gleich sind, da der Drucker in diesem Fall jederzeit verfügbar ist.  Wenn die Eigenschaften nicht gleich sind, ruft die Methode die aktuelle Uhrzeit ab, die dann in die Gesamtanzahl der Minuten nach Mitternacht konvertiert werden muss, weil es sich bei den Eigenschaften <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> um <xref:System.Int32> handelt, die Minuten nach Mitternacht darstellen, und nicht um <xref:System.DateTime>\-Objekte.  Schließlich überprüft die Methode, ob die aktuelle Zeit zwischen der Startzeit und der "bis"\-Zeit liegt.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## Siehe auch  
 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>   
 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>   
 <xref:System.DateTime>   
 <xref:System.Printing.PrintQueueStatus>   
 <xref:System.FlagsAttribute>   
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 [Operator & \(C\#\-Referenz\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)