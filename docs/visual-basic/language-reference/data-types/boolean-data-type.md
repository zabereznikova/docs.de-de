---
title: Datentyp "Boolean"
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
ms.openlocfilehash: 5d05514207c5d07e81aab897f40f728570f6bd87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347848"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean-Datentyp (Visual Basic)

Enthält Werte, die nur `True` oder `False`sein können. Die Schlüsselwörter `True` und `False` entsprechen den beiden Zuständen `Boolean` Variablen.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie den [booleschen Datentyp (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) , um zwei Zustands Werte wie "true", "false", "Ja/Nein" oder "ein/aus" zu enthalten.  
  
 Der Standardwert von `Boolean` ist `False`.  
  
 `Boolean` Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sind nicht als äquivalent zu zahlen vorgesehen. Sie sollten niemals Code schreiben, der auf äquivalente numerische Werte für `True` und `False`basiert. Wenn möglich, sollten Sie die Verwendung von `Boolean` Variablen auf die logischen Werte beschränken, für die Sie entworfen wurden.  
  
## <a name="type-conversions"></a>Typkonvertierungen  

 Wenn Visual Basic numerische Datentyp Werte in `Boolean`konvertiert, wird 0 `False`, und alle anderen Werte werden `True`. Wenn Visual Basic `Boolean` Werte in numerische Typen konvertiert, wird `False` zu 0 und `True` zu-1.  
  
 Wenn Sie zwischen `Boolean` Werten und numerischen Datentypen konvertieren, beachten Sie, dass die .NET Framework Konvertierungs Methoden nicht immer die gleichen Ergebnisse wie die Visual Basic Konvertierungs Schlüsselwörter erzielen. Dies liegt daran, dass die Visual Basic Konvertierung das Verhalten beibehält, das mit früheren Versionen kompatibel ist Weitere Informationen finden Sie in der Problembehandlung bei [Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)unter "boolescher Typ wird nicht in numerischen Typ konvertiert".  
  
## <a name="programming-tips"></a>Programmiertipps  
  
- **Negative Zahlen.** `Boolean` ist kein numerischer Typ und kann keinen negativen Wert darstellen. In jedem Fall sollten Sie `Boolean` nicht verwenden, um numerische Werte zu speichern.  
  
- **Geben Sie Zeichen ein.** `Boolean` hat kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.  
  
- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Boolean?displayProperty=nameWithType>-Struktur.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel ist `runningVB` eine `Boolean` Variable, in der eine einfache Ja/Nein-Einstellung gespeichert wird.  
  
```vb  
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
