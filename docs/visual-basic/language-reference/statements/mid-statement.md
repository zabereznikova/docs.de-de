---
title: Mid-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61d812ef91acc65728b04efc9aa99e3975e71d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mid-statement"></a>Mid-Anweisung
Ersetzt eine angegebene Anzahl von Zeichen in einem `String` -Variable mit Zeichen aus einer anderen Zeichenfolge.  
  
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
 Erforderlich. Name des der `String` Variable zu ändern.  
  
 `Start`  
 Erforderlich. `Integer`Ausdruck. Die Zeichenposition in `Target` , in dem die Ersetzung von Text beginnt. `Start`verwendet einen einsbasierten Index.  
  
 `Length`  
 Dies ist optional. `Integer`Ausdruck. Anzahl der zu ersetzenden Zeichen. Wenn nicht angegeben, alle `String` verwendet wird.  
  
 `StringExpression`  
 Erforderlich. `String`Ausdruck, der Teil des ersetzt `Target`.  
  
## <a name="exceptions"></a>Ausnahmen  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`< = 0 oder `Length` < 0.|  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl der Zeichen ersetzt ist immer kleiner oder gleich der Anzahl der Zeichen in `Target`.  
  
 Visual Basic verfügt über eine <xref:Microsoft.VisualBasic.Strings.Mid%2A> Funktion und eine `Mid` Anweisung. Diese Elemente, die beide auf eine angegebene Anzahl von Zeichen in eine Zeichenfolge funktionieren, aber die `Mid` Funktion gibt die Zeichen, während die `Mid` Anweisung ersetzt die Zeichen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  Die `MidB` -Anweisung aus früheren Versionen von Visual Basic ersetzt eine Teilzeichenfolge in Bytes anstatt Zeichen. Es dient in erster Linie für das Konvertieren von Zeichenfolgen in Doppelbyte-Zeichensatz (Character Set, DBCS) Anwendungen. Alle Visual Basic-Zeichenfolgen werden in Unicode und `MidB` wird nicht mehr unterstützt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Mid` Anweisung, um eine angegebene Anzahl von Zeichen in einer Zeichenfolgenvariablen durch Zeichen aus einer anderen Zeichenfolge zu ersetzen.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:**`Strings`  
  
 **Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Einführung in Zeichenfolgen in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
