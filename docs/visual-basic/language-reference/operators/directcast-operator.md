---
title: DirectCast-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 8ea29b80cf27bbb2c21a8cebbfaa0a294e05f11d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331309"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast-Operator (Visual Basic)
Führt eine Typkonvertierungs Operation auf der Grundlage von Vererbung oder Implementierung ein.  
  
## <a name="remarks"></a>Hinweise  
 `DirectCast` verwendet nicht die Visual Basic-Lauf Zeit Hilfsobjekte für die Konvertierung, sodass es eine etwas bessere Leistung als `CType` beim Konvertieren in und aus Datentyp `Object`bereitstellen kann.  
  
 Sie verwenden das Schlüsselwort `DirectCast` ähnlich der Verwendung der [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und des [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselworts. Sie geben einen Ausdruck als erstes Argument und einen Typ an, in den es als zweites Argument konvertiert werden soll. `DirectCast` erfordert eine Vererbungs-oder Implementierungs Beziehung zwischen den Datentypen der beiden Argumente. Dies bedeutet, dass ein Typ von einem Typ erben oder ihn implementieren muss.  
  
## <a name="errors-and-failures"></a>Fehler und Fehler  
 `DirectCast` generiert einen Compilerfehler, wenn erkannt wird, dass keine Vererbungs-oder Implementierungs Beziehung vorhanden ist. Das Fehlen eines Compilerfehlers garantiert jedoch nicht die erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann Sie zur Laufzeit fehlschlagen. Wenn dies der Fall ist, löst die Laufzeit einen <xref:System.InvalidCastException> Fehler aus.  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Ein Vergleich der Schlüsselwörter für die Typkonvertierung lautet wie folgt.  
  
|Schlüsselwort|Datentypen|Argument Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Beliebige Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert werden.|Löst <xref:System.InvalidCastException>|  
|`DirectCast`|Beliebige Datentypen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|Löst <xref:System.InvalidCastException>|  
|[TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)|Nur Verweis Typen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|Gibt [nichts](../../../visual-basic/language-reference/nothing.md) zurück.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Verwendungsmöglichkeiten von `DirectCast`veranschaulicht, eine, die zur Laufzeit fehlschlägt, und eine, die erfolgreich ausgeführt wird.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 Im vorherigen Beispiel ist der Lauf Zeittyp `q` `Double`. `CType` ist erfolgreich, da `Double` in `Integer`konvertiert werden kann. Allerdings schlägt der erste `DirectCast` zur Laufzeit fehl, da der Lauf Zeittyp `Double` keine Vererbungs Beziehung mit `Integer`hat, obwohl eine Konvertierung vorhanden ist. Die zweite `DirectCast` ist erfolgreich, da Sie von Type <xref:System.Windows.Forms.Form> in Type <xref:System.Windows.Forms.Control>konvertiert, von dem <xref:System.Windows.Forms.Form> erbt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
