---
title: Geschachtelte Typen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
ms.openlocfilehash: a3b090b39e1e907826551ed152d4eece4885ce41
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290135"
---
# <a name="nested-types"></a>Geschachtelte Typen
Ein geschachtelter Typ ist ein Typ, der innerhalb des Gültigkeits Bereichs eines anderen Typs definiert ist, der als einschließender Typ bezeichnet wird. Ein Typ, der einen Typ aufweist, hat Zugriff auf alle Member seines einschließenden Typs. Er hat z. b. Zugriff auf private Felder, die im einschließenden Typ definiert sind, sowie auf geschützte Felder, die in allen Vorgänger des einschließenden Typs definiert sind.

 Im Allgemeinen sollten die Typen von Typen sparsam verwendet werden. Hierfür gibt es mehrere Gründe: Einige Entwickler sind mit dem Konzept nicht vollständig vertraut. Diese Entwickler können z. b. Probleme mit der Syntax der Deklaration von Variablen geschieder Typen haben. Die Typen von Typen sind auch sehr eng mit ihren einschließenden Typen verknüpft und daher nicht als allgemeine Typen geeignet.

 Für die Modellierung von Implementierungsdetails der einschließenden Typen eignen sich die-Typen am besten. Der Endbenutzer sollte in seltenen Fällen Variablen eines genetzten Typs deklarieren, und es ist fast niemals erforderlich, dass die instanziierten Typen explizit instanziiert werden. Beispielsweise kann der Enumerator einer Auflistung ein Typ dieser Auflistung sein. Enumeratoren werden in der Regel durch ihren einschließenden Typ instanziiert, und da viele Sprachen die foreach-Anweisung unterstützen, müssen enumeratorvariablen selten vom Endbenutzer deklariert werden.

 ✔️ Verwenden Sie die Verwendung von Typen, wenn die Beziehung zwischen dem Typ des Typs und dem äußeren Typ so ist, dass die Semantik der Element Barrierefreiheit wünschenswert ist.

 ❌Verwenden Sie keine öffentlichen, nicht als logische Gruppierungs Konstrukt verwendeten Typen. Verwenden Sie hierfür Namespaces.

 ❌Vermeiden Sie öffentlich verfügbar gemachte. Die einzige Ausnahme besteht darin, dass Variablen des untergeordneten Typs nur in seltenen Szenarios, wie z. b. Unterklassen oder anderen erweiterten Anpassungs Szenarien, deklariert werden müssen.

 ❌Verwenden Sie keine untergeordneten Typen, wenn auf den Typ wahrscheinlich außerhalb des enthaltenden Typs verwiesen wird.

 Beispielsweise sollte eine Enumeration, die an eine Methode, die für eine Klasse definiert wurde, nicht als ein in der Klasse definierter Typ definiert werden.

 ❌Verwenden Sie keine Untertypen, wenn Sie vom Client Code instanziiert werden müssen.  Wenn ein Typ über einen öffentlichen Konstruktor verfügt, sollte er wahrscheinlich nicht eingebettet werden.

 Wenn ein Typ instanziiert werden kann, weist dies darauf hin, dass der Typ im Framework eigenständig ist (Sie können ihn erstellen, damit arbeiten und ihn zerstören, ohne den äußeren Typ zu verwenden). Daher sollte er nicht eingefügt werden. Innere Typen sollten außerhalb des äußeren Typs nicht weit verbreitet werden, ohne dass eine Beziehung zum äußeren Typ besteht.

 ❌Definieren Sie keinen als Member einer Schnittstelle definierten Typ. Viele Sprachen unterstützen kein solches Konstrukt.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Typentwurfs Richtlinien](type.md)
- [Framework-Entwurfs Richtlinien](index.md)
