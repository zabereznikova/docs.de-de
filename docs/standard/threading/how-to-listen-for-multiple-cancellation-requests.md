---
title: 'Gewusst wie: Lauschen auf mehrere Abbruchanforderungen'
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
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 397de114a3d8c3cbcfbc8ab55e4dbaf45ca9b652
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="5c53d-102">Gewusst wie: Lauschen auf mehrere Abbruchanforderungen</span><span class="sxs-lookup"><span data-stu-id="5c53d-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="5c53d-103">In diesem Beispiel wird gezeigt, wie Sie zwei Abbruchtoken gleichzeitig abhören können, um einen Vorgang abzubrechen, wenn dies von einem der beiden Token angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="5c53d-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c53d-104">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c53d-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="5c53d-105">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="5c53d-105">This error is benign.</span></span> <span data-ttu-id="5c53d-106">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="5c53d-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="5c53d-107">Um zu verhindern, dass Visual Studio beim ersten Fehler abbricht, deaktivieren Sie einfach unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.</span><span class="sxs-lookup"><span data-stu-id="5c53d-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c53d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c53d-108">Example</span></span>  
 <span data-ttu-id="5c53d-109">Im folgenden Beispiel werden mithilfe der <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A>-Methode zwei Token zu einem Token verbunden.</span><span class="sxs-lookup"><span data-stu-id="5c53d-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="5c53d-110">Dadurch kann das Token an Methoden übergeben werden, die nur ein Abbruchtoken als Argument akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="5c53d-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="5c53d-111">Das Beispiel veranschaulicht ein gängiges Szenario, in dem eine Methode sowohl ein Token, das von außerhalb der Klasse eingegangen ist, und ein Token, das innerhalb der Klasse generiert wurde, beachten muss.</span><span class="sxs-lookup"><span data-stu-id="5c53d-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="5c53d-112">Wenn das verknüpfte Token eine <xref:System.OperationCanceledException> auslöst, ist das Token, das an die Ausnahme übergeben wird, das verknüpfte Token, und nicht eines der Vorgängertoken.</span><span class="sxs-lookup"><span data-stu-id="5c53d-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="5c53d-113">Um zu ermitteln, welches Token abgebrochen wurde, prüfen Sie direkt den Status der Vorgängertoken.</span><span class="sxs-lookup"><span data-stu-id="5c53d-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="5c53d-114">In diesem Beispiel sollte <xref:System.AggregateException> niemals ausgelöst werden, aber es wird hier dennoch abgefangen, da in der Praxis alle anderen Ausnahmen außer <xref:System.OperationCanceledException>, die von dem Taskdelegaten ausgelöst werden, von einer <xref:System.OperationCanceledException> umschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="5c53d-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c53d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c53d-115">See Also</span></span>  
 [<span data-ttu-id="5c53d-116">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="5c53d-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
