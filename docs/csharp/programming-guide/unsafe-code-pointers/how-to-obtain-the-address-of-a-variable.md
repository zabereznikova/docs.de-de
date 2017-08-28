---
title: 'Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 169f68cc80b7a27427a9987942e66e0ba9ed1a02
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)
Um die Adresse eines unären Ausdrucks abzurufen, der eine feste Variable ergibt, verwenden Sie den address-of-Operator:  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 Der address-of-Operator kann nur auf eine Variable angewendet werden. Wenn die Variable beweglich ist, können Sie eine [feste Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) verwenden, um die Variable vorübergehen zu befestigen, um ihre Adresse abzurufen.  
  
 Sie müssen sicherstellen, dass die Variable initialisiert wird. Der Compiler gibt keine Fehlermeldung aus, wenn die Variable nicht initialisiert ist.  
  
 Sie können nicht die Adresse einer Konstanten oder eines Werts abrufen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein Zeiger auf `int`, `p`, deklariert. Die Adresse einer ganzzahligen Variable, `number`, wird ihm zugewiesen. Die Variable `number` wird als Ergebnis der Zuweisung zu *p initialisiert. Wenn Sie diese Zuweisungsanweisung zu einem Kommentar machen, wird die Initialisierung der Variablen `number` entfernt, aber kein Kompilierzeitfehler ausgestellt. Beachten Sie den Gebrauch des [Memberzugriffsoperators](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` zum Abrufen und Anzeigen der Adresse, die im Zeiger gespeichert ist.  
  
 [!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

