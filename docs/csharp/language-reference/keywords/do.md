---
title: do (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a>do (C#-Referenz)
Die `do`-Anweisung führt eine Anweisung oder einen Block wiederholt aus, bis ein bestimmter Ausdruck `false` ergibt. Der Text der Schleife muss in geschweifte Klammern eingeschlossen werden, `{}`, wenn es nicht aus einer einzelnen Anweisung besteht. In diesem Fall sind die Klammern optional.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel führen die `do-while`-Schleifenanweisungen solange aus, bis die Variable `x` kleiner als 5 ist.  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 Im Gegensatz zur [while](../../../csharp/language-reference/keywords/while.md)-Anweisung wird eine `do-while`-Schleife einmal ausgeführt, bevor der bedingte Ausdruck ausgewertet wird.  
  
 An jedem Punkt im `do-while`-Block können Sie mithilfe der [break](../../../csharp/language-reference/keywords/break.md)-Anweisung aus der Schleife ausbrechen. Sie können mithilfe der [continue](../../../csharp/language-reference/keywords/continue.md)-Anweisung direkt die `while`-Ausdrucksauswertung der Anweisung ausführen. Wenn der `while`-Ausdruck TRUE ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt. Wenn der Ausdruck FALSE ergibt, wird die Ausführung bei der ersten Anweisung nach der `do-while`-Schleife fortgesetzt.  
  
 Eine `do-while`-Schleife kann durch die Anweisungen [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md) beendet werden.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [do-while-Anweisung (C++)](/cpp/cpp/do-while-statement-cpp)  
 [Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md)
