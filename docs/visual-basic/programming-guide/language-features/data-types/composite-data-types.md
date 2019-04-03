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
ms.openlocfilehash: ea719b60a6bcd40494666d4923fad296a8ddae70
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833814"
---
# <a name="composite-data-types-visual-basic"></a>Zusammengesetzte Datentypen (Visual Basic)
Zusätzlich zu den bereitgestellten Typen Visual Basic elementarer Datentyp können Sie auch Elemente verschiedener Inhaltstypen erstellen zusammenstellen *zusammengesetzte Datentypen* wie z. B. Klassen, Strukturen und Arrays. Sie können zusammengesetzte Datentypen von elementare Typen und von anderen zusammengesetzten Typen erstellen. Beispielsweise können Sie ein Array von Strukturelementen oder eine Struktur mit Array-Elemente definieren.  
  
## <a name="data-types"></a>Datentypen  
 Ein zusammengesetzter Typ unterscheidet sich von dem Datentyp aller zugehörigen Komponenten. Z. B. ein Array von `Integer` Elemente weist nicht den `Integer` -Datentyp.  
  
 Datentyp eines Arrays wird normalerweise dargestellt mithilfe der Elementtyp, Klammern und Kommas nach Bedarf. Z. B. ein eindimensionales Array von `String` als Elemente dargestellt `String()`, und ein zweidimensionales Array von `Boolean` als Elemente dargestellt `Boolean(,)`.  
  
## <a name="structure-types"></a>Strukturtypen  
 Es gibt keinen universellen Datentyp werden alle vorhandenen Strukturen aus. Jede Definition einer Struktur stellt stattdessen einen eindeutigen Datentyp dar, auch wenn zwei Strukturen identischer Elemente in der gleichen Reihenfolge definieren. Allerdings berücksichtigt Visual Basic, wenn Sie mindestens zwei Instanzen derselben Struktur erstellen, zu dem gleichen Datentyp aufweisen.  
  
## <a name="tuples"></a>Tupel

Ein Tupel ist eine einfache Struktur, die zwei oder mehr Felder enthält, deren Typen vordefiniert sind. Tupel werden ab Visual Basic 2017 unterstützt. Tupel werden am häufigsten verwendet, um mehrere Werte aus einem Methodenaufruf zurückgeben, ohne dass Argumente als Verweis übergeben, oder Packen die zurückgegebenen Felder in einer mehr Heavyweight-Klasse oder Struktur. Finden Sie unter den [Tupel](tuples.md) Themas Weitere Informationen zu Tupeln.

## <a name="array-types"></a>Arraytypen  
 Es gibt keinen universellen Datentyp, der alle Arrays aus. Der Datentyp, der eine bestimmte Instanz eines Arrays wird durch Folgendes bestimmt:  
  
-   Die Tatsache, dass ein array  
  
-   Der Rang (Anzahl der Dimensionen) des Arrays  
  
-   Der Elementtyp des Arrays  
  
 Die Länge einer bestimmten Dimension ist vor allem nicht Teil der Datentyp der Instanz. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Im vorherigen Beispiel Arrayvariablen `arrayA` und `arrayB` gelten die gleichen Datentyp sein – `Byte()` –, obwohl sie mit unterschiedlicher Länge initialisiert werden. Variablen `arrayB` und `arrayC` sind nicht vom gleichen Typ, da sich die Elementtypen unterscheiden. Variablen `arrayC` und `arrayD` sind Sie nicht den gleichen Typ aufweisen, da ihre Ränge unterschiedlich sind. Variablen `arrayD` und `arrayE` vom gleichen Typ – `Short(,)` , da ihr Rang und Elementtypen identisch, obwohl sind `arrayD` wurde noch nicht initialisiert.  
  
 Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Klassentypen  
 Es gibt keinen universellen Datentyp, der alle Klassen aus. Obwohl eine Klasse von einer anderen Klasse erben kann, ist jeweils ein separates Data. Mehrere Instanzen derselben Klasse sind von den gleichen Datentyp. Wenn Sie eine Klassenvariable-Instanz zu einem anderen zuweisen, werden nicht nur verfügen sie über den gleichen Datentyp aufweisen, sie auf die gleiche Instanz der Klasse im Arbeitsspeicher verweisen.  
  
 Weitere Informationen über Klassen finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Vorgehensweise: Ablegen mehrerer Werte in einer Variablen](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
