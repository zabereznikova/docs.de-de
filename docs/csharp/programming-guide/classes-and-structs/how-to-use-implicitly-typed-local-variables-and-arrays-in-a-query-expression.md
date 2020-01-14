---
title: 'Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck – C#-Programmierhandbuch'
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: f4ff71fc4dc1a0b2affa1f032ab1d3d6bb04d297
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705560"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a>Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck (C#-Programmierhandbuch)
Sie können implizit typisierte lokale Variablen immer dann verwenden, wenn Sie möchten, dass der Compiler den Typ einer lokalen Variablen bestimmt. Sie müssen implizit typisierte lokale Variablen verwenden, um anonyme Typen zu speichern, die häufig in Abfrageausdrücken verwendet werden. In den folgenden Beispielen werden sowohl optionale als auch erforderliche Einsatzmöglichkeiten von implizit typisierte lokale Variablen in einer Abfrage veranschaulicht.  
  
 Implizit typisierte lokale Variablen werden mit dem kontextuellen Schlüsselwort [var](../../language-reference/keywords/var.md) deklariert. Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](./implicitly-typed-local-variables.md) und [Implizit typisierte Arrays](../arrays/implicitly-typed-arrays.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein häufiges Szenario gezeigt, in dem das Schlüsselwort `var` erforderlich ist: ein Abfrageausdruck, der eine Folge anonymer Typen erzeugt. In diesem Szenario müssen sowohl die Abfragevariable als auch die Iterationsvariable in der `foreach`-Anweisung mit `var` implizit typisiert werden, da Sie keinen Zugriff auf einen Typnamen für den anonymen Typ haben. Weitere Informationen zu anonymen Typen finden Sie unter [Anonyme Typen](./anonymous-types.md).  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel wird das Schlüsselwort `var` in einer ähnlichen Situation verwendet, wobei der Gebrauch von `var` jedoch optional ist. Da `student.LastName` eine Zeichenfolge ist, gibt die Ausführung der Abfrage eine Sequenz von Zeichenfolgen zurück. Deshalb kann der Typ von `queryID` als `System.Collections.Generic.IEnumerable<string>` statt als `var` deklariert werden. Das Schlüsselwort `var` wird aus praktischen Gründen verwendet. In dem Beispiel wird die Iterationsvariable in der `foreach`-Anweisung explizit als Zeichenfolge typisiert. Sie könnte aber auch alternativ mit `var` deklariert werden. Da der Typ der Iterationsvariablen kein anonymer Typ ist, ist das Verwenden von `var` optional aber nicht verpflichtend. Denken Sie daran, das `var` selbst kein Typ ist, sondern eine Anweisung an den Compiler, um den Typen abzuleiten und zuzuweisen.  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Erweiterungsmethoden](./extension-methods.md)
- [LINQ (Language Integrated Query)](../../linq/index.md)
- [var](../../language-reference/keywords/var.md)
- [LINQ in C#](../../linq/index.md)
