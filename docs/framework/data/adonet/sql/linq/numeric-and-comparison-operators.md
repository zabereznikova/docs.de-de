---
title: Numerische Operatoren und Vergleichsoperatoren
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: b29f78a13d6d0313e0ad29754f6d13ac08be1092
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783135"
---
# <a name="numeric-and-comparison-operators"></a>Numerische Operatoren und Vergleichsoperatoren

Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime (CLR):

- SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.

- SQL unterstützt ungeprüfte arithmetische Operatoren nicht.

- Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.

## <a name="supported-operators"></a>Unterstützte Operatoren

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden Operatoren.

- Grundlegende arithmetische Operatoren

  - `+`

  - `-` (Subtraktion)

  - `*`

  - `/`

  - Visual Basic-Ganzzahlendivision (`\`)

  - `%` (Visual Basic `Mod`)

  - `<<`

  - `>>`

  - `-` (unäre Negation)

- Grundlegende Vergleichsoperatoren:

  - Visual Basic `=` und C# `==`

  - Visual Basic `<>` und C# `!=`

  - Visual Basic `Is/IsNot`

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a>Siehe auch

- [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [C#-Operatoren](../../../../../../docs/csharp/language-reference/operators/index.md)
- [Operatoren](../../../../../visual-basic/language-reference/operators/index.md)
