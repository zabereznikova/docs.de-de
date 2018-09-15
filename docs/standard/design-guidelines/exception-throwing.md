---
title: Auslösen von Ausnahmen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fbbe84811e3fa096b9e13c459143311bb75a198
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45638440"
---
# <a name="exception-throwing"></a>Auslösen von Ausnahmen
In diesem Abschnitt beschriebene Richtlinien für die eine Ausnahme auslösen müssen klare Definition der Bedeutung des Fehler bei der Ausführung. Fehler bei der Ausführung tritt auf, wenn ein Member nicht möglich, was es ist vorgesehen haben (was der Membername impliziert). Z. B. wenn die `OpenFile` Methode kann keinen geöffneten Dateihandle an den Aufrufer zurückgeben, es Fehler bei der Ausführung betrachtet werden.  
  
 Die meisten Entwickler sind mit der Verwendung von Ausnahmen für Fehler z. B. Division durch 0 (null) oder null-Verweise vertraut geworden. Im Framework werden Ausnahmen für alle fehlerbedingungen, einschließlich der Fehler bei der Ausführung verwendet.  
  
 **X DO NOT** Fehlercodes zurück.  
  
 Ausnahmen sind das primäre Mittel zum Melden von Fehlern in Frameworks.  
  
 **✓ DO** Ausführungsfehler durch das Auslösen von Ausnahmen gemeldet werden.  
  
 **✓ CONSIDER** Beenden des Prozesses durch Aufrufen von `System.Environment.FailFast` (Feature von .NET Framework 2.0) anstatt eine Ausnahme auszulösen, wenn Ihr Code eine Situation vorfindet, wo es unsicher, für die weitere Ausführung ist.  
  
 **X DO NOT** verwenden Sie Ausnahmen für die normale ablaufsteuerung, falls möglich.  
  
 Mit Ausnahme von Systemfehlern und Vorgänge mit potenzielle Racebedingungen sollten Framework Designer APIs entwickeln, damit Sie Benutzercode schreiben können, die keine Ausnahmen auslöst. Sie können z. B. angeben, dass eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Aufrufen eines Members, damit Sie Benutzercode schreiben können, die keine Ausnahmen auslöst.  
  
 Das Element, das zum Überprüfen von Vorbedingungen eines anderen Elements verwendet wird häufig als ein Tester bezeichnet, und das Element, das eigentliche Arbeit übernimmt eine Doer aufgerufen wird.  
  
 Es gibt Fälle, bei dem Tester-Doer-Muster einen nicht akzeptablen Leistungsaufwand haben kann. In solchen Fällen das so genannte Versuch der Analyse Muster angesehen werden (siehe [Ausnahmen und Leistung](../../../docs/standard/design-guidelines/exceptions-and-performance.md) für Weitere Informationen).  
  
 **✓ CONSIDER** Leistungseinbußen bei der Auslösen von Ausnahmen. Throw-Preise über 100 pro Sekunde werden wahrscheinlich deutlich die Leistung der meisten Anwendungen auswirken.  
  
 **✓ DO** Dokument alle Ausnahmen öffentlich aufrufbare Member aufgrund einer Verletzung des Elements (anstatt aufgrund eines Systemfehlers) Vertrag, und behandeln Sie sie als Bestandteil des Vertrags.  
  
 Ausnahmen, die Teil des Vertrags sind sollten nicht von einer Version zur nächsten ändern (d. h. Typ der Ausnahme sollte nicht geändert werden und neue Ausnahmen sollten nicht hinzugefügt werden).  
  
 **X DO NOT** haben öffentliche Member, die entweder auslösen oder keine können basierend auf bestimmte Option.  
  
 **X DO NOT** öffentliche Member, die zum Zurückgeben von Ausnahmen als Rückgabewert oder ein `out` Parameter.  
  
 Zurückgeben von Ausnahmen von öffentlichen APIs, statt sie verfehlt viele der Vorteile bei der Fehlerberichterstattung ausnahmebasierten.  
  
 **✓ CONSIDER** Ausnahme-Generator-Methoden verwenden.  
  
 Es ist üblich, die an verschiedenen Stellen die gleiche Ausnahme ausgelöst. Um codeüberfrachtung zu vermeiden, verwenden Sie Hilfsmethoden, die erstellen Sie Ausnahmen und deren Eigenschaften zu initialisieren.  
  
 Darüber hinaus werden Elemente, die Ausnahmen auslösen nicht immer inline ersetzt. Verschieben die Throw-Anweisung in der Generator, kann das Element zu setzende machen.  
  
 **X DO NOT** lösen Ausnahmen aus Ausnahmeblöcke-Filter.  
  
 Wenn ein Ausnahmefilter eine Ausnahme auslöst, wird die Ausnahme von der CLR und der Filter "false" zurückgibt. Dieses Verhalten wird nicht aus dem Filter ausführen, und false zurückgibt, explizit zu unterscheiden und ist daher sehr schwer zu beheben.  
  
 **X AVOID** explizit Auslösen von Ausnahmen von finally-Blöcke. Implizit ausgelöste Ausnahmen, die durch Aufrufen von Methoden, die auslösen, sind zulässig.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
