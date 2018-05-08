---
title: DirectCast-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 534e94ecc0a394caa2865c2da754ad8f4dbc6f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="directcast-operator-visual-basic"></a>DirectCast-Operator (Visual Basic)
Führt einen Typkonvertierungsvorgang basierend auf vererbungs- oder implementierungseinschränkung an.  
  
## <a name="remarks"></a>Hinweise  
 `DirectCast` verwendet nicht das Visual Basic-Laufzeit Hilfsroutinen für die Konvertierung, damit er in einem gewissen bereitstellen kann eine Systemleistung als bessere `CType` beim Konvertieren in und aus Datentyp `Object`.  
  
 Verwenden Sie die `DirectCast` Schlüsselwort ähnlich wie bei Verwendung der [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort. Sie geben einen Ausdruck als erstes Argument und einen Typ als zweites Argument umzuwandeln. `DirectCast` erfordert eine vererbungs- oder implementierungseinschränkung Beziehung zwischen den Datentypen der beiden Argumente. Dies bedeutet, dass ein Typ den anderen implementieren oder davon erben muss.  
  
## <a name="errors-and-failures"></a>Fehler und Ausfälle  
 `DirectCast` generiert einen Compilerfehler, wenn er erkennt, dass keine Vererbung oder Implementierung Beziehung vorhanden. Der Mangel an einen Compilerfehler gewährleistet jedoch keine erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann sie zur Laufzeit fehlschlagen. In diesem Fall löst die Laufzeit eine <xref:System.InvalidCastException> Fehler.  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Ein Vergleich der Schlüsselwörter für die typkonvertierung lautet wie folgt.  
  
|Stichwort|Datentypen|Arguments-Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Alle Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert sein|Löst aus <xref:System.InvalidCastException>|  
|`DirectCast`|Alle Datentypen|Einen müssen anderen Typ zu implementieren oder davon erben|Löst aus <xref:System.InvalidCastException>|  
|[TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)|Nur Verweistypen|Einen müssen anderen Typ zu implementieren oder davon erben|Gibt [nichts](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Verwendungen von `DirectCast`, eines, die zur Laufzeit und eine, die nicht erfolgreich ist.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 Im vorherigen Beispiel der Laufzeittyp des `q` ist `Double`. `CType` ist erfolgreich, da `Double` konvertiert werden kann, um `Integer`. Allerdings die erste `DirectCast` zur Laufzeit ein Fehler auftritt, da der Laufzeittyp des `Double` verfügt über keine vererbungsbeziehung mit `Integer`, auch wenn eine Konvertierung vorhanden ist. Die zweite `DirectCast` ist erfolgreich, da er vom Typ konvertiert <xref:System.Windows.Forms.Form> Eingabe <xref:System.Windows.Forms.Control>, von dem <xref:System.Windows.Forms.Form> erbt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
