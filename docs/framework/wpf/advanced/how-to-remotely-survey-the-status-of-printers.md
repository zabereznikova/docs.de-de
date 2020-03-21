---
title: 'Gewusst wie: Remoteüberwachung des Druckerstatus'
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
ms.openlocfilehash: 859ccb703c6c54c66d6ea7b433c67d156627e25b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187039"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Gewusst wie: Remoteüberwachung des Druckerstatus
In mittleren und großen Unternehmen kann es jederzeit dazu kommen, dass mehrere Drucker wegen eines Papierstaus oder fehlenden Papiers oder anderer problematischer Situationen ausfallen. Der umfangreiche Satz von Druckereigenschaften, die in den APIs von Microsoft .NET Framework verfügbar gemacht werden, bietet eine Möglichkeit, eine schnelle Übersicht über den Zuständen von Druckern durchzuführen.  
  
## <a name="example"></a>Beispiel  
 Die wichtigsten Schritte beim Erstellen dieses Hilfsprogramms sind die folgenden.  
  
1. Rufen Sie eine Liste aller Druckerserver ab.  
  
2. Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.  
  
3. Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, und lesen Sie jede Eigenschaft, die auf eine nicht ordnungsgemäß funktionierende Warteschlange hinweisen könnte.  
  
 Der folgende Code ist eine Reihe von Ausschnitten. Der Einfachheit halber wird in diesem Beispiel davon ausgegangen, dass eine CRLF-getrennte Liste der Druckerserver vorhanden ist. Die `fileOfPrintServers` Variable <xref:System.IO.StreamReader> ist ein Objekt für diese Datei. Da sich jeder Servername in einer <xref:System.IO.StreamReader.ReadLine%2A> eigenen Zeile befindet, ruft jeder <xref:System.IO.StreamReader>Aufruf von den Namen des nächsten Servers ab und verschiebt den Cursor an den Anfang der nächsten Zeile.  
  
 Innerhalb der äußeren Schleife erstellt <xref:System.Printing.PrintServer> der Code ein Objekt für den neuesten Druckserver und gibt an, dass die Anwendung über Administratorrechte für den Server verfügen soll.  
  
> [!NOTE]
> Wenn viele Server vorhanden sind, können Sie <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> die Leistung verbessern, indem Sie die Konstruktoren verwenden, die nur die Eigenschaften initialisieren, die Sie benötigen.  
  
 Das Beispiel <xref:System.Printing.PrintServer.GetPrintQueues%2A> wird dann verwendet, um eine Auflistung aller Warteschlangen des Servers zu erstellen, und beginnt, sie zu durchlaufen. Diese innere Schleife enthält eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckers zu überprüfen:  
  
- Sie können die Flags <xref:System.Printing.PrintQueue.QueueStatus%2A> der Eigenschaft <xref:System.Printing.PrintQueueStatus>des Typs lesen.  
  
- Sie können jede relevante <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>Eigenschaft <xref:System.Printing.PrintQueue.IsPaperJammed%2A>wie lesen, z. B. und .  
  
 In diesem Beispiel werden beide Methoden veranschaulicht, sodass der Benutzer zuvor gefragt wurde, welche Methode <xref:System.Printing.PrintQueue.QueueStatus%2A> verwendet werden soll, und mit "y" antwortete, wenn er die Flags der Eigenschaft verwenden wollte. Weitere Informationen zu den beiden Methoden finden Sie unten.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Um den Druckerstatus mithilfe <xref:System.Printing.PrintQueue.QueueStatus%2A> der Flags der Eigenschaft zu überprüfen, überprüfen Sie jedes relevante Flag, um festzustellen, ob es festgelegt ist. Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist. Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist. Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen. Weitere Informationen finden <xref:System.Printing.PrintQueueStatus>Sie unter , der& <xref:System.FlagsAttribute>Operator [(C-Referenz)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)und .  
  
 Für jedes Attribut, dessen Bit festgelegt ist, fügt der Code einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird. (Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Um den Status des Druckers mit jeder Eigenschaft zu überprüfen, lesen Sie einfach jede Eigenschaft und fügen einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird, sofern die Eigenschaft auf `true` festgelegt ist. (Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Die **ReportAvailabilityAtThisTime**-Methode wurde für die Fälle erstellt, bei denen Sie bestimmen müssen, ob die Warteschlange zum aktuellen Zeitpunkt zur Verfügung steht.  
  
 Die Methode führt nichts <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> aus, wenn die und-Eigenschaften gleich sind. da in diesem Fall der Drucker jederzeit verfügbar ist. Wenn sie unterschiedlich sind, ruft die Methode die aktuelle Zeit ab, <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> die <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> dann <xref:System.Int32>in Gesamtminuten nach Mitternacht <xref:System.DateTime> konvertiert werden muss, da die und Eigenschaften s sind, die Minuten nach Mitternacht darstellen, nicht Objekte. Schließlich überprüft die Methode, ob die aktuelle Zeit zwischen der Startzeit und der „bis“-Zeit liegt.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>Weitere Informationen

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
- [&-Operator (C-Referenz)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
