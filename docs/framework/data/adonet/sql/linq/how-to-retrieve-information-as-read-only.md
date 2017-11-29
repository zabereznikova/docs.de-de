---
title: "Gewusst wie: Abrufen von Informationen als schreibgeschützt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9a9765d8d8330c7ad2a6e8cb25166427cdd9414a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-information-as-read-only"></a>Gewusst wie: Abrufen von Informationen als schreibgeschützt
Wenn Sie nicht beabsichtigen, die Daten zu ändern, können Sie die Abfrageleistung steigern, indem Sie schreibgeschützte Ergebnisse verwenden.  
  
 Sie implementieren die schreibgeschützte Verarbeitung, indem Sie <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festlegen.  
  
> [!NOTE]
>  Wird <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festgelegt, wird <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> implizit auf `false` festgelegt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird eine schreibgeschützte Auflistung von Mitarbeitereinstellungsdaten abgerufen.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [Verzögerte und unmittelbare Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
