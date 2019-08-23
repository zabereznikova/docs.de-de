---
title: 'Vorgehensweise: Überprüfen und Zusammenführen von PrintTickets'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 9e5242c07179501e6b39840a36f8dd6364d65b84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918348"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="fc2ae-102">Vorgehensweise: Überprüfen und Zusammenführen von PrintTickets</span><span class="sxs-lookup"><span data-stu-id="fc2ae-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="fc2ae-103">Das [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Druck Schema](https://go.microsoft.com/fwlink/?LinkId=186397) enthält die <xref:System.Printing.PrintCapabilities> flexiblen und erweiterbaren- <xref:System.Printing.PrintTicket> Elemente und.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="fc2ae-104">Die frühere Funktion stellt die Funktionen eines Druck Geräts dar, und letztere gibt an, wie das Gerät diese Funktionen in Bezug auf eine bestimmte Sequenz von Dokumenten, ein einzelnes Dokument oder eine einzelne Seite verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="fc2ae-105">Eine typische Abfolge von Aufgaben für eine Anwendung, die das Drucken unterstützt, sieht wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="fc2ae-106">Bestimmen Sie die Fähigkeiten eines Druckers.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="fc2ae-107"><xref:System.Printing.PrintTicket> Konfigurieren Sie, um diese Funktionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="fc2ae-108">Überprüfen <xref:System.Printing.PrintTicket>Sie die.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="fc2ae-109">Dieser Artikel zeigt, wie Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc2ae-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc2ae-110">Example</span></span>  
 <span data-ttu-id="fc2ae-111">Im folgenden einfachen Beispiel sind wir nur daran interessiert, ob ein Drucker Duplexing unterstützen kann – zweiseitiges Drucken.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="fc2ae-112">Die wichtigsten Schritte sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="fc2ae-113">Ein <xref:System.Printing.PrintCapabilities> -Objekt mit der <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> -Methode zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="fc2ae-114">Testen Sie, ob die gewünschte Funktion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="fc2ae-115">Im folgenden Beispiel wird die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> -Eigenschaft <xref:System.Printing.PrintCapabilities> des-Objekts für das vorhanden sein der Druckfunktion auf beiden Seiten eines Papier Blatts getestet, wobei die "Seiten Drehung" entlang der langen Seite des Blatts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="fc2ae-116">Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> eine Auflistung ist, verwenden wir die `Contains` -Methode <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>von.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fc2ae-117">Dieser Schritt ist nicht unbedingt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-117">This step is not strictly necessary.</span></span> <span data-ttu-id="fc2ae-118">Die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> unten verwendete Methode überprüft jede Anforderung in der <xref:System.Printing.PrintTicket> auf die Funktionen des Druckers.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="fc2ae-119">Wenn die angeforderte Funktion nicht vom Drucker unterstützt wird, ersetzt der Druckertreiber eine alternative Anforderung in <xref:System.Printing.PrintTicket> der, die von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="fc2ae-120">Wenn der Drucker Duplexing unterstützt, erstellt der Beispielcode <xref:System.Printing.PrintTicket> einen, der das Duplexing anfordert.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="fc2ae-121">Die Anwendung gibt jedoch nicht alle möglichen Druckereinstellungen an, die im <xref:System.Printing.PrintTicket> -Element verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="fc2ae-122">Der Programmierer und die Programmzeit würden verschwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="fc2ae-123">Stattdessen legt der Code nur die Duplexing-Anforderung fest und führt diese <xref:System.Printing.PrintTicket> dann mit einem vorhandenen, vollständig konfigurierten <xref:System.Printing.PrintTicket>und validierten,, in diesem Fall, <xref:System.Printing.PrintTicket>dem Standard des Benutzers zusammen.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="fc2ae-124">Entsprechend Ruft das Beispiel die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> -Methode auf, um den neuen <xref:System.Printing.PrintTicket> Minimalwert mit dem Standard <xref:System.Printing.PrintTicket>des Benutzers zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="fc2ae-125">Dadurch wird eine <xref:System.Printing.ValidationResult> zurückgegeben, die <xref:System.Printing.PrintTicket> die neue als eine ihrer Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="fc2ae-126">Im Beispiel wird dann getestet, ob <xref:System.Printing.PrintTicket> die neuen Anforderungen Duplexing werden.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="fc2ae-127">Wenn dies der Fall ist, wird das Beispiel zum neuen Standarddruck Ticket für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="fc2ae-128">Wenn Schritt 2 oben ausgelassen wurde und der Drucker die Duplexing-Komponente nicht auf der langen Seite unterstützte, hätte der Test dazu geführt `false`.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="fc2ae-129">(Siehe den obigen Hinweis.)</span><span class="sxs-lookup"><span data-stu-id="fc2ae-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="fc2ae-130">Der letzte bedeutende Schritt besteht darin, die Änderung <xref:System.Printing.PrintQueue.UserPrintTicket%2A> <xref:System.Printing.PrintQueue> mit der <xref:System.Printing.PrintQueue.Commit%2A> -Methode an die-Eigenschaft des zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="fc2ae-131">Um dieses Beispiel schnell testen zu können, wird der restliche Rest der Abbildung unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="fc2ae-132">Erstellen Sie ein Projekt und einen Namespace, und fügen Sie die Code Ausschnitte in diesem Artikel in den Namespace-Block ein.</span><span class="sxs-lookup"><span data-stu-id="fc2ae-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="fc2ae-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc2ae-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="fc2ae-134">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="fc2ae-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="fc2ae-135">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="fc2ae-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="fc2ae-136">Druck Schema</span><span class="sxs-lookup"><span data-stu-id="fc2ae-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
