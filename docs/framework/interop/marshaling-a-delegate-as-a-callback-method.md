---
title: Marshalling von Delegaten als Rückrufmethode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff875f2807a14493ab81a9e354b5c4dcdf3d5feb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389382"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="d7ab5-102">Marshalling von Delegaten als Rückrufmethode</span><span class="sxs-lookup"><span data-stu-id="d7ab5-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="d7ab5-103">In diesem Beispiel wird veranschaulicht, wie Delegaten an eine nicht verwaltete Funktion übergeben werden, die Funktionszeiger erwartet.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="d7ab5-104">Ein Delegat ist eine Klasse, die einen Verweis auf eine Methode enthalten kann, und gleichbedeutend mit einem typsicheren Funktionszeiger oder einer Rückruffunktion ist.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7ab5-105">Bei Verwendung eines Delegaten in einem Aufruf schützt die Common Language Runtime den Delegaten für die Dauer dieses Aufrufs vor der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="d7ab5-106">Wenn die nicht verwaltete Funktion jedoch den Delegaten speichert, um ihn nach dem Abschluss des Aufrufs zu verwenden, müssen Sie die Garbage Collection manuell verhindern, bis die nicht verwaltete Funktion mit dem Delegaten beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="d7ab5-107">Weitere Informationen finden Sie unter [HandleRef-Beispiel](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) und [GCHandle-Beispiel](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d7ab5-107">For more information, see the [HandleRef Sample](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) and [GCHandle Sample](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span></span>  
  
 <span data-ttu-id="d7ab5-108">Das Rückrufbeispiel verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d7ab5-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="d7ab5-109">**TestCallBack** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="d7ab5-110">**TestCallBack2** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="d7ab5-111">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-111">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="d7ab5-112">Die `LibWrap`-Klasse in diesem Beispiel enthält verwaltete Prototypen für die `TestCallBack`- und `TestCallBack2`-Methoden.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="d7ab5-113">Beide Methoden übergeben einen Delegaten als Parameter an eine Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="d7ab5-114">Die Signatur des Delegaten muss mit der Signatur der Methode übereinstimmen, auf die er verweist.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="d7ab5-115">Die `FPtr`- und `FPtr2`-Delegaten verfügen beispielsweise über Signaturen, die identisch mit den `DoSomething`- und `DoSomething2`-Methoden sind.</span><span class="sxs-lookup"><span data-stu-id="d7ab5-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="d7ab5-116">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="d7ab5-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="d7ab5-117">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="d7ab5-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="d7ab5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7ab5-118">See Also</span></span>  
 <span data-ttu-id="d7ab5-119">[Verschiedene Marshallingbeispiele](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d7ab5-119">[Miscellaneous Marshaling Samples](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span></span>  
 <span data-ttu-id="d7ab5-120">[Datentypen für den Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d7ab5-120">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="d7ab5-121">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="d7ab5-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
