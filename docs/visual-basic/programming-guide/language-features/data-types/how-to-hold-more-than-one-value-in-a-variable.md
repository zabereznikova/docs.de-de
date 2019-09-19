---
title: 'Vorgehensweise: Enthalten mehr als einen Wert in einer Variablen (Visual Basic)'
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
ms.openlocfilehash: 8d07a34a98303f9d220dba0a3c955120b421340e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054200"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Vorgehensweise: Enthalten mehr als einen Wert in einer Variablen (Visual Basic)

Eine Variable enthält mehr als einen Wert, wenn Sie Sie als einen zusammen *gesetzten Datentyp*deklarieren.

Zusammen [gesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) umfassen Strukturen, Arrays und Klassen. Eine Variable eines zusammengesetzten Datentyps kann eine Kombination aus elementaren Datentypen und anderen zusammengesetzten Typen enthalten. Strukturen und Klassen können sowohl Code als auch Daten enthalten.

## <a name="to-hold-more-than-one-value-in-a-variable"></a>So speichern Sie mehr als einen Wert in einer Variablen

1. Bestimmen Sie den zusammengesetzten Datentyp, den Sie für die Variable verwenden möchten.

2. Wenn der zusammengesetzte Datentyp nicht bereits definiert ist, definieren Sie ihn so, dass er von der Variablen verwendet werden kann.

    - Definieren Sie eine Struktur mit einer [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md).

    - Definieren Sie ein Array mit einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).

    - Definieren Sie eine Klasse mit einer [Class-Anweisung](../../../../visual-basic/language-reference/statements/class-statement.md).

3. Deklarieren Sie die Variable `Dim` mit einer-Anweisung.

4. Befolgen Sie den Variablennamen mit `As` einer-Klausel.

5. Befolgen Sie `As` das-Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten Datentyps.

## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
