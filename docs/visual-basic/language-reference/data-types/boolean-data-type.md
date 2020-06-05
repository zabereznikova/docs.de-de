---
title: Boolean-Datentyp
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
ms.openlocfilehash: 851c524a83c5f24b77a151634a96798249c5905e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374420"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean-Datentyp (Visual Basic)

Enthält Werte, die nur oder aufweisen können `True` `False` . Die Schlüsselwörter `True` und `False` entsprechen den beiden Zuständen der `Boolean` Variablen.  
  
## <a name="remarks"></a>Bemerkungen  

 Verwenden Sie den [booleschen Datentyp (Visual Basic)](boolean-data-type.md) , um zwei Zustands Werte wie "true", "false", "Ja/Nein" oder "ein/aus" zu enthalten.  
  
 Der Standardwert von `Boolean` ist `False`.  
  
 `Boolean`Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sind nicht als äquivalent zu zahlen vorgesehen. Sie sollten niemals Code schreiben, der auf äquivalenten numerischen Werten für `True` und basiert `False` . Wenn möglich, sollten Sie die Verwendung von `Boolean` Variablen auf die logischen Werte beschränken, für die Sie entworfen wurden.  
  
## <a name="type-conversions"></a>Typkonvertierungen  

 Wenn Visual Basic numerische Datentyp Werte in konvertiert `Boolean` , wird 0 zu, `False` und alle anderen Werte werden `True` . Wenn Visual Basic `Boolean` Werte in numerische Typen konvertiert, `False` wird 0 und `True` wird zu-1.  
  
 Wenn Sie zwischen `Boolean` Werten und numerischen Datentypen konvertieren, beachten Sie, dass die .NET Framework-Konvertierungs Methoden nicht immer die gleichen Ergebnisse wie die Visual Basic Konvertierungs Schlüsselwörter erzielen. Dies liegt daran, dass die Visual Basic Konvertierung das Verhalten beibehält, das mit früheren Versionen kompatibel ist Weitere Informationen finden Sie in der Problembehandlung bei [Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)unter "boolescher Typ wird nicht in numerischen Typ konvertiert".  
  
## <a name="programming-tips"></a>Programmiertipps  
  
- **Negative Zahlen.** `Boolean`ist kein numerischer Typ und kann keinen negativen Wert darstellen. In jedem Fall sollten Sie nicht verwenden `Boolean` , um numerische Werte zu speichern.  
  
- **Geben Sie Zeichen ein.** `Boolean`weist kein Literaltyp Zeichen oder Bezeichnertyp Zeichen auf.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Boolean?displayProperty=nameWithType>-Struktur.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel `runningVB` ist eine `Boolean` Variable, in der eine einfache Ja/Nein-Einstellung gespeichert wird.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Boolean?displayProperty=nameWithType>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../functions/ctype-function.md)
