---
title: moduloObjectHashcode-MDA
description: Überprüfen Sie den moduloObjectHashcode Managed Debug Assistant (MDA), der die Objektklasse ändert, um einen Restwert für ein GetHashCode-Methoden Ergebnis zu erhalten.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
ms.openlocfilehash: a929ec2b9196f1f6cad0528fdf7323839a86fa55
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052064"
---
# <a name="moduloobjecthashcode-mda"></a>moduloObjectHashcode-MDA
Der `moduloObjectHashcode`-MDA (Assistent für verwaltetes Debuggen) ändert das Verhalten der <xref:System.Object>-Klasse, um einen Modulo-Vorgang auf dem Hashcode auszuführen, der von der <xref:System.Object.GetHashCode%2A>-Methode zurückgegeben wurde. Der Standard-Modulo dieses MDA beträgt 1, wodurch <xref:System.Object.GetHashCode%2A> für alle Objekte 0 zurückgibt.  
  
## <a name="symptoms"></a>Symptome  
 Nachdem das Programm auf eine neue Version der Common Language Runtime (CLR) verschoben wurde, wird es nicht mehr ordnungsgemäß ausgeführt:  
  
- Das Programm erhält das falsche Objekt aus einem <xref:System.Collections.Hashtable>.  
  
- Die Reihenfolge der Enumeration aus einem <xref:System.Collections.Hashtable> hat eine Änderung, die die Anwendung unterbricht.  
  
- Zwei Objekte, die gleich waren, sind nicht mehr gleich.  
  
- Zwei Objekte, die nicht gleich waren, sind nun gleich.  
  
## <a name="cause"></a>Ursache  
 Ihr Programm erhält möglicherweise das falsche Objekt aus einer <xref:System.Collections.Hashtable>, da die Implementierung der <xref:System.Object.Equals%2A>-Methode der Klasse für den Schlüssel in der <xref:System.Collections.Hashtable> auf Objektgleichheit überprüft, indem die Ergebnisse des Aufrufs der <xref:System.Object.GetHashCode%2A>-Methode verglichen werden. Hashcodes sollten nicht verwendet werden, um auf Objektgleichheit zu testen, da zwei Objekte denselben Hashcode haben können, auch wenn ihre jeweiligen Felder unterschiedliche Werte aufweisen. Diese Hashcodekonflikte sind in der Praxis zwar selten, aber sie kommen vor. Als Konsequenz gibt es zwei Schlüssel in einem <xref:System.Collections.Hashtable>-Lookup, die nicht gleich sind, aber gleich zu sein scheinen, und das falsche Objekt wird aus der <xref:System.Collections.Hashtable> zurückgegeben. Zur Verbesserung der Leistung kann sich die Implementierung der <xref:System.Object.GetHashCode%2A> zwischen Laufzeitversionen unterscheiden, damit Konflikte, die auf einer Version nicht auftreten, in nachfolgenden Versionen auftreten können. Aktivieren Sie diesen MDA, um zu überprüfen, ob der Code Fehler aufweist, wenn Hashcodes in Konflikt stehen. Wenn dieser MDA aktiviert ist, gibt die <xref:System.Object.GetHashCode%2A>-Methode 0 (null) zurück, was zu einer Kollision aller Hashcodes führt. Die einzige Auswirkung, die die Aktivierung dieses MDAs auf Ihr Programm haben sollte, ist die, dass das Programm langsamer ausgeführt wird.  
  
 Die Reihenfolge der Enumeration aus einem <xref:System.Collections.Hashtable> kann sich möglicherweise von einer Laufzeitversion zur anderen ändern, wenn der Algorithmus für die Berechnung der Hashcodes für die Schlüsseländerung verwendet wird. Sie können diesen MDA aktivieren, um zu überprüfen, ob das Programm eine Abhängigkeit von der Reihenfolge der Enumeration der Schlüssel oder Werte aus einer Hashtabelle erstellt hat.  
  
## <a name="resolution"></a>Lösung  
 Verwenden Sie niemals Hashcodes als Ersatz für die Objektidentität. Implementieren Sie die Außerkraftsetzung der <xref:System.Object.Equals%2A?displayProperty=nameWithType>-Methode, um Hashcodes nicht zu vergleichen.  
  
 Erstellen Sie keine Abhängigkeiten von der Reihenfolge der Schlüsselenumerationen oder Werte in Hashtabellen.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Anwendungen werden langsamer ausgeführt, wenn dieser MDA aktiviert ist. Dieser MDA übernimmt lediglich den Hashcode, der zurückgegeben wurde und gibt stattdessen den Rest nach dem Dividieren durch einen Modulo zurück.  
  
## <a name="output"></a>Output  
 Es gibt keine Ausgabe für diesen MDA.  
  
## <a name="configuration"></a>Konfiguration  
 Das `modulus`-Attribut gibt den Modulo an, der auf dem Hashcode verwendet wird. Der Standardwert ist 1.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
