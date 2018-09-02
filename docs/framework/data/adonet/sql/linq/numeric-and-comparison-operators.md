---
title: Numerische Operatoren und Vergleichsoperatoren
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: a7a455730860e2b11a5ceff5a70934502b312e19
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401914"
---
# <a name="numeric-and-comparison-operators"></a>Numerische Operatoren und Vergleichsoperatoren
Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime (CLR):  
  
-   SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.  
  
-   SQL unterstützt ungeprüfte arithmetische Operatoren nicht.  
  
-   Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.  
  
## <a name="supported-operators"></a>Unterstützte Operatoren  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden Operatoren.  
  
-   Grundlegende arithmetische Operatoren  
  
    -   `+`  
  
    -   `-` (Subtraktion)  
  
    -   `*`  
  
    -   `/`  
  
    -   Visual Basic-Ganzzahlendivision (`\`)  
  
    -   `%` (Visual Basic `Mod`)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` (unäre Negation)  
  
-   Grundlegende Vergleichsoperatoren:  
  
    -   Visual Basic `=` und C# `==`  
  
    -   Visual Basic `<>` und C# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [C#-Operatoren](https://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [Operatoren](../../../../../visual-basic/language-reference/operators/index.md)
