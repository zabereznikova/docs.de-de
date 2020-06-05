---
title: 'Vorgehensweise: Ablegen mehrerer Werte in einer Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 399c5909ee6988f96bcc85260b0401f3bd18a0f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393895"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Gewusst wie: Ablegen mehrerer Werte in einer Variablen (Visual Basic)

Eine Variable enthält mehr als einen Wert, wenn Sie Sie als einen zusammen *gesetzten Datentyp*deklarieren.

Zusammen [gesetzte Datentypen](composite-data-types.md) umfassen Strukturen, Arrays und Klassen. Eine Variable eines zusammengesetzten Datentyps kann eine Kombination aus elementaren Datentypen und anderen zusammengesetzten Typen enthalten. Strukturen und Klassen können sowohl Code als auch Daten enthalten.

## <a name="to-hold-more-than-one-value-in-a-variable"></a>So speichern Sie mehr als einen Wert in einer Variablen

1. Bestimmen Sie den zusammengesetzten Datentyp, den Sie für die Variable verwenden möchten.

2. Wenn der zusammengesetzte Datentyp nicht bereits definiert ist, definieren Sie ihn so, dass er von der Variablen verwendet werden kann.

    - Definieren Sie eine Struktur mit einer [Structure-Anweisung](../../../language-reference/statements/structure-statement.md).

    - Definieren Sie ein Array mit einer [Dim-Anweisung](../../../language-reference/statements/dim-statement.md).

    - Definieren Sie eine Klasse mit einer [Class-Anweisung](../../../language-reference/statements/class-statement.md).

3. Deklarieren Sie die Variable mit einer- `Dim` Anweisung.

4. Befolgen Sie den Variablennamen mit einer- `As` Klausel.

5. Befolgen Sie das- `As` Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten Datentyps.

## <a name="see-also"></a>Weitere Informationen

- [Datentypen](../../../language-reference/data-types/index.md)
- [Typzeichen](type-characters.md)
- [Zusammengesetzte Datentypen](composite-data-types.md)
- [Strukturen](structures.md)
- [Arrays](../arrays/index.md)
- [Objekte und Klassen](../objects-and-classes/index.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
