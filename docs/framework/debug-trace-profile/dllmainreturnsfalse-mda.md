---
title: dllMainReturnsFalse-MDA
description: Informieren Sie sich über den DllMainReturnsFalse-Assistenten für verwaltetes Debuggen in .net. Dieser MDA wird aktiviert, wenn die DLL-Initialisierung fehlgeschlagen ist.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 83f38c4918c1354477627b70a62e60cbdc7de275
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273515"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="018b6-104">dllMainReturnsFalse-MDA</span><span class="sxs-lookup"><span data-stu-id="018b6-104">dllMainReturnsFalse MDA</span></span>

<span data-ttu-id="018b6-105">Der Assistent für verwaltetes Debuggen `dllMainReturnsFalse` (Managed Debugging Assistant, MDA) wird aktiviert, wenn die verwaltete Funktion `DllMain` einer Benutzerassembly, die mit der Ursache DLL_PROCESS_ATTACH aufgerufen wurde, FALSE zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="018b6-105">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="018b6-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="018b6-106">Symptoms</span></span>  

 <span data-ttu-id="018b6-107">Die Funktion `DllMain` gab FALSE zurück, um anzuzeigen, dass sie nicht ordnungsgemäß ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="018b6-107">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="018b6-108">Dies kann zu unbestimmten Problemen führen, da `DllMain`-Funktionen in der Regel wichtige Initialisierungscodes enthalten.</span><span class="sxs-lookup"><span data-stu-id="018b6-108">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="018b6-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="018b6-109">Cause</span></span>  

 <span data-ttu-id="018b6-110">Die Funktion `DllMain` wird zur DLL-Initialisierung mit der Ursache DLL_PROCESS_ATTACH beim Laden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="018b6-110">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="018b6-111">Wird FALSE zurückgegeben, trat bei der DLL-Initialisierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="018b6-111">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="018b6-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="018b6-112">Resolution</span></span>  

 <span data-ttu-id="018b6-113">Analysieren Sie den Code der `DllMain`-Funktion für die fehlgeschlagene DLL, und identifizieren Sie die Ursache des Initialisierungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="018b6-113">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="018b6-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="018b6-114">Effect on the Runtime</span></span>  

 <span data-ttu-id="018b6-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="018b6-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="018b6-116">Es werden nur Daten zum Rückgabewert für `DllMain` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="018b6-116">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="018b6-117">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="018b6-117">Output</span></span>  

 <span data-ttu-id="018b6-118">Eine Meldung, die anzeigt, dass eine mit der Ursache DLL_PROCESS_ATTACH aufgerufene `DllMain`-Funktion FALSE zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="018b6-118">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="018b6-119">Beachten Sie, dass dieser MDA nur aktiviert wird, wenn `DllMain` in verwalteten Code implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="018b6-119">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="018b6-120">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="018b6-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="018b6-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="018b6-121">See also</span></span>

- [<span data-ttu-id="018b6-122">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="018b6-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
