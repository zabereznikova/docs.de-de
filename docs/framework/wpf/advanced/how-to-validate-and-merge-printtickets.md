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
ms.openlocfilehash: bd7f399555b343a52ec6f36aa3b8c706747d8b06
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094526"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Gewusst wie: Überprüfen und Zusammenführen von PrintTickets
Das Microsoft Windows- [Druck Schema](/windows/win32/printdocs/printschema) enthält die flexiblen und erweiterbaren <xref:System.Printing.PrintCapabilities>-und <xref:System.Printing.PrintTicket>-Elemente. Die frühere Funktion stellt die Funktionen eines Druck Geräts dar, und letztere gibt an, wie das Gerät diese Funktionen in Bezug auf eine bestimmte Sequenz von Dokumenten, ein einzelnes Dokument oder eine einzelne Seite verwenden soll.  
  
 Eine typische Abfolge von Aufgaben für eine Anwendung, die das Drucken unterstützt, sieht wie folgt aus.  
  
1. Bestimmen Sie die Fähigkeiten eines Druckers.  
  
2. Konfigurieren Sie eine <xref:System.Printing.PrintTicket>, um diese Funktionen zu verwenden.  
  
3. Überprüfen Sie die <xref:System.Printing.PrintTicket>.  
  
 Dieser Artikel zeigt, wie Sie dies tun.  
  
## <a name="example"></a>Beispiel  
 Im folgenden einfachen Beispiel sind wir nur daran interessiert, ob ein Drucker Duplexing unterstützen kann – zweiseitiges Drucken. Die wichtigsten Schritte sind wie folgt.  
  
1. Ein <xref:System.Printing.PrintCapabilities>-Objekt mit der <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>-Methode erhalten.  
  
2. Testen Sie, ob die gewünschte Funktion vorhanden ist. Im folgenden Beispiel wird die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>-Eigenschaft des <xref:System.Printing.PrintCapabilities>-Objekts für das vorhanden sein der Druckfunktion auf beiden Seiten eines Blatts mit dem "Seiten Ende" auf der langen Seite des Blatts getestet. Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> eine Sammlung ist, verwenden wir die `Contains`-Methode von <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    > Dieser Schritt ist nicht unbedingt erforderlich. Die unten verwendete <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Methode überprüft jede Anforderung im <xref:System.Printing.PrintTicket> auf die Funktionen des Druckers. Wenn die angeforderte Funktion nicht vom Drucker unterstützt wird, ersetzt der Druckertreiber eine alternative Anforderung in der <xref:System.Printing.PrintTicket>, die von der-Methode zurückgegeben wird.  
  
3. Wenn der Drucker Duplexing unterstützt, erstellt der Beispielcode eine <xref:System.Printing.PrintTicket>, die nach Duplexing fragt. Die Anwendung gibt jedoch nicht alle möglichen Druckereinstellungen an, die im <xref:System.Printing.PrintTicket>-Element verfügbar sind. Der Programmierer und die Programmzeit würden verschwendet werden. Stattdessen legt der Code nur die Duplexing-Anforderung fest und führt diese <xref:System.Printing.PrintTicket> dann mit einem vorhandenen, vollständig konfigurierten und validierten <xref:System.Printing.PrintTicket>, in diesem Fall dem Standard <xref:System.Printing.PrintTicket>des Benutzers, zusammen.  
  
4. Entsprechend Ruft das Beispiel die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>-Methode auf, um die neue, minimale <xref:System.Printing.PrintTicket> mit dem Standard <xref:System.Printing.PrintTicket>des Benutzers zusammenzuführen. Dies gibt einen <xref:System.Printing.ValidationResult> zurück, der den neuen <xref:System.Printing.PrintTicket> als eine seiner Eigenschaften enthält.  
  
5. Anschließend testet das Beispiel, ob das neue <xref:System.Printing.PrintTicket> Duplexing anfordert. Wenn dies der Fall ist, wird das Beispiel zum neuen Standarddruck Ticket für den Benutzer. Wenn Schritt 2 oben ausgelassen wurde und der Drucker das Duplexing nicht auf der langen Seite unterstützte, hätte der Test zu `false`geführt. (Siehe den obigen Hinweis.)  
  
6. Der letzte bedeutende Schritt besteht darin, die Änderung für die <xref:System.Printing.PrintQueue.UserPrintTicket%2A>-Eigenschaft der <xref:System.Printing.PrintQueue> mit der <xref:System.Printing.PrintQueue.Commit%2A>-Methode zu übertragen.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Um dieses Beispiel schnell testen zu können, wird der restliche Rest der Abbildung unten dargestellt. Erstellen Sie ein Projekt und einen Namespace, und fügen Sie die Code Ausschnitte in diesem Artikel in den Namespace-Block ein.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Druck Schema](/windows/win32/printdocs/printschema)
