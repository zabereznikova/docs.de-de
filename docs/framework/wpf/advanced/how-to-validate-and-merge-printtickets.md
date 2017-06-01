---
title: "Gewusst wie: &#220;berpr&#252;fen und Zusammenf&#252;hren von PrintTickets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zusammenführen von PrintTickets"
  - "PrintTicket, Zusammenführen"
  - "PrintTicket, Überprüfung"
  - "Überprüfung von PrintTickets"
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: &#220;berpr&#252;fen und Zusammenf&#252;hren von PrintTickets
Das [Druckschema](http://go.microsoft.com/fwlink/?LinkId=186397) von [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] enthält die flexiblen und erweiterbaren Elemente <xref:System.Printing.PrintCapabilities> und <xref:System.Printing.PrintTicket>.  Das erste Element legt die Funktionen eines Druckgeräts einzeln fest, während das zweite Element angibt, wie das Gerät diese Funktionen im Hinblick auf eine bestimmte Folge von Dokumenten, ein einzelnes Dokument oder eine einzelne Seite nutzt.  
  
 Eine typische Aufgabenfolge für eine Anwendung, die das Drucken unterstützt, sieht wie folgt aus.  
  
1.  Bestimmen Sie die Funktionen eines Druckers.  
  
2.  Konfigurieren Sie ein <xref:System.Printing.PrintTicket> für die Verwendung dieser Funktionen.  
  
3.  Überprüfen Sie das <xref:System.Printing.PrintTicket>.  
  
 In diesem Artikel wird die Vorgehensweise veranschaulicht.  
  
## Beispiel  
 Im nächsten einfachen Beispiel interessiert nur, ob ein Drucker den Duplexdruck unterstützt, d. h. doppelseitig drucken kann.  Dazu müssen Sie die folgenden Hauptschritte ausführen.  
  
1.  Rufen Sie ein <xref:System.Printing.PrintCapabilities>\-Objekt mit der <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>\-Methode ab.  
  
2.  Testen Sie, ob die gewünschte Funktion verfügbar ist.  Im folgenden Beispiel testen wir, ob die <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>\-Eigenschaft des <xref:System.Printing.PrintCapabilities>\-Objekts die Funktion bietet, beide Seiten eines Blatts so zu bedrucken, dass an der langen Seite des Blatts umgeblättert wird.  Da <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> eine Auflistung ist, wird die `Contains`\-Methode von <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> verwendet.  
  
    > [!NOTE]
    >  Dieser Schritt ist nicht unbedingt erforderlich.  Die unten verwendete <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>\-Methode vergleicht jede Anforderung <xref:System.Printing.PrintTicket> mit den Funktionen des Druckers.  Wenn die angeforderte Funktion vom Drucker nicht unterstützt wird, verwendet der Druckertreiber eine alternative Anforderung im von der Methode zurückgebenen <xref:System.Printing.PrintTicket>.  
  
3.  Wenn der Drucker den Duplexdruck unterstützt, wird im Beispielcode ein <xref:System.Printing.PrintTicket> erstellt, das den Duplexdruck anfordert.  Die Anwendung gibt jedoch nicht jede mögliche Druckereinstellung im <xref:System.Printing.PrintTicket>\-Element an.  Dieser Aufwand wäre für den Programmierer wie für das Programm zu groß.  Stattdessen legt der Code nur die Duplexdruckanforderung fest und führt dieses <xref:System.Printing.PrintTicket> anschließend mit einem vorhandenen, vollständig konfigurierten und überprüften <xref:System.Printing.PrintTicket> zusammen, in diesem Fall dem Standard\-<xref:System.Printing.PrintTicket> des Benutzers.  
  
4.  Entsprechend wird im Beispiel die <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>\-Methode aufgerufen, um das neue, minimale <xref:System.Printing.PrintTicket> mit dem Standard\-<xref:System.Printing.PrintTicket> des Benutzers zusammenzuführen.  Daraufhin wird ein <xref:System.Printing.ValidationResult> mit einem neuen <xref:System.Printing.PrintTicket> als eine Eigenschaft zurückgegeben.  
  
5.  Anschließend wird im Beispiel getestet, ob das neue <xref:System.Printing.PrintTicket> den Duplexdruck anfordert.  Wenn dies der Fall ist, wird es im Beispiel als neues Standarddruckticket für den Benutzer definiert.  Wenn Sie Schritt 2 oben übersprungen und der Drucker den Duplexdruck entlang der langen Seite nicht unterstützt hat, würde das Testergebnis `false` lauten  \(siehe Hinweis oben\).  
  
6.  Der letzte wichtige Schritt besteht darin, die Änderung mit der <xref:System.Printing.PrintQueue.Commit%2A>\-Methode auf die <xref:System.Printing.PrintQueue.UserPrintTicket%2A>\-Eigenschaft von <xref:System.Printing.PrintQueue> anzuwenden.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Damit Sie dieses Beispiel schnell testen können, finden Sie unten den restlichen Code.  Erstellen Sie ein Projekt und einen Namespace, und fügen Sie anschließend die Codeausschnitte aus diesem Artikel in den Namespaceblock ein.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## Siehe auch  
 <xref:System.Printing.PrintCapabilities>   
 <xref:System.Printing.PrintTicket>   
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Druckschema](http://go.microsoft.com/fwlink/?LinkId=186397)