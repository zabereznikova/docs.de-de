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
# <a name="how-to-validate-and-merge-printtickets"></a>Vorgehensweise: Überprüfen und Zusammenführen von PrintTickets
Das [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Druck Schema](https://go.microsoft.com/fwlink/?LinkId=186397) enthält die <xref:System.Printing.PrintCapabilities> flexiblen und erweiterbaren- <xref:System.Printing.PrintTicket> Elemente und. Die frühere Funktion stellt die Funktionen eines Druck Geräts dar, und letztere gibt an, wie das Gerät diese Funktionen in Bezug auf eine bestimmte Sequenz von Dokumenten, ein einzelnes Dokument oder eine einzelne Seite verwenden soll.  
  
 Eine typische Abfolge von Aufgaben für eine Anwendung, die das Drucken unterstützt, sieht wie folgt aus.  
  
1. Bestimmen Sie die Fähigkeiten eines Druckers.  
  
2. <xref:System.Printing.PrintTicket> Konfigurieren Sie, um diese Funktionen zu verwenden.  
  
3. Überprüfen <xref:System.Printing.PrintTicket>Sie die.  
  
 Dieser Artikel zeigt, wie Sie dies tun.  
  
## <a name="example"></a>Beispiel  
 Im folgenden einfachen Beispiel sind wir nur daran interessiert, ob ein Drucker Duplexing unterstützen kann – zweiseitiges Drucken. Die wichtigsten Schritte sind wie folgt.  
  
1. Ein <xref:System.Printing.PrintCapabilities> -Objekt mit der <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> -Methode zu erhalten.  
  
2. Testen Sie, ob die gewünschte Funktion vorhanden ist. Im folgenden Beispiel wird die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> -Eigenschaft <xref:System.Printing.PrintCapabilities> des-Objekts für das vorhanden sein der Druckfunktion auf beiden Seiten eines Papier Blatts getestet, wobei die "Seiten Drehung" entlang der langen Seite des Blatts angezeigt wird. Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> eine Auflistung ist, verwenden wir die `Contains` -Methode <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>von.  
  
    > [!NOTE]
    > Dieser Schritt ist nicht unbedingt erforderlich. Die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> unten verwendete Methode überprüft jede Anforderung in der <xref:System.Printing.PrintTicket> auf die Funktionen des Druckers. Wenn die angeforderte Funktion nicht vom Drucker unterstützt wird, ersetzt der Druckertreiber eine alternative Anforderung in <xref:System.Printing.PrintTicket> der, die von der-Methode zurückgegeben wird.  
  
3. Wenn der Drucker Duplexing unterstützt, erstellt der Beispielcode <xref:System.Printing.PrintTicket> einen, der das Duplexing anfordert. Die Anwendung gibt jedoch nicht alle möglichen Druckereinstellungen an, die im <xref:System.Printing.PrintTicket> -Element verfügbar sind. Der Programmierer und die Programmzeit würden verschwendet werden. Stattdessen legt der Code nur die Duplexing-Anforderung fest und führt diese <xref:System.Printing.PrintTicket> dann mit einem vorhandenen, vollständig konfigurierten <xref:System.Printing.PrintTicket>und validierten,, in diesem Fall, <xref:System.Printing.PrintTicket>dem Standard des Benutzers zusammen.  
  
4. Entsprechend Ruft das Beispiel die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> -Methode auf, um den neuen <xref:System.Printing.PrintTicket> Minimalwert mit dem Standard <xref:System.Printing.PrintTicket>des Benutzers zusammenzuführen. Dadurch wird eine <xref:System.Printing.ValidationResult> zurückgegeben, die <xref:System.Printing.PrintTicket> die neue als eine ihrer Eigenschaften enthält.  
  
5. Im Beispiel wird dann getestet, ob <xref:System.Printing.PrintTicket> die neuen Anforderungen Duplexing werden. Wenn dies der Fall ist, wird das Beispiel zum neuen Standarddruck Ticket für den Benutzer. Wenn Schritt 2 oben ausgelassen wurde und der Drucker die Duplexing-Komponente nicht auf der langen Seite unterstützte, hätte der Test dazu geführt `false`. (Siehe den obigen Hinweis.)  
  
6. Der letzte bedeutende Schritt besteht darin, die Änderung <xref:System.Printing.PrintQueue.UserPrintTicket%2A> <xref:System.Printing.PrintQueue> mit der <xref:System.Printing.PrintQueue.Commit%2A> -Methode an die-Eigenschaft des zu übergeben.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Um dieses Beispiel schnell testen zu können, wird der restliche Rest der Abbildung unten dargestellt. Erstellen Sie ein Projekt und einen Namespace, und fügen Sie die Code Ausschnitte in diesem Artikel in den Namespace-Block ein.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Druck Schema](https://go.microsoft.com/fwlink/?LinkId=186397)
