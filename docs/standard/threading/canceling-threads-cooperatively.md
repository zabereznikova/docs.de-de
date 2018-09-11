---
title: Kooperatives Abbrechen von Threads
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd32deb9c8719a12b76aaea8ec91a17471cf18f9
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259859"
---
# <a name="canceling-threads-cooperatively"></a>Kooperatives Abbrechen von Threads

Vor .NET Framework 4 stellte .NET Framework keine integrierte Option zum kooperativen Abbrechen eines Threads bereit, nachdem dieser gestartet wurde. Ab .NET Framework 4 können Sie jedoch <xref:System.Threading.CancellationToken?displayProperty=nameWithType> zum Abbrechen von Threads verwenden, so, wie Sie diese auch zum Abbrechen von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekten oder PLINQ-Abfragen verwenden können. Obwohl die <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse keine integrierte Unterstützung für Abbruchtoken bietet, können Sie ein Token an eine Threadprozedur übergeben. Dazu verwenden Sie den <xref:System.Threading.Thread>-Konstruktor, der einen <xref:System.Threading.ParameterizedThreadStart>-Delegaten akzeptiert. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Threads und Threading](using-threads-and-threading.md)
