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
ms.openlocfilehash: dc187a4ea120661e8118ce79a966d3d4a3b40711
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340788"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="7ae38-102">Vorgehensweise: Remoteüberwachung des Druckerstatus</span><span class="sxs-lookup"><span data-stu-id="7ae38-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="7ae38-103">In mittleren und großen Unternehmen kann es jederzeit dazu kommen, dass mehrere Drucker wegen eines Papierstaus oder fehlenden Papiers oder anderer problematischer Situationen ausfallen.</span><span class="sxs-lookup"><span data-stu-id="7ae38-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="7ae38-104">Die umfangreichen verfügbar gemacht werden, der [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von Microsoft .NET Framework ermöglichen eine schnelle Überwachung der Druckerzustände.</span><span class="sxs-lookup"><span data-stu-id="7ae38-104">The rich set of printer properties exposed in the [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ae38-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ae38-105">Example</span></span>  
 <span data-ttu-id="7ae38-106">Die wichtigsten Schritte beim Erstellen dieses Dienstprogramms sind die folgenden.</span><span class="sxs-lookup"><span data-stu-id="7ae38-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="7ae38-107">Rufen Sie eine Liste aller Druckerserver ab.</span><span class="sxs-lookup"><span data-stu-id="7ae38-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="7ae38-108">Durchlaufen Sie die Server, um ihre Druckwarteschlangen abzufragen.</span><span class="sxs-lookup"><span data-stu-id="7ae38-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="7ae38-109">Durchlaufen Sie in jeder Phase der Serverschleife alle Serverwarteschlangen, und lesen Sie jede Eigenschaft, die auf eine nicht ordnungsgemäß funktionierende Warteschlange hinweisen könnte.</span><span class="sxs-lookup"><span data-stu-id="7ae38-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="7ae38-110">Der folgende Code ist eine Reihe von Ausschnitten.</span><span class="sxs-lookup"><span data-stu-id="7ae38-110">The code below is a series of snippets.</span></span> <span data-ttu-id="7ae38-111">Der Einfachheit halber wird in diesem Beispiel davon ausgegangen, dass eine CRLF-getrennte Liste der Druckerserver vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7ae38-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="7ae38-112">Die Variable `fileOfPrintServers` ist eine <xref:System.IO.StreamReader> Objekt für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="7ae38-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="7ae38-113">Da die Namen aller Server in einer eigenen Zeile ist, jeden Aufruf der <xref:System.IO.StreamReader.ReadLine%2A> Ruft den Namen des Servers weiter ab und verschiebt die <xref:System.IO.StreamReader>des Cursors am Anfang der nächsten Zeile.</span><span class="sxs-lookup"><span data-stu-id="7ae38-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="7ae38-114">In der äußeren Schleife wird der Code erstellt eine <xref:System.Printing.PrintServer> -Objekt für den letzten Druckerserver, und gibt an, dass die Anwendung über Administratorrechte auf dem Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="7ae38-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ae38-115">Wenn viele Server vorhanden sind, können Sie die Leistung verbessern, mit der <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> Konstruktoren, die nur die Eigenschaften zu initialisieren müssen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ae38-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="7ae38-116">Anschließend wird <xref:System.Printing.PrintServer.GetPrintQueues%2A> ist zum Erstellen einer Sammlung aller von dem Server, Warteschlangen und beginnt mit der durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="7ae38-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="7ae38-117">Diese innere Schleife enthält eine Verzweigungsstruktur, die den beiden Möglichkeiten entspricht, den Status eines Druckers zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7ae38-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
