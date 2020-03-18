---
title: try-finally – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 2c4c69b1e104aed968bc24bac690de83026643a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713013"
---
# <a name="try-finally-c-reference"></a>try-finally (C#-Referenz)

Mit einem `finally`-Block können Sie alle Ressourcen bereinigen, die in einem [try](try-catch.md)-Block belegt sind, und Sie können Code selbst dann ausführen, wenn eine Ausnahme im `try`-Block auftritt. In der Regel werden die Anweisungen eines `finally`-Blocks ausgeführt, wenn die Steuerung eine `try`-Anweisung verlässt. Die Übertragung eines Steuerelements kann infolge einer normalen Ausführung, der Ausführung einer `break`-, `continue`-, `goto`- oder `return`-Anweisung oder der Weitergabe einer Ausnahme aus der `try`-Anweisung auftreten.

Innerhalb einer behandelten Ausnahme ist sichergestellt, dass der zugeordnete `finally`-Block ausgeführt wird. Wenn die Ausnahme jedoch nicht behandelt wird, erfolgt die Ausführung des `finally`-Blocks je nachdem, wie der Entladevorgang für die Ausnahme ausgelöst wird. Das hängt wiederum davon ab, wie der Computer eingerichtet ist.

Wenn eine Anwendung durch einen Ausnahmefehler beendet wird, ist es in der Regel nicht wichtig, ob der `finally`-Block ausgeführt wird. Wenn der `finally`-Block jedoch Anweisungen aufweist, die auch in dieser Situation ausgeführt werden müssen, kann als Lösung ein `catch`-Block der `try`-`finally`-Anweisung hinzugefügt werden. Sie können auch die Ausnahme abfangen, die möglicherweise im `try`-Block einer `try`-`finally`-Anweisung weiter oben in der Aufrufliste ausgelöst wird. Die Ausnahme kann also in der Methode abgefangen werden, mit der die Methode mit der `try`-`finally`-Anweisung aufgerufen wird. Die Ausnahme kann aber auch in der Methode abgefangen werden, mit der diese Methode aufgerufen wird, oder in einer beliebigen Methode in der Aufrufliste. Wenn die Ausnahme nicht abgefangen wird, wird der `finally`-Block je nachdem, ob vom Betriebssystem ein Entladevorgang für die Ausnahme ausgelöst wird, ausgeführt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `System.InvalidCastException` Ausnahme durch eine ungültige Konvertierungsanweisung verursacht. Die Ausnahme wird nicht behandelt.

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

Im folgenden Beispiel wird eine Ausnahme von der `TryCast`-Methode in einer Methode weiter oben in der Aufrufliste abgefangen.

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

Weitere Informationen zu `finally` finden Sie unter [try-catch-finally](try-catch-finally.md).

C# enthält auch die [Using-Anweisung](using-statement.md), die eine ähnliche Funktionalität für <xref:System.IDisposable>-Objekte in einer zweckmäßigen Syntax bereitstellt.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Die Try-Anweisung](~/_csharplang/spec/statements.md#the-try-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [try, throw, and catch Statements (C++) (try-, throw- und catch-Anweisungen (C++))](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-catch](try-catch.md)
- [Vorgehensweise: Explizites Auslösen von Ausnahmen](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
