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
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="e8306-102">Vorgehensweise: Remoteüberwachung des Druckerstatus</span><span class="sxs-lookup"><span data-stu-id="e8306-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="e8306-103">In mittleren und großen Unternehmen kann es jederzeit dazu kommen, dass mehrere Drucker wegen eines Papierstaus oder fehlenden Papiers oder anderer problematischer Situationen ausfallen.</span><span class="sxs-lookup"><span data-stu-id="e8306-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="e8306-104">Der umfangreiche Satz von Druckereigenschaften, der in den APIs von Microsoft .NET Framework verfügbar gemacht wird, bietet die Möglichkeit, einen schnellen Überblick über die Zustände von Druckern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e8306-104">The rich set of printer properties exposed in the APIs of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8306-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8306-105">Example</span></span>  
 <span data-ttu-id="e8306-106">Die wichtigsten Schritte beim Erstellen dieses Dienstprogramms sind die folgenden.</span><span class="sxs-lookup"><span data-stu-id="e8306-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="e8306-107">Rufen Sie eine Liste aller Druckerserver ab.</span><span class="sxs-lookup"><span data-stu-id="e8306-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="e8306-108">Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.</span><span class="sxs-lookup"><span data-stu-id="e8306-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="e8306-109">Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, und lesen Sie jede Eigenschaft, die auf eine nicht ordnungsgemäß funktionierende Warteschlange hinweisen könnte.</span><span class="sxs-lookup"><span data-stu-id="e8306-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="e8306-110">Der folgende Code ist eine Reihe von Ausschnitten.</span><span class="sxs-lookup"><span data-stu-id="e8306-110">The code below is a series of snippets.</span></span> <span data-ttu-id="e8306-111">Der Einfachheit halber wird in diesem Beispiel davon ausgegangen, dass eine CRLF-getrennte Liste der Druckerserver vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e8306-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="e8306-112">Die- `fileOfPrintServers` Variable ist <xref:System.IO.StreamReader> ein-Objekt für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="e8306-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="e8306-113">Da sich jeder Servername in einer eigenen Zeile befindet, ruft jeder <xref:System.IO.StreamReader.ReadLine%2A> Aufrufe von den Namen des nächsten Servers ab und verschiebt <xref:System.IO.StreamReader>den Cursor an den Anfang der nächsten Zeile.</span><span class="sxs-lookup"><span data-stu-id="e8306-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="e8306-114">Innerhalb der äußeren Schleife erstellt der Code ein <xref:System.Printing.PrintServer> -Objekt für den neuesten Druckserver und gibt an, dass die Anwendung über Administratorrechte für den Server verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="e8306-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8306-115">Wenn viele Server vorhanden sind, können Sie die Leistung verbessern, indem Sie <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> die Konstruktoren verwenden, die nur die benötigten Eigenschaften initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e8306-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="e8306-116">Im Beispiel wird dann <xref:System.Printing.PrintServer.GetPrintQueues%2A> verwendet, um eine Auflistung aller Warteschlangen des Servers zu erstellen und mit der Schleife zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e8306-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="e8306-117">Diese innere Schleife enthält eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckers zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="e8306-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
- <span data-ttu-id="e8306-118">Sie können die Flags <xref:System.Printing.PrintQueue.QueueStatus%2A> der Eigenschaft lesen, die vom Typ <xref:System.Printing.PrintQueueStatus>ist.</span><span class="sxs-lookup"><span data-stu-id="e8306-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
- <span data-ttu-id="e8306-119">Sie können jede relevante Eigenschaft lesen <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, z. b. und. <xref:System.Printing.PrintQueue.IsPaperJammed%2A></span><span class="sxs-lookup"><span data-stu-id="e8306-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="e8306-120">In diesem Beispiel werden beide Methoden veranschaulicht. Daher wurde der Benutzer zuvor gefragt, welche Methode verwendet werden soll, und mit "y" geantwortet, wenn er die Flags <xref:System.Printing.PrintQueue.QueueStatus%2A> der Eigenschaft verwenden wollte.</span><span class="sxs-lookup"><span data-stu-id="e8306-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="e8306-121">Weitere Informationen zu den beiden Methoden finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="e8306-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="e8306-122">Abschließend werden dem Benutzer die Ergebnisse präsentiert.</span><span class="sxs-lookup"><span data-stu-id="e8306-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="e8306-123">Wenn Sie den Druckerstatus mithilfe der Flags der <xref:System.Printing.PrintQueue.QueueStatus%2A> Eigenschaft überprüfen möchten, überprüfen Sie jedes relevante Flag, um festzustellen, ob es festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8306-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="e8306-124">Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8306-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="e8306-125">Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8306-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="e8306-126">Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen.</span><span class="sxs-lookup"><span data-stu-id="e8306-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="e8306-127">Weitere Informationen finden <xref:System.Printing.PrintQueueStatus>Sie unter, dem [&-OperatorC# (Verweis)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)und <xref:System.FlagsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e8306-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="e8306-128">Für jedes Attribut, dessen Bit festgelegt ist, fügt der Code einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8306-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="e8306-129">(Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)</span><span class="sxs-lookup"><span data-stu-id="e8306-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="e8306-130">Um den Status des Druckers mit jeder Eigenschaft zu überprüfen, lesen Sie einfach jede Eigenschaft und fügen einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird, sofern die Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8306-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="e8306-131">(Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)</span><span class="sxs-lookup"><span data-stu-id="e8306-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="e8306-132">Die **ReportAvailabilityAtThisTime**-Methode wurde für die Fälle erstellt, bei denen Sie bestimmen müssen, ob die Warteschlange zum aktuellen Zeitpunkt zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="e8306-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="e8306-133">Die-Methode führt keine Aktion aus <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> , <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> wenn die-Eigenschaft und die-Eigenschaft gleich sind, da in diesem Fall der Drucker jederzeit verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e8306-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="e8306-134">Wenn Sie unterschiedlich sind, ruft die-Methode die aktuelle Zeit ab, die dann in die Gesamt Minuten nach Mitternacht konvertiert <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> werden <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> muss, <xref:System.Int32>da die-Eigenschaft und die-Eigenschaft die <xref:System.DateTime> Anzahl der Minuten nach Mitternacht darstellen, nicht Gütern.</span><span class="sxs-lookup"><span data-stu-id="e8306-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="e8306-135">Schließlich überprüft die Methode, ob die aktuelle Zeit zwischen der Startzeit und der „bis“-Zeit liegt.</span><span class="sxs-lookup"><span data-stu-id="e8306-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="e8306-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8306-136">See also</span></span>

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
- [<span data-ttu-id="e8306-137">&-OperatorC# (Referenz)</span><span class="sxs-lookup"><span data-stu-id="e8306-137">& Operator (C# Reference)</span></span>](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [<span data-ttu-id="e8306-138">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="e8306-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="e8306-139">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="e8306-139">Printing Overview</span></span>](printing-overview.md)
