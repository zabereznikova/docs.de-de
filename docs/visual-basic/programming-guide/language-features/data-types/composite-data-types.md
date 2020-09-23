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
ms.openlocfilehash: 842b74aa7cc99c8196fdfb1eb6c976d9e72a4fa4
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077162"
---
# <a name="composite-data-types-visual-basic"></a>Zusammengesetzte Datentypen (Visual Basic)

Zusätzlich zu den elementaren Datentypen Visual Basic-Bereitstellung können Sie auch Elemente verschiedener Typen zusammenstellen, um zusammen *gesetzte Datentypen* wie Strukturen, Arrays und Klassen zu erstellen. Sie können zusammengesetzte Datentypen aus elementaren Typen und aus anderen zusammengesetzten Typen erstellen. Beispielsweise können Sie ein Array von Strukturelementen oder eine Struktur mit Array Elementen definieren.  
  
## <a name="data-types"></a>Datentypen  

 Ein zusammengesetzter Typ unterscheidet sich vom Datentyp seiner Komponenten. Beispielsweise ist ein Array von- `Integer` Elementen nicht vom `Integer` Datentyp.  
  
 Ein Array Datentyp wird normalerweise mit dem Elementtyp, Klammern und Kommas dargestellt, wenn dies erforderlich ist. Beispielsweise wird ein eindimensionales Array von- `String` Elementen als dargestellt `String()` , und ein zweidimensionales Array von- `Boolean` Elementen wird als dargestellt `Boolean(,)` .  
  
## <a name="structure-types"></a>Strukturtypen  

 Es gibt keinen einzelnen Datentyp, der alle Strukturen umfasst. Stattdessen stellt jede Definition einer Struktur einen eindeutigen Datentyp dar, auch wenn zwei Strukturen identische Elemente in derselben Reihenfolge definieren. Wenn Sie jedoch zwei oder mehr Instanzen derselben Struktur erstellen, Visual Basic Sie als denselben Datentyp betrachtet.  
  
## <a name="tuples"></a>Tupel

Ein Tupel ist eine vereinfachte Struktur, die zwei oder mehr Felder enthält, deren Typen vordefiniert sind. Tupel werden ab Visual Basic 2017 unterstützt. Tupel werden am häufigsten verwendet, um mehrere Werte aus einem einzelnen Methoden aufzurufen, ohne Argumente als Verweis übergeben oder die zurückgegebenen Felder in einer höheren Klasse oder Struktur Verpacken zu müssen. Weitere Informationen zu Tupeln finden Sie im Thema [Tupel](tuples.md) .

## <a name="array-types"></a>Arraytypen  

 Es gibt keinen einzelnen Datentyp, der alle Arrays umfasst. Der Datentyp einer bestimmten Instanz eines Arrays wird durch Folgendes bestimmt:  
  
- Die Tatsache, dass es sich um ein Array handelt  
  
- Der Rang (Anzahl der Dimensionen) des Arrays.  
  
- Der Elementtyp des Arrays.  
  
 Insbesondere die Länge einer bestimmten Dimension ist nicht Teil des Datentyps der-Instanz. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Im vorherigen Beispiel werden Array Variablen `arrayA` und `arrayB` als denselben Datentyp – `Byte()` –, auch wenn Sie mit unterschiedlichen Längen initialisiert werden. Variablen `arrayB` und weisen `arrayC` nicht denselben Typ auf, da deren Elementtypen unterschiedlich sind. Variablen `arrayC` und weisen `arrayD` nicht denselben Typ auf, da sich ihre Ränge unterscheiden. Variablen `arrayD` und `arrayE` haben denselben Typ – `Short(,)` –, weil ihre Ränge und Elementtypen identisch sind, obwohl `arrayD` noch nicht initialisiert wurde.  
  
 Weitere Informationen zu Arrays finden Sie unter [Arrays](../arrays/index.md).  
  
## <a name="class-types"></a>Klassentypen  

 Es gibt keinen einzelnen Datentyp, der alle Klassen umfasst. Obwohl eine Klasse von einer anderen Klasse erben kann, handelt es sich bei jedem um einen separaten Datentyp. Mehrere Instanzen derselben Klasse weisen denselben Datentyp auf. Wenn Sie eine Klasseninstanzvariable einem anderen zuweisen, nicht nur denselben Datentyp haben, zeigen Sie auf dieselbe Klasseninstanz im Arbeitsspeicher.  
  
 Weitere Informationen zu-Klassen finden Sie unter [Objekte und Klassen](../objects-and-classes/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](index.md)
- [Elementare Datentypen](elementary-data-types.md)
- [Generische Typen in Visual Basic (Visual Basic)](generic-types.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Strukturen](structures.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Vorgehensweise: Ablegen mehrerer Werte in einer Variablen](how-to-hold-more-than-one-value-in-a-variable.md)
