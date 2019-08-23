---
title: 'Vorgehensweise: Abrufen von Informationen als schreibgeschützt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: b98c5e6ea49695015eb566ca2176b23c5260017a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928710"
---
# <a name="how-to-retrieve-information-as-read-only"></a>Vorgehensweise: Abrufen von Informationen als schreibgeschützt
Wenn Sie nicht beabsichtigen, die Daten zu ändern, können Sie die Abfrageleistung steigern, indem Sie schreibgeschützte Ergebnisse verwenden.  
  
 Sie implementieren die schreibgeschützte Verarbeitung, indem Sie <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festlegen.  
  
> [!NOTE]
> Wird <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festgelegt, wird <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> implizit auf `false` festgelegt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird eine schreibgeschützte Auflistung von Mitarbeitereinstellungsdaten abgerufen.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [Verzögertes im Vergleich zu unmittelbarem Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
