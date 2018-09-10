---
title: try-finally (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: beb54cf6c4e6dc87b9a08b81586b24d72f92b84b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505941"
---
# <a name="try-finally-c-reference"></a>try-finally (C#-Referenz)
Mit einem `finally`-Block können Sie alle Ressourcen bereinigen, die in einem [try](../../../csharp/language-reference/keywords/try-catch.md)-Block belegt sind, und Sie können Code selbst dann ausführen, wenn eine Ausnahme im `try`-Block auftritt. In der Regel werden die Anweisungen eines `finally`-Blocks ausgeführt, wenn die Steuerung eine `try`-Anweisung verlässt. Die Übertragung eines Steuerelements kann infolge einer normalen Ausführung, der Ausführung einer `break`-, `continue`-, `goto`- oder `return`-Anweisung oder der Weitergabe einer Ausnahme aus der `try`-Anweisung auftreten.  
  
 Innerhalb einer behandelten Ausnahme ist sichergestellt, dass der zugeordnete `finally`-Block ausgeführt wird. Wenn die Ausnahme jedoch nicht behandelt wird, erfolgt die Ausführung des `finally`-Blocks je nachdem, wie der Entladevorgang für die Ausnahme ausgelöst wird. Das hängt wiederum davon ab, wie der Computer eingerichtet ist.
  
 Wenn eine Anwendung durch einen Ausnahmefehler beendet wird, ist es in der Regel nicht wichtig, ob der `finally`-Block ausgeführt wird. Wenn der `finally`-Block jedoch Anweisungen aufweist, die auch in dieser Situation ausgeführt werden müssen, kann als Lösung ein `catch`-Block der `try`-`finally`-Anweisung hinzugefügt werden. Sie können auch die Ausnahme abfangen, die möglicherweise im `try`-Block einer `try`-`finally`-Anweisung weiter oben in der Aufrufliste ausgelöst wird. Die Ausnahme kann also in der Methode abgefangen werden, mit der die Methode mit der `try`-`finally`-Anweisung aufgerufen wird. Die Ausnahme kann aber auch in der Methode abgefangen werden, mit der diese Methode aufgerufen wird, oder in einer beliebigen Methode in der Aufrufliste. Wenn die Ausnahme nicht abgefangen wird, wird der `finally`-Block je nachdem, ob vom Betriebssystem ein Entladevorgang für die Ausnahme ausgelöst wird, ausgeführt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `System.InvalidCastException` Ausnahme durch eine ungültige Konvertierungsanweisung verursacht. Die Ausnahme wird nicht behandelt.  
  
 [!code-csharp[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 Im folgenden Beispiel wird eine Ausnahme von der `TryCast`-Methode in einer Methode weiter oben in der Aufrufliste abgefangen.  
  
 [!code-csharp[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 Weitere Informationen zu `finally` finden Sie unter [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).  
  
 C# enthält auch die [Using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md), die eine ähnliche Funktionalität für <xref:System.IDisposable>-Objekte in einer zweckmäßigen Syntax bereitstellt.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [try-, throw- und catch-Anweisungen (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)  
- [Ausnahmebehandlungsanweisungen](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
- [throw](../../../csharp/language-reference/keywords/throw.md)  
- [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
- [Vorgehensweise: Explizites Auslösen von Ausnahmen](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