-   <span data-ttu-id="7ae38-118">Sie können die Flags der Lesen der <xref:System.Printing.PrintQueue.QueueStatus%2A> Eigenschaft, die vom Typ <xref:System.Printing.PrintQueueStatus>.</span><span class="sxs-lookup"><span data-stu-id="7ae38-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
-   <span data-ttu-id="7ae38-119">Sie können jede relevante Eigenschaft wie z. B. Lesen <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, und <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ae38-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="7ae38-120">In diesem Beispiel werden beide Methoden veranschaulicht, damit der Benutzer zuvor hinsichtlich der zu verwendenden Methode aufgefordert und hat "y", wenn er die Flags der verwenden die <xref:System.Printing.PrintQueue.QueueStatus%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7ae38-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="7ae38-121">Weitere Informationen zu den beiden Methoden finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="7ae38-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="7ae38-122">Abschließend werden dem Benutzer die Ergebnisse präsentiert.</span><span class="sxs-lookup"><span data-stu-id="7ae38-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="7ae38-123">Überprüfen Sie den Status des Druckers mit den Flags der der <xref:System.Printing.PrintQueue.QueueStatus%2A> -Eigenschaft, zu überprüfen jedes relevante Flag überprüfen, ob es festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7ae38-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="7ae38-124">Standardmäßig wird durch Ausführen eines logischen AND-Vorgangs mit einem Satz von Flags als einem Operanden und dem Flag selbst als zweiten Operanden überprüft, ob ein Bit in einem Satz von Bitflags festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7ae38-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="7ae38-125">Da das Flag selbst nur über einen Bitsatz verfügt, ergibt der logische AND-Vorgang lediglich, dass dasselbe Bit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7ae38-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="7ae38-126">Um herauszufinden, ob das Bit festgelegt ist, können Sie das Ergebnis des logischen AND-Vorgangs einfach mit dem Flag selbst vergleichen.</span><span class="sxs-lookup"><span data-stu-id="7ae38-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="7ae38-127">Weitere Informationen finden Sie unter <xref:System.Printing.PrintQueueStatus>, [&-Operator (C# Verweis)](~/docs/csharp/language-reference/operators/and-operator.md), und <xref:System.FlagsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7ae38-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](~/docs/csharp/language-reference/operators/and-operator.md), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="7ae38-128">Für jedes Attribut, dessen Bit festgelegt ist, fügt der Code einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="7ae38-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="7ae38-129">(Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)</span><span class="sxs-lookup"><span data-stu-id="7ae38-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="7ae38-130">Um den Status des Druckers mit jeder Eigenschaft zu überprüfen, lesen Sie einfach jede Eigenschaft und fügen einen Hinweis zum endgültigen Bericht hinzu, der dem Benutzer präsentiert wird, sofern die Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7ae38-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="7ae38-131">(Die **ReportAvailabilityAtThisTime**-Methode, die am Ende des Codes aufgerufen wird, wird unten erläutert.)</span><span class="sxs-lookup"><span data-stu-id="7ae38-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="7ae38-132">Die **ReportAvailabilityAtThisTime**-Methode wurde für die Fälle erstellt, bei denen Sie bestimmen müssen, ob die Warteschlange zum aktuellen Zeitpunkt zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="7ae38-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="7ae38-133">Die Methode keine Wirkung, wenn die <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften gleich sind, da in diesem Fall der Drucker immer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7ae38-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="7ae38-134">Wenn sich die Werte unterscheiden, ruft die Methode die aktuelle Uhrzeit, die dann in der Gesamtzahl der Minuten nach Mitternacht konvertiert werden, da die <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften sind <xref:System.Int32>Minuten nach Mitternacht, nicht darstellen <xref:System.DateTime> -Objekte.</span><span class="sxs-lookup"><span data-stu-id="7ae38-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="7ae38-135">Schließlich überprüft die Methode, ob die aktuelle Zeit zwischen der Startzeit und der „bis“-Zeit liegt.</span><span class="sxs-lookup"><span data-stu-id="7ae38-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="7ae38-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ae38-136">See also</span></span>

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
- [<span data-ttu-id="7ae38-137">&-Operator (C# Verweis)</span><span class="sxs-lookup"><span data-stu-id="7ae38-137">& Operator (C# Reference)</span></span>](~/docs/csharp/language-reference/operators/and-operator.md)
- [<span data-ttu-id="7ae38-138">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="7ae38-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="7ae38-139">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="7ae38-139">Printing Overview</span></span>](printing-overview.md)
