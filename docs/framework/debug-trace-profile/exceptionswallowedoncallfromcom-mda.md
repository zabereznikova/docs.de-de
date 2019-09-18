---
title: exceptionSwallowedOnCallFromCom-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a49bdce78c1445cd25de8755ded0f27a4902937
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052821"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="306ad-102">exceptionSwallowedOnCallFromCom-MDA</span><span class="sxs-lookup"><span data-stu-id="306ad-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="306ad-103">Der `exceptionSwallowedOnCallFromCOM`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Ausnahme durch Common-Language-Runtime-Code (CLR-Code) ausgelöst wird, der aus COM über eine Methode aufgerufen wurde, die nicht über einen unverwalteten HRESULT-Rückgabetyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="306ad-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="306ad-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="306ad-104">Symptoms</span></span>  
 <span data-ttu-id="306ad-105">Der Aufruf einer verwalteten Komponente aus COM gibt den Wert FALSE oder 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="306ad-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="306ad-106">Wenn die Methode stattdessen einen leeren Rückgabetyp hat, gibt es möglicherweise keinen Hinweis darauf, dass während der Ausführung der Methode eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="306ad-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="306ad-107">In diesem Fall wird die Ausnahme automatisch abgefangen und die Ausführung wird zum COM-Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="306ad-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="306ad-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="306ad-108">Cause</span></span>  
 <span data-ttu-id="306ad-109">Es wurde eine Ausnahme ausgelöst, aber es gibt keine gültige Möglichkeit, diese zu melden.</span><span class="sxs-lookup"><span data-stu-id="306ad-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="306ad-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="306ad-110">Resolution</span></span>  
 <span data-ttu-id="306ad-111">Dient nur Informationszwecken; weist nicht notwendigerweise auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="306ad-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="306ad-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="306ad-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="306ad-113">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="306ad-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="306ad-114">Es werden nur Daten über automatisch abgefangene Ausnahmen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="306ad-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="306ad-115">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="306ad-115">Output</span></span>  
 <span data-ttu-id="306ad-116">Informationsmeldung, die den Methodennamen, Typnamen und die Ausnahmemeldung enthält.</span><span class="sxs-lookup"><span data-stu-id="306ad-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="306ad-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="306ad-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="306ad-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="306ad-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="306ad-119">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="306ad-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="306ad-120">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="306ad-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
