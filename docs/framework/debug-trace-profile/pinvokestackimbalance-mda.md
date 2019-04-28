---
title: pInvokeStackImbalance-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ecdfd708217f260b0c02383159fab88948029c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61874210"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="39dcc-102">PInvokeStackImbalance-MDA</span><span class="sxs-lookup"><span data-stu-id="39dcc-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="39dcc-103">Die `PInvokeStackImbalance` -Assistent für verwaltetes Debuggens (MDA) wird aktiviert, wenn die CLR erkennt, dass die Stapeltiefe nach einem Plattformaufruf nicht mit der Stapeltiefe, der angegebenen Aufrufkonvention entspricht der <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut und die die Deklaration der Parameter in der verwalteten Signatur.</span><span class="sxs-lookup"><span data-stu-id="39dcc-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="39dcc-104">Der `PInvokeStackImbalance`-MDA wird nur für 32-Bit-x86-Plattformen implementiert.</span><span class="sxs-lookup"><span data-stu-id="39dcc-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="39dcc-105">Die `PInvokeStackImbalance` MDA ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="39dcc-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="39dcc-106">In Visual Studio 2017 die `PInvokeStackImbalance` MDA wird angezeigt, der **Managed Debugging Assistants** Liste der **Ausnahmeeinstellungen** Dialogfeld (wird angezeigt, wenn Sie auswählen, **Debuggen**  >  **Windows** > **Ausnahmeeinstellungen**).</span><span class="sxs-lookup"><span data-stu-id="39dcc-106">In Visual Studio 2017, The `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="39dcc-107">Allerdings aktivieren bzw. Deaktivieren der **unterbrechen Wenn ausgelöst** das Kontrollkästchen nicht aktivieren oder deaktivieren Sie den MDA; Hierdurch wird nur festgelegt, ob es sich bei Visual Studio eine Ausnahme auslöst, wenn der MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="39dcc-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="39dcc-108">Symptome</span><span class="sxs-lookup"><span data-stu-id="39dcc-108">Symptoms</span></span>

<span data-ttu-id="39dcc-109">Während eines Plattformaufrufs in einer Anwendung oder danach kommt es zu einer Zugriffsverletzung oder Speicherbeschädigung.</span><span class="sxs-lookup"><span data-stu-id="39dcc-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="39dcc-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="39dcc-110">Cause</span></span>

<span data-ttu-id="39dcc-111">Die verwaltete Signatur des Plattformaufrufs stimmt möglicherweise nicht mit der nicht verwalteten Signatur der aufgerufenen Methode überein.</span><span class="sxs-lookup"><span data-stu-id="39dcc-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="39dcc-112">Dazu kann es kommen, wenn für die verwaltete Methode nicht die korrekte Anzahl der Parameter bzw. eine falsche Parametergröße deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="39dcc-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="39dcc-113">Der MDA wird auch aktiviert, wenn die ggf. durch das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut festgelegte Aufrufkonvention nicht mit der nicht verwalteten Aufrufkonvention übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="39dcc-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="39dcc-114">Auflösung</span><span class="sxs-lookup"><span data-stu-id="39dcc-114">Resolution</span></span>

<span data-ttu-id="39dcc-115">Überprüfen Sie die Signatur des verwalteten Plattformaufrufs sowie die Aufrufkonvention, um sich zu vergewissern, dass diese mit der Signatur und Aufrufkonvention des systemeigenen Ziels übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="39dcc-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="39dcc-116">Versuchen Sie, die Aufrufkonvention sowohl auf der verwalteten als auch auf der nicht verwalteten Seite explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="39dcc-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="39dcc-117">Es ist ebenfalls möglich (wenn auch weniger wahrscheinlich), dass die nicht verwaltete Funktion aus einem anderen Grund einen nicht ausgeglichenen Stapel verursacht hat, beispielsweise durch einen Programmfehler im nicht verwalteten Compiler.</span><span class="sxs-lookup"><span data-stu-id="39dcc-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="39dcc-118">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="39dcc-118">Effect on the Runtime</span></span>

<span data-ttu-id="39dcc-119">Erzwingt für alle Plattformaufrufe die Verwendung des nicht optimierten Pfads in die CLR.</span><span class="sxs-lookup"><span data-stu-id="39dcc-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="39dcc-120">Output</span><span class="sxs-lookup"><span data-stu-id="39dcc-120">Output</span></span>

<span data-ttu-id="39dcc-121">Die MDA-Meldung enthält den Namen der Plattformaufrufmethode, die das Stapelungleichgewicht verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="39dcc-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="39dcc-122">Beispielmeldung eines Plattformaufrufs der `SampleMethod`-Methode: </span><span class="sxs-lookup"><span data-stu-id="39dcc-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="39dcc-123">**Ein Aufruf PInvoke-Funktion "SampleMethod" hat einen nicht ausgeglichenen Stapel. Dies ist wahrscheinlich, weil die verwaltete PInvoke-Signatur nicht die Signatur nicht verwaltetes Ziel übereinstimmt. Überprüfen Sie, dass die Aufrufkonvention und die Parameter von PInvoke-Signatur die nicht verwalteten Ziel-Signatur entsprechen.**</span><span class="sxs-lookup"><span data-stu-id="39dcc-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="39dcc-124">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="39dcc-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="39dcc-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39dcc-125">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="39dcc-126">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="39dcc-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="39dcc-127">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="39dcc-127">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
