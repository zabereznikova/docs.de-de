---
title: pInvokeStackImbalance-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b33a3edc5780ecf07e7809ca327a304d748110f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="ea5f5-102">pInvokeStackImbalance-MDA</span><span class="sxs-lookup"><span data-stu-id="ea5f5-102">pInvokeStackImbalance MDA</span></span>
<span data-ttu-id="ea5f5-103">Der `pInvokeStackImbalance`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR erkennt, dass die Stapeltiefe nach einem Plattformaufruf nicht mit der Stapeltiefe übereinstimmt, die in Anbetracht der im <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut angegebenen Aufrufkonvention und der Parameter in der verwalteten Signatur zu erwarten war.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-103">The `pInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute as well as the declaration of the parameters in the managed signature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea5f5-104">Der `pInvokeStackImbalance`-MDA wird nur für 32-Bit-x86-Plattformen implementiert.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-104">The `pInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea5f5-105">In .NET Framework, Version 3.5, ist der `pInvokeStackImbalance`-MDA standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-105">In the .NET Framework version 3.5, the `pInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="ea5f5-106">Wenn Sie .NET Framework, Version 3.5, mit Visual Studio 2005 verwenden, wird der `pInvokeStackImbalance`-MDA in der Liste **Assistenten für verwaltetes Debuggen** im Dialogfeld **Ausnahmen** angezeigt. (Das Dialogfeld wird aufgerufen, wenn Sie im Menü **Debuggen** auf **Ausnahmen** klicken).</span><span class="sxs-lookup"><span data-stu-id="ea5f5-106">When you use the .NET Framework version 3.5 with Visual Studio 2005, the `pInvokeStackImbalance` MDA will appear in the **Managed Debugging Assistants** list in the **Exceptions** dialog box (which is displayed when you click **Exceptions** on the **Debug** menu).</span></span> <span data-ttu-id="ea5f5-107">Wenn Sie jedoch das Kontrollkästchen **Ausgelöst** für `pInvokeStackImbalance` aktivieren oder deaktivieren, wird der MDA nicht aktiviert bzw. deaktiviert; hierdurch wird nur festgelegt, ob Visual Studio beim Aktivieren des MDAs eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-107">However, selecting or clearing the **Thrown** check box for `pInvokeStackImbalance` does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ea5f5-108">Symptome</span><span class="sxs-lookup"><span data-stu-id="ea5f5-108">Symptoms</span></span>  
 <span data-ttu-id="ea5f5-109">Während eines Plattformaufrufs in einer Anwendung oder danach kommt es zu einer Zugriffsverletzung oder Speicherbeschädigung.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ea5f5-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="ea5f5-110">Cause</span></span>  
 <span data-ttu-id="ea5f5-111">Die verwaltete Signatur des Plattformaufrufs stimmt möglicherweise nicht mit der nicht verwalteten Signatur der aufgerufenen Methode überein.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="ea5f5-112">Dazu kann es kommen, wenn für die verwaltete Methode nicht die korrekte Anzahl der Parameter bzw. eine falsche Parametergröße deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="ea5f5-113">Der MDA wird auch aktiviert, wenn die ggf. durch das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut festgelegte Aufrufkonvention nicht mit der nicht verwalteten Aufrufkonvention übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ea5f5-114">Lösung</span><span class="sxs-lookup"><span data-stu-id="ea5f5-114">Resolution</span></span>  
 <span data-ttu-id="ea5f5-115">Überprüfen Sie die Signatur des verwalteten Plattformaufrufs sowie die Aufrufkonvention, um sich zu vergewissern, dass diese mit der Signatur und Aufrufkonvention des systemeigenen Ziels übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="ea5f5-116">Versuchen Sie, die Aufrufkonvention sowohl auf der verwalteten als auch auf der nicht verwalteten Seite explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="ea5f5-117">Es ist ebenfalls möglich (wenn auch weniger wahrscheinlich), dass die nicht verwaltete Funktion aus einem anderen Grund einen nicht ausgeglichenen Stapel verursacht hat, beispielsweise durch einen Programmfehler im nicht verwalteten Compiler. </span><span class="sxs-lookup"><span data-stu-id="ea5f5-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ea5f5-118">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ea5f5-118">Effect on the Runtime</span></span>  
 <span data-ttu-id="ea5f5-119">Erzwingt für alle Plattformaufrufe die Verwendung des nicht optimierten Pfads in die CLR.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ea5f5-120">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="ea5f5-120">Output</span></span>  
 <span data-ttu-id="ea5f5-121">Die MDA-Meldung enthält den Namen der Plattformaufrufmethode, die das Stapelungleichgewicht verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="ea5f5-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span>  <span data-ttu-id="ea5f5-122">Beispielmeldung eines Plattformaufrufs der `SampleMethod`-Methode: </span><span class="sxs-lookup"><span data-stu-id="ea5f5-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a><span data-ttu-id="ea5f5-123">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ea5f5-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea5f5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea5f5-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="ea5f5-125">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="ea5f5-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="ea5f5-126">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="ea5f5-126">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
