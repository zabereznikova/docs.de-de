---
title: dllMainReturnsFalse-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adc05ae9bd357c142ff09de069aff446b5ea60e8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052856"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="a87bf-102">dllMainReturnsFalse-MDA</span><span class="sxs-lookup"><span data-stu-id="a87bf-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="a87bf-103">Der Assistent für verwaltetes Debuggen `dllMainReturnsFalse` (Managed Debugging Assistant, MDA) wird aktiviert, wenn die verwaltete Funktion `DllMain` einer Benutzerassembly, die mit der Ursache DLL_PROCESS_ATTACH aufgerufen wurde, FALSE zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a87bf-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a87bf-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="a87bf-104">Symptoms</span></span>  
 <span data-ttu-id="a87bf-105">Die Funktion `DllMain` gab FALSE zurück, um anzuzeigen, dass sie nicht ordnungsgemäß ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a87bf-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="a87bf-106">Dies kann zu unbestimmten Problemen führen, da `DllMain`-Funktionen in der Regel wichtige Initialisierungscodes enthalten.</span><span class="sxs-lookup"><span data-stu-id="a87bf-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a87bf-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="a87bf-107">Cause</span></span>  
 <span data-ttu-id="a87bf-108">Die Funktion `DllMain` wird zur DLL-Initialisierung mit der Ursache DLL_PROCESS_ATTACH beim Laden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a87bf-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="a87bf-109">Wird FALSE zurückgegeben, trat bei der DLL-Initialisierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="a87bf-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a87bf-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="a87bf-110">Resolution</span></span>  
 <span data-ttu-id="a87bf-111">Analysieren Sie den Code der `DllMain`-Funktion für die fehlgeschlagene DLL, und identifizieren Sie die Ursache des Initialisierungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="a87bf-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a87bf-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a87bf-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="a87bf-113">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="a87bf-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="a87bf-114">Es werden nur Daten zum Rückgabewert für `DllMain` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a87bf-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a87bf-115">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="a87bf-115">Output</span></span>  
 <span data-ttu-id="a87bf-116">Eine Meldung, die anzeigt, dass eine mit der Ursache DLL_PROCESS_ATTACH aufgerufene `DllMain`-Funktion FALSE zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="a87bf-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="a87bf-117">Beachten Sie, dass dieser MDA nur aktiviert wird, wenn `DllMain` in verwalteten Code implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a87bf-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a87bf-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a87bf-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a87bf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a87bf-119">See also</span></span>

- [<span data-ttu-id="a87bf-120">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="a87bf-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
