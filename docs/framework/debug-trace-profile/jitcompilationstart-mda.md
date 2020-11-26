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
ms.openlocfilehash: 228226d90e70d296681e48ffe85dada8eb18209a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247368"
---
# <a name="jitcompilationstart-mda"></a>jitCompilationStart-MDA

Der Assistent für verwaltetes Debuggen (MDA) `jitCompilationStart` berichtet, wann der JIT-Compiler mit der Kompilierung einer Funktion beginnt.  
  
## <a name="symptoms"></a>Symptome  

 Die Workingsetgröße erhöht sich für ein Programm, das bereits im systemeigenen Bildformat vorliegt, da mscorjit.dll in den Prozess geladen wird.  
  
## <a name="cause"></a>Ursache  

Nicht alle Assemblys, von denen das Programm abhängt, wurden im nativen Format generiert, oder eine Assembly ist nicht ordnungsgemäß registriert.  

## <a name="resolution"></a>Lösung  

 Wenn Sie diesen MDA aktivieren, können Sie identifizieren, welche Funktion JIT-kompiliert wird. Stellen Sie sicher, dass die Assembly, die die Funktion enthält, in das systemeigene Format generiert und ordnungsgemäß registriert wird.
  
## <a name="effect-on-the-runtime"></a>Auswirkung auf die Laufzeit  

 Dieser MDA protokolliert eine Meldung, kurz bevor eine Methode JIT-kompiliert wird. Deshalb hat die Aktivierung dieses MDA erhebliche Auswirkungen auf die Leistung. Wenn eine Methode Inline ist, generiert dieser MDA keine separate Nachricht.  
  
## <a name="output"></a>Ausgabe  

 Das folgende Codebeispiel zeigt eine Beispielausgabe. In diesem Fall zeigt die Ausgabe, dass die Methode "m" für die Klasse "ns2.co" im assemblytest JIT-kompiliert wurde.  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a>Konfiguration  

 Die folgende Konfigurationsdatei zeigt eine Reihe von Filtern, die filtern können, welche Methoden gemeldet werden, wenn sie zuerst JIT-kompiliert werden. Sie können angeben, dass alle Methoden gemeldet werden, indem Sie den Wert des Name-Attributs auf festlegen \* .  
  
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
  
## <a name="example"></a>Beispiel  

 Das folgende Codebeispiel ist dazu vorgesehen, mit der vorangegangenen Konfigurationsdatei verwendet zu werden.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
