---
title: "Gewusst wie: Remoteüberwachung des Druckerstatus"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad824a1cef637edc99e6aaafc99d557167ea1f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Gewusst wie: Remoteüberwachung des Druckerstatus
In mittleren und großen Unternehmen kann es jederzeit dazu kommen, dass mehrere Drucker wegen eines Papierstaus oder fehlenden Papiers oder anderer problematischer Situationen ausfallen. Die zahlreichen Druckeigenschaften, die in den [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] verfügbar gemacht werden, ermöglichen eine schnelle Überwachung der Druckerzustände.  
  
## <a name="example"></a>Beispiel  
 Die wichtigsten Schritte beim Erstellen dieses Dienstprogramms sind die folgenden.  
  
1.  Rufen Sie eine Liste aller Druckerserver ab.  
  
2.  Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.  
  
3.  Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, und lesen Sie jede Eigenschaft, die auf eine nicht ordnungsgemäß funktionierende Warteschlange hinweisen könnte.  
  
 Der folgende Code ist eine Reihe von Ausschnitten. Der Einfachheit halber wird in diesem Beispiel davon ausgegangen, dass eine CRLF-getrennte Liste der Druckerserver vorhanden ist. Die Variable `fileOfPrintServers` ist ein <xref:System.IO.StreamReader> Objekt für diese Datei. Da die Namen aller Server in einer eigenen Zeile ist, jeden Aufruf von <xref:System.IO.StreamReader.ReadLine%2A> Ruft den Namen des nächsten Servers ab, und verschiebt die <xref:System.IO.StreamReader>des Cursors an den Anfang der nächsten Zeile.  
  
 In der äußeren Schleife im Code erstellt ein <xref:System.Printing.PrintServer> -Objekt für den letzten Druckerserver und gibt an, dass die Anwendung über Administratorrechte auf dem Server verfügen.  
  
> [!NOTE]
>  Wenn viele der Server vorhanden sind, können Sie die Leistung verbessern, mithilfe der <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> Konstruktoren, die nur die Eigenschaften zu Sie sind im Begriff initialisieren zu benötigen.  
  
 Anschließend wird <xref:System.Printing.PrintServer.GetPrintQueues%2A> zum Erstellen einer Auflistung aller von dem server's, Warteschlangen und beginnt, die durchlaufen werden. Diese innere Schleife enthält eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckers zu überprüfen:  
  
-   Informieren Sie sich die Flags der <xref:System.Printing.PrintQueue.QueueStatus%2A> Eigenschaft vom Typ <xref:System.Printing.PrintQueueStatus>.  
  
-   Sie können jede relevante Eigenschaft, z. B. Lesen <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, und <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 Dieses Beispiel zeigt beide Methoden aus, damit der Benutzer zuvor dazu aufgefordert, um die werden zu verwendende Methode und mit "y" geantwortet wird, wenn er oder sie verwenden wollten, die Flags der <xref:System.Printing.PrintQueue.QueueStatus%2A> Eigenschaft. Weitere Informationen zu den beiden Methoden finden Sie unten.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Überprüfen Sie den Status des Druckers mit den Flags der der <xref:System.Printing.PrintQueue.QueueStatus%2A> -Eigenschaft, überprüfen Sie jedes relevante Flag, um festzustellen, ob sie festgelegt ist. Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist. Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist. Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen. Weitere Informationen finden Sie unter <xref:System.Printing.PrintQueueStatus>, [&-Operator (C#-Referenz)](~/docs/csharp/language-reference/operators/and-operator.md), und <xref:System.FlagsAttribute>.  
  
 Für jedes Attribut, dessen Bit festgelegt ist, fügt der Code einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird. (Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Um den Status des Druckers mit jeder Eigenschaft zu überprüfen, lesen Sie einfach jede Eigenschaft und fügen einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird, sofern die Eigenschaft auf `true` festgelegt ist. (Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Die **ReportAvailabilityAtThisTime**-Methode wurde für die Fälle erstellt, bei denen Sie bestimmen müssen, ob die Warteschlange zum aktuellen Zeitpunkt zur Verfügung steht.  
  
 Die Methode keine Wirkung, wenn die <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften gleich sind, da in diesem Fall der Drucker jederzeit verfügbar ist. Falls verschieden, ruft die Methode die aktuelle Uhrzeit, die dann in der Gesamtzahl der Minuten nach Mitternacht konvertiert werden, da die <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften sind <xref:System.Int32>Minuten nach Mitternacht, nicht darstellen <xref:System.DateTime> -Objekte. Schließlich überprüft die Methode, ob die aktuelle Zeit zwischen der Startzeit und der „bis“-Zeit liegt.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>Siehe auch  
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
 [&-Operator (C#-Referenz)](~/docs/csharp/language-reference/operators/and-operator.md)  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)
