---
title: 'Vorgehensweise: Auslagerungs Ergebnisse laden (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: e718aad904a43d118a243afafc17834cba31f028
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790459"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Vorgehensweise: Auslagerungs Ergebnisse laden (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es dem Datendienst, die Anzahl von Entitäten zu beschränken, die in einem einzelnen Antwortfeed zurückgegeben werden. In diesem Fall enthält der abschließende Eintrag im Feed einen Link zur nächsten Datenseite. Der URI zur nächsten Datenseite wird abgerufen, indem Sie die <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>-Methode der <xref:System.Data.Services.Client.QueryOperationResponse%601> aufrufen, die beim Ausführen der <xref:System.Data.Services.Client.DataServiceQuery%601> zurückgegeben wird. Der von diesem Objekt dargestellte URI wird dann verwendet, um die nächste Ergebnisseite zu laden. Weitere Informationen finden Sie unter [Laden von verzögertem Inhalt](loading-deferred-content-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden `do…while`-Entitäten aus ausgelagerten Ergebnissen aus dem Datendienst mithilfe einer `Customers`-Schleife geladen.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden verknüpfte `Orders`-Entitäten mit jeder `Customers`-Entität zurückgegeben, und es wird eine `do…while`-Schleife zum Laden von `Customers`-Entitätenseiten und eine geschachtelte `while`-Schleife zum Laden verknüpfter `Orders`-Entitäten aus dem Datendienst verwendet.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>Siehe auch

- [Laden von verzögerten Inhalten](loading-deferred-content-wcf-data-services.md)
- [Vorgehensweise: Zugehörige Entitäten laden](how-to-load-related-entities-wcf-data-services.md)
