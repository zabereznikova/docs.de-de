---
title: 'Vorgehensweise: Schalten Sie verzögertes Laden aus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 9878ec468333ba79d0171d0bf96235d48273e03e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669535"
---
# <a name="how-to-turn-off-deferred-loading"></a>Vorgehensweise: Schalten Sie verzögertes Laden aus
Sie können verzögertes Laden ausschalten, indem Sie <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` festlegen. Weitere Informationen finden Sie unter [verzögertes im Vergleich zu den sofortigen Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
> [!NOTE]
>  Verzögertes Laden wird ausgeschaltet, wenn die Objektverfolgung ausgeschaltet wird. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Informationen als nur-Lese](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie verzögertes Laden durch Festlegen von <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` ausgeschaltet wird.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch
- [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
