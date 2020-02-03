---
title: Arrays
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: d4a1f379a88231654c710b1df7b505316377c915
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741805"
---
# <a name="arrays"></a>Arrays
✔️ bevorzugen die Verwendung von Sammlungen über Arrays in öffentlichen APIs. Der Abschnitt " [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) " enthält Details zur Auswahl zwischen Sammlungen und Arrays.

 ❌ nicht schreibgeschützte Array Felder verwenden. Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber Elemente im Array können geändert werden.

 ✔️ in Erwägung gezogen, verzweigte Arrays anstelle von mehrdimensionalen Arrays zu verwenden.

 Ein Jagged Array ist ein Array mit Elementen, die auch Arrays sind. Die Arrays, aus denen die Elemente bestehen, können unterschiedlich groß sein, was zu weniger vergeudetem Speicherplatz für einige Datensätze (z. b. sparsespalten) im Vergleich zu mehrdimensionalen Arrays führt. Außerdem optimiert die CLR Index Vorgänge für verzweigte Arrays, sodass Sie in einigen Szenarios möglicherweise eine bessere Laufzeitleistung aufweisen.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Array>
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
