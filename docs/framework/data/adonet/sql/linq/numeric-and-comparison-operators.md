---
title: Numerische Operatoren und Vergleichsoperatoren
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: e2bdc55cd6c2203bc96d0766e5e53a57294d4d7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554711"
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
- [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [C#-Operatoren](../../../../../../docs/csharp/language-reference/operators/index.md)
- [Operatoren](../../../../../visual-basic/language-reference/operators/index.md)
