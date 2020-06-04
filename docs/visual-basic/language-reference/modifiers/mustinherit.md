---
title: MustInherit
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
ms.openlocfilehash: 84df7a5cfdad3b5bc6764675725a5d0cb402b0b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396206"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Gibt an, dass eine Klasse nur als Basisklasse verwendet werden kann und dass Sie kein Objekt direkt aus der Klasse erstellen können.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Zweck einer *Basisklasse* (auch als *abstrakte Klasse*bezeichnet) besteht darin, die Funktionalität zu definieren, die allen von ihr abgeleiteten Klassen gemeinsam ist. Dadurch werden die abgeleiteten Klassen daran bewahrt, die gemeinsamen Elemente neu zu definieren. In einigen Fällen ist diese gängige Funktionalität nicht ausreichend, um ein verwendbares Objekt zu erstellen, und jede abgeleitete Klasse definiert die fehlende Funktionalität. In einem solchen Fall möchten Sie, dass der verarbeitende Code nur Objekte aus den abgeleiteten Klassen erstellt. Verwenden Sie für `MustInherit` die Basisklasse, um dies zu erzwingen.  
  
 Eine andere Verwendung einer- `MustInherit` Klasse besteht darin, eine Variable auf einen Satz verwandter Klassen zu beschränken. Sie können eine Basisklasse definieren und alle diese verknüpften Klassen davon ableiten. Die Basisklasse muss keine Funktionalität bereitstellen, die allen abgeleiteten Klassen gemeinsam ist. Sie kann jedoch als Filter zum Zuweisen von Werten zu Variablen dienen. Wenn in Ihrem verarbeitenden Code eine Variable als Basisklasse deklariert wird, können Sie mit Visual Basic nur ein Objekt aus einer der abgeleiteten Klassen der Variablen zuweisen.  
  
 Der-.NET Framework definiert mehrere `MustInherit` Klassen, darunter <xref:System.Array> , <xref:System.Enum> und <xref:System.ValueType> . <xref:System.ValueType>ist ein Beispiel für eine Basisklasse, die eine Variable einschränkt. Alle Werttypen werden von abgeleitet <xref:System.ValueType> . Wenn Sie eine Variable als deklarieren <xref:System.ValueType> , können Sie dieser Variablen nur Werttypen zuweisen.  
  
## <a name="rules"></a>Regeln  
  
- **Deklarationskontext.** Sie können `MustInherit` nur in einer- `Class` Anweisung verwenden.  
  
- **Kombinierte Modifizierer.** Sie können nicht `MustInherit` mit `NotInheritable` in der gleichen Deklaration angeben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht sowohl die erzwungene Vererbung als auch das erzwungene überschreiben. Die-Basisklasse `shape` definiert eine Variable `acrossLine` . Die Klassen `circle` und werden `square` von abgeleitet `shape` . Sie erben die Definition von `acrossLine` , müssen jedoch die-Funktion definieren, `area` da diese Berechnung für jede Art von Form unterschiedlich ist.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 Sie können `shape1` und `shape2` den Typ deklarieren `shape` . Es ist jedoch nicht möglich, ein Objekt aus zu erstellen, `shape` da es nicht über die Funktionen der-Funktion verfügt `area` und als gekennzeichnet ist `MustInherit` .  
  
 Da Sie als deklariert werden `shape` , sind die Variablen `shape1` und `shape2` auf Objekte aus den abgeleiteten Klassen `circle` und beschränkt `square` . In Visual Basic können Sie diesen Variablen keine anderen Objekte zuweisen, was Ihnen ein hohes Maß an Typsicherheit bietet.  
  
## <a name="usage"></a>Verwendung  
 Der- `MustInherit` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Class-Anweisung](../statements/class-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Inherits Statement](../statements/inherits-statement.md)
- [NotInheritable](notinheritable.md)
- [Schlüsselwörter](../keywords/index.md)
- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
