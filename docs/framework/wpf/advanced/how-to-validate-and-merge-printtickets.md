---
title: "Gewusst wie: Überprüfen und Zusammenführen von PrintTickets"
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
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5cf2091d50433bb936b3d4976d1c3eabea73edc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-and-merge-printtickets"></a>Gewusst wie: Überprüfen und Zusammenführen von PrintTickets
Die [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Druckschema](http://go.microsoft.com/fwlink/?LinkId=186397) enthält, die flexibel und erweiterbar sind <xref:System.Printing.PrintCapabilities> und <xref:System.Printing.PrintTicket> Elemente. Zählt die Funktionen von einem Druckgerät erstere auf und gibt der zweite Wert an, wie das Gerät für diese Funktionen in Bezug auf eine bestimmte Sequenz von Dokumenten, einzelnes Dokument oder eine einzelne Seite verwenden, sollten.  
  
 Eine typische Sequenz von Aufgaben für eine Anwendung, die unterstützt drucken würde wie folgt aussehen:  
  
1.  Bestimmen Sie die Leistungsmerkmale des Druckers.  
  
2.  Konfigurieren einer <xref:System.Printing.PrintTicket> zum Verwenden dieser Funktionen.  
  
3.  Überprüfen der <xref:System.Printing.PrintTicket>.  
  
 Dieser Artikel zeigt, wie dies.  
  
## <a name="example"></a>Beispiel  
 Im folgenden einfachen Beispiel, interessieren uns nur, ob ein Drucker Duplexdruck unterstützt – zweiseitigen drucken. Die wichtigsten Schritte sind wie folgt aus.  
  
1.  Abrufen einer <xref:System.Printing.PrintCapabilities> -Objekt mit den <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> Methode.  
  
2.  Testen Sie das Vorhandensein der gewünschten Funktion. Im folgenden Beispiel wir testen die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> Eigenschaft von der <xref:System.Printing.PrintCapabilities> -Objekt für das Vorhandensein der Funktion des Druckens auf beiden Seiten des Blatts mit "Deaktivieren der Seite" entlang der langen Seite des Blatts. Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> ist eine Auflistung, verwenden wir die `Contains` Methode <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Dieser Schritt ist nicht unbedingt erforderlich. Die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> unten verwendete Methode überprüft jede Anforderung die <xref:System.Printing.PrintTicket> gegenüber den Möglichkeiten des Druckers. Wenn die angeforderte Funktion vom Drucker nicht unterstützt wird, ersetzt der Druckertreiber wird eine alternative Anforderung in die <xref:System.Printing.PrintTicket> von der Methode zurückgegeben.  
  
3.  Wenn der Drucker Duplexdruck unterstützt, wird der Beispielcode erstellt eine <xref:System.Printing.PrintTicket> , die fordert Duplexdruck. Aber die Anwendung gibt keinen jede mögliche Drucker, die Einstellung in der <xref:System.Printing.PrintTicket> Element. Das wäre gehen zu Lasten der Programmierer und Programm. Stattdessen der Code legt nur die Duplex-Anforderung und führt Sie dies <xref:System.Printing.PrintTicket> mit einem vorhandenen, vollständig konfiguriert und überprüft, <xref:System.Printing.PrintTicket>, in diesem Fall den Benutzer standardmäßig <xref:System.Printing.PrintTicket>.  
  
4.  Dementsprechend im Beispiel ruft die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Methode, um die neue zusammenzuführen minimale <xref:System.Printing.PrintTicket> Standardwert des Benutzers <xref:System.Printing.PrintTicket>. Dies gibt eine <xref:System.Printing.ValidationResult> , enthält das neue <xref:System.Printing.PrintTicket> als eine seiner Eigenschaften.  
  
5.  Das Beispiel testet dann die neue <xref:System.Printing.PrintTicket> Duplexdruck anfordert. Wenn dies der Fall ist, erleichtert klicken Sie dann das Beispiel den neuen Standardwert Druckticket für den Benutzer. Wenn Schritt 2 oben wurde ausgelassen und Duplexdruck entlang der langen Seite wurde von der Drucker nicht unterstützt, dann die Tests zurückzuführen sein würden `false`. (Siehe Hinweis oben).  
  
6.  Der letzte wichtige Schritt ist, um die Änderung zu übernehmen die <xref:System.Printing.PrintQueue.UserPrintTicket%2A> Eigenschaft von der <xref:System.Printing.PrintQueue> mit der <xref:System.Printing.PrintQueue.Commit%2A> Methode.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Damit Sie schnell in diesem Beispiel testen können, wird im weiteren Verlauf unten dargestellt. Erstellen Sie ein Projekt und einen Namespace, und fügen Sie die Codeausschnitte in diesem Artikel in den Namespaceblock.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Drucken von Schemas](http://go.microsoft.com/fwlink/?LinkId=186397)
