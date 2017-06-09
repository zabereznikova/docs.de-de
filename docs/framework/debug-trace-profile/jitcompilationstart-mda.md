---
title: "jitCompilationStart MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "JIT compilation"
  - "MDAs (managed debugging assistants), JIT compilation"
  - "JitCompilationStart MDA"
  - "managed debugging assistants (MDAs), JIT compilation"
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# jitCompilationStart MDA
Der `jitCompilationStart`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird für die Berichterstellung aktiviert, wenn der Just\-In\-Time\-Compiler \(JIT\) mit dem Kompilieren einer Funktion beginnt.  
  
## Symptome  
 Die Größe des WorkingSets vergrößert sich für ein Programm, das bereits im Format für das systemeigene Abbild vorliegt, da mscorjit.dll in den Prozess geladen wird.  
  
## Ursache  
 Nicht alle Assemblys, von denen das Programm abhängt, wurden im systemeigenen Format generiert, oder sie wurden nicht ordnungsgemäß registriert.  
  
## Lösung  
 Durch das Aktivieren dieses MDA können Sie ermitteln, welche Funktion gerade vom JIT\-Compiler verarbeitet wird.  Ermitteln Sie, ob die Assembly, die diese Funktion enthält, im systemeigenen Format generiert und ordnungsgemäß registriert wurde.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA protokolliert eine Meldung, bevor eine Methode vom JIT\-Compiler verarbeitet wird. Das Aktivieren dieses MDA wirkt sich somit erheblich auf die Leistung aus.  Beachten Sie, dass dieser MDA keine separate Meldung generiert, wenn es sich um eine Inlinemethode handelt.  
  
## Ausgabe  
 Das folgende Codebeispiel zeigt eine Beispielausgabe.  In vorliegenden Fall geht aus der Ausgabe hervor, dass in Assembly Test die Methode "m" für die Klasse "ns2.CO" vom JIT\-Compiler kompiliert wurde.  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## Konfiguration  
 Die folgende Konfigurationsdatei zeigt eine Reihe von Filtern, die angewendet werden können, um die Methoden einzugrenzen, deren erstmalige Verarbeitung durch den JIT\-Compiler gemeldet werden soll.  Sie können angeben, dass Meldungen zu allen Methoden erstellt werden, indem Sie als Wert des Namensattributs \* festlegen.  
  
```  
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
  
## Beispiel  
 Das folgende Codebeispiel bezieht sich auf die vorangehende Konfigurationsdatei.  
  
```  
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
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)