---
title: 'Gewusst wie: Abrufen des Werts einer Zeigervariablen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 9a10bcc809f3ecbc9a0fa9b917940b8e030fab8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635101"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>Gewusst wie: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch)

Verwenden Sie den Zeigerdereferenzierungsoperator, um die Variable aus dem Speicherort abzurufen, auf den von einem Zeiger gezeigt wird. Der Ausdruck hat das folgende Format, wobei `p` ein Zeigertyp ist:  

```csharp
*p;  
```

Sie können den unären Dereferenzierungsoperator nicht auf einen Ausdruck anwenden, der nicht dem Zeigertyp entspricht. Zudem können Sie ihn nicht auf einen [leeren](../../../csharp/language-reference/keywords/void.md) Zeiger anwenden.  

Wenn Sie den Dereferenzierungsoperator auf einen [NULL](../../../csharp/language-reference/keywords/null.md)-Zeiger anwenden, ist das Ergebnis von der Implementierung abhängig.  

## <a name="example"></a>Beispiel

In folgendem Beispiel wird auf eine Variable des Typs `char` mithilfe eines Zeigers eines anderen Typs zugegriffen. Beachten Sie, dass die Adresse von `theChar` je nach Ausführung variiert, da sich die physische Adresse ändern kann, die der Variable zugewiesen ist.  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
**Wert von theChar = Z**  
**Adresse von theChar = 12F718**  
**Wert von pChar = Z**  
**Wert von pInt = 90**  

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Typen](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
