---
title: 'Vorgehensweise: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: 92ac601719ccb1c5e9f769c286a1d2dd443c713a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237804"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a>Vorgehensweise: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck (C#-Programmierhandbuch)
Sie können implizit typisierte lokale Variablen immer dann verwenden, wenn Sie möchten, dass der Compiler den Typ einer lokalen Variablen bestimmt. Sie müssen implizit typisierte lokale Variablen verwenden, um anonyme Typen zu speichern, die häufig in Abfrageausdrücken verwendet werden. In den folgenden Beispielen werden sowohl optionale als auch erforderliche Einsatzmöglichkeiten von implizit typisierte lokale Variablen in einer Abfrage veranschaulicht.  
  
 Implizit typisierte lokale Variablen werden mit dem kontextuellen Schlüsselwort [var](../../../csharp/language-reference/keywords/var.md) deklariert. Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein häufiges Szenario gezeigt, in dem das Schlüsselwort `var` erforderlich ist: ein Abfrageausdruck, der eine Folge anonymer Typen erzeugt. In diesem Szenario müssen sowohl die Abfragevariable als auch die Iterationsvariable in der `foreach`-Anweisung mit `var` implizit typisiert werden, da Sie keinen Zugriff auf einen Typnamen für den anonymen Typ haben. Weitere Informationen zu anonymen Typen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 [!code-csharp[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel wird das Schlüsselwort `var` in einer ähnlichen Situation verwendet, wobei der Gebrauch von `var` jedoch optional ist. Da `student.LastName` eine Zeichenfolge ist, gibt die Ausführung der Abfrage eine Sequenz von Zeichenfolgen zurück. Deshalb kann der Typ von `queryID` als `System.Collections.Generic.IEnumerable<string>` statt als `var` deklariert werden. Das Schlüsselwort `var` wird aus praktischen Gründen verwendet. In dem Beispiel wird die Iterationsvariable in der `foreach`-Anweisung explizit als Zeichenfolge typisiert. Sie könnte aber auch alternativ mit `var` deklariert werden. Da der Typ der Iterationsvariablen kein anonymer Typ ist, ist das Verwenden von `var` optional aber nicht verpflichtend. Denken Sie daran, das `var` selbst kein Typ ist, sondern eine Anweisung an den Compiler, um den Typen abzuleiten und zuzuweisen.  
  
 [!code-csharp[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
- [LINQ (Language Integrated Query)](../../../csharp/linq/index.md)  
- [var](../../../csharp/language-reference/keywords/var.md)  
- [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)
