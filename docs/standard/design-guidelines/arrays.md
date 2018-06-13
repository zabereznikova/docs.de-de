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
ms.openlocfilehash: 2945ead7c22b759ce88f6585e2254e9bc540a7ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570395"
---
# <a name="arrays"></a>Arrays
**Führen Sie ✓** lieber mithilfe von Sammlungen über Arrays in öffentlichen APIs. Die [Sammlungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) Abschnitt bietet ausführliche Informationen zur Wahl zwischen Auflistungen und Arrays.  
  
 **X nicht** schreibgeschützte Arrayfelder verwenden. Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber Elemente im Array können geändert werden.  
  
 **✓ GGF.** verzweigte Arrays anstelle von mehrdimensionalen Arrays verwenden.  
  
 Ein verzweigtes Array ist ein Array mit Elementen, die auch Arrays sind. Die Arrays, die die Elemente bilden können unterschiedliche Größen haben, was zu weniger Speicherplatz vergeudet bei einigen Gruppen von Daten (z. B. mit geringer Dichte Matrix) im Vergleich zu mehrdimensionalen Arrays sein. Darüber hinaus optimiert die CLR Indexvorgänge auf verzweigte Arrays, damit sie eine bessere Leistung zur Laufzeit in einigen Szenarien weisen möglicherweise.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Array>  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
