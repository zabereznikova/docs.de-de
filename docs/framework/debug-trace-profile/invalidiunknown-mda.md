---
title: invalidIUnknown-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fead50c42c0d686492459829f7629654c20a0f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582668"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="ab61a-102">invalidIUnknown-MDA</span><span class="sxs-lookup"><span data-stu-id="ab61a-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="ab61a-103">Der Assistent für verwaltetes Debuggen (Managed Debugging Assistant, MDA) `invalidIUnknown` wird aktiviert, wenn ein `IUnknown`-Zeiger aus dem nativen Code an verwalteten Code übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab61a-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="ab61a-104">Die Rückgabe einer Erfolgsmeldung durch `IUnknown` schlägt fehl, wenn die `IUnknown`-Schnittstelle abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="ab61a-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ab61a-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="ab61a-105">Symptoms</span></span>  
 <span data-ttu-id="ab61a-106">Beim Marshallen eines COM-Schnittstellenzeigers während des Marshallens von Argumenten tritt ein unerwarteter Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="ab61a-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ab61a-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="ab61a-107">Cause</span></span>  
 <span data-ttu-id="ab61a-108">Eine falsche `QueryInterface`-Implementierung der COM-Schnittstelle wurde an die CLR übergeben.</span><span class="sxs-lookup"><span data-stu-id="ab61a-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ab61a-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="ab61a-109">Resolution</span></span>  
 <span data-ttu-id="ab61a-110">Korrigieren Sie die `QueryInterface`-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ab61a-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ab61a-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ab61a-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="ab61a-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="ab61a-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ab61a-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="ab61a-113">Output</span></span>  
 <span data-ttu-id="ab61a-114">Die Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="ab61a-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ab61a-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ab61a-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab61a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab61a-116">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ab61a-117">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="ab61a-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ab61a-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="ab61a-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
