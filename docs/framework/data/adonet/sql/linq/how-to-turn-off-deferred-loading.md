---
title: 'Vorgehensweise: Deaktivieren des verzögerten Ladens'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 6559392527bb02afe9cea61e704f1f371c6d5470
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781654"
---
# <a name="how-to-turn-off-deferred-loading"></a>Vorgehensweise: Deaktivieren des verzögerten Ladens
Sie können verzögertes Laden ausschalten, indem Sie <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` festlegen. Weitere Informationen finden Sie unter [Verzögertes im Vergleich zu unmittelbarem laden](deferred-versus-immediate-loading.md).  
  
> [!NOTE]
> Verzögertes Laden wird ausgeschaltet, wenn die Objektverfolgung ausgeschaltet wird. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Informationen als](how-to-retrieve-information-as-read-only.md)schreibgeschützt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie verzögertes Laden durch Festlegen von <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` ausgeschaltet wird.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragekonzepte](query-concepts.md)
- [Abfragen der Datenbank](querying-the-database.md)
