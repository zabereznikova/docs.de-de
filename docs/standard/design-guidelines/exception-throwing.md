---
title: "Ausl&#246;sen von Ausnahmen | Microsoft Docs"
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
  - "Auslösen von Ausnahmen"
  - "Explizites Auslösen von Ausnahmen"
  - "Auslösen von Ausnahmen, Entwurfsrichtlinien"
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Ausl&#246;sen von Ausnahmen
Eine Ausnahme auslösen die Richtlinien in diesem Abschnitt beschriebenen erfordern eine gute Definition der Bedeutung der Fehler bei der Ausführung. Fehler bei der Ausführung tritt auf, wenn ein Element nicht möglich war entwickelt wurde \(was der Membername impliziert\). Zum Beispiel wenn die `OpenFile` Methode darf keine geöffnete Datei\-Handle an den Aufrufer zurückgeben, es werden Fehler bei der Ausführung betrachtet.  
  
 Die meisten Entwickler sind mit der Verwendung von Ausnahmen für Syntaxfehler z. B. Division durch 0 \(null\) oder null\-Verweise vertraut geworden. Im Framework werden Ausnahmen für alle fehlerbedingungen, einschließlich der Fehler bei der Ausführung verwendet.  
  
 **X nicht** Fehlercodes zurück.  
  
 Ausnahmen sind das primäre Mittel zum Melden von Fehlern in Frameworks.  
  
 **✓ führen** Fehler bei der Ausführung durch das Auslösen von Ausnahmen gemeldet werden.  
  
 **✓ ggf.** Beenden des Prozesses durch Aufrufen von `System.Environment.FailFast` \(.NET Framework 2.0\-Funktion\) anstatt eine Ausnahme auszulösen, wenn der Code eine Situation, in denen es unsicher, für die weitere Ausführung ist.  
  
 **X nicht** sollten Sie Ausnahmen für den normalen Programmablauf, wenn möglich.  
  
 Abgesehen von Systemausfällen und Operationen mit potenziellen Racebedingungen sollten Framework\-Entwickler APIs entwerfen, damit Benutzer Code schreiben können, die keine Ausnahmen auslöst. Beispielsweise bieten eine Möglichkeit, Vorbedingungen zu überprüfen, bevor Sie ein Element aufrufen, damit Benutzer Code schreiben können, die keine Ausnahmen auslöst.  
  
 Das Element eines anderen Elements Preconditions überprüft wird häufig als ein Tester bezeichnet, und der Member, der eigentliche Arbeit übernimmt einen Ausführer aufgerufen.  
  
 Es gibt Fälle, bei dem Tester\-Ausführer\-Muster können einen unzulässigen Performance\-Overhead. In solchen Fällen sollte die so genannte Muster Try\-Analyse berücksichtigt werden \(siehe [Ausnahmen und Leistung](../../../docs/standard/design-guidelines/exceptions-and-performance.md) für Weitere Informationen\).  
  
 **✓ ggf.** Leistungseinbußen bei der Auslösung von Ausnahmen. Throw\-Raten über 100 pro Sekunde sind wahrscheinlich deutlich die Leistung der meisten Anwendungen.  
  
 **✓ führen** Dokument alle Ausnahmen, die von öffentlich aufrufbaren Membern aufgrund einer Verletzung des Elements \(und keines Systemausfalls\) und als Bestandteil des Vertrags behandelt werden.  
  
 Ausnahmen, die Teil des Vertrags sind sollten nicht von einer Version zur nächsten ändern \(d. h. Ausnahmetyp sollte nicht geändert werden, und neue Ausnahmen sollten nicht hinzugefügt werden\).  
  
 **X nicht** haben öffentliche Member, die entweder auslösen oder nicht basierend auf einige Optionen.  
  
 **X nicht** öffentliche Member, die Ausnahmen als Rückgabewert zurückgeben oder ein `out` Parameter.  
  
 Zurückgeben von Ausnahmen von öffentlichen APIs statt sie vereitelt viele der Vorteile von Ausnahmen basierende Fehlerberichterstattung.  
  
 **✓ ggf.** Ausnahme\-Generator\-Methoden verwenden.  
  
 Es ist üblich, die an verschiedenen Stellen die gleiche Ausnahme ausgelöst. Um umfangreichen Code zu vermeiden, verwenden Sie Hilfsmethoden, die Ausnahmen erstellen und ihre Eigenschaften initialisieren.  
  
 Member, die Ausnahmen auslösen werden auch nicht immer inline erweitert. Verschieben die Throw\-Anweisung in der\-Generator können das Element inline zu setzen.  
  
 **X nicht** lösen Ausnahmen aus Ausnahme Filter blockiert.  
  
 Wenn ein Ausnahmefilter eine Ausnahme auslöst, wird die Ausnahme von der CLR und der Filter gibt false zurück. Dieses Verhalten wird nicht von den Filter ausführen und die Rückgabe von false explizit unterscheiden und ist daher sehr schwierig zu debuggen.  
  
 **X vermeiden** Explizites Auslösen von Ausnahmen von finally\-Blöcken. Implizit ausgelöste Ausnahmen, die die durch Aufrufen von Methoden, die ausgelöst werden, sind zulässig.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)