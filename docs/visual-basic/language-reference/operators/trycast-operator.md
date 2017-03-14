---
title: "TryCast Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.trycast"
  - "trycast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "TryCast keyword"
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# TryCast Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Leitet eine Typkonvertierungsoperation ein, die keine Ausnahme auslöst.  
  
## Hinweise  
 Wenn eine Konvertierungsversuch fehlschlägt, lösen sowohl `CType` als auch `DirectCast` einen <xref:System.InvalidCastException>\-Fehler aus.  Dies kann die Leistung Ihrer Anwendung beeinträchtigen.  `TryCast` gibt [Nothing](../../../visual-basic/language-reference/nothing.md) zurück, sodass Sie keine Ausnahme behandeln, sondern nur das zurückgegebene Ergebnis mit `Nothing` testen müssen.  
  
 Sie verwenden das `TryCast`\-Schlüsselwort auf die gleiche Weise wie die [CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und das [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md)\-Schlüsselwort.  Als erstes Argument ist ein Ausdruck anzugeben und als zweites Argument ein Typ, in den dieser Ausdruck konvertiert werden soll.  `TryCast` kann nur für Verweistypen, z. B. Klassen und Schnittstellen, verwendet werden.  Es erfordert eine Vererbungs\- oder Implementierungsbeziehung zwischen den beiden Typen.  Dies bedeutet, dass ein Typ von dem anderen erben bzw. ein Typ den anderen implementieren muss.  
  
## Fehler  
 `TryCast` generiert einen Compilerfehler, wenn festgestellt wird, dass keine Vererbungs\- oder Implementierungsbeziehung vorhanden ist.  Das Ausbleiben eines Compilerfehlers ist jedoch keine Garantie für eine erfolgreiche Konvertierung.  Wenn die gewünschte Konvertierung eingrenzend ist, kann sie zur Laufzeit fehlschlagen.  In diesem Fall gibt `TryCast` [Nothing](../../../visual-basic/language-reference/nothing.md) zurück.  
  
## Konvertierungsschlüsselwörter  
 Im Folgenden werden die Typkonvertierungsschlüsselwörter miteinander verglichen.  
  
|||||  
|-|-|-|-|  
|Schlüsselwort|Datentypen|Argumentbeziehung|Laufzeitfehler|  
|[CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Beliebige Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder eingrenzende Konvertierung definiert werden.|Löst <xref:System.InvalidCastException> aus.|  
|[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md)|Beliebige Datentypen|Ein Datentyp muss von dem anderen Datentyp erben oder den anderen Datentyp implementieren.|Löst <xref:System.InvalidCastException> aus.|  
|`TryCast`|Nur Verweise auf Typen|Ein Datentyp muss von dem anderen Datentyp erben oder den anderen Datentyp implementieren.|Gibt [Nothing](../../../visual-basic/language-reference/nothing.md) zurück.|  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## Siehe auch  
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)