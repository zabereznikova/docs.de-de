---
title: Auslösen von Ausnahmen
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 6f22878a9ddfb394f6705a335930ef2cc270895f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821267"
---
# <a name="exception-throwing"></a>Auslösen von Ausnahmen
Die in diesem Abschnitt beschriebenen Richtlinien zum Auslösen von Ausnahmen erfordern eine gute Definition der Bedeutung von Ausführungsfehlern. Ein Ausführungsfehler tritt auf, wenn ein Member nicht die Aufgaben ausführen kann, die er ausführen soll (was der Elementname impliziert). Wenn die Methode beispielsweise `OpenFile` kein geöffnetes Datei Handle an den Aufrufer zurückgeben kann, wird Sie als Ausführungsfehler betrachtet.

 Die meisten Entwickler sind mit der Verwendung von Ausnahmen für Verwendungs Fehler wie der Division durch Null oder NULL-Verweise vertraut. Im Framework werden Ausnahmen für alle Fehlerbedingungen verwendet, einschließlich Ausführungsfehlern.

 ❌ Keine Fehlercodes zurückgeben.

 Ausnahmen sind die primäre Methode, Fehler in Frameworks zu melden.

 ✔️ Fehler bei der Berichts Ausführung durch Auslösen von Ausnahmen.

 ✔️ sollten den Prozess durch Aufrufen von `System.Environment.FailFast` (.NET Framework 2,0-Funktion) beenden, anstatt eine Ausnahme auszulösen, wenn der Code auf eine Situation trifft, in der er bei der weiteren Ausführung unsicher ist.

 ❌ Verwenden Sie nach Möglichkeit keine Ausnahmen für die normale Ablauf Steuerung.

 Mit Ausnahme von Systemfehlern und-Vorgängen mit potenziellen Racebedingungen sollten frameworkdesigner APIs entwerfen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst. Sie können z. b. eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Aufrufen eines Members bereitstellen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst.

 Der Member, der zum Prüfen der Vorbedingungen eines anderen Elements verwendet wird, wird häufig als Tester bezeichnet, und der Member, der die Arbeit tatsächlich erledigt, wird als doer bezeichnet.

 Es gibt Fälle, in denen das Tester-Doer Muster einen unzulässigen Leistungs Aufwand verursachen kann. In solchen Fällen sollte das so genannte Try-Parse Muster berücksichtigt werden (Weitere Informationen finden Sie unter [Ausnahmen und Leistung](exceptions-and-performance.md) ).

 ✔️ die Auswirkungen auf die Leistung beim Auslösen von Ausnahmen in Erwägung gezogen. Auslöse Raten oberhalb von 100 pro Sekunde bewirken wahrscheinlich die Leistung der meisten Anwendungen merklich.

 ✔️ dokumentieren alle Ausnahmen, die von öffentlich aufgerufenen Membern ausgelöst werden, aufgrund einer Verletzung des Mitglieds Vertrags (statt eines Systemfehlers) und behandeln Sie als Teil Ihres Vertrags.

 Ausnahmen, die Teil des Vertrags sind, sollten sich nicht von einer Version zur nächsten ändern (d. h., der Ausnahmetyp sollte nicht geändert werden, und es sollten keine neuen Ausnahmen hinzugefügt werden).

 ❌ Sie verfügen über keine öffentlichen Member, die eine bestimmte Option auslösen oder nicht verwenden können.

 ❌ Es sind keine öffentlichen Member vorhanden, die Ausnahmen als Rückgabewert oder Parameter zurückgeben `out` .

 Wenn Sie Ausnahmen aus öffentlichen APIs zurückgeben, anstatt sie auszulösen, werden viele der Vorteile der Ausnahme basierten Fehlerberichterstattung nicht mehr unterwirft.

 ✔️ sollten Sie die Verwendung von Exception Builder-Methoden in Erwägung

 Es kommt häufig vor, dass die gleiche Ausnahme von unterschiedlichen Stellen ausgelöst wird. Um codebloat zu vermeiden, verwenden Sie Hilfsmethoden, die Ausnahmen erstellen und ihre Eigenschaften initialisieren.

 Außerdem werden Member, die Ausnahmen auslösen, nicht Inline angezeigt. Wenn Sie die throw-Anweisung innerhalb des Generators verschieben, kann es vorkommen, dass der Member Inline ist.

 ❌ Lösen Sie keine Ausnahmen aus Ausnahme Filter Blöcken aus.

 Wenn ein Ausnahme Filter eine Ausnahme auslöst, wird die Ausnahme von der CLR abgefangen, und der Filter gibt false zurück. Dieses Verhalten kann nicht vom Filter unterschieden werden, der ausgeführt wird, und false explizit zurückgeben und daher sehr schwer zu Debuggen ist.

 ❌ Vermeiden Sie das explizite Auslösen von Ausnahmen von Blöcken. Implizit ausgelöste Ausnahmen, die sich aus aufrufenden Methoden ergeben, die ausgelöst werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Entwurfsrichtlinien für Ausnahmen](exceptions.md)
