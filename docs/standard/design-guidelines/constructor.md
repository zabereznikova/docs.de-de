---
title: Konstruktorentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: 823bc893c9384bb687e5f9a196abe497db14f4db
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709477"
---
# <a name="constructor-design"></a>Konstruktorentwurf

Es gibt zwei Arten von Konstruktoren: Typkonstruktoren und Instanzkonstruktoren.

Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der-Typ verwendet wird. Instanzkonstruktoren werden ausgeführt, wenn eine Instanz eines Typs erstellt wird.

Typkonstruktoren können keine Parameter annehmen. Instanzkonstruktoren können dies tun. Instanzkonstruktoren, die keine Parameter annehmen, werden häufig als Parameter lose Konstruktoren bezeichnet.

Konstruktoren sind die natürlichste Methode, Instanzen eines Typs zu erstellen. Die meisten Entwickler suchen und versuchen, einen Konstruktor zu verwenden, bevor Sie alternative Methoden zum Erstellen von Instanzen (z. b. Factorymethoden) berücksichtigen.

**✓ CONSIDER** einfach, im Idealfall Standard, Konstruktoren bereitstellen.

Ein einfacher Konstruktor verfügt über eine sehr geringe Anzahl von Parametern, und alle Parameter sind primitive oder enumeraten. Solche einfachen Konstruktoren erhöhen die Verwendbarkeit des Frameworks.

**✓ CONSIDER** eine statische Factorymethode statt einen Konstruktor verwenden, wenn die Semantik des gewünschten Vorgangs nicht direkt der Erstellung einer neuen Instanz zugeordnet sind, oder der Konstruktor Entwurfsrichtlinien unnatürlichen idealer.

**✓ DO** Konstruktorparameter als Tastenkombinationen verwenden, für die wichtigsten Eigenschaften festlegen.

Es sollte kein Unterschied in der Semantik zwischen der Verwendung des leeren Konstruktors bestehen, gefolgt von einigen Eigenschafts Sätzen und der Verwendung eines Konstruktors mit mehreren Argumenten.

**✓ DO** verwenden Sie denselben Namen für Konstruktorparameter und eine Eigenschaft aus, wenn der Konstruktorparameter verwendet werden, einfach die Eigenschaft festgelegt.

Der einzige Unterschied zwischen diesen Parametern und den Eigenschaften sollte die Schreibweise sein.

**✓ DO** nur minimale Arbeitsschritte im Konstruktor.

Konstruktoren sollten nicht viel Arbeitsaufgaben ausführen, außer die Konstruktorparameter zu erfassen. Die Kosten für jede andere Verarbeitung sollten verzögert werden, bis Sie erforderlich ist.

**✓ DO** Ausnahmen von Instanzkonstruktoren, falls zutreffend.

"-" **Wird explizit den** öffentlichen Parameter losen Konstruktor in Klassen deklarieren, wenn ein solcher Konstruktor erforderlich ist.

Wenn Sie nicht explizit Konstruktoren für einen Typ deklarieren, fügen viele Sprachen (z C#. b.) automatisch einen öffentlichen Parameter losen Konstruktor hinzu. (Abstrakte Klassen erhalten einen geschützten Konstruktor.)

Durch das Hinzufügen eines parametrisierten Konstruktors zu einer Klasse wird verhindert, dass der Compiler den Parameter losen Konstruktor hinzufügt. Dies verursacht häufig versehentlich wichtige Änderungen.

**X vermeiden** Sie das explizite Definieren von Parameter losen Konstruktoren für Strukturen.

Dadurch wird die Array Erstellung beschleunigt, denn wenn der Parameter lose Konstruktor nicht definiert ist, muss er nicht an jedem Slot im Array ausgeführt werden. Beachten Sie, dass viele Compiler, C#einschließlich, nicht zulassen, dass Strukturen aus diesem Grundparameter lose Konstruktoren aufweisen.

**X AVOID** virtuelle Member für ein Objekt in seinem Konstruktor aufrufen.

Das Aufrufen eines virtuellen Members bewirkt, dass die am meisten abgeleitete außer Kraft Setzung aufgerufen wird, auch wenn der Konstruktor des am weitesten abgeleiteten Typs noch nicht vollständig ausgeführt wurde.

## <a name="type-constructor-guidelines"></a>Typkonstruktorrichtlinien

**✓ DO** als statische Konstruktoren privat festlegen.

Ein statischer Konstruktor, der auch als Klassenkonstruktor bezeichnet wird, wird verwendet, um einen Typ zu initialisieren. Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erstellt wird oder statische Member dieses Typs aufgerufen werden. Der Benutzer hat keine Kontrolle darüber, wann der statische Konstruktor aufgerufen wird. Wenn ein statischer Konstruktor nicht privat ist, kann er von Code aufgerufen werden, der nicht die CLR ist. Abhängig von den Vorgängen, die im Konstruktor ausgeführt werden, kann dies zu unerwartetem Verhalten führen. Der C# Compiler erzwingt, dass statische Konstruktoren privat sind.

**X DO NOT** lösen Ausnahmen aus statischen Konstruktoren.

Wenn von einem Typkonstruktor eine Ausnahme ausgelöst wird, kann der Typ in der aktuellen Anwendungsdomäne nicht verwendet werden.

**✓ CONSIDER** statische Felder von Inline initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Common Language Runtime ist in der Lage, zur Optimierung der Leistung von Typen, die nicht über einen explizit definierten statischen Konstruktor verfügen.

*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
