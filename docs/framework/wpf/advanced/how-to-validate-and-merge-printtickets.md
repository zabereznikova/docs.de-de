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
ms.openlocfilehash: 2be08f5d3c2cd82e50569a105e3fa15f12ad352c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355167"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Vorgehensweise: Überprüfen und Zusammenführen von PrintTickets
Die [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Druckschema](https://go.microsoft.com/fwlink/?LinkId=186397) enthält, die flexible und erweiterbare <xref:System.Printing.PrintCapabilities> und <xref:System.Printing.PrintTicket> Elemente. Ersteres aufführt, die Funktionen von einem Druckgerät und letzterer angibt, wie das Gerät auf diese Funktionen in Bezug auf eine bestimmte Sequenz von Dokumenten, einzelnes Dokument oder einzelne Seite verwenden soll.  
  
 Eine typische Sequenz von Aufgaben für eine Anwendung, die Drucken unterstützt würde wie folgt lauten.  
  
1.  Bestimmen Sie die Funktionen des Druckers.  
  
2.  Konfigurieren einer <xref:System.Printing.PrintTicket> diese Funktionen verwenden.  
  
3.  Überprüfen Sie die <xref:System.Printing.PrintTicket>.  
  
 In diesem Artikel veranschaulicht dies.  
  
## <a name="example"></a>Beispiel  
 Im einfachen Beispiel interessieren wir uns nur, ob ein Drucker Duplexdruck unterstützen kann – doppelseitigen Druck. Die wichtigsten Schritte sind wie folgt aus.  
  
1.  Abrufen einer <xref:System.Printing.PrintCapabilities> Objekt mit der <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> Methode.  
  
2.  Testen Sie das Vorhandensein der gewünschten Funktion. Im folgenden Beispiel, das wir testen die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> Eigenschaft der <xref:System.Printing.PrintCapabilities> -Objekt an den der langen Seite des Blatts auf das Vorhandensein der Fähigkeit des Druckens auf beiden Seiten der Blatt Papier mit der "Seite"aktivieren". Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> ist eine Auflistung, verwenden wir die `Contains` -Methode der <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Dieser Schritt ist nicht unbedingt erforderlich ist. Die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> unten verwendete Methode prüft jede Anforderung die <xref:System.Printing.PrintTicket> anhand der Funktionen des Druckers. Wenn die erforderlichen Funktionen, die vom Drucker nicht unterstützt wird, ersetzt der Druckertreiber wird eine alternative Anforderung in die <xref:System.Printing.PrintTicket> von der Methode zurückgegeben.  
  
3.  Wenn der Drucker Duplexdruck unterstützt, wird der Beispielcode erstellt eine <xref:System.Printing.PrintTicket> , die für Duplexdruck gefragt. Aber die Anwendung nicht alle möglichen Drucker, die Einstellung in der <xref:System.Printing.PrintTicket> Element. Das wäre sehr aufwändig für den Programmierer Programm Zeit. Stattdessen der Code legt nur die Duplex-Anforderung und führt dies dann zusammen <xref:System.Printing.PrintTicket> mit einem vorhandenen, vollständig konfiguriert und überprüft, <xref:System.Printing.PrintTicket>, in diesem Fall des Benutzers <xref:System.Printing.PrintTicket>.  
  
4.  Entsprechend ist das Beispiel ruft die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Methode, um die neue merge sehr einfach gehalten und <xref:System.Printing.PrintTicket> Standardwert des Benutzers <xref:System.Printing.PrintTicket>. Dies gibt eine <xref:System.Printing.ValidationResult> , enthält das neue <xref:System.Printing.PrintTicket> als eine seiner Eigenschaften.  
  
5.  Das Beispiel testet, klicken Sie dann die neue <xref:System.Printing.PrintTicket> Duplexdruck anfordert. Wenn dies der Fall ist, vereinfacht klicken Sie dann das Beispiel die neue Standardeinstellung Druckticket für den Benutzer. Wenn Schritt 2 oben musste außer acht gelassen wurde und Duplexdruck entlang der langen Seite wurde von der Drucker nicht unterstützt, wird der Test hat `false`. (Siehe Hinweis oben).  
  
6.  Der letzte wichtige Schritt ist die Änderung mit der <xref:System.Printing.PrintQueue.UserPrintTicket%2A> Eigenschaft der <xref:System.Printing.PrintQueue> mit der <xref:System.Printing.PrintQueue.Commit%2A> Methode.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Damit Sie schnell in diesem Beispiel testen können, ist der Rest des nachstehend dargestellt. Erstellen Sie ein Projekt und einen Namespace, und fügen Sie die Codeausschnitte in diesem Artikel in den Namespaceblock.  
  
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
- [Druckschema](https://go.microsoft.com/fwlink/?LinkId=186397)
