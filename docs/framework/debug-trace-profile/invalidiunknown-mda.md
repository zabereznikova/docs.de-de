---
title: invalidIUnknown-MDA
description: Überprüfen Sie den invalidIUnknown-MDA (Managed Debug Assistant), der aktiviert wird, wenn ein ungültiger IUnknown-Zeiger von System eigenem Code an verwalteten Code übergeben wird.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 65d704463ed746390ff1710b590bf080013bf53d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051726"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="2f3d1-103">invalidIUnknown-MDA</span><span class="sxs-lookup"><span data-stu-id="2f3d1-103">invalidIUnknown MDA</span></span>
<span data-ttu-id="2f3d1-104">Der Assistent für verwaltetes Debuggen (Managed Debugging Assistant, MDA) `invalidIUnknown` wird aktiviert, wenn ein `IUnknown`-Zeiger aus dem systemeigenen Code an verwalteten Code übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="2f3d1-104">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="2f3d1-105">Die Rückgabe einer Erfolgsmeldung durch `IUnknown` schlägt fehl, wenn die `IUnknown`-Schnittstelle abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="2f3d1-105">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2f3d1-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="2f3d1-106">Symptoms</span></span>  
 <span data-ttu-id="2f3d1-107">Beim Marshallen eines COM-Schnittstellenzeigers während des Marshallens von Argumenten tritt ein unerwarteter Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="2f3d1-107">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2f3d1-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="2f3d1-108">Cause</span></span>  
 <span data-ttu-id="2f3d1-109">Eine falsche `QueryInterface`-Implementierung der COM-Schnittstelle wurde an die CLR übergeben.</span><span class="sxs-lookup"><span data-stu-id="2f3d1-109">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2f3d1-110">Lösung</span><span class="sxs-lookup"><span data-stu-id="2f3d1-110">Resolution</span></span>  
 <span data-ttu-id="2f3d1-111">Korrigieren Sie die `QueryInterface`-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="2f3d1-111">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2f3d1-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2f3d1-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="2f3d1-113">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="2f3d1-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2f3d1-114">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="2f3d1-114">Output</span></span>  
 <span data-ttu-id="2f3d1-115">Die Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="2f3d1-115">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="2f3d1-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2f3d1-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f3d1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f3d1-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="2f3d1-118">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="2f3d1-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2f3d1-119">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="2f3d1-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
