---
title: 'Vorgehensweise: Ablegen von mehr als einen Wert in einer Variablen (Visual Basic)'
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
ms.openlocfilehash: e2e1648ea508ecdd744adb8d2a4f7fdbc1e586c4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332260"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Vorgehensweise: Ablegen von mehr als einen Wert in einer Variablen (Visual Basic)
Eine Variable enthält mehr als einen Wert aus, wenn Sie vom deklariert eine *zusammengesetzten Datentyp*.  
  
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) enthalten Klassen, Strukturen und Arrays. Eine Variable einen zusammengesetzten Datentyp aufweisen, kann eine Kombination von elementare Datentypen und andere zusammengesetzten Typen enthalten. Strukturen und Klassen können sowohl Code als auch Daten enthalten.  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a>Um mehr als einen Wert in einer Variablen zu speichern.  
  
1. Bestimmen des Typs, zusammengesetzte Datenelemente für die Variable verwenden möchten.  
  
2. Falls bereits nicht der zusammengesetzten Datentyp definiert ist, definieren sie, damit die Variable verwendet werden kann.  
  
    -   Definieren Sie eine Struktur mit einem [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md).  
  
    -   Definieren Sie ein Array mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
    -   Definieren einer Klasse mit einem [Class-Anweisung](../../../../visual-basic/language-reference/statements/class-statement.md).  
  
3. Deklarieren Sie die Variable mit einem `Dim` Anweisung.  
  
4. Gehen Sie vor dem Variablennamen ein `As` Klausel.  
  
5. Führen Sie die `As` Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten-Datentyps.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Wert- und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
