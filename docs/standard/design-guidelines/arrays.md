---
title: Arrays
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: ac4b073d2d3291922498a0e56c7e81f7e7868c65
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709568"
---
# <a name="arrays"></a>Arrays
**✓ DO** lieber mithilfe von Sammlungen über Arrays in öffentlichen APIs. Der Abschnitt " [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) " enthält Details zur Auswahl zwischen Sammlungen und Arrays.  
  
 **X DO NOT** schreibgeschützte Arrayfelder verwenden. Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber Elemente im Array können geändert werden.  
  
 **✓ CONSIDER** verzweigte Arrays anstelle von mehrdimensionalen Arrays verwenden.  
  
 Ein Jagged Array ist ein Array mit Elementen, die auch Arrays sind. Die Arrays, aus denen die Elemente bestehen, können unterschiedlich groß sein, was zu weniger vergeudetem Speicherplatz für einige Datensätze (z. b. sparsespalten) im Vergleich zu mehrdimensionalen Arrays führt. Außerdem optimiert die CLR Index Vorgänge für verzweigte Arrays, sodass Sie in einigen Szenarios möglicherweise eine bessere Laufzeitleistung aufweisen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Array>
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
