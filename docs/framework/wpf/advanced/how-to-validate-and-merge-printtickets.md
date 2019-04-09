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
ms.openlocfilehash: 750234a7073b3931b4f3ce5674f3989fe119c50c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199946"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="38781-102">Vorgehensweise: Überprüfen und Zusammenführen von PrintTickets</span><span class="sxs-lookup"><span data-stu-id="38781-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="38781-103">Die [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Druckschema](https://go.microsoft.com/fwlink/?LinkId=186397) enthält, die flexible und erweiterbare <xref:System.Printing.PrintCapabilities> und <xref:System.Printing.PrintTicket> Elemente.</span><span class="sxs-lookup"><span data-stu-id="38781-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="38781-104">Ersteres aufführt, die Funktionen von einem Druckgerät und letzterer angibt, wie das Gerät auf diese Funktionen in Bezug auf eine bestimmte Sequenz von Dokumenten, einzelnes Dokument oder einzelne Seite verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="38781-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="38781-105">Eine typische Sequenz von Aufgaben für eine Anwendung, die Drucken unterstützt würde wie folgt lauten.</span><span class="sxs-lookup"><span data-stu-id="38781-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="38781-106">Bestimmen Sie die Funktionen des Druckers.</span><span class="sxs-lookup"><span data-stu-id="38781-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="38781-107">Konfigurieren einer <xref:System.Printing.PrintTicket> diese Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="38781-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="38781-108">Überprüfen Sie die <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="38781-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="38781-109">In diesem Artikel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="38781-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38781-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38781-110">Example</span></span>  
 <span data-ttu-id="38781-111">Im einfachen Beispiel interessieren wir uns nur, ob ein Drucker Duplexdruck unterstützen kann – doppelseitigen Druck.</span><span class="sxs-lookup"><span data-stu-id="38781-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="38781-112">Die wichtigsten Schritte sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="38781-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="38781-113">Abrufen einer <xref:System.Printing.PrintCapabilities> Objekt mit der <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="38781-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="38781-114">Testen Sie das Vorhandensein der gewünschten Funktion.</span><span class="sxs-lookup"><span data-stu-id="38781-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="38781-115">Im folgenden Beispiel, das wir testen die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> Eigenschaft der <xref:System.Printing.PrintCapabilities> -Objekt an den der langen Seite des Blatts auf das Vorhandensein der Fähigkeit des Druckens auf beiden Seiten der Blatt Papier mit der "Seite"aktivieren".</span><span class="sxs-lookup"><span data-stu-id="38781-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="38781-116">Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> ist eine Auflistung, verwenden wir die `Contains` -Methode der <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="38781-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38781-117">Dieser Schritt ist nicht unbedingt erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="38781-117">This step is not strictly necessary.</span></span> <span data-ttu-id="38781-118">Die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> unten verwendete Methode prüft jede Anforderung die <xref:System.Printing.PrintTicket> anhand der Funktionen des Druckers.</span><span class="sxs-lookup"><span data-stu-id="38781-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="38781-119">Wenn die erforderlichen Funktionen, die vom Drucker nicht unterstützt wird, ersetzt der Druckertreiber wird eine alternative Anforderung in die <xref:System.Printing.PrintTicket> von der Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="38781-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="38781-120">Wenn der Drucker Duplexdruck unterstützt, wird der Beispielcode erstellt eine <xref:System.Printing.PrintTicket> , die für Duplexdruck gefragt.</span><span class="sxs-lookup"><span data-stu-id="38781-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="38781-121">Aber die Anwendung nicht alle möglichen Drucker, die Einstellung in der <xref:System.Printing.PrintTicket> Element.</span><span class="sxs-lookup"><span data-stu-id="38781-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="38781-122">Das wäre sehr aufwändig für den Programmierer Programm Zeit.</span><span class="sxs-lookup"><span data-stu-id="38781-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="38781-123">Stattdessen der Code legt nur die Duplex-Anforderung und führt dies dann zusammen <xref:System.Printing.PrintTicket> mit einem vorhandenen, vollständig konfiguriert und überprüft, <xref:System.Printing.PrintTicket>, in diesem Fall des Benutzers <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="38781-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="38781-124">Entsprechend ist das Beispiel ruft die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Methode, um die neue merge sehr einfach gehalten und <xref:System.Printing.PrintTicket> Standardwert des Benutzers <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="38781-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="38781-125">Dies gibt eine <xref:System.Printing.ValidationResult> , enthält das neue <xref:System.Printing.PrintTicket> als eine seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="38781-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="38781-126">Das Beispiel testet, klicken Sie dann die neue <xref:System.Printing.PrintTicket> Duplexdruck anfordert.</span><span class="sxs-lookup"><span data-stu-id="38781-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="38781-127">Wenn dies der Fall ist, vereinfacht klicken Sie dann das Beispiel die neue Standardeinstellung Druckticket für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="38781-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="38781-128">Wenn Schritt 2 oben musste außer acht gelassen wurde und Duplexdruck entlang der langen Seite wurde von der Drucker nicht unterstützt, wird der Test hat `false`.</span><span class="sxs-lookup"><span data-stu-id="38781-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="38781-129">(Siehe Hinweis oben).</span><span class="sxs-lookup"><span data-stu-id="38781-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="38781-130">Der letzte wichtige Schritt ist die Änderung mit der <xref:System.Printing.PrintQueue.UserPrintTicket%2A> Eigenschaft der <xref:System.Printing.PrintQueue> mit der <xref:System.Printing.PrintQueue.Commit%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="38781-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="38781-131">Damit Sie schnell in diesem Beispiel testen können, ist der Rest des nachstehend dargestellt.</span><span class="sxs-lookup"><span data-stu-id="38781-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="38781-132">Erstellen Sie ein Projekt und einen Namespace, und fügen Sie die Codeausschnitte in diesem Artikel in den Namespaceblock.</span><span class="sxs-lookup"><span data-stu-id="38781-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="38781-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38781-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="38781-134">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="38781-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="38781-135">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="38781-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="38781-136">Druckschema</span><span class="sxs-lookup"><span data-stu-id="38781-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
