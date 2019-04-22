---
title: DirectCast-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 628ce4f06b91d0f514f71dea3aad8ea0fee6dccf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821503"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast-Operator (Visual Basic)
Führt einen Typkonvertierungsvorgang, basierend auf vererbungs- oder implementierungsbeziehung an.  
  
## <a name="remarks"></a>Hinweise  
 `DirectCast` verwendet nicht das Visual Basic-Laufzeit Hilfsroutinen für die Konvertierung, damit es ein wenig bereitstellen kann eine Leistung als bessere `CType` beim Konvertieren in und aus-Datentyp `Object`.  
  
 Sie verwenden die `DirectCast` Schlüsselwort ähnlich wie die Verwendung der [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort. Sie geben einen Ausdruck als erstes Argument und einen Typ als das zweite Argument konvertiert. `DirectCast` erfordert eine Beziehung vererbungs- oder implementierungsbeziehung zwischen den Datentypen der beiden Argumente. Dies bedeutet, dass ein Typ erben oder den anderen implementieren muss.  
  
## <a name="errors-and-failures"></a>Fehler und Ausfälle  
 `DirectCast` generiert einen Compilerfehler, wenn er erkennt, dass keine vererbungs- oder implementierungsbeziehung Beziehung vorhanden ist. Der Mangel an einen Compilerfehler gewährleistet jedoch keine erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann sie zur Laufzeit fehlschlagen. In diesem Fall löst die Laufzeit eine <xref:System.InvalidCastException> Fehler.  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Ein Vergleich der Schlüsselwörter für die typkonvertierung lautet wie folgt aus:  
  
|Stichwort|Datentypen|Argument-Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Alle Datentypen|Erweiternde oder einschränkende Konvertierung muss zwischen den beiden Datentypen definiert werden|Löst aus <xref:System.InvalidCastException>|  
|`DirectCast`|Alle Datentypen|Einem Typ muss erben oder implementieren Sie den anderen Typ|Löst aus <xref:System.InvalidCastException>|  
|[TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)|Nur Verweistypen|Einem Typ muss erben oder implementieren Sie den anderen Typ|Gibt ["Nothing"](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Verwendungen von `DirectCast`, eine, die zur Laufzeit und eine, die nicht erfolgreich ausgeführt wird.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 Im vorherigen Beispiel den Laufzeittyp der `q` ist `Double`. `CType` ist erfolgreich, da `Double` konvertiert werden kann, um `Integer`. Jedoch die erste `DirectCast` schlägt zur Laufzeit fehl, da der Laufzeittyp des `Double` verfügt über keine vererbungsbeziehung mit `Integer`, auch wenn eine Konvertierung vorhanden ist. Die zweite `DirectCast` ist erfolgreich, da er vom Typ konvertiert <xref:System.Windows.Forms.Form> eingeben <xref:System.Windows.Forms.Control>, von dem <xref:System.Windows.Forms.Form> erbt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
