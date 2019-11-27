---
title: Mid-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: eeef4c13743b75a3d5e61ac46afb94d9ea105b7a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348026"
---
# <a name="mid-statement"></a>Mid-Anweisung
Ersetzt eine angegebene Anzahl von Zeichen in einer `String` Variablen durch Zeichen aus einer anderen Zeichenfolge.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>-Komponenten  
 `Target`  
 Erforderlich Der Name der `String` Variablen, die geändert werden soll.  
  
 `Start`  
 Erforderlich `Integer` Ausdruck. Die Zeichenposition in `Target`, an der der Text ersetzt werden soll. `Start` verwendet einen 1-basierten Index.  
  
 `Length`  
 Optional. `Integer` Ausdruck. Anzahl der zu ersetzenden Zeichen. Wenn der Wert weggelassen wird, wird der gesamte `String` verwendet.  
  
 `StringExpression`  
 Erforderlich `String` Ausdruck, der einen Teil `Target`ersetzt.  
  
## <a name="exceptions"></a>Ausnahmen  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 oder `Length` < 0.|  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl der ersetzten Zeichen ist immer kleiner oder gleich der Anzahl der Zeichen in `Target`.  
  
 Visual Basic verfügt über eine <xref:Microsoft.VisualBasic.Strings.Mid%2A>-Funktion und eine `Mid`-Anweisung. Diese Elemente funktionieren beide mit einer angegebenen Anzahl von Zeichen in einer Zeichenfolge, aber die `Mid`-Funktion gibt die Zeichen zurück, während die `Mid` Anweisung die Zeichen ersetzt. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> Die `MidB`-Anweisung früherer Versionen von Visual Basic ersetzt eine Teil Zeichenfolge in Bytes und nicht als Zeichen. Es wird hauptsächlich zum Umrechnen von Zeichen folgen in DBCS-Anwendungen (Double-Byte Character Set) verwendet. Alle Visual Basic Zeichenfolgen sind in Unicode, und `MidB` wird nicht mehr unterstützt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die `Mid`-Anweisung verwendet, um eine angegebene Anzahl von Zeichen in einer Zeichen folgen Variablen durch Zeichen aus einer anderen Zeichenfolge zu ersetzen.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Voraussetzungen  
 **Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:** `Strings`  
  
 **Assembly:** Visual Basic-Lauf Zeit Bibliothek (in "Microsoft. VisualBasic. dll")  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Einführung in Zeichenfolgen in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
