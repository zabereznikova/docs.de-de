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
ms.openlocfilehash: 36de18e976401dd0cde878852c064aa982b8acde
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188496"
---
# <a name="canceling-threads-cooperatively"></a>Kooperatives Abbrechen von Threads

Vor .NET Framework 4 stellte .NET keine integrierte Option zum kooperativen Abbrechen eines Threads bereit, nachdem dieser gestartet wurde. Ab .NET Framework 4 können Sie jedoch <xref:System.Threading.CancellationToken?displayProperty=nameWithType> zum Abbrechen von Threads verwenden, und zwar auf dieselbe Weise wie Sie diese zum Abbrechen von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekten oder PLINQ-Abfragen verwenden können. Obwohl die <xref:System.Threading.Thread?displayProperty=nameWithType> -Klasse keine integrierte Unterstützung für Abbruchtoken bietet, können Sie ein Token an eine Threadprozedur übergeben. Dazu verwenden Sie den <xref:System.Threading.Thread> -Konstruktor, der ein <xref:System.Threading.ParameterizedThreadStart> -Delegat akzeptiert. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Threads und Threading](using-threads-and-threading.md)
