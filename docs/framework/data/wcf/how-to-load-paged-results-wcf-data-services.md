---
title: "Gewusst wie: Laden von ausgelagerten Ergebnissen (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Verzögerte Inhalte"
  - "WCF Data Services, Laden von Daten"
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Laden von ausgelagerten Ergebnissen (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es dem Datendienst, die Anzahl von Entitäten zu beschränken, die in einem einzelnen Antwortfeed zurückgegeben werden.  In diesem Fall enthält der abschließende Eintrag im Feed einen Link zur nächsten Datenseite.  Der URI zur nächsten Datenseite wird abgerufen, indem Sie die <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>\-Methode der <xref:System.Data.Services.Client.QueryOperationResponse%601> aufrufen, die beim Ausführen der <xref:System.Data.Services.Client.DataServiceQuery%601> zurückgegeben wird. Der von diesem Objekt dargestellte URI wird dann verwendet, um die nächste Ergebnisseite zu laden.  Weitere Informationen finden Sie unter [Laden von verzögertem Inhalt](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 In diesem Beispiel werden `Customers`\-Entitäten aus ausgelagerten Ergebnissen aus dem Datendienst mithilfe einer `do…while`\-Schleife geladen.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspaged)]  
  
## Beispiel  
 In diesem Beispiel werden verknüpfte `Orders`\-Entitäten mit jeder `Customers`\-Entität zurückgegeben, und es wird eine `do…while`\-Schleife zum Laden von `Customers`\-Entitätenseiten und eine geschachtelte `while`\-Schleife zum Laden verknüpfter `Orders`\-Entitäten aus dem Datendienst verwendet.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspagednested)]  
  
## Siehe auch  
 [Laden von verzögertem Inhalt](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)   
 [Gewusst wie: Laden von verknüpften Entitäten](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)