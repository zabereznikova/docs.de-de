---
title: 'Vorgehensweise: Abrufen des Werts einer Zeigervariablen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 5fbc925b6770bc951a0d7ec856898f62c265462e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577151"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>Vorgehensweise: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch)
Verwenden Sie den Zeigerdereferenzierungsoperator, um die Variable aus dem Speicherort abzurufen, auf den von einem Zeiger gezeigt wird. Der Ausdruck hat das folgende Format, wobei `p` ein Zeigertyp ist:  
  
```  
*p;  
```  
  
 Sie können den unären Dereferenzierungsoperator nicht auf einen Ausdruck anwenden, der nicht dem Zeigertyp entspricht. Zudem können Sie ihn nicht auf einen [leeren](../../../csharp/language-reference/keywords/void.md) Zeiger anwenden.  
  
 Wenn Sie den Dereferenzierungsoperator auf einen [NULL](../../../csharp/language-reference/keywords/null.md)-Zeiger anwenden, ist das Ergebnis von der Implementierung abhängig.  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel wird auf eine Variable des Typs `char` mithilfe eines Zeigers eines anderen Typs zugegriffen. Beachten Sie, dass die Adresse von `theChar` je nach Ausführung variiert, da sich die physische Adresse ändern kann, die der Variable zugewiesen ist.  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Typen](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
