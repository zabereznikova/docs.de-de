---
title: "DirectCast Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.directCast"
  - "directCast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DirectCast keyword"
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# DirectCast Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Leitet eine Typkonvertierungsoperation ein, die auf Vererbung oder Implementierung beruht.  
  
## Hinweise  
 `DirectCast` führt Konvertierungen nicht mithilfe der Hilfsfunktionen der Visual Basic\-Laufzeitbibliothek durch und zeigt daher bei Konvertierungen in und aus dem `Object`\-Datentyp etwas besseres Leistungsverhalten als `CType`.  
  
 Das `DirectCast`\-Schlüsselwort wird auf die gleiche Weise verwendet wie die [CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und das [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)\-Schlüsselwort.  Als erstes Argument ist ein Ausdruck anzugeben und als zweites Argument ein Typ, in den dieser Ausdruck konvertiert werden soll.  `DirectCast` erfordert eine Vererbungs\- oder Implementierungsbeziehung zwischen den Datentypen der beiden Argumente.  Dies bedeutet, dass ein Typ von dem anderen erben bzw. ein Typ den anderen implementieren muss.  
  
## Fehler  
 `DirectCast` generiert einen Compilerfehler, wenn erkannt wird, dass keine Vererbungs\- oder Implementierungsbeziehung vorhanden ist.  Das Ausbleiben eines Compilerfehlers ist jedoch keine Garantie für eine erfolgreiche Konvertierung.  Wenn die gewünschte Konvertierung eingrenzend ist, kann sie zur Laufzeit fehlschlagen.  Wenn dies passiert, löst die Laufzeitumgebung einen <xref:System.InvalidCastException>\-Fehler aus.  
  
## Konvertierungsschlüsselwörter  
 Im Folgenden werden die Typkonvertierungsschlüsselwörter miteinander verglichen.  
  
|||||  
|-|-|-|-|  
|Schlüsselwort|Datentypen|Argumentbeziehung|Laufzeitfehler|  
|[CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Beliebige Datentypen|Zwischen den beiden Datentypen muss eine erweiternde oder eingrenzende Konvertierung definiert werden.|Löst <xref:System.InvalidCastException> aus.|  
|`DirectCast`|Beliebige Datentypen|Ein Datentyp muss von dem anderen Datentyp erben oder den anderen Datentyp implementieren.|Löst <xref:System.InvalidCastException> aus.|  
|[TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)|Nur Verweise auf Typen|Ein Datentyp muss von dem anderen Datentyp erben oder den anderen Datentyp implementieren.|Gibt [Nothing](../../../visual-basic/language-reference/nothing.md) zurück.|  
  
## Beispiel  
 Im folgenden Beispiel wird `DirectCast` zweimal verwendet; einmal scheitert die Konvertierung zur Laufzeit und im anderen Fall wird sie erfolgreich ausgeführt.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 Im vorangehenden Beispiel hat `q` zur Laufzeit den Typ `Double`.  `CType` wird erfolgreich ausgeführt, da `Double` in `Integer` konvertiert werden kann.  Der erste Aufruf von `DirectCast` schlägt fehl, weil zwischen dem Laufzeittyp `Double` und `Integer` keine Vererbungsbeziehung besteht, auch wenn eine Konvertierung möglich ist.  Der zweite Aufruf von `DirectCast` ist erfolgreich, da vom Typ <xref:System.Windows.Forms.Form> in den Typ <xref:System.Windows.Forms.Control>, der von <xref:System.Windows.Forms.Form> erbt, konvertiert wird.  
  
## Siehe auch  
 <xref:System.Convert.ChangeType%2A?displayProperty=fullName>   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)