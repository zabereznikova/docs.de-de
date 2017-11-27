---
title: "Auslösen von Ausnahmen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b1aa0eaccc26e1bd7cc6b78953dc0a782b2f952e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exception-throwing"></a>Auslösen von Ausnahmen
Ausnahme auslösende-Richtlinien, die in diesem Abschnitt beschriebenen erfordern eine gute Definition der Bedeutung der Ausführung ein Fehler aufgetreten. Fehler bei der Ausführung tritt auf, wenn es sich bei Mitglied nicht seiner Vorgehensweise (welche die Elementnamen impliziert) entwickelt. Beispielsweise, wenn die `OpenFile` Methode kann nicht an den Aufrufer eine geöffnete Dateihandle zurückgeben, es werden Fehler bei der Ausführung betrachtet.  
  
 Die meisten Entwickler haben mit der Verwendung von Ausnahmen für Verwendungsfehler z. B. Division durch 0 (null) oder null-Verweise vertraut werden. Ausnahmen werden in das Framework für alle fehlerbedingungen, einschließlich Fehler bei der Ausführung verwendet.  
  
 **X nicht** Fehlercodes zurück.  
  
 Ausnahmen sind das primäre Mittel zum Melden von Fehlern in Frameworks.  
  
 **Führen Sie ✓** Ausführungsfehler durch das Auslösen von Ausnahmen gemeldet werden.  
  
 **✓ GGF.** Beenden des Prozesses durch Aufrufen von `System.Environment.FailFast` (Feature von .NET Framework 2.0) anstatt eine Ausnahme auszulösen, wenn Ihr Code eine Situation vorfindet, wo es unsicher, für die weitere Ausführung ist.  
  
 **X nicht** verwenden Sie Ausnahmen für die normale ablaufsteuerung, falls möglich.  
  
 Mit Ausnahme von Systemfehlern und Vorgänge mit potenzielle Racebedingungen sollten Framework-Entwickler APIs entwerfen, damit Benutzer Code schreiben können, der keine Ausnahmen auslöst. Sie können z. B. angeben, dass eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Mitglied aufrufen, damit Benutzer Code schreiben können, der keine Ausnahmen auslöst.  
  
 Das Element zum Prüfen auf Vorbedingungen eines anderen Elements wird häufig als ein Tester bezeichnet, und der Member, der eigentliche Arbeit übernimmt einen Ausführer aufgerufen.  
  
 Es gibt Fälle, wenn der Tester-Ausführer-Muster ein inakzeptabler Leistung auswirken können. In solchen Fällen sollte dem so genannten Try-Analyse Muster berücksichtigt werden (finden Sie unter [Ausnahmen und Leistungsfähigkeit](../../../docs/standard/design-guidelines/exceptions-and-performance.md) für Weitere Informationen).  
  
 **✓ GGF.** Leistungseinbußen bei der Auslösen von Ausnahmen. Throw-Raten über 100 pro Sekunde sind wahrscheinlich die Leistung der meisten Anwendung deutlich beeinträchtigen.  
  
 **Führen Sie ✓** Dokument alle Ausnahmen öffentlich aufrufbare Member aufgrund einer Verletzung des Elements (anstatt aufgrund eines Systemfehlers) Vertrag, und behandeln Sie sie als Bestandteil des Vertrags.  
  
 Ausnahmen, die Bestandteil des Vertrags sind sollten nicht von einer Version zur nächsten ändern (d. h. Ausnahmetyp nicht ändern sollten, und neue Ausnahmen nicht hinzugefügt werden sollen).  
  
 **X nicht** haben öffentliche Member, die entweder auslösen oder keine können basierend auf bestimmte Option.  
  
 **X nicht** öffentliche Member, die zum Zurückgeben von Ausnahmen als Rückgabewert oder ein `out` Parameter.  
  
 Zurückgeben von Ausnahmen von öffentlichen APIs, statt sie unterlaufen kann viele der Vorteile von Ausnahmen basierende-Fehlerberichterstattung.  
  
 **✓ GGF.** Ausnahme-Generator-Methoden verwenden.  
  
 Es ist üblich, die von verschiedenen Positionen in die gleiche Ausnahme auslöst. Um Codeumfang zu vermeiden, verwenden Sie Hilfsmethoden, die Ausnahmen zu erstellen und initialisieren Sie ihre Eigenschaften.  
  
 Außerdem werden Elemente, die Ausnahmen auslösen nicht abrufen Inlining. Verschieben die Throw-Anweisung in der Generator lassen möglicherweise das Element inline zu setzen.  
  
 **X nicht** lösen Ausnahmen aus Ausnahmeblöcke-Filter.  
  
 Wenn ein Ausnahmefilter eine Ausnahme auslöst, wird die Ausnahme von der CLR und der Filter "false" zurückgegeben. Dieses Verhalten ist nicht von den Filter ausführen und explizit "false" zurückgeben und ist daher sehr schwer zu beheben.  
  
 **X vermeiden** explizit Auslösen von Ausnahmen von finally-Blöcke. Implizit ausgelöste Ausnahmen, Aufrufen von Methoden, die ausgelöst werden, sind zulässig.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
