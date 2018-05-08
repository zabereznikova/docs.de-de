---
title: Zusammengesetzte Datentypen (Visual Basic)
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
ms.openlocfilehash: 73867a5881db7c94d258e8716c4ff4c5b1119e71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="composite-data-types-visual-basic"></a>Zusammengesetzte Datentypen (Visual Basic)
Zusätzlich zu den bereitgestellten elementarer Datentyp Typen Visual Basic können Sie auch Elemente unterschiedlichen Typs zu erstellen assemblieren *zusammengesetzte Datentypen* wie z. B. Arrays, Strukturen und Klassen. Sie können zusammengesetzte Datentypen aus elementare Typen und aus anderen zusammengesetzten Typen erstellen. Sie können z. B. ein Array von Strukturelementen oder eine Struktur mit Arraymember definieren.  
  
## <a name="data-types"></a>Datentypen  
 Ein zusammengesetzter Typ ist der Datentyp eines beliebigen Komponenten unterscheiden. Angenommen, ein Array von `Integer` Elemente weist nicht die `Integer` -Datentyp.  
  
 Datentyp eines Arrays wird normalerweise mithilfe von Elementtyp, Klammern und Kommas nach Bedarf dargestellt. Z. B. ein eindimensionales Array vom `String` Elemente wird dargestellt als `String()`, und ein zweidimensionales Array von `Boolean` Elemente wird als `Boolean(,)`.  
  
## <a name="structure-types"></a>Strukturtypen  
 Es gibt keinen universellen Datentyp, der alle Strukturen umfasst. Stattdessen stellt jede Definition einer Struktur einen eindeutigen Datentyp dar, auch wenn die beiden Strukturen identischer Elemente in derselben Reihenfolge definiert werden. Allerdings berücksichtigt Visual Basic, wenn Sie zwei oder mehr Instanzen derselben Struktur erstellen, zu dem gleichen Datentyp aufweisen.  
  
## <a name="tuples"></a>Tupel

Ein Tupel ist eine einfache Struktur, die zwei oder mehr Felder enthält, deren Typen vordefiniert sind. Tupel werden beginnend mit Visual Basic 2017 unterstützt. Tupel werden am häufigsten verwendet, um mehrere Werte aus einem einzelnen Methodenaufruf zurückzugeben, ohne Argumente nach Verweis übergeben müssen, oder Packen die zurückgegebenen Felder in einer mehr Heavyweight-Klasse oder Struktur. Finden Sie unter der [Tupel](tuples.md) Thema Weitere Informationen zu Tupeln.

## <a name="array-types"></a>Arraytypen  
 Es gibt keinen universellen Datentyp, der alle Arrays umfasst. Der Datentyp einer bestimmten Instanz eines Arrays wird durch Folgendes bestimmt:  
  
-   Die Tatsache, dass ein array  
  
-   Der Rang (Anzahl der Dimensionen) des Arrays  
  
-   Der Elementtyp des Arrays  
  
 Insbesondere ist die Länge einer bestimmten Dimension nicht Teil der Datentyp der Instanz. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Im vorherigen Beispiel Arrayvariablen `arrayA` und `arrayB` gelten die gleichen Datentyp sein – `Byte()` –, obwohl sie mit unterschiedlichen Längen initialisiert werden. Variablen `arrayB` und `arrayC` sind Sie nicht den gleichen Typ aufweisen, da ihre Elementtypen unterschiedlich sind. Variablen `arrayC` und `arrayD` sind Sie nicht den gleichen Typ aufweisen, da ihre Ränge unterschiedlich sind. Variablen `arrayD` und `arrayE` vom gleichen Typ – `Short(,)` – da ihre Ränge und Elementtypen identisch, obwohl sind `arrayD` wurde noch nicht initialisiert.  
  
 Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Klassentypen  
 Es gibt keinen universellen Datentyp, der alle Klassen umfasst. Obwohl eine Klasse von einer anderen Klasse erben kann, ist jeweils eine separate Datentyp. Mehrere Instanzen derselben Klasse sind vom gleichen Datentyp. Wenn Sie eine Klasseninstanzvariable zu einem anderen zuweisen, nicht nur verfügen sie über den gleichen Datentyp aufweisen, sie mit der gleichen Klasseninstanz im Arbeitsspeicher verweisen.  
  
 Weitere Informationen zu Klassen finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Gewusst wie: Ablegen mehrerer Werte in einer Variablen](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
