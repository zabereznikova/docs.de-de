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
ms.openlocfilehash: 30befaaf194d78d26a57f29c59bf0a603e9f07a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351495"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Gibt an, dass eine Klasse nur als Basisklasse verwendet werden kann und dass Sie kein Objekt direkt aus der Klasse erstellen können.  
  
## <a name="remarks"></a>Hinweise  
 Der Zweck einer *Basisklasse* (auch als *abstrakte Klasse*bezeichnet) besteht darin, die Funktionalität zu definieren, die allen von ihr abgeleiteten Klassen gemeinsam ist. Dadurch werden die abgeleiteten Klassen daran bewahrt, die gemeinsamen Elemente neu zu definieren. In einigen Fällen ist diese gängige Funktionalität nicht ausreichend, um ein verwendbares Objekt zu erstellen, und jede abgeleitete Klasse definiert die fehlende Funktionalität. In einem solchen Fall möchten Sie, dass der verarbeitende Code nur Objekte aus den abgeleiteten Klassen erstellt. Verwenden Sie `MustInherit` für die Basisklasse, um dies zu erzwingen.  
  
 Eine andere Verwendung einer `MustInherit`-Klasse besteht darin, eine Variable auf einen Satz verwandter Klassen zu beschränken. Sie können eine Basisklasse definieren und alle diese verknüpften Klassen davon ableiten. Die Basisklasse muss keine Funktionalität bereitstellen, die allen abgeleiteten Klassen gemeinsam ist. Sie kann jedoch als Filter zum Zuweisen von Werten zu Variablen dienen. Wenn in Ihrem verarbeitenden Code eine Variable als Basisklasse deklariert wird, können Sie mit Visual Basic nur ein Objekt aus einer der abgeleiteten Klassen der Variablen zuweisen.  
  
 Der .NET Framework definiert mehrere `MustInherit` Klassen, darunter <xref:System.Array>, <xref:System.Enum>und <xref:System.ValueType>. <xref:System.ValueType> ist ein Beispiel für eine Basisklasse, die eine Variable einschränkt. Alle Werttypen werden von <xref:System.ValueType>abgeleitet. Wenn Sie eine Variable als <xref:System.ValueType>deklarieren, können Sie dieser Variablen nur Werttypen zuweisen.  
  
## <a name="rules"></a>Regeln  
  
- **Deklarations Kontext.** Sie können `MustInherit` nur in einer `Class`-Anweisung verwenden.  
  
- **Kombinierte modifiziererer.** Sie können `MustInherit` nicht mit `NotInheritable` in derselben Deklaration angeben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht sowohl die erzwungene Vererbung als auch das erzwungene überschreiben. Die Basisklasse `shape` definiert eine Variable `acrossLine`. Die Klassen `circle` und `square` von `shape`abgeleitet. Sie erben die Definition von `acrossLine`, aber Sie müssen die Funktion `area` definieren, da diese Berechnung für jede Art von Form unterschiedlich ist.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 Sie können `shape1` und `shape2` deklarieren, der vom Typ `shape`ist. Es ist jedoch nicht möglich, ein Objekt aus `shape` zu erstellen, da es nicht die Funktionen der Funktion `area` und als `MustInherit`gekennzeichnet ist.  
  
 Da Sie als `shape`deklariert werden, sind die Variablen `shape1` und `shape2` auf Objekte aus den abgeleiteten Klassen `circle` und `square`beschränkt. In Visual Basic können Sie diesen Variablen keine anderen Objekte zuweisen, was Ihnen ein hohes Maß an Typsicherheit bietet.  
  
## <a name="usage"></a>Verwendung  
 Der `MustInherit` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
