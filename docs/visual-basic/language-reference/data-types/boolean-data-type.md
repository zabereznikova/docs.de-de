---
title: Boolean-Datentyp (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdc106f1ec874c1a2165df069d5f3485fe5b2e43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-data-type-visual-basic"></a>Boolean-Datentyp (Visual Basic)
Enthält Werte, die nur können `True` oder `False`. Die Schlüsselwörter `True` und `False` entsprechen die beiden Status `Boolean` Variablen.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [Boolean-Datentyp (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) zwei-Status-Werte wie wahr/falsch, enthalten, Ja/Nein, oder ein/aus.  
  
 Der Standardwert von `Boolean` ist `False`.  
  
 `Boolean`Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte dürfen nicht mit Zahlen gleichwertig sein. Schreiben Sie Code, der auf den entsprechenden numerischen Werten für nutzt `True` und `False`. Wann immer möglich, beschränken Sie die Verwendung von `Boolean` Variablen, die für sie vorgesehenen logischen Werte.  
  
## <a name="type-conversions"></a>Typkonvertierungen  
 Wenn Visual Basic numerische Datentypwerte konvertiert `Boolean`, wird 0 `False` und alle anderen Werte werden `True`. Wenn Visual Basic konvertiert `Boolean` Werte in numerische Typen `False` wird 0 und `True` wird – 1.  
  
 Bei der Konvertierung zwischen `Boolean` Werte und numerische Datentypen ausgelöst werden, sollten Sie bedenken, dass die .NET Framework-Konvertierungsmethoden nicht immer die gleichen Ergebnisse wie die Visual Basic-Konvertierungsschlüsselwörter erzeugen. Dies ist, da die Visual Basic-Konvertierung Verhalten kompatibel mit früheren Versionen werden beibehalten. Weitere Informationen finden Sie unter "Boolescher Typ wird nicht präzise zu den numerischen Typ konvertieren" in [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Negative Zahlen.** `Boolean`ist kein numerischen Typ und einen negativen Wert nicht darstellen kann. In jedem Fall sollten Sie nicht verwenden `Boolean` für numerische Werte.  
  
-   **Typzeichen.** `Boolean`hat kein literal-Typzeichen oder Bezeichner-Typzeichen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Boolean?displayProperty=nameWithType>-Struktur.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `runningVB` ist eine `Boolean` Variable, die eine einfache Ja/Nein-Einstellung speichert.  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Boolean?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
