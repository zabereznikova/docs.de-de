---
title: Auslösen von Ausnahmen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 7d1b63e5fde57cbe37a1250d16b6bf74a2d5dc8e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709399"
---
# <a name="exception-throwing"></a>Auslösen von Ausnahmen
Die in diesem Abschnitt beschriebenen Richtlinien zum Auslösen von Ausnahmen erfordern eine gute Definition der Bedeutung von Ausführungsfehlern. Ein Ausführungsfehler tritt auf, wenn ein Member nicht die Aufgaben ausführen kann, die er ausführen soll (was der Elementname impliziert). Wenn die `OpenFile`-Methode z. b. kein geöffnetes Datei Handle an den Aufrufer zurückgeben kann, wird Sie als Ausführungsfehler betrachtet.  
  
 Die meisten Entwickler sind mit der Verwendung von Ausnahmen für Verwendungs Fehler wie der Division durch Null oder NULL-Verweise vertraut. Im Framework werden Ausnahmen für alle Fehlerbedingungen verwendet, einschließlich Ausführungsfehlern.  
  
 **X DO NOT** Fehlercodes zurück.  
  
 Ausnahmen sind die primäre Methode, Fehler in Frameworks zu melden.  
  
 **✓ DO** Ausführungsfehler durch das Auslösen von Ausnahmen gemeldet werden.  
  
 **✓ CONSIDER** Beenden des Prozesses durch Aufrufen von `System.Environment.FailFast` (Feature von .NET Framework 2.0) anstatt eine Ausnahme auszulösen, wenn Ihr Code eine Situation vorfindet, wo es unsicher, für die weitere Ausführung ist.  
  
 **X DO NOT** verwenden Sie Ausnahmen für die normale ablaufsteuerung, falls möglich.  
  
 Mit Ausnahme von Systemfehlern und-Vorgängen mit potenziellen Racebedingungen sollten frameworkdesigner APIs entwerfen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst. Sie können z. b. eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Aufrufen eines Members bereitstellen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst.  
  
 Der Member, der zum Prüfen der Vorbedingungen eines anderen Elements verwendet wird, wird häufig als Tester bezeichnet, und der Member, der die Arbeit tatsächlich erledigt, wird als doer bezeichnet.  
  
 Es gibt Fälle, in denen das Tester-doer-Muster einen unzulässigen Leistungs Aufwand verursachen kann. In solchen Fällen sollte das so genannte try-Analyse-Muster berücksichtigt werden (Weitere Informationen finden Sie unter [Ausnahmen und Leistung](../../../docs/standard/design-guidelines/exceptions-and-performance.md) ).  
  
 **✓ CONSIDER** Leistungseinbußen bei der Auslösen von Ausnahmen. Auslöse Raten oberhalb von 100 pro Sekunde bewirken wahrscheinlich die Leistung der meisten Anwendungen merklich.  
  
 **✓ DO** Dokument alle Ausnahmen öffentlich aufrufbare Member aufgrund einer Verletzung des Elements (anstatt aufgrund eines Systemfehlers) Vertrag, und behandeln Sie sie als Bestandteil des Vertrags.  
  
 Ausnahmen, die Teil des Vertrags sind, sollten sich nicht von einer Version zur nächsten ändern (d. h., der Ausnahmetyp sollte nicht geändert werden, und es sollten keine neuen Ausnahmen hinzugefügt werden).  
  
 **X DO NOT** haben öffentliche Member, die entweder auslösen oder keine können basierend auf bestimmte Option.  
  
 **X DO NOT** öffentliche Member, die zum Zurückgeben von Ausnahmen als Rückgabewert oder ein `out` Parameter.  
  
 Wenn Sie Ausnahmen aus öffentlichen APIs zurückgeben, anstatt sie auszulösen, werden viele der Vorteile der Ausnahme basierten Fehlerberichterstattung nicht mehr unterwirft.  
  
 **✓ CONSIDER** Ausnahme-Generator-Methoden verwenden.  
  
 Es kommt häufig vor, dass die gleiche Ausnahme von unterschiedlichen Stellen ausgelöst wird. Um codebloat zu vermeiden, verwenden Sie Hilfsmethoden, die Ausnahmen erstellen und ihre Eigenschaften initialisieren.  
  
 Außerdem werden Member, die Ausnahmen auslösen, nicht Inline angezeigt. Wenn Sie die throw-Anweisung innerhalb des Generators verschieben, kann es vorkommen, dass der Member Inline ist.  
  
 **X DO NOT** lösen Ausnahmen aus Ausnahmeblöcke-Filter.  
  
 Wenn ein Ausnahme Filter eine Ausnahme auslöst, wird die Ausnahme von der CLR abgefangen, und der Filter gibt false zurück. Dieses Verhalten kann nicht vom Filter unterschieden werden, der ausgeführt wird, und false explizit zurückgeben und daher sehr schwer zu Debuggen ist.  
  
 **X AVOID** explizit Auslösen von Ausnahmen von finally-Blöcke. Implizit ausgelöste Ausnahmen, die sich aus aufrufenden Methoden ergeben, die ausgelöst werden.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
