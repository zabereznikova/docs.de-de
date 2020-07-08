---
title: Marshalling von Delegaten als Rückrufmethode
description: Erfahren Sie mehr zum Marshalling eines Delegaten als Rückrufmethode. In diesem Beispiel wird veranschaulicht, wie Delegaten an eine nicht verwaltete Funktion übergeben werden, die Funktionszeiger erwartet.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
ms.openlocfilehash: bf9ef3b9d48c0869dcc96820c3a2fb6fb608479e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618947"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="bc5c9-104">Marshalling von Delegaten als Rückrufmethode</span><span class="sxs-lookup"><span data-stu-id="bc5c9-104">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="bc5c9-105">In diesem Beispiel wird veranschaulicht, wie Delegaten an eine nicht verwaltete Funktion übergeben werden, die Funktionszeiger erwartet.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-105">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="bc5c9-106">Ein Delegat ist eine Klasse, die einen Verweis auf eine Methode enthalten kann, und gleichbedeutend mit einem typsicheren Funktionszeiger oder einer Rückruffunktion ist.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-106">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>

> [!NOTE]
> <span data-ttu-id="bc5c9-107">Bei Verwendung eines Delegaten in einem Aufruf schützt die Common Language Runtime den Delegaten für die Dauer dieses Aufrufs vor der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-107">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="bc5c9-108">Wenn die nicht verwaltete Funktion jedoch den Delegaten speichert, um ihn nach dem Abschluss des Aufrufs zu verwenden, müssen Sie die Garbage Collection manuell verhindern, bis die nicht verwaltete Funktion mit dem Delegaten beendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-108">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="bc5c9-109">Weitere Informationen finden Sie unter [HandleRef-Beispiel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) und [GCHandle-Beispiel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bc5c9-109">For more information, see the [HandleRef Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) and [GCHandle Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span></span>

<span data-ttu-id="bc5c9-110">Das Rückrufbeispiel verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="bc5c9-110">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="bc5c9-111">`TestCallBack` aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-111">`TestCallBack` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack(FPTR pf, int value);
    ```

- <span data-ttu-id="bc5c9-112">`TestCallBack2` aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-112">`TestCallBack2` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack2(FPTR2 pf2, char* value);
    ```

<span data-ttu-id="bc5c9-113">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-113">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>

<span data-ttu-id="bc5c9-114">Die `NativeMethods`-Klasse in diesem Beispiel enthält verwaltete Prototypen für die `TestCallBack`- und `TestCallBack2`-Methoden.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-114">In this sample, the `NativeMethods` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="bc5c9-115">Beide Methoden übergeben einen Delegaten als Parameter an eine Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-115">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="bc5c9-116">Die Signatur des Delegaten muss mit der Signatur der Methode übereinstimmen, auf die er verweist.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-116">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="bc5c9-117">Die `FPtr`- und `FPtr2`-Delegaten verfügen beispielsweise über Signaturen, die identisch mit den `DoSomething`- und `DoSomething2`-Methoden sind.</span><span class="sxs-lookup"><span data-stu-id="bc5c9-117">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>

## <a name="declaring-prototypes"></a><span data-ttu-id="bc5c9-118">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="bc5c9-118">Declaring Prototypes</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
[!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
[!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]

## <a name="calling-functions"></a><span data-ttu-id="bc5c9-119">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="bc5c9-119">Calling Functions</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
[!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
[!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]

## <a name="see-also"></a><span data-ttu-id="bc5c9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc5c9-120">See also</span></span>

- <span data-ttu-id="bc5c9-121">[Verschiedene Marshallingbeispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bc5c9-121">[Miscellaneous Marshaling Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span></span>
- [<span data-ttu-id="bc5c9-122">Datentypen für den Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="bc5c9-122">Platform Invoke Data Types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="bc5c9-123">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="bc5c9-123">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
