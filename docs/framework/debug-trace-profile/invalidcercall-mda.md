---
title: "invalidCERCall MDA | Microsoft Docs"
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
  - "invalid CER calls"
  - "InvalidCERCall MDA"
  - "MDAs (managed debugging assistants), CER calls"
  - "constrained execution regions"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# invalidCERCall MDA
Der `invalidCERCall`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn im Diagramm eines eingeschränkten Ausführungsbereichs \(Constrained Execution Region, CER\) ein Aufruf einer Methode erfolgt, die keinen oder einen zu schwachen Zuverlässigkeitsvertrag besitzt.  In einem schwachen Vertrag wird angegeben, dass der beschädigte Zustand im schlimmsten Fall einen größeren Gültigkeitsbereich aufweist als die Instanz, die an den Aufruf übergeben wurde, d. h., die <xref:System.AppDomain> oder der Prozesszustand können beschädigt werden, oder dass das Ergebnis bei einem Aufruf in einem CER nicht immer deterministisch berechnet werden kann.  
  
## Symptome  
 Unerwartete Ergebnisse beim Ausführen von Code in einem CER.  Es gibt keine spezifischen Symptome.  Es könnte sich um eine unerwartete <xref:System.OutOfMemoryException>, eine <xref:System.Threading.ThreadAbortException> oder eine andere Ausnahme handeln, die beim Aufruf der unzuverlässigen Methode auftritt, weil die Laufzeit diese nicht im Voraus vorbereitet hat oder sie beim Ausführen vor <xref:System.Threading.ThreadAbortException>\-Ausnahmen schützt.  Gefährlicher ist, dass eine Ausnahme, die von der Methode zur Laufzeit verursacht wird, zu einem instabilen Zustand der <xref:System.AppDomain> oder des Prozesses führen kann. Dies widerspricht dem Zweck eines CER.  Ein CER wird erstellt, um eine Beschädigung des Zustands zu vermeiden.  Die Symptome eines beschädigten Zustands sind anwendungsspezifisch, weil ein konsistenter Zustand in unterschiedlichen Anwendungen unterschiedlich definiert ist.  
  
## Ursache  
 Code in einer CER ruft eine Funktion auf, die kein <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> oder ein schwaches, für die Ausführung in einem CER ungeeignetes <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> besitzt.  
  
 In der syntaktischen Konstruktion eines schwachen Vertrags wird kein <xref:System.Runtime.ConstrainedExecution.Consistency>\-Enumerationswert oder ein <xref:System.Runtime.ConstrainedExecution.Consistency>\-Wert von <xref:System.Runtime.ConstrainedExecution.Consistency>, <xref:System.Runtime.ConstrainedExecution.Consistency> oder <xref:System.Runtime.ConstrainedExecution.Cer> angegeben.  Diese Bedingungen bedeuten, dass der aufgerufene Code möglicherweise dem Ziel des weiteren Codes in der CER widerspricht, einen konsistenten Zustand beizubehalten.  Code in CERs kann Fehler streng deterministisch behandeln. Dabei werden intern unveränderliche Werte beibehalten, die wichtig für die Anwendung sind, und es wird ermöglicht, dass die Anwendung bei vorübergehenden Fehlern wie Ausnahmen wegen ungenügendem Speicherplatz weiterhin ausgeführt wird.  
  
 Wenn dieser MDA aktiviert wird, bedeutet dies möglicherweise, dass die in der CER aufgerufene Methode auf eine Art fehlschlagen kann, die vom Aufrufer nicht erwartet wurde oder die <xref:System.AppDomain> bzw. den Prozesszustand beschädigt oder nicht mehr wiederherstellbar hinterlässt.  Natürlich ist es auch möglich, dass der aufgerufene Code ordnungsgemäß ausgeführt wird und das Problem einfach ein fehlender Vertrag ist.  Beim Verfassen von zuverlässigem Code spielen jedoch subtile Faktoren eine Rolle; das Fehlen eines Vertrags ist ein gutes Anzeichen, dass der Code nicht korrekt ausgeführt wird.  Die Verträge sind Hinweise, dass der Programmierer zuverlässigen Code produziert hat und außerdem zusichert, dass diese Vereinbarungen in künftigen Versionen des Codes nicht geändert werden.  Das heißt, die Verträge sind Absichtserklärungen und nicht nur Implementierungsdetails.  
  
 Da jede Methode mit einem schwachen oder gar keinem Vertrag potenziell auf viele unvorhersagbare Arten fehlschlagen kann, versucht die Laufzeit nicht, ihre eigenen unvorhersagbaren Fehlermöglichkeiten, die z. B. auf die träge JIT\-Kompilierung, das Füllen des Wörterbuchs mit Generika und Threadabbrüche zurückzuführen sind, von der Methode zu entfernen.  Wenn dieser MDA also aktiviert wird, bedeutet dies, dass die Laufzeit die aufgerufene Methode nicht in den definierten CER aufnimmt. Das Aufrufdiagramm wurde an diesem Knoten beendet, weil eine weitere Vorbereitung dieser Teilstruktur dazu beitragen würde, den potenziellen Fehler zu maskieren.  
  
## Lösung  
 Fügen Sie der Funktion einen gültigen Zuverlässigkeitsvertrag hinzu, oder vermeiden Sie diesen Funktionsaufruf.  
  
## Auswirkungen auf die Laufzeit  
 Ein Aufruf eines schwachen Vertrags aus einem CER könnte dazu führen, dass der CER den vorgesehenen Vorgang nicht abschließen kann.  Dies könnte dazu führen, dass die <xref:System.AppDomain> oder der Prozesszustand beschädigt wird.  
  
## Ausgabe  
 Im Folgenden finden Sie eine Beispielausgabe dieses MDA.  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)