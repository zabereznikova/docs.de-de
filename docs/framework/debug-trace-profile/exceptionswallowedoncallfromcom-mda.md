---
title: exceptionSwallowedOnCallFromCom-MDA
description: Überprüfen Sie den Assistenten für das Debuggen von exceptionschluchwedoncallfromcom in .net. Dieser MDA tritt auf, wenn eine Ausnahme ausgelöst wurde, aber es gibt keine gute Möglichkeit, Sie zu melden.
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
ms.openlocfilehash: 11daccb4d1e757bf2fae25858d706eee5921c509
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244352"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="eaea4-104">exceptionSwallowedOnCallFromCom-MDA</span><span class="sxs-lookup"><span data-stu-id="eaea4-104">exceptionSwallowedOnCallFromCom MDA</span></span>

<span data-ttu-id="eaea4-105">Der `exceptionSwallowedOnCallFromCOM`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Ausnahme durch Common-Language-Runtime-Code (CLR-Code) ausgelöst wird, der aus COM über eine Methode aufgerufen wurde, die nicht über einen unverwalteten HRESULT-Rückgabetyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="eaea4-105">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="eaea4-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="eaea4-106">Symptoms</span></span>  

 <span data-ttu-id="eaea4-107">Der Aufruf einer verwalteten Komponente aus COM gibt den Wert FALSE oder 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="eaea4-107">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="eaea4-108">Wenn die Methode stattdessen einen leeren Rückgabetyp hat, gibt es möglicherweise keinen Hinweis darauf, dass während der Ausführung der Methode eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="eaea4-108">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="eaea4-109">In diesem Fall wird die Ausnahme automatisch abgefangen und die Ausführung wird zum COM-Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eaea4-109">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="eaea4-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="eaea4-110">Cause</span></span>  

 <span data-ttu-id="eaea4-111">Es wurde eine Ausnahme ausgelöst, aber es gibt keine gültige Möglichkeit, diese zu melden.</span><span class="sxs-lookup"><span data-stu-id="eaea4-111">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="eaea4-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="eaea4-112">Resolution</span></span>  

 <span data-ttu-id="eaea4-113">Dient nur Informationszwecken; weist nicht notwendigerweise auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="eaea4-113">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="eaea4-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="eaea4-114">Effect on the Runtime</span></span>  

 <span data-ttu-id="eaea4-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="eaea4-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="eaea4-116">Es werden nur Daten über automatisch abgefangene Ausnahmen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="eaea4-116">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="eaea4-117">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="eaea4-117">Output</span></span>  

 <span data-ttu-id="eaea4-118">Informationsmeldung, die den Methodennamen, Typnamen und die Ausnahmemeldung enthält.</span><span class="sxs-lookup"><span data-stu-id="eaea4-118">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="eaea4-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="eaea4-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eaea4-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eaea4-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="eaea4-121">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="eaea4-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="eaea4-122">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="eaea4-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
