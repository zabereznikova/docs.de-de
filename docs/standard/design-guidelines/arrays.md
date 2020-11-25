---
title: Arrays
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: 11c1d23af4cf599ba632144634947520a1647ae7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701392"
---
# <a name="arrays"></a>Arrays

✔️ bevorzugen die Verwendung von Sammlungen über Arrays in öffentlichen APIs. Der Abschnitt " [Sammlungen](guidelines-for-collections.md) " enthält Details zur Auswahl zwischen Sammlungen und Arrays.

 ❌ Verwenden Sie keine schreibgeschützten Array Felder. Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber Elemente im Array können geändert werden.

 ✔️ in Erwägung gezogen, verzweigte Arrays anstelle von mehrdimensionalen Arrays zu verwenden.

 Ein Jagged Array ist ein Array mit Elementen, die auch Arrays sind. Die Arrays, aus denen die Elemente bestehen, können unterschiedlich groß sein, was zu weniger vergeudetem Speicherplatz für einige Datensätze (z. b. sparsespalten) im Vergleich zu mehrdimensionalen Arrays führt. Außerdem optimiert die CLR Index Vorgänge für verzweigte Arrays, sodass Sie in einigen Szenarios möglicherweise eine bessere Laufzeitleistung aufweisen.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Array>
- [Framework-Entwurfs Richtlinien](index.md)
- [Verwendungs Richtlinien](usage-guidelines.md)
