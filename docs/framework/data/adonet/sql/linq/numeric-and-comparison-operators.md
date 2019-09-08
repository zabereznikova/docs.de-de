---
title: Numerische Operatoren und Vergleichsoperatoren
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 7e7af725864aa191f092055fa32b403093321aa5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781295"
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

- [Datentypen und Funktionen](data-types-and-functions.md)
- [C#-Operatoren](../../../../../csharp/language-reference/operators/index.md)
- [Operatoren](../../../../../visual-basic/language-reference/operators/index.md)
