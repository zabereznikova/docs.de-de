---
title: Zusammengesetzte Datentypen
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 1c099c5082f1c4173a50c70998c99135c94821e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346374"
---
# <a name="composite-data-types-visual-basic"></a>Zusammengesetzte Datentypen (Visual Basic)
Zusätzlich zu den elementaren Datentypen Visual Basic-Bereitstellung können Sie auch Elemente verschiedener Typen zusammenstellen, um zusammen *gesetzte Datentypen* wie Strukturen, Arrays und Klassen zu erstellen. Sie können zusammengesetzte Datentypen aus elementaren Typen und aus anderen zusammengesetzten Typen erstellen. Beispielsweise können Sie ein Array von Strukturelementen oder eine Struktur mit Array Elementen definieren.  
  
## <a name="data-types"></a>Datentypen  
 Ein zusammengesetzter Typ unterscheidet sich vom Datentyp seiner Komponenten. Beispielsweise ist ein Array von `Integer` Elementen nicht vom `Integer` Datentyp.  
  
 Ein Array Datentyp wird normalerweise mit dem Elementtyp, Klammern und Kommas dargestellt, wenn dies erforderlich ist. Beispielsweise wird ein eindimensionales Array von `String` Elementen als `String()`dargestellt, und ein zweidimensionales Array von `Boolean` Elementen wird als `Boolean(,)`dargestellt.  
  
## <a name="structure-types"></a>Strukturtypen  
 Es gibt keinen einzelnen Datentyp, der alle Strukturen umfasst. Stattdessen stellt jede Definition einer Struktur einen eindeutigen Datentyp dar, auch wenn zwei Strukturen identische Elemente in derselben Reihenfolge definieren. Wenn Sie jedoch zwei oder mehr Instanzen derselben Struktur erstellen, Visual Basic Sie als denselben Datentyp betrachtet.  
  
## <a name="tuples"></a>Tupel

Ein Tupel ist eine vereinfachte Struktur, die zwei oder mehr Felder enthält, deren Typen vordefiniert sind. Tupel werden ab Visual Basic 2017 unterstützt. Tupel werden am häufigsten verwendet, um mehrere Werte aus einem einzelnen Methoden aufzurufen, ohne Argumente als Verweis übergeben oder die zurückgegebenen Felder in einer höheren Klasse oder Struktur Verpacken zu müssen. Weitere Informationen zu Tupeln finden Sie im Thema [Tupel](tuples.md) .

## <a name="array-types"></a>Array Typen  
 Es gibt keinen einzelnen Datentyp, der alle Arrays umfasst. Der Datentyp einer bestimmten Instanz eines Arrays wird durch Folgendes bestimmt:  
  
- Die Tatsache, dass es sich um ein Array handelt  
  
- Der Rang (Anzahl der Dimensionen) des Arrays.  
  
- Der Elementtyp des Arrays.  
  
 Insbesondere die Länge einer bestimmten Dimension ist nicht Teil des Datentyps der-Instanz. Das folgende Beispiel veranschaulicht dies.  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Im vorherigen Beispiel werden Array Variablen `arrayA` und `arrayB` als identisch mit dem gleichen Datentyp – `Byte()` –, auch wenn Sie mit unterschiedlichen Längen initialisiert werden. Variablen `arrayB` und `arrayC` sind nicht vom gleichen Typ, da ihre Elementtypen unterschiedlich sind. Variablen `arrayC` und `arrayD` sind nicht vom gleichen Typ, da sich ihre Ränge unterscheiden. Variablen `arrayD` und `arrayE` haben denselben Typ – `Short(,)` –, weil ihre Ränge und Elementtypen identisch sind, obwohl `arrayD` noch nicht initialisiert ist.  
  
 Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Klassentypen  
 Es gibt keinen einzelnen Datentyp, der alle Klassen umfasst. Obwohl eine Klasse von einer anderen Klasse erben kann, handelt es sich bei jedem um einen separaten Datentyp. Mehrere Instanzen derselben Klasse weisen denselben Datentyp auf. Wenn Sie eine Klasseninstanzvariable einem anderen zuweisen, nicht nur denselben Datentyp haben, zeigen Sie auf dieselbe Klasseninstanz im Arbeitsspeicher.  
  
 Weitere Informationen zu-Klassen finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Gewusst wie: Ablegen mehrerer Werte in einer Variablen](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
