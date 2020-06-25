---
title: JitCompilationStart-Assistent für verwaltetes Debuggen (MDA)
description: Der JitCompilationStart-MDA (Managed Debugging Assistant) meldet, wann der JIT-Compiler (Just-in-Time) mit dem Kompilieren einer .net-Funktion beginnt.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
ms.openlocfilehash: 13e20c1a940b7bfa777245ba35f3cc1b003d15b2
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325533"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="5588f-103">jitCompilationStart-MDA</span><span class="sxs-lookup"><span data-stu-id="5588f-103">jitCompilationStart MDA</span></span>

<span data-ttu-id="5588f-104">Der Assistent für verwaltetes Debuggen (MDA) `jitCompilationStart` berichtet, wann der JIT-Compiler mit der Kompilierung einer Funktion beginnt.</span><span class="sxs-lookup"><span data-stu-id="5588f-104">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5588f-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="5588f-105">Symptoms</span></span>  
 <span data-ttu-id="5588f-106">Die Workingsetgröße erhöht sich für ein Programm, das bereits im systemeigenen Bildformat vorliegt, da mscorjit.dll in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="5588f-106">The working set size increases for a program that's already in native image format, because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5588f-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="5588f-107">Cause</span></span>  
<span data-ttu-id="5588f-108">Nicht alle Assemblys, von denen das Programm abhängt, wurden im nativen Format generiert, oder eine Assembly ist nicht ordnungsgemäß registriert.</span><span class="sxs-lookup"><span data-stu-id="5588f-108">Not all the assemblies the program depends on have been generated into native format, or an assembly is not registered correctly.</span></span>  

## <a name="resolution"></a><span data-ttu-id="5588f-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="5588f-109">Resolution</span></span>  
 <span data-ttu-id="5588f-110">Wenn Sie diesen MDA aktivieren, können Sie identifizieren, welche Funktion JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="5588f-110">Enabling this MDA allows you to identify which function is being JIT-compiled.</span></span> <span data-ttu-id="5588f-111">Stellen Sie sicher, dass die Assembly, die die Funktion enthält, in das systemeigene Format generiert und ordnungsgemäß registriert wird.</span><span class="sxs-lookup"><span data-stu-id="5588f-111">Make sure that the assembly that contains the function is generated to native format and properly registered.</span></span>
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5588f-112">Auswirkung auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5588f-112">Effect on the runtime</span></span>  
 <span data-ttu-id="5588f-113">Dieser MDA protokolliert eine Meldung, kurz bevor eine Methode JIT-kompiliert wird. Deshalb hat die Aktivierung dieses MDA erhebliche Auswirkungen auf die Leistung.</span><span class="sxs-lookup"><span data-stu-id="5588f-113">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="5588f-114">Wenn eine Methode Inline ist, generiert dieser MDA keine separate Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5588f-114">If a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5588f-115">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="5588f-115">Output</span></span>  
 <span data-ttu-id="5588f-116">Das folgende Codebeispiel zeigt eine Beispielausgabe.</span><span class="sxs-lookup"><span data-stu-id="5588f-116">The following code sample shows sample output.</span></span> <span data-ttu-id="5588f-117">In diesem Fall zeigt die Ausgabe, dass die Methode "m" für die Klasse "ns2.co" im assemblytest JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="5588f-117">In this case, the output shows that, in assembly Test, the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="5588f-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5588f-118">Configuration</span></span>  
 <span data-ttu-id="5588f-119">Die folgende Konfigurationsdatei zeigt eine Reihe von Filtern, die filtern können, welche Methoden gemeldet werden, wenn sie zuerst JIT-kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="5588f-119">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="5588f-120">Sie können angeben, dass alle Methoden gemeldet werden, indem Sie den Wert des Name-Attributs auf festlegen \* .</span><span class="sxs-lookup"><span data-stu-id="5588f-120">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="5588f-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5588f-121">Example</span></span>  
 <span data-ttu-id="5588f-122">Das folgende Codebeispiel ist dazu vorgesehen, mit der vorangegangenen Konfigurationsdatei verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="5588f-122">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5588f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5588f-123">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="5588f-124">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="5588f-124">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5588f-125">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="5588f-125">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
