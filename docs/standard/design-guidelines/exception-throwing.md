---
title: Auslösen von Ausnahmen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 18927d242c2ed957d2bc9f8b481beeed775a4e4e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741677"
---
# <a name="exception-throwing"></a>Auslösen von Ausnahmen
Die in diesem Abschnitt beschriebenen Richtlinien zum Auslösen von Ausnahmen erfordern eine gute Definition der Bedeutung von Ausführungsfehlern. Ein Ausführungsfehler tritt auf, wenn ein Member nicht die Aufgaben ausführen kann, die er ausführen soll (was der Elementname impliziert). Wenn die `OpenFile`-Methode z. b. kein geöffnetes Datei Handle an den Aufrufer zurückgeben kann, wird Sie als Ausführungsfehler betrachtet.

 Die meisten Entwickler sind mit der Verwendung von Ausnahmen für Verwendungs Fehler wie der Division durch Null oder NULL-Verweise vertraut. Im Framework werden Ausnahmen für alle Fehlerbedingungen verwendet, einschließlich Ausführungsfehlern.

 ❌ keine Fehlercodes zurückgeben.

 Ausnahmen sind die primäre Methode, Fehler in Frameworks zu melden.

 ✔️ Fehler bei der Berichts Ausführung durch Auslösen von Ausnahmen.

 ✔️ sollten den Prozess beenden, indem Sie `System.Environment.FailFast` (.NET Framework 2,0-Feature) aufrufen, anstatt eine Ausnahme auszulösen, wenn der Code auf eine Situation trifft, in der er bei der weiteren Ausführung unsicher ist.

 ❌ verwenden keine Ausnahmen für die normale Ablauf Steuerung, wenn möglich.

 Mit Ausnahme von Systemfehlern und-Vorgängen mit potenziellen Racebedingungen sollten frameworkdesigner APIs entwerfen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst. Sie können z. b. eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Aufrufen eines Members bereitstellen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst.

 Der Member, der zum Prüfen der Vorbedingungen eines anderen Elements verwendet wird, wird häufig als Tester bezeichnet, und der Member, der die Arbeit tatsächlich erledigt, wird als doer bezeichnet.

 Es gibt Fälle, in denen das Tester-doer-Muster einen unzulässigen Leistungs Aufwand verursachen kann. In solchen Fällen sollte das so genannte try-Analyse-Muster berücksichtigt werden (Weitere Informationen finden Sie unter [Ausnahmen und Leistung](../../../docs/standard/design-guidelines/exceptions-and-performance.md) ).

 ✔️ die Auswirkungen auf die Leistung beim Auslösen von Ausnahmen in Erwägung gezogen. Auslöse Raten oberhalb von 100 pro Sekunde bewirken wahrscheinlich die Leistung der meisten Anwendungen merklich.

 ✔️ dokumentieren alle Ausnahmen, die von öffentlich aufgerufenen Membern ausgelöst werden, aufgrund einer Verletzung des Mitglieds Vertrags (statt eines Systemfehlers) und behandeln Sie als Teil Ihres Vertrags.

 Ausnahmen, die Teil des Vertrags sind, sollten sich nicht von einer Version zur nächsten ändern (d. h., der Ausnahmetyp sollte nicht geändert werden, und es sollten keine neuen Ausnahmen hinzugefügt werden).

 ❌ verfügen über keine öffentlichen Member, die eine bestimmte Option auslösen oder nicht verwenden können.

 ❌ verfügen über keine öffentlichen Member, die Ausnahmen als Rückgabewert oder `out` Parameter zurückgeben.

 Wenn Sie Ausnahmen aus öffentlichen APIs zurückgeben, anstatt sie auszulösen, werden viele der Vorteile der Ausnahme basierten Fehlerberichterstattung nicht mehr unterwirft.

 ✔️ sollten Sie die Verwendung von Exception Builder-Methoden in Erwägung

 Es kommt häufig vor, dass die gleiche Ausnahme von unterschiedlichen Stellen ausgelöst wird. Um codebloat zu vermeiden, verwenden Sie Hilfsmethoden, die Ausnahmen erstellen und ihre Eigenschaften initialisieren.

 Außerdem werden Member, die Ausnahmen auslösen, nicht Inline angezeigt. Wenn Sie die throw-Anweisung innerhalb des Generators verschieben, kann es vorkommen, dass der Member Inline ist.

 ❌ keine Ausnahmen aus Ausnahme Filter Blöcken auslösen.

 Wenn ein Ausnahme Filter eine Ausnahme auslöst, wird die Ausnahme von der CLR abgefangen, und der Filter gibt false zurück. Dieses Verhalten kann nicht vom Filter unterschieden werden, der ausgeführt wird, und false explizit zurückgeben und daher sehr schwer zu Debuggen ist.

 ❌ vermeiden, dass Ausnahmen explizit aus den letzten Blöcken ausgelöst werden. Implizit ausgelöste Ausnahmen, die sich aus aufrufenden Methoden ergeben, die ausgelöst werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
