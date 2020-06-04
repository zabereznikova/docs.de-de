---
title: DirectCast-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 96cb2082d59373deb34d6894270205b7c1045850
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371517"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast-Operator (Visual Basic)
Führt eine Typkonvertierungs Operation auf der Grundlage von Vererbung oder Implementierung ein.  
  
## <a name="remarks"></a>Bemerkungen  
 `DirectCast`verwendet nicht die Routinen für die Visual Basic-Lauf Zeit Hilfsprogramme für die Konvertierung, sodass eine etwas bessere Leistung erzielt werden kann als `CType` beim Konvertieren von Datentypen in und aus dem-Datentyp `Object` .  
  
 Sie verwenden das `DirectCast` Schlüsselwort ähnlich der Verwendung der [CType-Funktion](../functions/ctype-function.md) und des [TryCast-Operator](trycast-operator.md) Schlüsselworts. Sie geben einen Ausdruck als erstes Argument und einen Typ an, in den es als zweites Argument konvertiert werden soll. `DirectCast`erfordert eine Vererbungs-oder Implementierungs Beziehung zwischen den Datentypen der beiden Argumente. Dies bedeutet, dass ein Typ von einem Typ erben oder ihn implementieren muss.  
  
## <a name="errors-and-failures"></a>Fehler und Fehler  
 `DirectCast`generiert einen Compilerfehler, wenn erkannt wird, dass keine Vererbungs-oder Implementierungs Beziehung vorhanden ist. Das Fehlen eines Compilerfehlers garantiert jedoch nicht die erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann Sie zur Laufzeit fehlschlagen. Wenn dies der Fall ist, löst die Laufzeit einen <xref:System.InvalidCastException> Fehler aus.  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Ein Vergleich der Schlüsselwörter für die Typkonvertierung lautet wie folgt.  
  
|Schlüsselwort|Datentypen|Argument Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|Beliebige Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert werden.|KEH<xref:System.InvalidCastException>|  
|`DirectCast`|Beliebige Datentypen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|KEH<xref:System.InvalidCastException>|  
|[TryCast-Operator](trycast-operator.md)|Nur Verweis Typen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|Gibt [nichts](../nothing.md) zurück.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Verwendungsmöglichkeiten von veranschaulicht `DirectCast` : eine, die zur Laufzeit fehlschlägt, und eine, die erfolgreich ausgeführt wird.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 Im vorherigen Beispiel ist der Lauf Zeittyp von `q` `Double` . `CType`ist erfolgreich `Double` , da in konvertiert werden kann `Integer` . Allerdings schlägt der erste `DirectCast` zur Laufzeit fehl, da der Lauf Zeittyp von `Double` keine Vererbungs Beziehung mit aufweist `Integer` , obwohl eine Konvertierung vorhanden ist. Die zweite `DirectCast` ist erfolgreich, da Sie vom Typ <xref:System.Windows.Forms.Form> in den Typ konvertiert <xref:System.Windows.Forms.Control> , von dem <xref:System.Windows.Forms.Form> erbt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
