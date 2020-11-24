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
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="70b02-102">Kooperatives Abbrechen von Threads</span><span class="sxs-lookup"><span data-stu-id="70b02-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="70b02-103">Vor .NET Framework 4 stellte .NET keine integrierte Option zum kooperativen Abbrechen eines Threads bereit, nachdem dieser gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="70b02-103">Prior to .NET Framework 4, .NET provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="70b02-104">Ab .NET Framework 4 können Sie jedoch <xref:System.Threading.CancellationToken?displayProperty=nameWithType> zum Abbrechen von Threads verwenden, und zwar auf dieselbe Weise wie Sie diese zum Abbrechen von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekten oder PLINQ-Abfragen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="70b02-104">However, starting with .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="70b02-105">Obwohl die <xref:System.Threading.Thread?displayProperty=nameWithType> -Klasse keine integrierte Unterstützung für Abbruchtoken bietet, können Sie ein Token an eine Threadprozedur übergeben. Dazu verwenden Sie den <xref:System.Threading.Thread> -Konstruktor, der ein <xref:System.Threading.ParameterizedThreadStart> -Delegat akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="70b02-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="70b02-106">Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="70b02-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="70b02-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70b02-107">See also</span></span>

- [<span data-ttu-id="70b02-108">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="70b02-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
