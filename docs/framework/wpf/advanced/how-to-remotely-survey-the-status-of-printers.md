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
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="ca411-102">Gewusst wie: Remoteüberwachung des Druckerstatus</span><span class="sxs-lookup"><span data-stu-id="ca411-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="ca411-103">In mittleren und großen Unternehmen kann es jederzeit dazu kommen, dass mehrere Drucker wegen eines Papierstaus oder fehlenden Papiers oder anderer problematischer Situationen ausfallen.</span><span class="sxs-lookup"><span data-stu-id="ca411-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="ca411-104">Der umfangreiche Satz von Druckereigenschaften, die in den APIs von Microsoft .NET Framework verfügbar gemacht werden, bietet eine Möglichkeit, eine schnelle Übersicht über den Zuständen von Druckern durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ca411-104">The rich set of printer properties exposed in the APIs of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca411-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca411-105">Example</span></span>  
 <span data-ttu-id="ca411-106">Die wichtigsten Schritte beim Erstellen dieses Hilfsprogramms sind die folgenden.</span><span class="sxs-lookup"><span data-stu-id="ca411-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="ca411-107">Rufen Sie eine Liste aller Druckerserver ab.</span><span class="sxs-lookup"><span data-stu-id="ca411-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="ca411-108">Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.</span><span class="sxs-lookup"><span data-stu-id="ca411-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="ca411-109">Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, und lesen Sie jede Eigenschaft, die auf eine nicht ordnungsgemäß funktionierende Warteschlange hinweisen könnte.</span><span class="sxs-lookup"><span data-stu-id="ca411-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="ca411-110">Der folgende Code ist eine Reihe von Ausschnitten.</span><span class="sxs-lookup"><span data-stu-id="ca411-110">The code below is a series of snippets.</span></span> <span data-ttu-id="ca411-111">Der Einfachheit halber wird in diesem Beispiel davon ausgegangen, dass eine CRLF-getrennte Liste der Druckerserver vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ca411-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="ca411-112">Die `fileOfPrintServers` Variable <xref:System.IO.StreamReader> ist ein Objekt für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="ca411-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="ca411-113">Da sich jeder Servername in einer <xref:System.IO.StreamReader.ReadLine%2A> eigenen Zeile befindet, ruft jeder <xref:System.IO.StreamReader>Aufruf von den Namen des nächsten Servers ab und verschiebt den Cursor an den Anfang der nächsten Zeile.</span><span class="sxs-lookup"><span data-stu-id="ca411-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="ca411-114">Innerhalb der äußeren Schleife erstellt <xref:System.Printing.PrintServer> der Code ein Objekt für den neuesten Druckserver und gibt an, dass die Anwendung über Administratorrechte für den Server verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="ca411-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca411-115">Wenn viele Server vorhanden sind, können Sie <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> die Leistung verbessern, indem Sie die Konstruktoren verwenden, die nur die Eigenschaften initialisieren, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="ca411-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="ca411-116">Das Beispiel <xref:System.Printing.PrintServer.GetPrintQueues%2A> wird dann verwendet, um eine Auflistung aller Warteschlangen des Servers zu erstellen, und beginnt, sie zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="ca411-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="ca411-117">Diese innere Schleife enthält eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckers zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="ca411-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
- <span data-ttu-id="ca411-118">Sie können die Flags <xref:System.Printing.PrintQueue.QueueStatus%2A> der Eigenschaft <xref:System.Printing.PrintQueueStatus>des Typs lesen.</span><span class="sxs-lookup"><span data-stu-id="ca411-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
- <span data-ttu-id="ca411-119">Sie können jede relevante <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>Eigenschaft <xref:System.Printing.PrintQueue.IsPaperJammed%2A>wie lesen, z. B. und .</span><span class="sxs-lookup"><span data-stu-id="ca411-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="ca411-120">In diesem Beispiel werden beide Methoden veranschaulicht, sodass der Benutzer zuvor gefragt wurde, welche Methode <xref:System.Printing.PrintQueue.QueueStatus%2A> verwendet werden soll, und mit "y" antwortete, wenn er die Flags der Eigenschaft verwenden wollte.</span><span class="sxs-lookup"><span data-stu-id="ca411-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if they wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="ca411-121">Weitere Informationen zu den beiden Methoden finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="ca411-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="ca411-122">Abschließend werden dem Benutzer die Ergebnisse präsentiert.</span><span class="sxs-lookup"><span data-stu-id="ca411-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="ca411-123">Um den Druckerstatus mithilfe <xref:System.Printing.PrintQueue.QueueStatus%2A> der Flags der Eigenschaft zu überprüfen, überprüfen Sie jedes relevante Flag, um festzustellen, ob es festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ca411-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="ca411-124">Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ca411-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="ca411-125">Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ca411-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="ca411-126">Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen.</span><span class="sxs-lookup"><span data-stu-id="ca411-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="ca411-127">Weitere Informationen finden <xref:System.Printing.PrintQueueStatus>Sie unter , der& <xref:System.FlagsAttribute>Operator [(C-Referenz)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)und .</span><span class="sxs-lookup"><span data-stu-id="ca411-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="ca411-128">Für jedes Attribut, dessen Bit festgelegt ist, fügt der Code einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="ca411-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="ca411-129">(Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)</span><span class="sxs-lookup"><span data-stu-id="ca411-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="ca411-130">Um den Status des Druckers mit jeder Eigenschaft zu überprüfen, lesen Sie einfach jede Eigenschaft und fügen einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird, sofern die Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ca411-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="ca411-131">(Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)</span><span class="sxs-lookup"><span data-stu-id="ca411-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="ca411-132">Die **ReportAvailabilityAtThisTime**-Methode wurde für die Fälle erstellt, bei denen Sie bestimmen müssen, ob die Warteschlange zum aktuellen Zeitpunkt zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="ca411-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="ca411-133">Die Methode führt nichts <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> aus, wenn die und-Eigenschaften gleich sind. da in diesem Fall der Drucker jederzeit verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ca411-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="ca411-134">Wenn sie unterschiedlich sind, ruft die Methode die aktuelle Zeit ab, <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> die <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> dann <xref:System.Int32>in Gesamtminuten nach Mitternacht <xref:System.DateTime> konvertiert werden muss, da die und Eigenschaften s sind, die Minuten nach Mitternacht darstellen, nicht Objekte.</span><span class="sxs-lookup"><span data-stu-id="ca411-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="ca411-135">Schließlich überprüft die Methode, ob die aktuelle Zeit zwischen der Startzeit und der „bis“-Zeit liegt.</span><span class="sxs-lookup"><span data-stu-id="ca411-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="ca411-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca411-136">See also</span></span>

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
- [<span data-ttu-id="ca411-137">&-Operator (C-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ca411-137">& Operator (C# Reference)</span></span>](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [<span data-ttu-id="ca411-138">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="ca411-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="ca411-139">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="ca411-139">Printing Overview</span></span>](printing-overview.md)
