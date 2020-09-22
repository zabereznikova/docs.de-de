---
title: TryCast-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: dc4807781f9e1aaf894016952911bd7b32c42948
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875314"
---
# <a name="trycast-operator-visual-basic"></a>TryCast-Operator (Visual Basic)

Führt einen Typkonvertierungs Vorgang ein, der keine Ausnahme auslöst.  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn eine Konvertierungs Versuch fehlschlägt, lösen `CType` `DirectCast` beide einen <xref:System.InvalidCastException> Fehler aus. Dies kann sich negativ auf die Leistung Ihrer Anwendung auswirken. `TryCast` gibt [nichts](../nothing.md)zurück, sodass Sie nur das zurückgegebene Ergebnis für testen müssen, anstatt eine mögliche Ausnahme behandeln zu müssen `Nothing` .  
  
 Sie verwenden das `TryCast` -Schlüsselwort auf die gleiche Weise wie die [CType-Funktion](../functions/ctype-function.md) und das [DirectCast-Operator](directcast-operator.md) Schlüsselwort. Sie geben einen Ausdruck als erstes Argument und einen Typ an, in den es als zweites Argument konvertiert werden soll. `TryCast` funktioniert nur für Verweis Typen, z. b. Klassen und Schnittstellen. Es ist eine Vererbungs-oder Implementierungs Beziehung zwischen den beiden Typen erforderlich. Dies bedeutet, dass ein Typ von einem Typ erben oder ihn implementieren muss.  
  
## <a name="errors-and-failures"></a>Fehler und Fehler  

 `TryCast` generiert einen Compilerfehler, wenn erkannt wird, dass keine Vererbungs-oder Implementierungs Beziehung vorhanden ist. Das Fehlen eines Compilerfehlers garantiert jedoch nicht die erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann Sie zur Laufzeit fehlschlagen. Wenn dies der Fall ist, wird `TryCast` [nichts](../nothing.md)zurückgegeben.  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  

 Ein Vergleich der Schlüsselwörter für die Typkonvertierung lautet wie folgt.  
  
|Stichwort|Datentypen|Argument Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|Beliebige Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert werden.|KEH <xref:System.InvalidCastException>|  
|[DirectCast-Operator](directcast-operator.md)|Beliebige Datentypen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|KEH <xref:System.InvalidCastException>|  
|`TryCast`|Nur Verweis Typen|Ein Typ muss von einem anderen Typ erben oder ihn implementieren.|Gibt [nichts](../nothing.md) zurück.|  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel veranschaulicht die Verwendung von `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
