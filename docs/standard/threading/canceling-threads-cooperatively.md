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
ms.openlocfilehash: 24cacf0323c96f6959442dea94b0540633661bce
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485598"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="62982-102">Kooperatives Abbrechen von Threads</span><span class="sxs-lookup"><span data-stu-id="62982-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="62982-103">Vor .NET Framework 4 stellte .NET Framework keine integrierte Option zum kooperativen Abbrechen eines Threads bereit, nachdem dieser gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="62982-103">Prior to the .NET Framework 4, the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="62982-104">Ab .NET Framework 4 können Sie jedoch <xref:System.Threading.CancellationToken?displayProperty=nameWithType> zum Abbrechen von Threads verwenden, so, wie Sie diese auch zum Abbrechen von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekten oder PLINQ-Abfragen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="62982-104">However, starting with the .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="62982-105">Obwohl die <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse keine integrierte Unterstützung für Abbruchtoken bietet, können Sie ein Token an eine Threadprozedur übergeben. Dazu verwenden Sie den <xref:System.Threading.Thread>-Konstruktor, der einen <xref:System.Threading.ParameterizedThreadStart>-Delegaten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="62982-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="62982-106">Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="62982-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="62982-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62982-107">See also</span></span>

 [<span data-ttu-id="62982-108">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="62982-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)  
