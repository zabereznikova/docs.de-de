---
title: "moduloObjectHashcode MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), hashcode modulus"
  - "Modulo object hash code"
  - "moduloObjectHashcode MDA"
  - "hashcode modulus"
  - "MDAs (managed debugging assistants), hashcode modulus"
  - "GetHashCode method"
  - "modulus of hashcodes"
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# moduloObjectHashcode MDA
Der `moduloObjectHashcode`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) ändert das Verhalten der <xref:System.Object>\-Klasse, sodass eine Moduloberechnung mit dem von der <xref:System.Object.GetHashCode%2A>\-Methode zurückgegebenen Hashcode ausgeführt wird.  Das Standardmodulo für diesen MDA ist 1. Deshalb gibt <xref:System.Object.GetHashCode%2A> für alle Objekte 0 zurück.  
  
## Symptome  
 Nach dem Wechsel zu einer neuen Version der Common Language Runtime \(CLR\) wird ein Programm nicht mehr ordnungsgemäß ausgeführt:  
  
-   Das Programm ruft ein falsches Objekt aus einer <xref:System.Collections.Hashtable> ab.  
  
-   Die Enumerationsreihenfolge einer <xref:System.Collections.Hashtable> weist eine Änderung auf, die die Konsistenz des Programmcodes zerstört.  
  
-   Zwei Objekte, die bisher gleich waren, sind jetzt ungleich.  
  
-   Zwei Objekte, die bisher ungleich waren, sind jetzt gleich.  
  
## Ursache  
 Möglicherweise ruft das Programm das falsche Objekt aus einer <xref:System.Collections.Hashtable> ab, weil die in der Klasse vorhandene Implementierung der <xref:System.Object.Equals%2A>\-Methode für den Schlüssel für die <xref:System.Collections.Hashtable> die Gleichheit von Objekten prüft, indem die Ergebnisse eines Aufrufs der <xref:System.Object.GetHashCode%2A>\-Methode verglichen werden.  Hashcodes sollten nicht verwendet werden, um die Gleichheit von Objekten zu prüfen, weil zwei Objekte denselben Hashcode besitzen können, auch wenn deren jeweilige Felder unterschiedliche Werte aufweisen.  Solche Hashcodekonflikte sind zwar selten, kommen aber durchaus vor.  Bei einer Suche in einer <xref:System.Collections.Hashtable> führt dies dazu, dass zwei ungleiche Schlüssel scheinbar gleich sind, und es wird das falsche Objekt aus der <xref:System.Collections.Hashtable> zurückgegeben.  Aus Leistungsgründen ist es möglich, dass die Implementierung von <xref:System.Object.GetHashCode%2A> zwischen Versionen der Laufzeit geändert wird. Es kann deshalb möglicherweise vorkommen, dass eine Version konfliktfrei funktioniert, aber in nachfolgenden Versionen Konflikte auftreten.  Stellen Sie diesen MDA bereit, um zu testen, ob im Code bei einem Hashcodekonflikt Probleme auftreten.  Wenn dieser MDA bereitgestellt ist, gibt die <xref:System.Object.GetHashCode%2A>\-Methode 0 zurück. Dies führt dazu, dass alle Hashcodes miteinander in Konflikt stehen.  Dieser MDA sollte lediglich eine langsamere Ausführung des Programms zur Folge haben.  
  
 Die Enumerationsreihenfolge einer <xref:System.Collections.Hashtable> kann sich zwischen Versionen der Laufzeit ändern, wenn der zur Berechnung der Hashcodes für den Schlüssel verwendete Algorithmus geändert wird.  Um zu testen, ob das Programm von der Enumerationsreihenfolge von Schlüsseln oder Werten in einer Hashtabelle abhängt, können Sie diesen MDA bereitstellen.  
  
## Lösung  
 Verwenden Sie nie Hashcodes als Ersatz für die Objektidentität.  Implementieren Sie die Überschreibung der <xref:System.Object.Equals%2A?displayProperty=fullName>\-Methode, damit keine Hashcodes verglichen werden.  
  
 Verfassen Sie keinen Code, der von der Enumerationsreihenfolge von Schlüsseln oder Werten in Hashtabellen abhängt.  
  
## Auswirkungen auf die Laufzeit  
 Wenn dieser MDA bereitgestellt wird, werden Anwendungen langsamer ausgeführt.  Dieser MDA übernimmt den Hashcode, der zurückgegeben würde, und gibt stattdessen den Restwert einer Division des Hashcodes durch ein Modulo zurück.  
  
## Ausgabe  
 Dieser MDA produziert keine Ausgabe.  
  
## Konfiguration  
 Das `modulus`\-Attribut gibt das für den Hashcode verwendete Modulo an.  Der Standardwert ist 1.  
  
```  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)