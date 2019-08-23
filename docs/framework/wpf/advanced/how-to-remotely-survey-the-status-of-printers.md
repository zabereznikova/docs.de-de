---
title: 'Vorgehensweise: Remoteüberwachung des Druckerstatus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: 0a7756684d5a133fa9cb014f109d14e413223ea9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945225"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Vorgehensweise: Remoteüberwachung des Druckerstatus
In mittleren und großen Unternehmen kann es jederzeit dazu kommen, dass mehrere Drucker wegen eines Papierstaus oder fehlenden Papiers oder anderer problematischer Situationen ausfallen. Der umfangreiche Satz von Druckereigenschaften, der in den APIs von Microsoft .NET Framework verfügbar gemacht wird, bietet die Möglichkeit, einen schnellen Überblick über die Zustände von Druckern zu erhalten.  
  
## <a name="example"></a>Beispiel  
 Die wichtigsten Schritte beim Erstellen dieses Dienstprogramms sind die folgenden.  
  
1. Rufen Sie eine Liste aller Druckerserver ab.  
  
2. Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.  
  
3. Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, und lesen Sie jede Eigenschaft, die auf eine nicht ordnungsgemäß funktionierende Warteschlange hinweisen könnte.  
  
 Der folgende Code ist eine Reihe von Ausschnitten. Der Einfachheit halber wird in diesem Beispiel davon ausgegangen, dass eine CRLF-getrennte Liste der Druckerserver vorhanden ist. Die- `fileOfPrintServers` Variable ist <xref:System.IO.StreamReader> ein-Objekt für diese Datei. Da sich jeder Servername in einer eigenen Zeile befindet, ruft jeder <xref:System.IO.StreamReader.ReadLine%2A> Aufrufe von den Namen des nächsten Servers ab und verschiebt <xref:System.IO.StreamReader>den Cursor an den Anfang der nächsten Zeile.  
  
 Innerhalb der äußeren Schleife erstellt der Code ein <xref:System.Printing.PrintServer> -Objekt für den neuesten Druckserver und gibt an, dass die Anwendung über Administratorrechte für den Server verfügen soll.  
  
> [!NOTE]
> Wenn viele Server vorhanden sind, können Sie die Leistung verbessern, indem Sie <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> die Konstruktoren verwenden, die nur die benötigten Eigenschaften initialisieren.  
  
 Im Beispiel wird dann <xref:System.Printing.PrintServer.GetPrintQueues%2A> verwendet, um eine Auflistung aller Warteschlangen des Servers zu erstellen und mit der Schleife zu beginnen. Diese innere Schleife enthält eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckers zu überprüfen:  
  
- Sie können die Flags <xref:System.Printing.PrintQueue.QueueStatus%2A> der Eigenschaft lesen, die vom Typ <xref:System.Printing.PrintQueueStatus>ist.  
  
- Sie können jede relevante Eigenschaft lesen <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, z. b. und. <xref:System.Printing.PrintQueue.IsPaperJammed%2A>  
  
 In diesem Beispiel werden beide Methoden veranschaulicht. Daher wurde der Benutzer zuvor gefragt, welche Methode verwendet werden soll, und mit "y" geantwortet, wenn er die Flags <xref:System.Printing.PrintQueue.QueueStatus%2A> der Eigenschaft verwenden wollte. Weitere Informationen zu den beiden Methoden finden Sie unten.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Wenn Sie den Druckerstatus mithilfe der Flags der <xref:System.Printing.PrintQueue.QueueStatus%2A> Eigenschaft überprüfen möchten, überprüfen Sie jedes relevante Flag, um festzustellen, ob es festgelegt ist. Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist. Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist. Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen. Weitere Informationen finden <xref:System.Printing.PrintQueueStatus>Sie unter, dem [&-OperatorC# (Verweis)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)und <xref:System.FlagsAttribute>.  
  
 Für jedes Attribut, dessen Bit festgelegt ist, fügt der Code einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird. (Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Um den Status des Druckers mit jeder Eigenschaft zu überprüfen, lesen Sie einfach jede Eigenschaft und fügen einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird, sofern die Eigenschaft auf `true` festgelegt ist. (Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Die **ReportAvailabilityAtThisTime**-Methode wurde für die Fälle erstellt, bei denen Sie bestimmen müssen, ob die Warteschlange zum aktuellen Zeitpunkt zur Verfügung steht.  
  
 Die-Methode führt keine Aktion aus <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> , <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> wenn die-Eigenschaft und die-Eigenschaft gleich sind, da in diesem Fall der Drucker jederzeit verfügbar ist. Wenn Sie unterschiedlich sind, ruft die-Methode die aktuelle Zeit ab, die dann in die Gesamt Minuten nach Mitternacht konvertiert <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> werden <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> muss, <xref:System.Int32>da die-Eigenschaft und die-Eigenschaft die <xref:System.DateTime> Anzahl der Minuten nach Mitternacht darstellen, nicht Gütern. Schließlich überprüft die Methode, ob die aktuelle Zeit zwischen der Startzeit und der „bis“-Zeit liegt.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [&-OperatorC# (Referenz)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
