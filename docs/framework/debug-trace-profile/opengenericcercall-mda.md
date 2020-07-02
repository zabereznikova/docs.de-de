---
title: OpenGenericCERCall-MDA
description: Weitere Informationen finden Sie unter opengenericcercallverwalteter debugassistent, der aktiviert werden kann, wenn der CER-Code nicht ausgeführt wird, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: 4df33b0cdf9759edec47f02b3feb671d03284ec8
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803936"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="bc1da-103">OpenGenericCERCall-MDA</span><span class="sxs-lookup"><span data-stu-id="bc1da-103">openGenericCERCall MDA</span></span>

<span data-ttu-id="bc1da-104">Der `openGenericCERCall`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, um zu warnen, dass ein CER-Diagramm mit generischen Typvariablen in der Stammmethode zum Zeitpunkt der JIT-Kompilierung oder der nativen Imagegenerierung verarbeitet wird und mindestens eine der generischen Typvariablen ein Objektverweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="bc1da-104">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>

## <a name="symptoms"></a><span data-ttu-id="bc1da-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="bc1da-105">Symptoms</span></span>

<span data-ttu-id="bc1da-106">CER-Code, der nicht ausgeführt wird, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="bc1da-106">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>

## <a name="cause"></a><span data-ttu-id="bc1da-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="bc1da-107">Cause</span></span>

<span data-ttu-id="bc1da-108">Zum Zeitpunkt der JIT-Kompilierung ist eine Instanziierung, die einen Objektverweistyp enthält, nur repräsentativ, da der resultierende Code freigegeben wird und jede Variable des Objektverweistyps ggf. ein beliebiger Objektverweistyp sein kann.</span><span class="sxs-lookup"><span data-stu-id="bc1da-108">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="bc1da-109">Dies kann die Vorbereitung einiger Laufzeitressourcen im Voraus verhindern.</span><span class="sxs-lookup"><span data-stu-id="bc1da-109">This can prevent the preparation of some run-time resources ahead of time.</span></span>

<span data-ttu-id="bc1da-110">Methoden mit generischen Typvariablen können Ressourcen im Hintergrund verzögert zuordnen.</span><span class="sxs-lookup"><span data-stu-id="bc1da-110">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="bc1da-111">Diese werden als generische Wörterbucheinträge bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bc1da-111">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="bc1da-112">Beispielsweise muss für die Anweisung, `List<T> list = new List<T>();` bei der `T` es sich um eine generische Typvariable handelt, die Laufzeit nachschlagen und möglicherweise die genaue Instanziierung zur Laufzeit erstellen, z `List<Object>, List<String>` . b., usw.</span><span class="sxs-lookup"><span data-stu-id="bc1da-112">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`, and so forth.</span></span> <span data-ttu-id="bc1da-113">Dies kann aus einer Vielzahl von Gründen fehlschlagen, die außerhalb der Kontrolle des Entwicklers liegen, z.B. fehlendem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="bc1da-113">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>

<span data-ttu-id="bc1da-114">Dieser MDA sollte nur zum Zeitpunkt der JIT-Kompilierung aktiviert werden, und nicht bei einer genauen Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="bc1da-114">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>

<span data-ttu-id="bc1da-115">Wenn dieser MDA aktiviert wird, ist es wahrscheinlich, dass die CERs für fehlerhafte Instanziierungen nicht funktionsfähig sind.</span><span class="sxs-lookup"><span data-stu-id="bc1da-115">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="bc1da-116">Die Common Language Runtime hat in der Tat nicht versucht, einen CER unter den Umständen zu implementieren, die zur Aktivierung der MDA geführt haben.</span><span class="sxs-lookup"><span data-stu-id="bc1da-116">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="bc1da-117">Wenn der Entwickler eine freigegebene Instanziierung des CER verwendet, dann werden JIT-Kompilierungsfehler, Fehler beim Laden von Generics oder Threadabbrüche innerhalb des Bereichs des vorgesehenen CERs nicht abgefangen.</span><span class="sxs-lookup"><span data-stu-id="bc1da-117">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>

## <a name="resolution"></a><span data-ttu-id="bc1da-118">Lösung</span><span class="sxs-lookup"><span data-stu-id="bc1da-118">Resolution</span></span>

<span data-ttu-id="bc1da-119">Verwenden Sie keine generischen Typvariablen, die Objektverweistypen für Methoden sind, die möglicherweise eine CER enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc1da-119">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="bc1da-120">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bc1da-120">Effect on the Runtime</span></span>

<span data-ttu-id="bc1da-121">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="bc1da-121">This MDA has no effect on the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="bc1da-122">Output</span><span class="sxs-lookup"><span data-stu-id="bc1da-122">Output</span></span>

<span data-ttu-id="bc1da-123">Im folgenden finden Sie ein Beispiel für die Ausgabe dieses MDA:</span><span class="sxs-lookup"><span data-stu-id="bc1da-123">The following is a sample of output from this MDA:</span></span>
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution.
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a><span data-ttu-id="bc1da-124">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bc1da-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a><span data-ttu-id="bc1da-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc1da-125">Example</span></span>

<span data-ttu-id="bc1da-126">Der CER-Code wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bc1da-126">The CER code is not executed.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="bc1da-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc1da-127">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [<span data-ttu-id="bc1da-128">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="bc1da-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
