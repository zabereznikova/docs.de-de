---
title: "virtualCERCall MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), CER calls"
  - "virtualCERCall MDA"
  - "virtual CER calls"
  - "constrained execution regions"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# virtualCERCall MDA
Der `virtualCERCall`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird als Warnung aktiviert. Er gibt an, dass sich eine Aufrufsite in einem Aufrufdiagramm eines eingeschränkten Ausführungsbereichs \(Constrained Execution Region, CER\) auf ein virtuelles Ziel bezieht, d. h. auf einen virtuellen Aufruf einer virtuellen Methode, die nicht final ist, oder einen Aufruf unter Verwendung einer Schnittstelle.  Die CLR \(Common Language Runtime\) kann die Zielmethode dieser Aufrufe nicht allein aus der Analyse der Intermediate Language und der Metadaten bestimmen.  Daher kann keine Aufrufstruktur als Teil des CER\-Diagramms vorbereitet werden, und Threadabbrüche in dieser Teilstruktur können nicht automatisch blockiert werden.  Dieser MDA warnt in den Fällen, in denen eine CER möglicherweise durch ausdrückliche Aufrufe der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>\-Methode erweitert werden muss, nachdem zur Laufzeit die zum Berechnen des Aufrufsziels benötigten Informationen ermittelt wurden.  
  
## Symptome  
 CERs, die nicht ausgeführt werden, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.  
  
## Ursache  
 Eine CER enthält einen Aufruf einer virtuellen Methode, die nicht automatisch vorbereitet werden kann.  
  
## Lösung  
 Rufen Sie für die virtuelle Methode <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> auf.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
  
```  
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    < VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
  
```  
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of   
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)