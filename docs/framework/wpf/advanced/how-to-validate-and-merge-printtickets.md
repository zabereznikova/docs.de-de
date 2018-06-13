---
title: 'Gewusst wie: Überprüfen und Zusammenführen von PrintTickets'
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
ms.openlocfilehash: 11160d7ec59914afbe501ba731c0c04a85ffc4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548492"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="24923-102">Gewusst wie: Überprüfen und Zusammenführen von PrintTickets</span><span class="sxs-lookup"><span data-stu-id="24923-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="24923-103">Die [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Druckschema](http://go.microsoft.com/fwlink/?LinkId=186397) enthält, die flexibel und erweiterbar sind <xref:System.Printing.PrintCapabilities> und <xref:System.Printing.PrintTicket> Elemente.</span><span class="sxs-lookup"><span data-stu-id="24923-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="24923-104">Zählt die Funktionen von einem Druckgerät erstere auf und gibt der zweite Wert an, wie das Gerät für diese Funktionen in Bezug auf eine bestimmte Sequenz von Dokumenten, einzelnes Dokument oder eine einzelne Seite verwenden, sollten.</span><span class="sxs-lookup"><span data-stu-id="24923-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="24923-105">Eine typische Sequenz von Aufgaben für eine Anwendung, die unterstützt drucken würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="24923-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="24923-106">Bestimmen Sie die Leistungsmerkmale des Druckers.</span><span class="sxs-lookup"><span data-stu-id="24923-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="24923-107">Konfigurieren einer <xref:System.Printing.PrintTicket> zum Verwenden dieser Funktionen.</span><span class="sxs-lookup"><span data-stu-id="24923-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="24923-108">Überprüfen der <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="24923-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="24923-109">Dieser Artikel zeigt, wie dies.</span><span class="sxs-lookup"><span data-stu-id="24923-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24923-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24923-110">Example</span></span>  
 <span data-ttu-id="24923-111">Im folgenden einfachen Beispiel, interessieren uns nur, ob ein Drucker Duplexdruck unterstützt – zweiseitigen drucken.</span><span class="sxs-lookup"><span data-stu-id="24923-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="24923-112">Die wichtigsten Schritte sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="24923-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="24923-113">Abrufen einer <xref:System.Printing.PrintCapabilities> -Objekt mit den <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="24923-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="24923-114">Testen Sie das Vorhandensein der gewünschten Funktion.</span><span class="sxs-lookup"><span data-stu-id="24923-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="24923-115">Im folgenden Beispiel wir testen die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> Eigenschaft von der <xref:System.Printing.PrintCapabilities> -Objekt für das Vorhandensein der Funktion des Druckens auf beiden Seiten des Blatts mit "Deaktivieren der Seite" entlang der langen Seite des Blatts.</span><span class="sxs-lookup"><span data-stu-id="24923-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="24923-116">Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> ist eine Auflistung, verwenden wir die `Contains` Methode <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="24923-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="24923-117">Dieser Schritt ist nicht unbedingt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24923-117">This step is not strictly necessary.</span></span> <span data-ttu-id="24923-118">Die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> unten verwendete Methode überprüft jede Anforderung die <xref:System.Printing.PrintTicket> gegenüber den Möglichkeiten des Druckers.</span><span class="sxs-lookup"><span data-stu-id="24923-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="24923-119">Wenn die angeforderte Funktion vom Drucker nicht unterstützt wird, ersetzt der Druckertreiber wird eine alternative Anforderung in die <xref:System.Printing.PrintTicket> von der Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24923-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="24923-120">Wenn der Drucker Duplexdruck unterstützt, wird der Beispielcode erstellt eine <xref:System.Printing.PrintTicket> , die fordert Duplexdruck.</span><span class="sxs-lookup"><span data-stu-id="24923-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="24923-121">Aber die Anwendung gibt keinen jede mögliche Drucker, die Einstellung in der <xref:System.Printing.PrintTicket> Element.</span><span class="sxs-lookup"><span data-stu-id="24923-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="24923-122">Das wäre gehen zu Lasten der Programmierer und Programm.</span><span class="sxs-lookup"><span data-stu-id="24923-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="24923-123">Stattdessen der Code legt nur die Duplex-Anforderung und führt Sie dies <xref:System.Printing.PrintTicket> mit einem vorhandenen, vollständig konfiguriert und überprüft, <xref:System.Printing.PrintTicket>, in diesem Fall den Benutzer standardmäßig <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="24923-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="24923-124">Dementsprechend im Beispiel ruft die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Methode, um die neue zusammenzuführen minimale <xref:System.Printing.PrintTicket> Standardwert des Benutzers <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="24923-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="24923-125">Dies gibt eine <xref:System.Printing.ValidationResult> , enthält das neue <xref:System.Printing.PrintTicket> als eine seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="24923-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="24923-126">Das Beispiel testet dann die neue <xref:System.Printing.PrintTicket> Duplexdruck anfordert.</span><span class="sxs-lookup"><span data-stu-id="24923-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="24923-127">Wenn dies der Fall ist, erleichtert klicken Sie dann das Beispiel den neuen Standardwert Druckticket für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="24923-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="24923-128">Wenn Schritt 2 oben wurde ausgelassen und Duplexdruck entlang der langen Seite wurde von der Drucker nicht unterstützt, dann die Tests zurückzuführen sein würden `false`.</span><span class="sxs-lookup"><span data-stu-id="24923-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="24923-129">(Siehe Hinweis oben).</span><span class="sxs-lookup"><span data-stu-id="24923-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="24923-130">Der letzte wichtige Schritt ist, um die Änderung zu übernehmen die <xref:System.Printing.PrintQueue.UserPrintTicket%2A> Eigenschaft von der <xref:System.Printing.PrintQueue> mit der <xref:System.Printing.PrintQueue.Commit%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="24923-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="24923-131">Damit Sie schnell in diesem Beispiel testen können, wird im weiteren Verlauf unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="24923-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="24923-132">Erstellen Sie ein Projekt und einen Namespace, und fügen Sie die Codeausschnitte in diesem Artikel in den Namespaceblock.</span><span class="sxs-lookup"><span data-stu-id="24923-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="24923-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24923-133">See Also</span></span>  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="24923-134">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="24923-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="24923-135">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="24923-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="24923-136">Drucken von Schemas</span><span class="sxs-lookup"><span data-stu-id="24923-136">Print Schema</span></span>](http://go.microsoft.com/fwlink/?LinkId=186397)
