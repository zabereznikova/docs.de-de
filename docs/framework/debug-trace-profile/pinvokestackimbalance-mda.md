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
ms.openlocfilehash: c789e8cb409bd4c59c91d6b646efe428afe7c86d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217246"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="356eb-102">PInvokeStackImbalance-MDA</span><span class="sxs-lookup"><span data-stu-id="356eb-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="356eb-103">Der `PInvokeStackImbalance` Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn die CLR erkennt, dass die Stapel Tiefe nach einem Platt Form Aufruf nicht mit der erwarteten Stapel Tiefe übereinstimmt, wenn die im <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut angegebene Aufruf Konvention und die Deklaration der Parameter in der verwalteten Signatur angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="356eb-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="356eb-104">Der `PInvokeStackImbalance`-MDA wird nur für 32-Bit-x86-Plattformen implementiert.</span><span class="sxs-lookup"><span data-stu-id="356eb-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="356eb-105">Der `PInvokeStackImbalance`-MDA ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="356eb-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="356eb-106">In Visual Studio 2017 und höheren Versionen wird der `PInvokeStackImbalance`-MDA in der Liste der **Assistenten für verwaltetes Debuggen** im Dialogfeld **Ausnahme Einstellungen** angezeigt (wird angezeigt, wenn Sie > **Windows** - > **Ausnahme Einstellungen** **Debuggen** auswählen).</span><span class="sxs-lookup"><span data-stu-id="356eb-106">In Visual Studio 2017 and later versions, the `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="356eb-107">Durch Aktivieren oder Deaktivieren des Kontrollkästchens "unter **brechen bei** auslösen" wird jedoch der MDA nicht aktiviert bzw. deaktiviert. Es steuert nur, ob Visual Studio eine Ausnahme auslöst, wenn der MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="356eb-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="356eb-108">Symptome</span><span class="sxs-lookup"><span data-stu-id="356eb-108">Symptoms</span></span>

<span data-ttu-id="356eb-109">Während eines Plattformaufrufs in einer Anwendung oder danach kommt es zu einer Zugriffsverletzung oder Speicherbeschädigung.</span><span class="sxs-lookup"><span data-stu-id="356eb-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="356eb-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="356eb-110">Cause</span></span>

<span data-ttu-id="356eb-111">Die verwaltete Signatur des Plattformaufrufs stimmt möglicherweise nicht mit der nicht verwalteten Signatur der aufgerufenen Methode überein.</span><span class="sxs-lookup"><span data-stu-id="356eb-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="356eb-112">Dazu kann es kommen, wenn für die verwaltete Methode nicht die korrekte Anzahl der Parameter bzw. eine falsche Parametergröße deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="356eb-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="356eb-113">Der MDA wird auch aktiviert, wenn die ggf. durch das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut festgelegte Aufrufkonvention nicht mit der nicht verwalteten Aufrufkonvention übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="356eb-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="356eb-114">Lösung</span><span class="sxs-lookup"><span data-stu-id="356eb-114">Resolution</span></span>

<span data-ttu-id="356eb-115">Überprüfen Sie die Signatur des verwalteten Plattformaufrufs sowie die Aufrufkonvention, um sich zu vergewissern, dass diese mit der Signatur und Aufrufkonvention des systemeigenen Ziels übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="356eb-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="356eb-116">Versuchen Sie, die Aufrufkonvention sowohl auf der verwalteten als auch auf der nicht verwalteten Seite explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="356eb-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="356eb-117">Es ist ebenfalls möglich (wenn auch weniger wahrscheinlich), dass die nicht verwaltete Funktion aus einem anderen Grund einen nicht ausgeglichenen Stapel verursacht hat, beispielsweise durch einen Programmfehler im nicht verwalteten Compiler.</span><span class="sxs-lookup"><span data-stu-id="356eb-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="356eb-118">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="356eb-118">Effect on the Runtime</span></span>

<span data-ttu-id="356eb-119">Erzwingt für alle Plattformaufrufe die Verwendung des nicht optimierten Pfads in die CLR.</span><span class="sxs-lookup"><span data-stu-id="356eb-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="356eb-120">Output</span><span class="sxs-lookup"><span data-stu-id="356eb-120">Output</span></span>

<span data-ttu-id="356eb-121">Die MDA-Meldung enthält den Namen der Plattformaufrufmethode, die das Stapelungleichgewicht verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="356eb-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="356eb-122">Beispielmeldung eines Plattformaufrufs der `SampleMethod`-Methode:</span><span class="sxs-lookup"><span data-stu-id="356eb-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="356eb-123">**Ein Ping-Befehl für die PInvoke-Funktion "SampleMethod" hat den Stapel nicht ausgeglichen. Dies liegt wahrscheinlich daran, dass die verwaltete PInvoke-Signatur nicht mit der nicht verwalteten Ziel Signatur identisch ist. Überprüfen Sie, ob die Aufruf Konvention und die Parameter der PInvoke-Signatur mit der nicht verwalteten Ziel Signatur übereinstimmen.**</span><span class="sxs-lookup"><span data-stu-id="356eb-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="356eb-124">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="356eb-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="356eb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="356eb-125">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="356eb-126">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="356eb-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="356eb-127">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="356eb-127">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
