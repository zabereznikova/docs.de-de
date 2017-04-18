---
title: Mid-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e385d6838daa16d45903c6b270fc47ad88797845
ms.lasthandoff: 03/13/2017

---
# <a name="mid-statement"></a>Mid-Anweisung
Ersetzt eine angegebene Anzahl von Zeichen in einem `String` -Variablen durch Zeichen aus einer anderen Zeichenfolge.  
  
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
 Erforderlich. Der Name der `String` zu ändernden Variablen.  
  
 `Start`  
 Erforderlich. `Integer`Ausdruck. Die Zeichenposition in `Target` , an dem die Ersetzung von Text beginnt. `Start`verwendet einen einsbasierten Index.  
  
 `Length`  
 Optional. `Integer`Ausdruck. Die Anzahl der zu ersetzenden Zeichen. Wenn nicht angegeben, alle `String` verwendet wird.  
  
 `StringExpression`  
 Erforderlich. `String`Ausdruck, der Teil des ersetzt `Target`.  
  
## <a name="exceptions"></a>Ausnahmen  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentException></xref:System.ArgumentException>|`Start`<= 0="" or=""></=>`Length`< 0.></ 0.>|  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl der ersetzten Zeichen ist immer kleiner oder gleich der Anzahl der Zeichen in `Target`.  
  
 Visual Basic verfügt über eine <xref:Microsoft.VisualBasic.Strings.Mid%2A>Funktion und eine `Mid` Anweisung.</xref:Microsoft.VisualBasic.Strings.Mid%2A> Beiden Elementen auf einer bestimmten Anzahl von Zeichen in einer Zeichenfolge, aber die `Mid` wird während der `Mid` Anweisung ersetzt die Zeichen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</xref:Microsoft.VisualBasic.Strings.Mid%2A>  
  
> [!NOTE]
>  Die `MidB` -Anweisung aus früheren Versionen von Visual Basic ersetzt eine Teilzeichenfolge in Bytes und nicht in Zeichen. Es dient in erster Linie für die Konvertierung von Zeichenfolgen in Doppelbyte-Zeichensatz (DBCS)-Satz Anwendungen. Alle Visual Basic-Zeichenfolgen sind in Unicode und `MidB` wird nicht mehr unterstützt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Mid` Anweisung, um eine angegebene Anzahl von Zeichen in einer Zeichenfolgenvariablen durch Zeichen aus einer anderen Zeichenfolge zu ersetzen.  
  
 [!code-vb[VbVbalrStrings&5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:**`Strings`  
  
 **Assembly:**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Einführung in Zeichenfolgen in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
