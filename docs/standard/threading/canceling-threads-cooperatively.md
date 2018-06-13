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
ms.openlocfilehash: 3edd0f9c991df8d8d70b14f4439c5c477e8f1401
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581341"
---
# <a name="canceling-threads-cooperatively"></a>Kooperatives Abbrechen von Threads
Vor [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]stellte .NET Framework keine integrierte Option zum kooperativen Abbrechen eines Threads bereit, nachdem dieser gestartet wurde. Sie können in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] jedoch Abbruchtoken verwenden, um Threads abzubrechen, so, wie Sie diese auch zum Abbrechen von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekten oder PLINQ-Abfragen verwenden würden. Obwohl die <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse keine integrierte Unterstützung für Abbruchtoken bietet, können Sie ein Token an eine Threadprozedur übergeben. Dazu verwenden Sie den <xref:System.Threading.Thread>-Konstruktor, der einen <xref:System.Threading.ParameterizedThreadStart>-Delegaten akzeptiert. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Threads und Threading](../../../docs/standard/threading/using-threads-and-threading.md)
