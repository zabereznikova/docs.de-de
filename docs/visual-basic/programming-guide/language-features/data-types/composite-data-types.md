---
title: Zusammengesetzte Datentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types
- composite data types
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures, composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d81b2c08155cb16754e780fdfb341b596322302d
ms.lasthandoff: 03/13/2017

---
# <a name="composite-data-types-visual-basic"></a>Zusammengesetzte Datentypen (Visual Basic)
Zusätzlich zu den elementare Datentypen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] bereitstellt, können Sie auch Elemente unterschiedlichen Typs erstellen zusammenstellen *zusammengesetzte Datentypen* wie Strukturen, Arrays und Klassen. Sie können zusammengesetzte Datentypen aus elementaren Typen und aus anderen zusammengesetzten Typen erstellen. Beispielsweise können Sie ein Array von Strukturelementen oder eine Struktur mit Array-Elemente definieren.  
  
## <a name="data-types"></a>Datentypen  
 Ein zusammengesetzter Typ unterscheidet sich von dem Datentyp seiner Komponenten. Angenommen, ein Array von `Integer` Elemente ist nicht von der `Integer` -Datentyp.  
  
 Datentyp eines Arrays wird normalerweise mithilfe von Elementtyp, Klammern und Kommas nach Bedarf dargestellt. Angenommen, ein eindimensionales Array von `String` wird `String()`, und ein zweidimensionales Array von `Boolean` wird `Boolean(,)`.  
  
## <a name="structure-types"></a>Strukturtypen  
 Es gibt keinen universellen Datentyp, der alle Strukturen umfasst. Stattdessen stellt jede Definition einer Struktur einen eindeutigen Datentyp dar, auch wenn zwei Strukturen identischer Elemente in der gleichen Reihenfolge definieren. Jedoch, wenn Sie zwei oder mehr Instanzen dieselbe Struktur erstellen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] berücksichtigt diese den gleichen Datentyp sein.  
  
## <a name="array-types"></a>Arraytypen  
 Es gibt keinen universellen Datentyp aller Arrays aus. Der Datentyp einer bestimmten Instanz eines Arrays wird durch Folgendes bestimmt:  
  
-   Die Tatsache, dass ein array  
  
-   Der Rang (Anzahl der Dimensionen) des Arrays  
  
-   Der Elementtyp des Arrays  
  
 Insbesondere ist die Länge einer bestimmten Dimension nicht Teil des Datentyps für die Instanz. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Im vorangehenden Beispiel Arrayvariablen `arrayA` und `arrayB` gelten die gleichen Datentyp – `Byte()` –, obwohl sie mit unterschiedlichen Längen initialisiert werden. Variablen `arrayB` und `arrayC` sind nicht vom gleichen Typ, da ihre Elementtypen unterschiedlich sind. Variablen `arrayC` und `arrayD` sind nicht vom gleichen Typ, da ihre Ränge unterschiedlich sind. Variablen `arrayD` und `arrayE` denselben Typ haben – `Short(,)` , da ihre Ränge und Elementtypen identisch, obwohl sind `arrayD` wurde noch nicht initialisiert.  
  
 Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Klassentypen  
 Es gibt keinen universellen Datentyp, der alle Klassen umfasst. Obwohl eine Klasse von einer anderen Klasse erben kann, ist jede ein separater Datentyp. Mehrere Instanzen derselben Klasse sind vom gleichen Datentyp. Wenn Sie eine Klassenvariable Instanz zu einem anderen zuweisen, werden nicht nur besitzen den gleichen Datentyp aufweisen, sie zeigen auf die gleiche Klasseninstanz im Speicher.  
  
 Weitere Informationen über Klassen finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Gewusst wie: Ablegen mehrerer Werte in einer Variablen](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
