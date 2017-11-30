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
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="2aa0d-102">Gewusst wie: Lauschen auf mehrere Abbruchanforderungen</span><span class="sxs-lookup"><span data-stu-id="2aa0d-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="2aa0d-103">In diesem Beispiel wird gezeigt, wie auf zwei Abbruchtoken gleichzeitig lauschen, so, dass Sie einen Vorgang abbrechen können, wenn beide Token angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2aa0d-104">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="2aa0d-105">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-105">This error is benign.</span></span> <span data-ttu-id="2aa0d-106">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="2aa0d-107">Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa0d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aa0d-108">Example</span></span>  
 <span data-ttu-id="2aa0d-109">Im folgenden Beispiel die <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> Methode wird verwendet, um zwei Token zu einem Token zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="2aa0d-110">Dadurch wird das Token an Methoden übergeben werden, die nur ein Abbruchtoken als Argument annehmen.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="2aa0d-111">Das Beispiel veranschaulicht ein häufiges Szenario, in dem eine Methode sowohl ein Token, die von außerhalb der Klasse und ein Token generiert innerhalb der Klasse übergeben beachten muss.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="2aa0d-112">Wenn das verknüpfte Token löst ein <xref:System.OperationCanceledException>, das Token, das auf die Ausnahme übergeben wird ist das verknüpfte Token nicht entweder die Vorgängertoken.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="2aa0d-113">Um zu bestimmen, welches Token abgebrochen wurde, überprüfen Sie den Status der Vorgängertoken direkt.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="2aa0d-114">In diesem Beispiel <xref:System.AggregateException> niemals ausgelöst werden soll, aber es ist hier abgefangen, da in realen Szenarios beliebige andere Ausnahmen außer <xref:System.OperationCanceledException> die ausgelöst werden, aus den Aufgabendelegaten umschlossen eine <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="2aa0d-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa0d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aa0d-115">See Also</span></span>  
 [<span data-ttu-id="2aa0d-116">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="2aa0d-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
