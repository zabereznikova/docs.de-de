---
title: invalidIUnknown-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff88f8bc544c95a4fe5149cd517d9157d5ac23c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="0c5bf-102">invalidIUnknown-MDA</span><span class="sxs-lookup"><span data-stu-id="0c5bf-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="0c5bf-103">Der Assistent für verwaltetes Debuggen (Managed Debugging Assistant, MDA) `invalidIUnknown` wird aktiviert, wenn ein `IUnknown`-Zeiger aus dem systemeigenen Code an verwalteten Code übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="0c5bf-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="0c5bf-104">Die Rückgabe einer Erfolgsmeldung durch `IUnknown` schlägt fehl, wenn die `IUnknown`-Schnittstelle abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="0c5bf-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0c5bf-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="0c5bf-105">Symptoms</span></span>  
 <span data-ttu-id="0c5bf-106">Beim Marshallen eines COM-Schnittstellenzeigers während des Marshallens von Argumenten tritt ein unerwarteter Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="0c5bf-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0c5bf-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="0c5bf-107">Cause</span></span>  
 <span data-ttu-id="0c5bf-108">Eine falsche `QueryInterface`-Implementierung der COM-Schnittstelle wurde an die CLR übergeben.</span><span class="sxs-lookup"><span data-stu-id="0c5bf-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0c5bf-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="0c5bf-109">Resolution</span></span>  
 <span data-ttu-id="0c5bf-110">Korrigieren Sie die `QueryInterface`-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="0c5bf-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0c5bf-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0c5bf-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="0c5bf-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="0c5bf-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0c5bf-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="0c5bf-113">Output</span></span>  
 <span data-ttu-id="0c5bf-114">Die Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="0c5bf-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0c5bf-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c5bf-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c5bf-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c5bf-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="0c5bf-117">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="0c5bf-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="0c5bf-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="0c5bf-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
