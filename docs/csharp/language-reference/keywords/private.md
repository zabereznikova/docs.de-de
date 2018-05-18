---
title: private (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 26eab2912923c9fcae1ce930bd5b59a2740d500e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="private-c-reference"></a>private (C#-Referenz)
Das `private`-Schlüsselwort ist ein Zugriffsmodifizierer für Member. 
   
 > Auf dieser Seite wird der Zugriff auf `private` behandelt. Das Schlüsselwort `private` ist auch Teil des Zugriffsmodifizierers [`private protected`](./private-protected.md).
  
Privater-Zugriff ist die am wenigsten eingeschränkte Zugriffsebene. Private Member sind nur innerhalb der Klasse oder Struktur, in der sie, wie im folgenden Beispiel, deklariert werden:  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 Geschachtelte Typen im gleichen Text können auch auf diese privaten Member zugreifen.  
  
 Es ist ein Kompilierzeitfehler auf einen privaten Member außerhalb der Klasse oder Struktur, in der sie deklariert ist, zu verweisen.  
  
 Einen Vergleich von `private` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel enthält die `Employee`-Klasse zwei private Datenmember, `name` und `salary`. Als private Member können nur Membermethoden auf sie zugreifen. Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um gesteuerten Zugriff auf die privaten Member zu ermöglichen. Auf den `name`-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen. (Weitere Informationen finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).)  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)
