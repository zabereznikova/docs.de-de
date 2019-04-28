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
ms.openlocfilehash: df83fd527612af1a6a4b8131ffa2643ef0d1d7dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784241"
---
# <a name="mid-statement"></a>Mid-Anweisung
Ersetzt eine angegebene Anzahl von Zeichen in einem `String` Variable mit dem Zeichen aus einer anderen Zeichenfolge.  
  
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
 Erforderlich. Name des der `String` zu ändernden Variablen.  
  
 `Start`  
 Erforderlich. `Integer` -Ausdruck. Die Zeichenposition in `Target` , an dem das Ersetzen des Texts beginnt. `Start` verwendet einen einsbasierten Index.  
  
 `Length`  
 Dies ist optional. `Integer` -Ausdruck. Die Anzahl der zu ersetzenden Zeichen. Wenn nicht angegeben, alle `String` verwendet wird.  
  
 `StringExpression`  
 Erforderlich. `String` Ausdruck, der Teil des ersetzt `Target`.  
  
## <a name="exceptions"></a>Ausnahmen  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 oder `Length` < 0.|  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl der Zeichen ersetzt ist immer kleiner oder gleich der Anzahl der Zeichen in `Target`.  
  
 Visual Basic verfügt über eine <xref:Microsoft.VisualBasic.Strings.Mid%2A> Funktion und ein `Mid` Anweisung. Diese Elemente beide für eine angegebene Anzahl von Zeichen in eine Zeichenfolge funktionieren, aber die `Mid` Funktionsergebnis ist die Zeichen bei der die `Mid` Anweisung ersetzt die Zeichen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  Die `MidB` frühere Versionen von Visual Basic-Anweisung ersetzt eine Teilzeichenfolge in Byte, anstatt in Zeichen. Es dient in erster Linie für das Konvertieren von Zeichenfolgen in Doppelbyte-Zeichensatz (DBCS)-Satz Anwendungen. Alle Visual Basic-Zeichenfolgen werden in Unicode und `MidB` wird nicht mehr unterstützt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Mid` Anweisung, um eine angegebene Anzahl von Zeichen in einer Zeichenfolgenvariablen durch Zeichen aus einer anderen Zeichenfolge ersetzen.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:** `Strings`  
  
 **Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Einführung in Zeichenfolgen in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
