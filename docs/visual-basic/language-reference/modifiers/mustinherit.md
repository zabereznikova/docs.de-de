---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 0bda03d3c01356317fbcc56d44199ff4f9484b5b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816563"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Gibt an, dass eine Klasse nur als Basisklasse verwendet werden kann und ein Objekt kann nicht direkt daraus erstellen.  
  
## <a name="remarks"></a>Hinweise  
 Der Zweck einer *Basisklasse* (auch bekannt als ein *abstrakte Klasse*) besteht darin, Funktionen zu definieren, die für alle Klassen, die davon abgeleitet ist. Dies erspart die abgeleiteten Klassen, die gängigen Elemente neu zu definieren. In einigen Fällen diesen häufig verwendeten Funktionen ist nicht umfassend genug, um ein Objekt verwendbar zu machen, und jede abgeleitete Klasse definiert die fehlende Funktion. In diesem Fall möchten Sie den verwendeten Code zum Erstellen von Objekten nur von den abgeleiteten Klassen. Verwenden Sie `MustInherit` in der Basisklasse, dies durchzusetzen.  
  
 Eine andere Verwendung von einem `MustInherit` Klasse ist, um eine Variable auf einen Satz verwandter Klassen einzuschränken. Sie können eine Basisklasse definieren und diese verwandten Klassen abgeleitet. Die Basisklasse muss keine Funktionen, die auf alle abgeleiteten Klassen bereitstellen, aber als einen Filter für das Zuweisen von Werten zu Variablen dienen. Wenn im verwendeten Code eine Variable als Basisklasse deklariert können Visual Basic Sie nur ein Objekt eine abgeleitete Klasse diese Variable zuweisen.  
  
 .NET Framework definiert verschiedene `MustInherit` Klassen, u. a. <xref:System.Array>, <xref:System.Enum>, und <xref:System.ValueType>. <xref:System.ValueType> ist ein Beispiel für eine Basisklasse, die eine Variable beschränkt. Alle Werttypen werden von <xref:System.ValueType>. Wenn Sie eine Variable deklarieren <xref:System.ValueType>, Sie können diese Variable nur Werttypen zuweisen.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `MustInherit` nur in einem `Class` Anweisung.  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `MustInherit` zusammen mit `NotInheritable` in der gleichen Deklaration.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die erzwungene Vererbung und erzwungene überschreiben. Die Basisklasse `shape` definiert eine Variable `acrossLine`. Die Klassen `circle` und `square` abgeleitet `shape`. Sie erben die Definition der `acrossLine`, jedoch müssen sie die Funktion definieren `area` , da die Berechnung für jede Art von Form unterscheidet.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 Sie können deklarieren, `shape1` und `shape2` Typ `shape`. Sie können nicht jedoch ein Objekt aus erstellen `shape` weil. die Funktionen der fehlt `area` und markiert `MustInherit`.  
  
 Da sie als deklariert werden `shape`, die Variablen `shape1` und `shape2` auf Objekte beschränkt sind, die von den abgeleiteten Klassen `circle` und `square`. Visual Basic erlaubt Ihnen kein anderes Objekt zuweisen, diese Variablen, die Ihnen ein hohes Maß an typsicherheit bietet.  
  
## <a name="usage"></a>Verwendung  
 Die `MustInherit` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
