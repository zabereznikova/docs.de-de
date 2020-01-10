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
ms.openlocfilehash: 3467851aa767efcd0557e8a412cd36316a48b9b0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709152"
---
# <a name="nested-types"></a>Geschachtelte Typen
Ein geschachtelter Typ ist ein Typ, der innerhalb des Gültigkeits Bereichs eines anderen Typs definiert ist, der als einschließender Typ bezeichnet wird. Ein Typ, der einen Typ aufweist, hat Zugriff auf alle Member seines einschließenden Typs. Er hat z. b. Zugriff auf private Felder, die im einschließenden Typ definiert sind, sowie auf geschützte Felder, die in allen Vorgänger des einschließenden Typs definiert sind.  
  
 Im Allgemeinen sollten die Typen von Typen sparsam verwendet werden. Hierfür gibt es mehrere Gründe: Einige Entwickler sind mit dem Konzept nicht vollständig vertraut. Diese Entwickler können z. b. Probleme mit der Syntax der Deklaration von Variablen geschieder Typen haben. Die Typen von Typen sind auch sehr eng mit ihren einschließenden Typen verknüpft und daher nicht als allgemeine Typen geeignet.  
  
 Für die Modellierung von Implementierungsdetails der einschließenden Typen eignen sich die-Typen am besten. Der Endbenutzer sollte in seltenen Fällen Variablen eines genetzten Typs deklarieren, und es ist fast niemals erforderlich, dass die instanziierten Typen explizit instanziiert werden. Beispielsweise kann der Enumerator einer Auflistung ein Typ dieser Auflistung sein. Enumeratoren werden in der Regel durch ihren einschließenden Typ instanziiert, und da viele Sprachen die foreach-Anweisung unterstützen, müssen enumeratorvariablen selten vom Endbenutzer deklariert werden.  
  
 **✓ DO** geschachtelte Typen verwenden, wenn die Beziehung zwischen den geschachtelten Typ und der äußere Typ ist, sodass Memberzugriff Semantik wünschenswert ist.  
  
 **X DO NOT** verwenden öffentlichen geschachtelten Typen als eine logische Gruppierung zu erstellen; für diese Namespaces verwenden.  
  
 **X AVOID** öffentlich verfügbar gemacht werden geschachtelte Typen. Die einzige Ausnahme besteht darin, dass Variablen des untergeordneten Typs nur in seltenen Szenarios, wie z. b. Unterklassen oder anderen erweiterten Anpassungs Szenarien, deklariert werden müssen.  
  
 **X DO NOT** geschachtelte Typen verwenden, wenn der Typ wahrscheinlich außerhalb der enthaltende Typ verwiesen werden.  
  
 Beispielsweise sollte eine Enumeration, die an eine Methode, die für eine Klasse definiert wurde, nicht als ein in der Klasse definierter Typ definiert werden.  
  
 **X DO NOT** geschachtelte Typen verwenden, wenn sie vom Clientcode instanziiert werden müssen.  Wenn ein Typ über einen öffentlichen Konstruktor verfügt, sollte er wahrscheinlich nicht eingebettet werden.  
  
 Wenn ein Typ instanziiert werden kann, weist dies darauf hin, dass der Typ im Framework eigenständig ist (Sie können ihn erstellen, damit arbeiten und ihn zerstören, ohne den äußeren Typ zu verwenden). Daher sollte er nicht eingefügt werden. Innere Typen sollten außerhalb des äußeren Typs nicht weit verbreitet werden, ohne dass eine Beziehung zum äußeren Typ besteht.  
  
 **X DO NOT** einen geschachtelten Typ als Member einer Schnittstelle definieren. Viele Sprachen unterstützen kein solches Konstrukt.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
