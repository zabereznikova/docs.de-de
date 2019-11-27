---
title: TryCast-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 53306575cfc385039be3939fd87cf993b4509af4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348214"
---
# <a name="trycast-operator-visual-basic"></a>TryCast-Operator (Visual Basic)
Führt einen Typkonvertierungs Vorgang ein, der keine Ausnahme auslöst.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Konvertierungs Versuch fehlschlägt, lösen `CType` und `DirectCast` beide einen <xref:System.InvalidCastException> Fehler aus. Dies kann sich negativ auf die Leistung Ihrer Anwendung auswirken. `TryCast` gibt [nichts](../../../visual-basic/language-reference/nothing.md)zurück, sodass anstelle einer möglichen Ausnahme nur das zurückgegebene Ergebnis mit `Nothing`getestet werden muss.  
  
 Sie verwenden das `TryCast`-Schlüsselwort auf die gleiche Weise wie die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und das [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) Schlüsselwort. Sie geben einen Ausdruck als erstes Argument und einen Typ an, in den es als zweites Argument konvertiert werden soll. `TryCast` funktioniert nur für Verweis Typen, z. b. Klassen und Schnittstellen. Es ist eine Vererbungs-oder Implementierungs Beziehung zwischen den beiden Typen erforderlich. Dies bedeutet, dass ein Typ von einem Typ erben oder ihn implementieren muss.  
  
## <a name="errors-and-failures"></a>Fehler und Fehler  
 `TryCast` generiert einen Compilerfehler, wenn erkannt wird, dass keine Vererbungs-oder Implementierungs Beziehung vorhanden ist. Das Fehlen eines Compilerfehlers garantiert jedoch nicht die erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann Sie zur Laufzeit fehlschlagen. Wenn dies geschieht, gibt `TryCast` [nichts](../../../visual-basic/language-reference/nothing.md)zurück.  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Ein Vergleich der Schlüsselwörter für die Typkonvertierung lautet wie folgt.  
  
|Schlüsselwort|Datentypen|Argument Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Beliebige Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert werden.|Löst <xref:System.InvalidCastException>|  
|[DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md)|Beliebige Datentypen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|Löst <xref:System.InvalidCastException>|  
|`TryCast`|Nur Verweis Typen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|Gibt [nichts](../../../visual-basic/language-reference/nothing.md) zurück.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
