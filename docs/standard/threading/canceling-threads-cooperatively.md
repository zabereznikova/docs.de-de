---
title: Kooperatives Abbrechen von Threads
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
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="7fb47-102">Kooperatives Abbrechen von Threads</span><span class="sxs-lookup"><span data-stu-id="7fb47-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="7fb47-103">Vor [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]stellte .NET Framework keine integrierte Option zum kooperativen Abbrechen eines Threads bereit, nachdem dieser gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="7fb47-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="7fb47-104">Allerdings in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], können Sie Abbruchtoken zum Abbrechen von Threads, wie Sie sie verwenden können, auf "Abbrechen" <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> -Objekten oder PLINQ-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="7fb47-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="7fb47-105">Obwohl die <xref:System.Threading.Thread?displayProperty=nameWithType> Klasse keinen integrierten Unterstützung für Abbruchtoken bietet, können Sie ein Token an eine Threadprozedur übergeben, indem die <xref:System.Threading.Thread> Konstruktor, akzeptiert eine <xref:System.Threading.ParameterizedThreadStart> delegieren.</span><span class="sxs-lookup"><span data-stu-id="7fb47-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="7fb47-106">Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7fb47-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="7fb47-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fb47-107">See Also</span></span>  
 [<span data-ttu-id="7fb47-108">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="7fb47-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
