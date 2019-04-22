---
title: Boolean-Datentyp (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 7b64302d801a08f976de0ec969983c821f7a8471
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841217"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean-Datentyp (Visual Basic)
Enthält Werte, die nur können `True` oder `False`. Die Schlüsselwörter `True` und `False` entsprechen, die beiden Status `Boolean` Variablen.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [Boolean-Datentyp (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) enthält zwei-Status-Werte wie wahr/falsch, Ja/Nein, oder ein/aus.  
  
 Der Standardwert von `Boolean` ist `False`.  
  
 `Boolean` Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sind nicht für das Zahlen entsprechen soll. Schreiben Sie Code, der auf den entsprechenden numerischen Werten für basiert `True` und `False`. Wann immer möglich, beschränken Sie die Verwendung von `Boolean` Variablen, um die logischen Werte, die für die sie entworfen werden.  
  
## <a name="type-conversions"></a>Typkonvertierungen  
 Wenn konvertiert Visual Basic numerischen Typ Datenwerte `Boolean`, wird 0 `False` und alle anderen Werte werden `True`. Wenn Visual Basic konvertiert `Boolean` Werten in numerische Typen `False` ist 0 und `True` wird – 1.  
  
 Beim Konvertieren zwischen `Boolean` Werte und numerische Datentypen und Bedenken Sie, dass die .NET Framework-Konvertierungsmethoden nicht immer die gleichen Ergebnisse wie die Schlüsselwörter der Visual Basic-Konvertierung erzeugen. Dies ist, da die Visual Basic-Konvertierung Verhalten kompatibel mit früheren Versionen werden beibehalten. Weitere Informationen finden Sie unter "Boolescher Typ ist nicht präzise, den numerischen Typ konvertieren" in [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Negative Zahlen.** `Boolean` ist kein numerischer Typ und einen negativen Wert nicht darstellen kann. In jedem Fall sollten Sie nicht verwenden `Boolean` für numerische Werte.  
  
-   **Typzeichen.** `Boolean` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.  
  
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

- <xref:System.Boolean?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
