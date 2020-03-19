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
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401244"
---
# <a name="constructor-design"></a>Konstruktorentwurf

Es gibt zwei Arten von Konstruktoren: Typkonstruktoren und Instanzkonstruktoren.

Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der Typ verwendet wird. Instanzkonstruktoren werden ausgeführt, wenn eine Instanz eines Typs erstellt wird.

Typkonstruktoren können keine Parameter annehmen. Instanzkonstruktoren können dies. Instanzkonstruktoren, die keine Parameter annehmen, werden häufig als parameterlose Konstruktoren bezeichnet.

Konstruktoren sind die natürlichste Möglichkeit, Instanzen eines Typs zu erstellen. Die meisten Entwickler suchen und versuchen, einen Konstruktor zu verwenden, bevor sie alternative Möglichkeiten zum Erstellen von Instanzen (z. B. Factorymethoden) in Betracht ziehen.

✔️ CONSIDER bietet einfache, idealerweise Standardkonstruktoren.

Ein einfacher Konstruktor hat eine sehr kleine Anzahl von Parametern, und alle Parameter sind Primitive oder Enumerungen. Solche einfachen Konstruktoren erhöhen die Benutzerfreundlichkeit des Frameworks.

✔️ CONSIDER mit einer statischen Factorymethode anstelle eines Konstruktors, wenn die Semantik des gewünschten Vorgangs nicht direkt der Konstruktion einer neuen Instanz zugeordnet wird oder wenn sich die Entwurfsrichtlinien des Konstruktors als unnatürlich anfühlen.

✔️ verwenden Konstruktorparameter als Verknüpfungen zum Festlegen von Haupteigenschaften.

Es sollte keinen Unterschied in der Semantik zwischen der Verwendung des leeren Konstruktors gefolgt von einigen Eigenschaftssätzen und der Verwendung eines Konstruktors mit mehreren Argumenten geben.

✔️ verwenden denselben Namen für Konstruktorparameter und eine Eigenschaft, wenn die Konstruktorparameter verwendet werden, um einfach die Eigenschaft festzulegen.

Der einzige Unterschied zwischen solchen Parametern und den Eigenschaften sollte das Gehäuse sein.

✔️ minimale Arbeit im Konstruktor.

Konstruktoren sollten nicht viel anderes tun, als die Konstruktorparameter zu erfassen. Die Kosten für jede andere Verarbeitung sollten bis erforderlich verzögert werden.

✔️ werden ggf. Ausnahmen von Instanzkonstruktoren ausgelöst.

✔️ DO explizit den öffentlichen parameterlosen Konstruktor in Klassen deklarieren, wenn ein solcher Konstruktor erforderlich ist.

Wenn Sie keine Konstruktoren für einen Typ explizit deklarieren, fügen viele Sprachen (z. B. C') automatisch einen öffentlichen parameterlosen Konstruktor hinzu. (Abstrakte Klassen erhalten einen geschützten Konstruktor.)

Das Hinzufügen eines parametrisierten Konstruktors zu einer Klasse verhindert, dass der Compiler den parameterlosen Konstruktor hinzufügt. Dies führt häufig zu zufälligen Bruchänderungen.

❌AVOID definiert explizit parameterlose Konstruktoren für Strukturen.

Dies beschleunigt die Arrayerstellung, da der Parameterlose Konstruktor nicht definiert ist und nicht auf jedem Slot im Array ausgeführt werden muss. Beachten Sie, dass viele Compiler, einschließlich C', aus diesem Grund nicht zulassen, dass Strukturen über parameterlose Konstruktoren verfügen.

❌AVOID, die virtuelle Member für ein Objekt innerhalb des Konstruktors aufruft.

Wenn ein virtueller Member aufgerufen wird, wird die am häufigsten abgeleitete Außerkraftsetzung aufgerufen, auch wenn der Konstruktor des am häufigsten abgeleiteten Typs noch nicht vollständig ausgeführt wurde.

## <a name="type-constructor-guidelines"></a>Typkonstruktorrichtlinien

✔️ machen statische Konstruktoren privat.

Ein statischer Konstruktor, der auch als Klassenkonstruktor bezeichnet wird, wird verwendet, um einen Typ zu initialisieren. Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erstellt oder statische Member für diesen Typ aufgerufen werden. Der Benutzer hat keine Kontrolle darüber, wann der statische Konstruktor aufgerufen wird. Wenn ein statischer Konstruktor nicht privat ist, kann er durch einen anderen Code als die CLR aufgerufen werden. Abhängig von den im Konstruktor ausgeführten Vorgängen kann dies zu unerwartetem Verhalten führen. Der C-Compiler erzwingt, dass statische Konstruktoren privat sind.

❌Nicht Ausnahmen von statischen Konstruktoren auslösen.

Wenn eine Ausnahme von einem Typkonstruktor ausgelöst wird, kann der Typ in der aktuellen Anwendungsdomäne nicht verwendet werden.

✔️ CONSIDER, statische Felder inline zu initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Laufzeit in der Lage ist, die Leistung von Typen zu optimieren, die keinen explizit definierten statischen Konstruktor haben.

*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Framework Design-Richtlinien](../../../docs/standard/design-guidelines/index.md)
