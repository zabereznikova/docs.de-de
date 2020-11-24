---
title: Kooperatives Abbrechen von Threads
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 9e9224e9dc9ac57defe75e916dd6b9844bba7f12
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826611"
---
# <a name="canceling-threads-cooperatively"></a>Kooperatives Abbrechen von Threads

Vor .NET Framework 4 stellte .NET keine integrierte Option zum kooperativen Abbrechen eines Threads bereit, nachdem dieser gestartet wurde. Ab .NET Framework 4 können Sie jedoch <xref:System.Threading.CancellationToken?displayProperty=nameWithType> zum Abbrechen von Threads verwenden, und zwar auf dieselbe Weise wie Sie diese zum Abbrechen von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekten oder PLINQ-Abfragen verwenden können. Obwohl die <xref:System.Threading.Thread?displayProperty=nameWithType> -Klasse keine integrierte Unterstützung für Abbruchtoken bietet, können Sie ein Token an eine Threadprozedur übergeben. Dazu verwenden Sie den <xref:System.Threading.Thread> -Konstruktor, der ein <xref:System.Threading.ParameterizedThreadStart> -Delegat akzeptiert. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Threads und Threading](using-threads-and-threading.md)
