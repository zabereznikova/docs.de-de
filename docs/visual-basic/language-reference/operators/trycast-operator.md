---
title: TryCast-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a>TryCast-Operator (Visual Basic)
Führt einen Typkonvertierungsvorgang, der keine Ausnahme auslöst.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine versuchte Konvertierung ein Fehler auftritt, `CType` und `DirectCast` sowohl Auslösen einer <xref:System.InvalidCastException> Fehler. Dies kann die Leistung der Anwendung beeinträchtigen. `TryCast`Gibt [nichts](../../../visual-basic/language-reference/nothing.md), sodass anstatt auf eine mögliche Ausnahme behandeln Sie nur das zurückgegebene Ergebnis mit testen müssen `Nothing`.  
  
 Verwenden Sie die `TryCast` Schlüsselwort die gleiche Weise, die Sie verwenden die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) Schlüsselwort. Sie geben einen Ausdruck als erstes Argument und einen Typ als zweites Argument umzuwandeln. `TryCast`kann nur für Verweistypen, z. B. Klassen und Schnittstellen. Voraussetzung hierfür ist eine Beziehung vererbungs- oder implementierungsbeziehung zwischen den beiden Typen. Dies bedeutet, dass ein Typ den anderen implementieren oder davon erben muss.  
  
## <a name="errors-and-failures"></a>Fehler und Ausfälle  
 `TryCast`generiert einen Compilerfehler, wenn er erkennt, dass keine Vererbung oder Implementierung Beziehung vorhanden. Der Mangel an einen Compilerfehler gewährleistet jedoch keine erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann sie zur Laufzeit fehlschlagen. In diesem Fall `TryCast` gibt [nichts](../../../visual-basic/language-reference/nothing.md).  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Ein Vergleich der Schlüsselwörter für die typkonvertierung lautet wie folgt.  
  
|Stichwort|Datentypen|Arguments-Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Alle Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert sein|Löst aus<xref:System.InvalidCastException>|  
|[DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md)|Alle Datentypen|Einen müssen anderen Typ zu implementieren oder davon erben|Löst aus<xref:System.InvalidCastException>|  
|`TryCast`|Nur Verweistypen|Einen müssen anderen Typ zu implementieren oder davon erben|Gibt [nichts](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
