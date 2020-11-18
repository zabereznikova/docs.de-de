---
title: Konstruktorentwurf
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 27fb73aa01adf31117d1b82724873db3a03fd269
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821397"
---
# <a name="constructor-design"></a>Konstruktorentwurf

Es gibt zwei Arten von Konstruktoren: Typkonstruktoren und Instanzkonstruktoren.

Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der-Typ verwendet wird. Instanzkonstruktoren werden ausgeführt, wenn eine Instanz eines Typs erstellt wird.

Typkonstruktoren können keine Parameter annehmen. Instanzkonstruktoren können dies tun. Instanzkonstruktoren, die keine Parameter annehmen, werden häufig als Parameter lose Konstruktoren bezeichnet.

Konstruktoren sind die natürlichste Methode, Instanzen eines Typs zu erstellen. Die meisten Entwickler suchen und versuchen, einen Konstruktor zu verwenden, bevor Sie alternative Methoden zum Erstellen von Instanzen (z. b. Factorymethoden) berücksichtigen.

✔️ sollten Sie eine einfache, idealerweise standardmäßige Konstruktoren bereitstellen.

Ein einfacher Konstruktor verfügt über eine sehr geringe Anzahl von Parametern, und alle Parameter sind primitive oder enumeraten. Solche einfachen Konstruktoren erhöhen die Verwendbarkeit des Frameworks.

✔️ sollten Sie anstelle eines Konstruktors eine statische Factorymethode verwenden, wenn die Semantik des gewünschten Vorgangs nicht direkt der Erstellung einer neuen Instanz zugeordnet wird oder wenn Sie die Entwurfs Richtlinien für den Konstruktor befolgen.

✔️ Konstruktorparameter als Verknüpfungen zum Festlegen von Haupteigenschaften verwenden.

Es sollte kein Unterschied in der Semantik zwischen der Verwendung des leeren Konstruktors bestehen, gefolgt von einigen Eigenschafts Sätzen und der Verwendung eines Konstruktors mit mehreren Argumenten.

✔️ den gleichen Namen für Konstruktorparameter und eine-Eigenschaft verwenden, wenn die Konstruktorparameter zum einfachen Festlegen der-Eigenschaft verwendet werden.

Der einzige Unterschied zwischen diesen Parametern und den Eigenschaften sollte die Schreibweise sein.

✔️ führen im Konstruktor nur wenig Arbeit aus.

Konstruktoren sollten nicht viel Arbeitsaufgaben ausführen, außer die Konstruktorparameter zu erfassen. Die Kosten für jede andere Verarbeitung sollten verzögert werden, bis Sie erforderlich ist.

✔️ lösen ggf. Ausnahmen von Instanzkonstruktoren aus.

✔️ den öffentlichen Parameter losen Konstruktor explizit in Klassen deklarieren, wenn ein solcher Konstruktor erforderlich ist.

Wenn Sie nicht explizit Konstruktoren für einen Typ deklarieren, fügen viele Sprachen (z. b. c#) automatisch einen öffentlichen Parameter losen Konstruktor hinzu. (Abstrakte Klassen erhalten einen geschützten Konstruktor.)

Durch das Hinzufügen eines parametrisierten Konstruktors zu einer Klasse wird verhindert, dass der Compiler den Parameter losen Konstruktor hinzufügt. Dies verursacht häufig versehentlich wichtige Änderungen.

❌ Vermeiden Sie das explizite Definieren von Parameter losen Konstruktoren für Strukturen.

Dadurch wird die Array Erstellung beschleunigt, denn wenn der Parameter lose Konstruktor nicht definiert ist, muss er nicht an jedem Slot im Array ausgeführt werden. Beachten Sie, dass viele Compiler, einschließlich c#, nicht zulassen, dass Strukturen aus diesem Grundparameter lose Konstruktoren aufweisen.

❌ Vermeiden Sie das Aufrufen von virtuellen Membern für ein Objekt innerhalb des Konstruktors.

Das Aufrufen eines virtuellen Members bewirkt, dass die am meisten abgeleitete außer Kraft Setzung aufgerufen wird, auch wenn der Konstruktor des am weitesten abgeleiteten Typs noch nicht vollständig ausgeführt wurde.

## <a name="type-constructor-guidelines"></a>Typkonstruktorrichtlinien

✔️ statische Konstruktoren als privat festlegen.

Ein statischer Konstruktor, der auch als Klassenkonstruktor bezeichnet wird, wird verwendet, um einen Typ zu initialisieren. Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erstellt wird oder statische Member dieses Typs aufgerufen werden. Der Benutzer hat keine Kontrolle darüber, wann der statische Konstruktor aufgerufen wird. Wenn ein statischer Konstruktor nicht privat ist, kann er von Code aufgerufen werden, der nicht die CLR ist. Abhängig von den Vorgängen, die im Konstruktor ausgeführt werden, kann dies zu unerwartetem Verhalten führen. Der c#-Compiler erzwingt, dass statische Konstruktoren privat sind.

❌ Lösen Sie keine Ausnahmen von statischen Konstruktoren aus.

Wenn von einem Typkonstruktor eine Ausnahme ausgelöst wird, kann der Typ in der aktuellen Anwendungsdomäne nicht verwendet werden.

✔️ sollten Sie die Initialisierung statischer Felder Inline anstelle von expliziter Verwendung statischer Konstruktoren in Erwägung gezogen, da die Laufzeit die Leistung von Typen optimieren kann, die über keinen explizit definierten statischen Konstruktor verfügen.

*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
