---
title: Arrays
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44361929"
---
# <a name="arrays"></a>Arrays
**✓ DO** lieber mithilfe von Sammlungen über Arrays in öffentlichen APIs. Die [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) Abschnitt enthält ausführliche Informationen zur Wahl zwischen Auflistungen und Arrays.  
  
 **X DO NOT** schreibgeschützte Arrayfelder verwenden. Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber der Elemente im Array können geändert werden.  
  
 **✓ CONSIDER** verzweigte Arrays anstelle von mehrdimensionalen Arrays verwenden.  
  
 Ein verzweigtes Array ist ein Array mit Elementen, die auch Arrays sind. Die Arrays, die die Elemente bilden können unterschiedliche Größen haben, führt zu weniger Speicherplatz vergeudet bei einigen Gruppen von Daten (z. B. mit geringer Dichte Matrix) im Vergleich zu mehrdimensionalen Arrays sein. Darüber hinaus wird die CLR Indexvorgänge auf verzweigte Arrays optimiert, damit sie möglicherweise eine bessere Leistung zur Laufzeit in einigen Szenarien weisen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Array>  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
