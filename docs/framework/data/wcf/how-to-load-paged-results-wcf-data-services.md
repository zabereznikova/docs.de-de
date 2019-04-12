---
title: 'Vorgehensweise: Laden von ausgelagerten Ergebnissen (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: 0be7dcbefb23d2f2b283ac498f3b0ea43278f2d4
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517251"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Vorgehensweise: Laden von ausgelagerten Ergebnissen (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es dem Datendienst, die Anzahl von Entitäten zu beschränken, die in einem einzelnen Antwortfeed zurückgegeben werden. In diesem Fall enthält der abschließende Eintrag im Feed einen Link zur nächsten Datenseite. Der URI zur nächsten Datenseite wird abgerufen, indem Sie die <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>-Methode der <xref:System.Data.Services.Client.QueryOperationResponse%601> aufrufen, die beim Ausführen der <xref:System.Data.Services.Client.DataServiceQuery%601> zurückgegeben wird. Der von diesem Objekt dargestellte URI wird dann verwendet, um die nächste Ergebnisseite zu laden. Weitere Informationen finden Sie unter [verzögerte Inhalte laden](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden `do…while`-Entitäten aus ausgelagerten Ergebnissen aus dem Datendienst mithilfe einer `Customers`-Schleife geladen.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden verknüpfte `Orders`-Entitäten mit jeder `Customers`-Entität zurückgegeben, und es wird eine `do…while`-Schleife zum Laden von `Customers`-Entitätenseiten und eine geschachtelte `while`-Schleife zum Laden verknüpfter `Orders`-Entitäten aus dem Datendienst verwendet.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>Siehe auch

- [Laden von verzögerten Inhalten](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [Vorgehensweise: Laden von verbundenen Entitäten](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)
