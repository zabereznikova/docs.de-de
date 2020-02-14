---
title: OpenGenericCERCall-MDA
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
ms.openlocfilehash: de1735103314dfedbabe27623f579ce2c1e728af
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217267"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="9d541-102">OpenGenericCERCall-MDA</span><span class="sxs-lookup"><span data-stu-id="9d541-102">openGenericCERCall MDA</span></span>

<span data-ttu-id="9d541-103">Der `openGenericCERCall`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, um zu warnen, dass ein CER-Diagramm mit generischen Typvariablen in der Stammmethode zum Zeitpunkt der JIT-Kompilierung oder der nativen Imagegenerierung verarbeitet wird und mindestens eine der generischen Typvariablen ein Objektverweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="9d541-103">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>

## <a name="symptoms"></a><span data-ttu-id="9d541-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="9d541-104">Symptoms</span></span>

<span data-ttu-id="9d541-105">CER-Code, der nicht ausgeführt wird, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="9d541-105">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>

## <a name="cause"></a><span data-ttu-id="9d541-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="9d541-106">Cause</span></span>

<span data-ttu-id="9d541-107">Zum Zeitpunkt der JIT-Kompilierung ist eine Instanziierung, die einen Objektverweistyp enthält, nur repräsentativ, da der resultierende Code freigegeben wird und jede Variable des Objektverweistyps ggf. ein beliebiger Objektverweistyp sein kann.</span><span class="sxs-lookup"><span data-stu-id="9d541-107">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="9d541-108">Dies kann die Vorbereitung einiger Laufzeitressourcen im Voraus verhindern.</span><span class="sxs-lookup"><span data-stu-id="9d541-108">This can prevent the preparation of some run-time resources ahead of time.</span></span>

<span data-ttu-id="9d541-109">Methoden mit generischen Typvariablen können Ressourcen im Hintergrund verzögert zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9d541-109">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="9d541-110">Diese werden als generische Wörterbucheinträge bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9d541-110">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="9d541-111">Beispielsweise muss für die-Anweisung `List<T> list = new List<T>();`, bei der `T` eine generische Typvariable ist, die Laufzeit nachschlagen und möglicherweise die genaue Instanziierung zur Laufzeit erstellen, z. b. `List<Object>, List<String>`usw.</span><span class="sxs-lookup"><span data-stu-id="9d541-111">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`, and so forth.</span></span> <span data-ttu-id="9d541-112">Dies kann aus einer Vielzahl von Gründen fehlschlagen, die außerhalb der Kontrolle des Entwicklers liegen, z.B. fehlendem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="9d541-112">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>

<span data-ttu-id="9d541-113">Dieser MDA sollte nur zum Zeitpunkt der JIT-Kompilierung aktiviert werden, und nicht bei einer genauen Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="9d541-113">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>

<span data-ttu-id="9d541-114">Wenn dieser MDA aktiviert wird, ist es wahrscheinlich, dass die CERs für fehlerhafte Instanziierungen nicht funktionsfähig sind.</span><span class="sxs-lookup"><span data-stu-id="9d541-114">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="9d541-115">Die Common Language Runtime hat in der Tat nicht versucht, einen CER unter den Umständen zu implementieren, die zur Aktivierung der MDA geführt haben.</span><span class="sxs-lookup"><span data-stu-id="9d541-115">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="9d541-116">Wenn der Entwickler eine freigegebene Instanziierung des CER verwendet, dann werden JIT-Kompilierungsfehler, Fehler beim Laden von Generics oder Threadabbrüche innerhalb des Bereichs des vorgesehenen CERs nicht abgefangen.</span><span class="sxs-lookup"><span data-stu-id="9d541-116">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>

## <a name="resolution"></a><span data-ttu-id="9d541-117">Lösung</span><span class="sxs-lookup"><span data-stu-id="9d541-117">Resolution</span></span>

<span data-ttu-id="9d541-118">Verwenden Sie keine generischen Typvariablen, die Objektverweistypen für Methoden sind, die möglicherweise eine CER enthalten.</span><span class="sxs-lookup"><span data-stu-id="9d541-118">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="9d541-119">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9d541-119">Effect on the Runtime</span></span>

<span data-ttu-id="9d541-120">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="9d541-120">This MDA has no effect on the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="9d541-121">Output</span><span class="sxs-lookup"><span data-stu-id="9d541-121">Output</span></span>

<span data-ttu-id="9d541-122">Im folgenden finden Sie ein Beispiel für die Ausgabe dieses MDA:</span><span class="sxs-lookup"><span data-stu-id="9d541-122">The following is a sample of output from this MDA:</span></span>
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution. 
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a><span data-ttu-id="9d541-123">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9d541-123">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a><span data-ttu-id="9d541-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d541-124">Example</span></span>

<span data-ttu-id="9d541-125">Der CER-Code wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9d541-125">The CER code is not executed.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9d541-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d541-126">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [<span data-ttu-id="9d541-127">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="9d541-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
