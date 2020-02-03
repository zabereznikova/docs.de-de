---
title: Auswählen zwischen Klasse und Struktur
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
ms.openlocfilehash: 76042bef1475f2fdf14e309390dcba6654ccfaa9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741745"
---
# <a name="choosing-between-class-and-struct"></a>Auswählen zwischen Klasse und Struktur
Eine der grundlegenden Entwurfsentscheidungen jedes Framework-Designers besteht darin, einen Typ als Klasse (einen Verweistyp) oder als Struktur (Werttyp) zu entwerfen. Ein gutes Verständnis der Unterschiede im Verhalten von Verweis Typen und Werttypen ist wichtig für diese Auswahl.

 Der erste Unterschied zwischen Verweis Typen und Werttypen, die wir in Erwägung gezogen werden, besteht darin, dass Verweis Typen auf dem Heap und der Garbage Collection zugeordnet werden, wohingegen Werttypen entweder im Stapel oder Inline in enthaltenden Typen zugeordnet werden und die Zuordnung aufgehoben wird, die Zuordnung des enthaltenden Typs wird aufgehoben Daher sind Zuordnungen und Aufhebungen von Werttypen im allgemeinen günstiger als Zuordnungen und Aufhebungen von Verweis Typen.

 Als nächstes werden Arrays von Verweis Typen out-of-Line zugeordnet, was bedeutet, dass die Array Elemente lediglich Verweise auf Instanzen des Verweis Typs sind, die sich auf dem Heap befinden. Werttyp Arrays werden Inline zugeordnet, d. h., die Array Elemente sind die tatsächlichen Instanzen des Werttyps. Daher sind Zuordnungen und Aufhebungen von Werttyp Arrays weitaus günstiger als Zuordnungen und Aufhebungen von Verweistyp Arrays. Außerdem weisen Werttyp Arrays in den meisten Fällen eine viel bessere Lokalität auf.

 Der nächste Unterschied bezieht sich auf die Speicherauslastung. Werttypen werden bei der Umwandlung in einen Verweistyp oder in eine der Schnittstellen, die Sie implementieren, als gekapselt. Sie werden bei der Umwandlung zurück in den Werttyp Unboxing. Da es sich bei Feldern um Objekte handelt, die auf dem Heap zugeordnet sind und für die eine Garbage Collection durchgeführt wird, können sich zu viele Boxing-und Unboxing-Objekte negativ auf den Heap, den Garbage Collector und schließlich die Leistung der Anwendung auswirken.  Im Gegensatz dazu kommt es nicht zu einem solchen Boxing, wenn Verweis Typen umgewandelt werden. (Weitere Informationen finden Sie unter [Boxing und Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)).

 Im nächsten Schritt kopieren Verweistyp Zuweisungen den Verweis, während Werttyp Zuweisungen den gesamten Wert kopieren. Daher sind Zuweisungen von großen Verweis Typen günstiger als Zuweisungen von großen Werttypen.

 Schließlich werden Verweis Typen als Verweis übermittelt, wohingegen Werttypen als Wert übermittelt werden. Änderungen an einer Instanz eines Verweis Typs wirken sich auf alle Verweise aus, die auf die-Instanz verweisen. Werttyp Instanzen werden kopiert, wenn Sie als Wert übermittelt werden. Wenn eine Instanz eines Werttyps geändert wird, wirkt sich dies natürlich nicht auf seine Kopien aus. Da die Kopien nicht explizit vom Benutzer erstellt werden, sondern implizit erstellt werden, wenn Argumente übermittelt werden oder Rückgabewerte zurückgegeben werden, können Werttypen, die geändert werden können, für viele Benutzer verwirrend sein. Daher sollten Werttypen unveränderlich sein.

 Als Faustregel gilt: die Mehrzahl der Typen in einem Framework sollten Klassen sein. Es gibt jedoch einige Situationen, in denen die Merkmale eines Werttyps die Verwendung von Strukturen erleichtern.

 ✔️ sollten eine Struktur anstelle einer Klasse definieren, wenn Instanzen des Typs klein und häufig kurzlebig sind oder häufig in andere Objekte eingebettet sind.

 ❌ vermeiden Sie das Definieren einer Struktur, es sei denn, der Typ hat alle der folgenden Eigenschaften:

- Sie stellt logisch einen einzelnen Wert dar, ähnlich wie primitive Typen (`int`, `double`usw.).

- Sie verfügt über eine instanzgröße von weniger als 16 Bytes.

- Er ist unveränderlich.

- Er muss nicht häufig geachtelt werden.

 In allen anderen Fällen sollten Sie die Typen als Klassen definieren.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
