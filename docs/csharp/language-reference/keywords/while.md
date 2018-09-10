---
title: while (C#-Referenz)
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: e3e9493b5371fbd6f53a779ba73743efc6d6e05b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514059"
---
# <a name="while-c-reference"></a>while (C#-Referenz)

Die Anweisung `while` führt eine Anweisung oder einen Anweisungsblock aus, während ein angegebener boolescher Ausdruck `true` ergibt. Da der Ausdruck vor jeder Ausführung der Schleife ausgewertet wird, wird eine `while`-Schleife entweder nie oder mehrmals ausgeführt. Dies unterscheidet sich von der [do](do.md)-Schleife, die ein oder mehrmals ausgeführt wird.

Sie können zu jedem Zeitpunkt im Anweisungsblock `while` aus der Schleife ausbrechen, indem Sie die Anweisung [break](break.md) verwenden.

Sie können mithilfe der [continue](continue.md)-Anweisung direkt die Auswertung des `while`-Ausdrucks ausführen. Wenn der Ausdruck `true` ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt. Andernfalls wird die Ausführung mit der ersten Anweisung nach der Schleife ausgeführt.

Sie können eine `while`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der `while`-Anweisung veranschaulicht. Klicken Sie auf **Run** (Ausführen), um den Beispielcode auszuführen. Danach können Sie Änderungen am Code vornehmen und ihn erneut ausführen.

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)  
- [C#-Programmierhandbuch](../../programming-guide/index.md)  
- [C#-Schlüsselwörter](index.md)  
- [while-Anweisung (C++)](/cpp/cpp/while-statement-cpp)  
- [Iterationsanweisungen](iteration-statements.md)  
- [do-Anweisung](do.md)  
