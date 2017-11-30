---
title: "Gewusst wie: Umschließen von EAP-Mustern in einer Aufgabe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae9d90c9bb3d0e8d315cbef510cdfe1b54e66da4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>Gewusst wie: Umschließen von EAP-Mustern in einer Aufgabe
Im folgende Beispiel wird gezeigt, wie eine beliebige Abfolge von Vorgängen für das ereignisbasierte asynchrone Muster (EAP) als eine Aufgabe mit verfügbar machen eine <xref:System.Threading.Tasks.TaskCompletionSource%601>. Außerdem wird gezeigt, wie eine <xref:System.Threading.CancellationToken> für die integrierte Abbruchmethoden aufgerufen werden soll die <xref:System.Net.WebClient> Objekte.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>Siehe auch  
 [TPL und herkömmliche asynchrone .NET Framework-Programmierung](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
