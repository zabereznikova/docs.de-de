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
ms.openlocfilehash: 35560b966d5fba60ac35b2eb1e559e196fc868f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223354"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="7f2b6-102">invalidIUnknown-MDA</span><span class="sxs-lookup"><span data-stu-id="7f2b6-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="7f2b6-103">Der Assistent für verwaltetes Debuggen (Managed Debugging Assistant, MDA) `invalidIUnknown` wird aktiviert, wenn ein `IUnknown`-Zeiger aus dem systemeigenen Code an verwalteten Code übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="7f2b6-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="7f2b6-104">Die Rückgabe einer Erfolgsmeldung durch `IUnknown` schlägt fehl, wenn die `IUnknown`-Schnittstelle abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="7f2b6-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7f2b6-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="7f2b6-105">Symptoms</span></span>  
 <span data-ttu-id="7f2b6-106">Beim Marshallen eines COM-Schnittstellenzeigers während des Marshallens von Argumenten tritt ein unerwarteter Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="7f2b6-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7f2b6-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="7f2b6-107">Cause</span></span>  
 <span data-ttu-id="7f2b6-108">Eine falsche `QueryInterface`-Implementierung der COM-Schnittstelle wurde an die CLR übergeben.</span><span class="sxs-lookup"><span data-stu-id="7f2b6-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7f2b6-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="7f2b6-109">Resolution</span></span>  
 <span data-ttu-id="7f2b6-110">Korrigieren Sie die `QueryInterface`-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="7f2b6-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7f2b6-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7f2b6-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="7f2b6-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="7f2b6-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7f2b6-113">Output</span><span class="sxs-lookup"><span data-stu-id="7f2b6-113">Output</span></span>  
 <span data-ttu-id="7f2b6-114">Die Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="7f2b6-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7f2b6-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7f2b6-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f2b6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f2b6-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="7f2b6-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="7f2b6-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7f2b6-118">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="7f2b6-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
