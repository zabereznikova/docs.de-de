---
title: Mid-Anweisung (Visual Basic)
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
ms.openlocfilehash: 212ce1f06a01c39acbce43d8d069dae3526b1b4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963548"
---
# <a name="mid-statement"></a>Mid-Anweisung
Ersetzt eine angegebene Anzahl von Zeichen in einer `String` Variablen durch Zeichen aus einer anderen Zeichenfolge.  
  
## <a name="syntax"></a>Syntax  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Teile  
 `Target`  
 Erforderlich. Der Name der `String` Variablen, die geändert werden soll.  
  
 `Start`  
 Erforderlich. `Integer`Begriff. Zeichenposition in `Target` , an der die Text Ersetzung beginnt. `Start`verwendet einen 1-basierten Index.  
  
 `Length`  
 Optional. `Integer`Begriff. Anzahl der zu ersetzenden Zeichen. Wenn der `String` Wert weggelassen wird, wird all verwendet.  
  
 `StringExpression`  
 Erforderlich. `String`Ausdruck, der einen Teil `Target`von ersetzt.  
  
## <a name="exceptions"></a>Ausnahmen  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`< = 0 oder `Length` < 0.|  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl der ersetzten Zeichen ist immer kleiner oder gleich der Anzahl von Zeichen in `Target`.  
  
 Visual Basic verfügt über <xref:Microsoft.VisualBasic.Strings.Mid%2A> eine-Funktion `Mid` und eine-Anweisung. Diese Elemente funktionieren beide mit einer angegebenen Anzahl von Zeichen in einer Zeichenfolge, aber `Mid` die-Funktion gibt die Zeichen `Mid` zurück, während die-Anweisung die Zeichen ersetzt. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> Die `MidB` -Anweisung früherer Versionen von Visual Basic ersetzt eine Teil Zeichenfolge in Bytes und nicht als Zeichen. Es wird hauptsächlich zum Umrechnen von Zeichen folgen in DBCS-Anwendungen (Double-Byte Character Set) verwendet. Alle Visual Basic Zeichenfolgen sind in Unicode `MidB` und werden nicht mehr unterstützt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird `Mid` die-Anweisung verwendet, um eine angegebene Anzahl von Zeichen in einer Zeichen folgen Variablen durch Zeichen aus einer anderen Zeichenfolge zu ersetzen.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:** `Strings`  
  
 **Stadtverordneten** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Einführung in Zeichenfolgen in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
