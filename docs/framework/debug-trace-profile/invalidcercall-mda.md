---
title: invalidCERCall-MDA
description: Überprüfen Sie den invalidcercallmda (Managed Debug Assistant), der aktiviert wird, wenn ein Ungültiger Aufruf innerhalb des CER-Diagramms (eingeschränkter Ausführungs Bereich) vorliegt.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid CER calls
- InvalidCERCall MDA
- MDAs (managed debugging assistants), CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
ms.openlocfilehash: 6f0d9d8e3059729098975080224999d0c0fac46e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272656"
---
# <a name="invalidcercall-mda"></a>invalidCERCall-MDA

Der `invalidCERCall`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein Aufruf innerhalb des Diagramms des eingeschränkten Ausführungsbereichs (CER) an eine Methode stattfindet, die keinen Zuverlässigkeitsvertrag oder einen übermäßig schwachen Vertrag besitzt. Ein schwacher Vertrag ist ein Vertrag, der deklariert, dass die schlimmste Zustandsbeschädigung einen größeren Umfang hat als die an den Aufruf übergebene Instanz. <xref:System.AppDomain> oder der Prozessstatus werden also möglicherweise beschädigt oder das Ergebnis bei einem Aufruf innerhalb eines CER kann nicht immer deterministisch berechnet werden.  
  
## <a name="symptoms"></a>Symptome  

 Unerwartete Ergebnisse beim Ausführen von Code in einem CER. Die Symptome sind nicht spezifisch. Bei diesen handelt es sich möglicherweise um unerwartete <xref:System.OutOfMemoryException>-, <xref:System.Threading.ThreadAbortException>- oder andere Ausnahmen beim Aufruf der unzuverlässigen Methode, da die Common Language Runtime sie nicht rechtzeitig vorbereitet hat oder vor <xref:System.Threading.ThreadAbortException>-Ausnahmen zur Laufzeit schützt. Eine stärkere Bedrohung ist die Tatsache, dass eine Ausnahme aus der Methode zur Laufzeit <xref:System.AppDomain> oder Prozesse in einem instabilen Zustand hinterlassen könnte, was im Gegensatz zum Ziel eines CER steht. Ein CER wird erstellt, um Beschädigungen des Zustands wie diese zu vermeiden. Die Symptome des beschädigten Zustands sind anwendungsspezifisch, da die Definition des konsistenten Zustands sich zwischen den Anwendungen unterscheidet.  
  
## <a name="cause"></a>Ursache  

 Code in einem CER ruft eine Funktion ohne <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> oder mit einem schwachen <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> auf, die nicht für die Ausführung in einem CER kompatibel ist.  
  
 In Bezug auf die Syntax der Zuverlässigkeitsverträge ist ein schwacher Vertrag ein Vertrag, der keinen <xref:System.Runtime.ConstrainedExecution.Consistency>-Enumerationswert oder einen <xref:System.Runtime.ConstrainedExecution.Consistency>-Wert von <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain> oder <xref:System.Runtime.ConstrainedExecution.Cer.None> angibt. Jede dieser Bedingungen gibt an, dass der aufgerufene Code die Anstrengungen des anderen Codes im CER beeinträchtigen kann, um einen konsistenten Zustand beizubehalten.  Durch CERs kann Code Fehler sehr deterministisch behandeln. Interne Varianten, die für die Anwendung von Bedeutung sind, werden beibehalten, und bei vorübergehenden Fehlern wie Out-of-Memory-Ausnahmen wird die Anwendung weiterhin ausgeführt.  
  
 Die Aktivierung dieses MDAs gibt an, dass diese Methode, die im CER aufgerufen wurde, in einer Weise fehlschlagen kann, die der Aufrufer nicht erwartet hat oder die bewirkt, dass <xref:System.AppDomain> oder der Prozesszustand beschädigt oder nicht wiederherstellbar sind. Natürlich kann der aufgerufene Code ordnungsgemäß ausgeführt werden, und das Problem ist ganz einfach nur ein fehlender Vertrag. Allerdings sind die Probleme beim Schreiben von zuverlässigem Code subtil, und das Fehlen eines Vertrags ist ein guter Indikator dafür, dass der Code möglicherweise nicht ordnungsgemäß ausgeführt wird. Die Verträge sind Indikatoren, die der Programmierer zuverlässig codiert hat, und diese Garantien werden zukünftige Versionen des Codes nicht ändern.  Die Verträge sind also Absichtserklärungen und nicht nur Implementierungsdetails.  
  
 Da jede Methode mit einem schwachen oder nicht vorhandenen Vertrag auf unvorhersehbare Weise fehlschlagen kann, versucht die Common Language Runtime, nicht die eigenen unvorhersehbaren Fehler der Methode zu entfernen, die beispielsweise durch verzögerte JIT-Kompilierung, Generics-Wörterbuchauffüllung oder Threadabbrüche eingeführt werden. Wenn dieser MDA aktiviert wird, bedeutet dies also, dass die Runtime die aufgerufene Methode nicht in den definierten CER einschließt. Das Aufrufdiagramm wurde an diesem Knoten beendet, da die Vorbereitung dieser Teilstruktur potenzielle Fehler maskieren würde.  
  
## <a name="resolution"></a>Lösung  

 Fügen Sie einen gültigen Zuverlässigkeitsvertrag zur Funktion hinzu, oder vermeiden Sie die Verwendung dieses Funktionsaufrufs.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  

 Der Aufruf eines schwachen Vertrags aus einem CER führt möglicherweise dazu, dass der CER seine Vorgänge nicht vollständig ausführen kann. Dies kann zu einer Beschädigung des <xref:System.AppDomain>-Prozesszustands führen.  
  
## <a name="output"></a>Ausgabe  

 Im Folgenden finden Sie eine Beispielausgabe dieses MDAs.  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
