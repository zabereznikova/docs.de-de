---
title: "openGenericCERCall MDA | Microsoft Docs"
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
  - "open generic CER calls"
  - "constrained execution regions"
  - "openGenericCERCall MDA"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
  - "generics [.NET Framework], open generic CER calls"
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# openGenericCERCall MDA
Der `openGenericCERCall`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, um davor zu warnen, dass ein Diagramm eines eingeschränkten Ausführungsbereichs \(Constrained Execution Region, CER\) mit generischen Typvariablen in der Stammmethode bei der JIT \(Just\-in\-Time\)\-Kompilierung oder der Generierung systemeigener Abbilder verarbeitet wird und mindestens eine der generischen Typvariablen ein ObjektReferenztyp ist.  
  
## Symptome  
 CER\-Code wird nicht ausgeführt, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.  
  
## Ursache  
 Bei der JIT\-Kompilierung ist eine Instanziierung mit einem ObjektReferenztyp nur repräsentativ, weil der resultierende Code gemeinsam genutzt wird, und jede der ObjektReferenztyp\-Variablen kann ein beliebiger ObjektReferenztyp sein.  Dies kann die Vorbereitung einiger Laufzeitressourcen im Voraus verhindern.  
  
 Insbesondere gilt, dass die Zuordnung von Ressourcen durch Methoden mit generischen Typvariablen träge im Hintergrund erfolgen kann.  Diese werden als generische Wörterbucheinträge bezeichnet.  So muss die Laufzeit beispielsweise für die Anweisung `List<T> list = new List<T>();` \(wobei `T` eine generische Typvariable ist\) die genaue Instanziierung zur Laufzeit suchen und möglicherweise erstellen, z. B. `List<Object>, List<String>`, ``  usw.  Dies kann aus verschiedenen Gründen fehlschlagen, die bei der Entwicklung nicht beeinflusst werden können, z. B., weil nicht genügend Speicherplatz verfügbar ist.  
  
 Dieser MDA sollte nur bei der JIT\-Kompilierung aktiviert werden, nicht jedoch, wenn eine genaue Instanziierung vorhanden ist.  
  
 Wenn dieser MDA aktiviert wird, werden Sie als Symptom wahrscheinlich bemerken, dass CERs nicht funktionieren, weil fehlerhafte Instanziierungen vorliegen.  Die Laufzeit hat unter den Bedingungen, aufgrund derer der MDA aktiviert wurde, tatsächlich nicht versucht, eine CER zu implementieren.  Wenn ein Entwickler also eine gemeinsam genutzte Instanziierung der CER verwendet, werden Fehler bei der JIT\-Kompilierung, Fehler beim Laden von generischen Typen und Threadabbrüche im Bereich der vorgesehenen CER nicht abgefangen.  
  
## Lösung  
 Verwenden Sie keine generischen Typvariablen vom ObjektReferenztyp in Methoden, die möglicherweise eine CER enthalten.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Im Folgenden finden Sie ein Beispiel für Ausgabe dieses MDA.  
  
 `Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.`  
  
 `The caller must ensure this method is prepared explicitly at run time prior to execution.`  
  
 `method name="GenericMethodWithCer"`  
  
 `declaringType name="OpenGenericCERCall"`  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <openGenericCERCall/>  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 Der CER\-Code wird nicht ausgeführt.  
  
```  
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
  
## Siehe auch  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)