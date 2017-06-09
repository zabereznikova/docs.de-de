---
title: "Ausw&#228;hlen zwischen Klassen und Strukturen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Strukturen"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Klassen"
  - "[Strukturen [.NET Framework], im Vergleich zu Klassen"
  - "[Klassen [.NET Framework], Entwurfsrichtlinien"
  - "Typentwurfsrichtlinien Strukturen"
  - "[Strukturen [.NET Framework], Entwurfsrichtlinien"
  - "[Klassen [.NET Framework], im Vergleich zu Strukturen"
  - "Typentwurfsrichtlinien Klassen"
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Ausw&#228;hlen zwischen Klassen und Strukturen
Eine der grundlegenden Entscheidungen, die jedes Framework\-Designer zeigt, ist an, ob einen Typ als eine Klasse \(Referenztyp\) oder als eine Struktur \(Werttyp\) entworfen. Gute Kenntnisse der Unterschiede im Verhalten von Verweistypen und Werttypen ist entscheidend für die Auswahl dieser Option.  
  
 Der erste Unterschied zwischen Verweistypen und Werttypen, die wir in Betracht ziehen, ist, dass Verweistypen auf dem Heap reserviert und die Garbage Collection, Werttypen werden entweder auf dem Stapel oder Inline in Typen mit zugeordnet und freigegeben, wenn der Stapel abgearbeitet wird oder wenn ihrem enthaltenden Typ freigegeben wird. Daher werden speicherzuordnungen und Aufhebungen von Werttypen im Allgemeinen günstiger als speicherzuordnungen und Aufhebungen von Verweistypen sind.  
  
 Als Nächstes Arrays von Verweisdaten sind Out\-of\-Line, d. h. die Arrayelemente nur die Verweise auf Instanzen des Referenztyps auf dem Heap zugeordnet. Wert Typ Arrays sind Inline, d. h., die Elemente des Arrays die eigentlichen Instanzen des Werttyps zugeordnet. Daher sind speicherzuordnungen und Aufhebungen von Wert Typ Arrays wesentlich günstiger als speicherzuordnungen und Aufhebungen von Verweis Typ Arrays. In den meisten Fällen weisen Wert Typ Arrays darüber hinaus eine viel bessere Positionierung von verweisen.  
  
 Nächste Unterschied bezieht sich auf die Speicherverwendung. Werttypen erste geschachtelt beim Umwandeln in einen Verweistyp oder eine der Schnittstellen, die sie implementieren. Sie erhalten nicht geschachtelten Wenn zurück, der Werttyp umgewandelt. Da werden Objekte, die auf dem Heap reserviert werden und Garbage Collection, viel Boxing und unboxing können sich negativ auf den Heap der Garbage Collection und letztlich die Leistung der Anwendung verfügen.  Im Gegensatz dazu tritt kein solcher Boxing Verweistypen umgewandelt werden.  
  
 Kopieren Sie als Nächstes Verweis Zuweisung den Verweis, während der Zuweisung Wert kopieren Sie den gesamten Wert. Aus diesem Grund sind Zuweisungen von großen Verweistypen günstiger als Zuweisungen von großen Werttypen.  
  
 Schließlich sind Verweistypen nach Verweis übergeben werden, wohingegen Werttypen als Wert übergeben werden. Mit einer Instanz eines Verweistyps beeinflussen Sie alle Verweise auf die Instanz zeigen. Wenn sie als Wert übergeben werden, werden Werttypinstanzen kopiert. Wenn eine Instanz eines Werttyps geändert wird, wirkt es natürlich seine Kopien sich nicht. Die Kopien werden nicht explizit vom Benutzer erstellt werden implizit erstellt, wenn Argumente übergeben oder zurückgeben Werte zurückgegeben werden, dagegen können Werttypen, die geändert werden können, für viele Benutzer verwirrend sein. Aus diesem Grund sollten Werttypen unveränderlich sein.  
  
 Als Faustregel gilt sollten die meisten der Typen in einem Framework Klassen sein. Es gibt jedoch einige Situationen, in denen die Merkmale eines Werttyps besser geeignet, Strukturen verwenden erleichtern.  
  
 **✓ ggf.** eine Struktur anstelle einer Klasse definieren, wenn Instanzen des Typs klein und im Allgemeinen kurzlebig oder in andere Objekte eingebettet sind.  
  
 **X vermeiden** eine Struktur definieren, es sei denn, der Typ alle der folgenden Merkmale aufweist:  
  
-   Logisch stellt dar, einen einzelnen Wert, wie primitive Typen \(`int`, `double`, usw..\).  
  
-   Es wurde eine Instanzgröße kleiner als 16 Bytes.  
  
-   Er ist unveränderlich.  
  
-   Es wird kein häufig geschachtelt werden.  
  
 In allen anderen Fällen sollten Sie die Typen als Klassen definieren.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)